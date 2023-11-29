---
title: Curtain Breaks
type: docs
---

# Curtain Breaks

## Pins on the Arduino

LED 7-segment Display
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
