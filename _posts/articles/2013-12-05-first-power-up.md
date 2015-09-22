---
layout: article
title: "First board assembled and powered-up, update / 1"
categories: articles
author: plinio_seniore
excerpt: "Marco has just powered the RS485 board."
tags: [arduino, ethermania, rs485, relay]
modified: 2013-12-05
image:
  feature: 
  teaser: 2013-12/firstpowerup-teaser.jpg
ads: false  
redirect_from: "2013/12/first-board-assembled-and-powered-up.html"
---

Starting from a [software CAD and a 3D rendering](http://www.souliss.net/2013/09/3d-rendering-for-new-rs-485-boards.html), the LED board is now a prototype. At time of the picture the board was powered and the bootloader installed.

The on-board switching regulator is working fine and the next step is the test of the MOSFET drivers using the shift-registers, that way was inspired by ShiftPWM and allow a single ATmega328 to drive the 12 sink output (2.5A) channels.
After it will be the time for the RS485 driver and then we will start testing the boards with Souliss.

![](http://souliss.net/images/2013-12/firstpowerup.JPG?raw=true)

The board carry-out a large current value (up to 30 A) and for that reason has two ground planes connected in a single point, where the LED power supply will close its loop.

This is probably the first single board that is born with the idea of a complete tool for LED lighting in an house. It will support the new auto-detection feature introduced in [release Alpha 5](http://www.souliss.net/2013/11/lets-jump-in-alpha-5.html) giving multiple control of all the strips around the house with a single point of control.

Here the first power-up of a couple of LED strips, then we will move to heavy load of the board and communication on the bus.