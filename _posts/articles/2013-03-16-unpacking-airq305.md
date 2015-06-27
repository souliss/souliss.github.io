---
layout: article
title: "Unpacking the AirQ 305 Relay Board"
categories: articles
author: plinio_seniore
excerpt: "Air305 just arrived."
tags: [arduino, android, relay, 433 MHz, radio, remote control]
modified: 2013-03-16
image:
  feature: 2013-03/UnpackingA305.jpg
  teaser: 2013-03/UnpackingA305-teaser.jpg
ads: false  
redirect_from: "2013/03/unpack-airq-305-relay-board.html"
---

There is an interesting new entry in the relay boards, the [AirQ 305](http://dev.airqnetworks.com/2013/03/08/new-control-board-from-airq-networks/) is based on the [SNET](http://wiki.airqnetworks.com/index.php/SNET_Protocol) 433 MHz transceiver and has four relays rated for 6A at 250V and four opto-isolated inputs, thanks to the used carrier frequency data can be transmitter as far as 500 meters in open air.

The goal is integrate that hardware into Souliss, is quite a straightforward activity that is not so different from what we did for the [Olimex MOD-IO2](http://www.souliss.net/2013/02/souliss-and-uext-its-plug.html), where instead of an I2C communication there will be a wireless one. Once in Souliss, the AirQ hardware will interact with all other devices supported in our framework and will have a gateway to Android, Modbus and HTTP/JSON.

From the code point of view, once developed the interaction code between the Souliss data structure and the AirQ library, all supported nodes can compile a code running the support for AirQ boards, the only constrains is on the available space in terms of RAM. The communication between the AVR where Souliss runs and the SNET radio that give the communication link with the board, is handled via a virtual USART, that require some more RAM rather than SPI, I2C or the hardware USART.

Support for Souliss running over Wiznet W5100 (Arduino Ethernet or with Ethernet Shield and similar) will have enough room due to the TCP/IP stack in hardware, rather the Microchip ENC28J60 and MRF24WB0MA (Olimex based nodes) needs the software TCP/IP stack and so the RAM availability shall be verified.

The AirQ boards are products and not development boards, these make straight the certification process if using that boards into a final installation.

Stay tuned!
