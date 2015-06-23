---
layout: article
title: "Hardware-less Binary FKS"
categories: articles
author: plinio_seniore
excerpt: "Experiments with FKS."
tags: [arduino, fks, bfks, oscilloscope]
modified: 2012-07-29
ads: false  
redirect_from: "2012/07/hardware-less-bfks.html"
---

Modulate and demodulate a signal using your mind... no, that's not. Hardware-less to say do it without add extra components on your boards.The Binary FSK is a modulation/demodulation technique used to transfer data over an "high" frequency carrier, that's useful when data shall be transferred over a shared communication channel. In our case, the channel is shared with the power supply.

![](https://github.com/souliss/souliss.github.io/blob/master/images/2012-07/BFKS_01.jpg?raw=true)

These drivers aren't born for an hardware-less communication, but are coming from this [design](http://arduino.cc/forum/index.php/topic,97347.15.html) where I'm involved, and since we are now meditating on the hardware side, I've skipped on the drivers. Basically, we build a PWM signal over two frequencies: near 5 KHz for the '0' and 7 KHz for the '1'; the signal is demodulated using the ATmega internal analog compator and timer, counting the crossing of the modulated wave over a DC reference signal into fixed period of time.

![](https://github.com/souliss/souliss.github.io/blob/master/images/2012-07/BFKS-Wikipedia.png?raw=true)

The driver that I've build is called plinio and let more boards communicate over a bus just using some wires and resistor. It include a collision avoidance management and now is working over a few centimetre bus; is a work in progress but can be a base for a cheap communication. Is based on SoftModem by arm22.

I'm confident that over a shielded cable it may run for 50/100 meters at few frames per second, enough for home automation. For sure, these distances require a tuning of the collision avoidance and a checksum (that is not yet integrated in the driver).

Is just an experiment, but I'm thinking to release the code of plinio from the next Souliss release, the A3.1 that is basically a set of bug-fixes for the ENC28J60.

If you like to try it out, just wait few days.

Stay tuned,
Dario.