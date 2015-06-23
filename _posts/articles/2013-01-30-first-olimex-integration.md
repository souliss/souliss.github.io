---
layout: article
title: "First step of Olimex integration near to complete"
categories: articles
author: plinio_seniore
excerpt: "Support for Olimex board is almost complete."
tags: [arduino, android, olimex, souliss, enc28j60]
modified: 2013-01-30
image:
  teaser: 2013-01/olimexnode.jpg
ads: false  
redirect_from: "2013/01/first-step-of-olimex-integration-near.html"
---

After a while  the Atmel AVR on board of Olimex AVR-T32U4 (using Arduino Leonardo bootloader) is now running Souliss with both support for MOD-IO and MOD-WIFI giving access to I/O via Android (using MaCaco protocol) and/or Modbus.

We get time to work on Olimex's MOD-IO2 board and fully include that board into Souliss, the first step started from [Wayne's I2C library](http://dsscircuits.com/articles/arduino-i2c-master-library.html) that after some work became lighter and basic enough to be part of Souliss. The I2C library is the core for the MODIO one, that provide similar methods to access standard I/O pins, so now the Olimex's MOD-IO2 (and MOD-IO) can be controlled like standard pins.

In the top of the picture shows the IDC10 cable breaked out on a bread board, this because we need from the UEXT the SPI for the MRF24WB0MA WiFi module and the I2C for the PIC on board of the I/O board. Unfortunately the MOD-IO2 doesn't extend the whole UEXT bus and so this workaround was needed. *There is one more clean solution*, that use an IDC10 cable with one female and two male headers, that can easily be build using a crimping tool for IDC cables.

The code will be released under revision A4.1 just after completion of ready to use examples for Olimex boards, this revision will support also MOD-ENC28J60 and MOD-IO. For these two boards we cannot perform any test, but Microchip ENC28J60 is yet working under Souliss and MOD-IO is pretty similar to the smaller MOD-IO2. If you would like to get the code before the public release, just email us.

There are other Olimex's boards that we would like to support, like the [RF ones](https://www.olimex.com/Products/Modules/RF/) but this will depend on hardware availability.

At the end one important note, the Microchip MRF24WB0MA is distributed with different firmwares and the latest 0x120C is not yet supported in our drivers. We will work to include latest modules, but for now ensure that you are getting boards  with module manufactured before August 2012.

Regards,
Dario.