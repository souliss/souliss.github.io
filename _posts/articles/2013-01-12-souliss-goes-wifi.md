---
layout: article
title: "Souliss goes WiFi"
categories: articles
author: plinio_seniore
excerpt: "Support for Olimex WiFi transceiver is near to be completed."
tags: [arduino, android, olimex, souliss, MRF24WB0MA ]
modified: 2013-01-12
image:
  teaser: 2013-01/Souliss with MODWIFI.jpg
ads: false  
redirect_from: "2013/01/souliss-goes-wifi.html"
---

After a long run in design the Alpha 4 release of Souliss, we are back on the drivers, working on the cheap and spread used Microchip MRF24WB0MA.

Starting from [AsynchLabs / Open Electronics porting of ZeroG Wireless G2100](http://code.google.com/p/wifi-shield-oe/downloads/list) drivers we have now included in the working-on release of vNet the code for pairing the Microchip radio in both standard or AdHoc connections.

In the actual picture we are using a [MOD-WIFI](https://www.olimex.com/Products/Duino/AVR/AVR-T32U4/) from Olimex connected to an ever-green Arduino Duemilanove, then we will move Souliss to the ATmega32U4 microcontroller and the [Olimex AVR-T32U4](https://www.olimex.com/Products/Modules/Ethernet/MOD-WIFI) board before release the code as Souliss A4.1.

Stay tuned,
Dario.