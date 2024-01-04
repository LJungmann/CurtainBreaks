---
title: Curtain Breaks
type: docs
---

# Curtain Breaks

Project documentation for the Design for **Physical Prototyping** course 2023/24 focusing on the topic of **Chindōgu**

## Team

- Jungmann Leo
- Rodler Hanna
- Romelli Elena

## Abstract

## Concept

People usually spend too much time sitting down at the desk. They take too little breaks to stand up, walk a few steps and get a fresh mind. The Chindogu Curtain Breaks helps people take these breaks.
{{< figure src="assets/CurtainBreaks1.png" caption="*Sketch of the originally planned Curtain Breaks.*">}}
When the user sits down, they can set a time on a LED Display using a rotary button (originally an "up" and "down" button) that will determine how many minutes they can remain sitting. The maximum that they can stay seated is 60 minutes. The LED Display is mounted on the top of the laptop screen along with the buttons. Next to the LED Display, there is a proximity sensor that senses if the user is sitting in front of the screen.
Above these sensors there is a bar mounted to the screen with a fabric rolled around it.
{{< figure src="assets/Curtainbreaks2.png" caption="*Curtain Breaks from the front showing the LED Display, the buttons, the proximity sensor and the curtain mounted on top.*">}}
{{< figure src="assets/CurtainBreaks3.png" caption="*Curtain Breaks from the back still showing an originally planned battery and on/off button.*">}}
{{< figure src="assets/CurtainBreaks4.png" caption="*Curtain Breaks from the side.*">}}

When the user is not standing up after the set time, the proximity sensor will sense it and the curtain will start to be rolled down in front of the laptop screen.
{{< figure src="assets/CurtainBreaks5.png" caption="*Sketch of the curtain being rolled down in front of the laptop.*">}}

The curtain will only roll back up if the user is gone at least one minute. This is again sensed by the proximity sensor.

## Implementation

## Conclusion

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

Rotary Thing
5V Power
GND Pin
A0

### Stepper Motor

- IN1 -> 8
- IN2 -> 10
- IN3 -> 9
- IN4 -> 11

### Ultrasonic Sensor

- trigPin is on 12
- echo Pin is on 13
- connected to GND and 5V

## Abstract

A short and concise description of your project.

## Introduction

A detailed description of the concept and sketches of the planned implementation.

If a section grows too large or handles a very specific part of the project it can be put into [subpages]({{< ref "subpage_1#how-to-format" >}}).

{{< figure src="get_in.jpg" caption="*A drawing by David Shrigley.*">}}

## Related work

References to related concepts, projects, books, websites, stories, systems, fruits, etc. and their relation to the project at hand.

## Implementation

A detailed description of your prototyping process.

### Iteration №1

This did not work.

### Iteration №2

This did also not work.

### Iteration №3

This worked!

## Conclusion

A reflection on your prototyping process and the project outcome. What happens to the prototype after the project?
