---
layout: article
title: "IONO Ethernet Relay Board"
categories: articles
excerpt: "A new, professional looking Relay board that can be used with Souliss"
ads: false
share: true
author: ribico
image:
  feature: 2015-09/Iono-1.jpg
  teaser: 2015-09/Iono-1-teaser.jpg
  credit: Iono
  creditlink: http://iono.cc/
---

This year September has been [a month full of news](http://souliss.net/articles/multicolor-wifi-bulb-arduino-based/), and the latest is the support of [IONO](http://iono.cc/) a professional-like relay board that can be used for home automation. We just got a sample to work with and evaluate the product, that has a good manufacturing and interesting features.

![](http://souliss.net/images/2015-09/Iono-3.jpg?raw=true)

The **IONO** is mostly an Arduino shield with a DIN-rail enclosure, you can purchase it as standalone (IONO Solo) or packed with an Arduino Ethernet. The board has a socket compatible with Arduino UNO rev3, so you can plug in any compatible Arduino board or Arduino Ethernet.

> The focus for the IONO is on the I/O side, because it support input as Digital or Analog 0-10V / 4-20 mA and has six relays with bistable coil with 12 A of steady current and 80 A for inrush.

The inputs use an Operational Comparator to work either as digital or analog, using resistor to scale the value from 0-10V or 4-20 mA as 0-5V. The use of 0-10V and 4-20 mA is a standard in industrial application, current loop have better noise rejection, but isn't common for home application.
There are totally 6 inputs, 4 of them are connected to an Analog Input with ADC so that can be used either as digital or analog values; the other two are connected to digital inputs and can be attached to an interrupt.
The use of digital is in **voltage-free** configuration, so you should connect a switch and power the input.

![](http://souliss.net/images/2015-09/Iono-4.jpg?raw=true)

On the output side, the relays have a bistable coil and an embed driver, so from the user point of view are just standard digital outputs but there is no current waste because the relay is designed to mechanical retrieve the last position. As example, in case of power outage relays will remain in their position.
Generally speaking this nice trick can improve relays life very much.

![](http://souliss.net/images/2015-09/Iono-2.jpg?raw=true)

All terminals are detachable, this is also a common feature in industrial protocol, allow easy and reliable replacement of the electronics without have to rewire all the connection and helps in case of constrained spaces.

A **detailed focus** on the I/O design is available on the [IONO website](http://iono.cc) with details on [power supply](https://iono.cc/highlights-power-supply), [inputs](https://iono.cc/highlights-inputs), [digital outputs](https://iono.cc/highlights-power-outputs) and [analog outputs](https://iono.cc/highlights-analog-outputs). The [hardware manual](https://iono.cc/app/uploads/2015/02/iono-hardware-guide.pdf) is also a good reference to understand if the I/O fits your needs and how you can wire it.

> IONO support will be officially available in Souliss v7.1 but as preview you can get it from the current [souliss](https://github.com/souliss/souliss) branch

The guys at IONO will expose their boards at Maker Faire Rome from 16th to 18th October, and they will also setup a small demo with Souliss running on two IONO Ethernet.

Stay tuned!
