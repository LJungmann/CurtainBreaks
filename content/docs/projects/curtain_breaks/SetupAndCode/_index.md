---
title: Setup and Code
weight: 10
---

# Setup

## Pins on the Arduino

### LED 7-segment Display

5V Power
GND Pin
A4
A5
Address to use in Code is 0x71

- 0x70 by default and +1 for A0 jumper
- documentation states that A1 would be +2 and A2 would be +4
- which means 0x70 until 0x77 are available addresses, but we have 0x71 since there's a jumper on A0

### Rotary Button

| What   | Where |
| :----- | ----: |
| Power  |    5V |
| Ground |   GND |
| Pin    |    A0 |

### Stepper Motor

| Sensor | Pin |
| :----- | --: |
| IN1    |   8 |
| IN2    |  10 |
| IN3    |   9 |
| IN4    |  11 |

### Ultrasonic Sensor

| What    | Pin |
| :------ | --: |
| trigPin |  12 |
| echoPin |  13 |
| Ground  | GND |
| Power   |  5V |

# Code

```python
print("Format code in your Markdown file.")
```
