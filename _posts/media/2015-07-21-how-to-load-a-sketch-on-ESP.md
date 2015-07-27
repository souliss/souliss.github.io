---
layout: article
title: "How to load a sketch on ESP12 Module."
categories: media
excerpt: "Custom written post descriptions are the way to go... if you're not lazy."
ads: false
share: true
author: juanpintom
image:
  feature: 
  teaser: 
  credit: Name
  creditlink: http://alink.com
---

# How to Load a Sketch on ESP Module

## Material Needed:
  -ESP12 module
  -USB to Serial Converter (FTDI PL2303 - CH340 and others)
  
## Wiring:
### Minimal Hardware Setup for Bootloading only ##
ESPxx Hardware

| PIN           | Resistor | Serial Adapter  |
| ------------- | -------- | --------------- |
| VCC           |          | VCC (3.3V)      |
| GND           |          | GND             |
| TX or GPIO2   |          | RX              |
| RX            |          | TX              |
| GPIO0         |          | GND             |
| Reset         |          | RTS*            |
| GPIO15        | PullDown |                 |
| CH_PD         | PullUp   |                 |

* Note
	- if no RTS is used a manual power toggle is needed

### Minimal Hardware Setup for Running only ##

ESPxx Hardware

| PIN           | Resistor | Power supply    |
| ------------- | -------- | --------------- |
| VCC           |          | VCC (3.3V)      |
| GND           |          | GND             |
| GPIO0         | PullUp   |                 |
| GPIO15        | PullDown |                 |
| CH_PD         | PullUp   |                 |

### Minimal
![ESP min](https://raw.githubusercontent.com/Links2004/Arduino/esp8266/docs/ESP_min.png)

### Improved Stability
![ESP improved stability](https://raw.githubusercontent.com/Links2004/Arduino/esp8266/docs/ESP_improved_stability.png)


## Software needed: Arduino IDE

### Steps to configure Arduino IDE:
•Install Arduino 1.6.5 from the Arduino website.

•Start Arduino and open Perferences window.

•Enter http://arduino.esp8266.com/package_esp8266com_index.json into Additional Board Manager URLs field. You can add multiple URLs, separating them with commas.

•Open Boards Manager from Tools > Board menu and install esp8266 platform (and don't forget to select your ESP8266 board from Tools > Board menu after installation).

•Install "Souliss" library on Library Manager of Arduino IDE

•Load Helloworld example from Souliss: e01_Hello_ESP8266.ino

Reference: https://github.com/esp8266/Arduino
