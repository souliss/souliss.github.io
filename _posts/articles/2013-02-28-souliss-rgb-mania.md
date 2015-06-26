---
layout: article
title: "Souliss and the RGB Mania"
categories: articles
author: plinio_seniore
excerpt: "Experimenting with RGB LED Strips."
tags: [arduino, android, led strip, led light]
modified: 2013-02-28
image:
  teaser: 2013-02/ledchar-teaser.jpg
ads: false  
redirect_from: "2013/02/souliss-and-rgb-mania.html"
---

The future of lighting is in the way of LEDs and in the last years the number of solutions is increased dramatically.

Recently many manufactured introduced their boards (or shield) to control lighting LEDs easily, there are interesting board like the one available from [Open Electronics](http://store.open-electronics.org/Arduino/Shield/Arduino%20RGB%20shield), [Olimex](https://www.olimex.com/Products/Modules/LED/MOD-RGB/) and Ethermania.

<iframe width="420" height="315" src="https://www.youtube.com/embed/LBV1dOsjkZ4" frameborder="0" allowfullscreen></iframe>

Basically these contains three mosfet controller via PWM to give power to the LEDs, these are suitable for 12V LED strip and others and needs really few effort to get them working.

Just introduce some theory to understand the differencies between these boards, LEDs are current controlled devices and are able to have an almost fixed voltage across anode and cathode regardless the current that they get.

![](https://github.com/souliss/souliss.github.io/blob/master/images/2013-02/ledchar.gif?raw=true)

In the above picture are shown some V-I graphics for different LED color, and basically over a certain threshold the voltage remain fixed also if the current increase (within the current ratings) that basically make the LEDs current controlled devices.

From Ethermania there is a shield that do this job, is build over a step-down converter (the AP8800) that can drive into the LED the desired amount of current with an high efficiency. This is accomplished using an high frequency pattern over an inductor to filter and get a constant current value.

There is another way to control the current into an LED, simpler as inefficient, using a resistor. This way is the most used and is the supposed one for the shield from Open Electronics and Olimex.
Basically, the introduction of a resistor make the device (resistor + LED) controllable in voltage and no longer in current, so this make a standard transistor suitable for the case. This solution is simpler, but waste energy and is less flexible in terms of desired currents values.

Looking to a LED strip,it yet contains the resistors, so could be driven directly with an input voltage (typically is 12V) and doesn't allow a control directly in current, that means that only the first two shield could be used for this type of device.

In the next days drivers and examples for Olimex MOD-RGB controller will be released, giving the opportunity to connect you strip to the outside world. The goal is not only the release of the supporting code, but to build a DIY lamp.

More details will follow, for now just have a look to the video where we are trying the application color picker.
