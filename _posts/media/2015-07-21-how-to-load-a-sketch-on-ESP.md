---
layout: article
title: "How to load a sketch on ESP12 Module."
categories: media
excerpt: "First steps to load Souliss on ESP8266 WiFi modules"
ads: false
share: true
author: juanpintom
image:
  feature: 2015-07/esp12_1600.jpg
  teaser: 2015-07/esp12_400.jpg 
  credit: ESP8266 Community
  creditlink: http://www.esp8266.com/
---

This tutorial shows how to load custom code on the ESP8266 and relevant breakout modules, like ESP-01 or ESP-12, this is based on the porting of Arduino cores for the ESP8266 microcontroller.

We focus on ESP-12, but this tutorial applies for all breakout modules based on ESP8266, you just need to cross check the pin assignment on the PCB, to start you need:

* ESP-12 module
* USB to Serial Converter at 3v3(FTDI PL2303 - CH340 and others)
  
## Wiring:

The minimal setup required to load a new sketch on your ESP8266 based module is the following one

**ESP-01 and others**

| PIN | Resistor | Serial Adapter  |
| :---: |  :---:  |  :---:  |
| VCC           |          | VCC (3.3V)      |
| GND           |          | GND             |
| TX or GPIO1   |          | RX              |
| RX or GPIO3   |          | TX              |
| GPIO0         |          | GND             |
| Reset         |          | RTS*            |
| GPIO15        | PullDown |                 |
| CH_PD         | PullUp   |                 |

* Note
	- if no RTS is used a manual toggle is needed

Once the sketch has been loaded, you can run your module using the following setup

**ESP-01 and others**

| PIN| Resistor | Power supply    |
| :---: |  :---:  |  :---:  |
| VCC | | VCC (3.3V)|
| GND|| GND |
| GPIO0 | PullUp | |
| GPIO15 | PullDown |  |
| CH_PD| PullUp |  |

### Minimal
![ESP min](https://raw.githubusercontent.com/Links2004/Arduino/esp8266/docs/ESP_min.png)

### Improved Stability
![ESP improved stability](https://raw.githubusercontent.com/Links2004/Arduino/esp8266/docs/ESP_improved_stability.png)


## Arduino IDE

The Arduino IDE allow an easy add-on of cores that has been developed by the community, this allow you reuse Arduino-like codes and libraries on non official boards. Perform the following steps to add the ESP8266 cores:


* Install the latest Souliss' supported Arduino IDE and have a general read of the [Getting Started guide](https://github.com/souliss/souliss/wiki/Getting%20Started%20with%20Souliss).
* Start Arduino and open Perferences window.
* Enter http://arduino.esp8266.com/stable/package_esp8266com_index.json into Additional Board Manager URLs field. You can add multiple URLs, separating them with commas.
* Open Boards Manager from Tools > Board menu and install **ESP8266** platform (you will need to select your ESP8266 board from Tools > Board menu after installation).
* Install Souliss library on [Library Manager](https://github.com/souliss/souliss/wiki/Your%20First%20Upload) of Arduino IDE
* Load the Hello World example [e01_Hello_ESP8266](https://github.com/souliss/souliss/tree/friariello/examples/WiFi/e01_Hello_ESP8266)

The [ESP8266 cores for Arduino](https://github.com/esp8266/Arduino) are mantained by the [ESP8266 Community](http://www.esp8266.com/).
