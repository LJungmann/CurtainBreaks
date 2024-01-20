---
title: Setup and Code
weight: 10
---

# Setup

## Pins on the Arduino

### LED 7-segment Display

| What   | Where | Wire Color |
| :----- | ----: | ---------- |
| Power  |    5V | gray       |
| Ground |   GND | violet     |
| Pin1   |    A4 |            |
| Pin2   |    A5 |            |

We used this [library](https://github.com/RobTillaart/HT16K33) to program the LED display.
The LED display can be bound in code by assigning a HEX address. The default address would be 0x70.
But, our display has a jumper on A0. The documentation of the HT16K33 library states, that A0 means +1, A1 means +2 and A2 means +4.
For us, this means that we have to add +1 to 0x70, which is 0x71. So we bind it on address 0x71.

### Potentiometer

| What   | Where | Wire Color |
| :----- | ----: | ---------- |
| Power  |    5V | violet     |
| Ground |   GND | white      |
| Pin    |    A0 | gray       |

The potentiometer gives values from 0 to 1028, we mapped that to be between 0 and 60.
We can use these values to show them as minutes on the LED display in 5 minute steps.

### Stepper Motor

| Sensor | Pin | Wire Color |
| :----- | --: | ---------- |
| IN1    |   8 | blue       |
| IN2    |   9 | green      |
| IN3    |  10 | yellow     |
| IN4    |  11 | orange     |
| Power  |  5V | white      |
| GND    | GND | black      |

The stepper motor is turned in one direction when the curtain should be moved down (timer is up).
However, the maximum steps per revolution are 2049, which were not enough to get the curtain fully down.
So we empirically tested how many times we had to call the maximum steps per revolution, so the curtain is fully down.
This is hard coded and is repeated in the other direction, for turning the curtain back up.

### Ultrasonic Sensor

| What    | Pin | Color  |
| :------ | --: | ------ |
| trigPin |  12 | orange |
| echoPin |  13 | red    |
| Ground  | GND | brown  |
| Power   |  5V | yellow |

The ultrasonic sensor has a set variable userDistance, that the user has to be away on average for some set time (15 seconds for the presentation, but can be set longer in code, when in actual use).
The average is important, because the values we get from the sensor are not 100% trustworthy.

# Code

```c++

#include "HT16K33.h"
#include <Stepper.h>

HT16K33 seg(0x71);
// Timer setup
int minutesShown = 0;
bool timeChanged = false;
bool colon = false;
int secondsToStart = 15;
uint32_t lastTimerSet = 0;
int lastMinutesShown = 0;
int secondsShown = 0;

bool timerMode = false;
bool timerStarted = false;
long timerInMs = 0;
long timeOnTimerStart = 0;

// Ultrasonic Sensor
// defines pins numbers
const int trigPin = 12; // Ultrasonic Sensor
const int echoPin = 13; // Ultrasonic Sensor
// defines params
const float alpha = 0.8;
const int userDistance = 200;
int sensorValAvg = 1;
int lastSensorValAvg = 1;
int currSensorVal;
long startTime,stopTime;
long milliSecsGoneTime = 15000;
long duration;
int distance;

// Stepper Motor params
const int stepsPerRevolution = 2049;  // change this to fit the number of steps per revolution
// for your motor
// initialize the stepper library on pins 8 through 11:
Stepper myStepper(stepsPerRevolution, 8, 10, 9, 11);

void setup()
{
  pinMode(trigPin, OUTPUT); // Sets the trigPin as an Output
  pinMode(echoPin, INPUT); // Sets the echoPin as an Input
  // set the speed at 60 rpm:
  myStepper.setSpeed(16);

  Serial.begin(9600);
  Serial.println(__FILE__);

  seg.begin();
  Wire.setClock(100000);
  seg.displayOn();
  seg.setDigits(4);
}


void loop()
{
    uint32_t now = millis(); // milli seconds since program started
  if(!timerMode) {
    Serial.println("timer mode is false");
    // listen for user input and calc max sitting time
    if(!timerStarted){
      getPotentioAndSetTimer(now);
    }else{
      long m = (long)(timerInMs/1000.0/60.0); // actual minutes that are to be shown
      long s = (m*60) - (long)(timerInMs/1000.0); // actual minutes in seconds minus all the seconds right now (results in -59 .. -1, so *-1 later)
      colon = !colon;
      if(m == 0 && s == 0){
        // roll curtain down
        Serial.println("---curtain down---");
        myStepper.step(stepsPerRevolution);
        myStepper.step(stepsPerRevolution);
        myStepper.step(stepsPerRevolution);
        myStepper.step(stepsPerRevolution);
        myStepper.step(stepsPerRevolution);
        myStepper.step(stepsPerRevolution);
        myStepper.step(stepsPerRevolution);
        myStepper.step(stepsPerRevolution);
        myStepper.step(440);
        delay(2000);
        timerMode = true;
      }
      seg.displayTime(m, s * -1, colon, false);
      timerInMs = timerInMs - (now-timeOnTimerStart);
      timeOnTimerStart = millis(); // delay is 1 second, so it should approximately be 1 second until line above is called again, substracting 1 second from timer
    }
    if(((lastTimerSet + secondsToStart * 1000) < now) && !timerStarted){
      Serial.println("time has passed, starting timer");
      timerStarted = true;
      timeOnTimerStart = millis();
    }
    delay(1000);
  } else {
    // check if the user is away and roll curtain up when they are away long enough
    unsigned int i;

    static uint32_t last = 0;

    // Clears the trigPin
    digitalWrite(trigPin, LOW);
    delayMicroseconds(50);
    // Sets the trigPin on HIGH state for 10 micro seconds
    digitalWrite(trigPin, HIGH);
    delayMicroseconds(50);
    digitalWrite(trigPin, LOW);
    // Reads the echoPin, returns the sound wave travel time in microseconds
    duration = pulseIn(echoPin, HIGH);
    // Calculating the distance
    distance = duration * 0.034 / 2;
    currSensorVal = distance;
    lastSensorValAvg = sensorValAvg;
    sensorValAvg = sensorValAvg  * (1- alpha) + currSensorVal * alpha;

    // Prints the distance on the Serial Monitor
    Serial.print("Average Distance: ");
    Serial.print(sensorValAvg);
    Serial.print("\n");

    if(sensorValAvg > userDistance && lastSensorValAvg > userDistance) {
      Serial.println("multiple > 200 in a row.");
      stopTime = millis();
      Serial.print("stop time:");
      Serial.println(stopTime);
      // roll curtain down since the user is away a long enough time
      if(stopTime - startTime >= milliSecsGoneTime) {
        // step one revolution  in one direction:
        Serial.println("-- curtain up --");
        myStepper.step(-stepsPerRevolution);
        myStepper.step(-stepsPerRevolution);
        myStepper.step(-stepsPerRevolution);
        myStepper.step(-stepsPerRevolution);
        myStepper.step(-stepsPerRevolution);
        myStepper.step(-stepsPerRevolution);
        myStepper.step(-stepsPerRevolution);
        myStepper.step(-stepsPerRevolution);
        myStepper.step(-1500);
        delay(2000);
        resetTimer(millis());
      }

    } else if(sensorValAvg > userDistance) {
      Serial.println("start count");
      startTime = millis();
      Serial.print("userAway after react:");
      Serial.println(startTime);
      Serial.print("\n");
    } else {
      Serial.println("stop stepper Motor");
      //myStepper.setSpeed(0);
    }
  }
}

void resetTimer(uint32_t now){
  Serial.println("resetting timer");
  minutesShown = 0;
  timeChanged = false;
  secondsToStart = 15;
  lastTimerSet = now;
  lastMinutesShown = 0;
  secondsShown = 0;

  timerMode = false;
  timerStarted = false;
  Serial.print("timer started");
  Serial.println(timerStarted);
  timerInMs = 0;
  timeOnTimerStart = 0;
}

void getPotentioAndSetTimer(uint32_t now){
  int potentio = analogRead(A0);
  Serial.println(potentio);
  int minPo = 0;
  float maxPo = 1002;
  int minSeconds = 0;
  int maxSeconds = 3600;
  // mm:ss
  bool lz = true;
  float allSeconds = ((float)potentio / maxPo) * maxSeconds;
  int minutesShown = allSeconds / 60;
  if(minutesShown % 5 != 0){
    minutesShown = minutesShown - (minutesShown % 5) + 5;
  }
  if(minutesShown == 0) {
    minutesShown = 1;
  }
  seg.displayTime(minutesShown, secondsShown, colon, lz);
  seg.displayColon(1);
  timerInMs = ((long)minutesShown * 60 * 1000);
  if(minutesShown != lastMinutesShown){
    Serial.println(now);
    lastTimerSet = now;
    lastMinutesShown = minutesShown;
  }
}

// -- END OF FILE --
```
