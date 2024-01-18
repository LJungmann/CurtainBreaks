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
| ?      |    A4 |            |
| ?      |    A5 |            |

<!-- TODO -->

Address to use in Code is 0x71

- 0x70 by default and +1 for A0 jumper
- documentation states that A1 would be +2 and A2 would be +4
- which means 0x70 until 0x77 are available addresses, but we have 0x71 since there's a jumper on A0

### Potentiometer

| What   | Where | Wire Color |
| :----- | ----: | ---------- |
| Power  |    5V | violet     |
| Ground |   GND | white      |
| Pin    |    A0 | gray       |

### Stepper Motor

| Sensor | Pin | Wire Color |
| :----- | --: | ---------- |
| IN1    |   8 | blue       |
| IN2    |   9 | green      |
| IN3    |  10 | yellow     |
| IN4    |  11 | orange     |
| Power  |  5V | white      |
| GND    | GND | black      |

### Ultrasonic Sensor

| What    | Pin | Color  |
| :------ | --: | ------ |
| trigPin |  12 | orange |
| echoPin |  13 | red    |
| Ground  | GND | brown  |
| Power   |  5V | yellow |

# Code

```python
print("Format code in your Markdown file.")
```
