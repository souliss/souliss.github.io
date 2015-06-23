---
layout: article
title: "Souliss goes WiFi / 2"
categories: articles
author: plinio_seniore
excerpt: "Support for Olimex WiFi transceiver is near to be completed."
tags: [arduino, android, olimex, souliss, MRF24WB0MA ]
modified: 2013-01-13
image:
  teaser: 2013-01/Souliss with MODWIFI and AVRT32U4_1.jpg
ads: false  
redirect_from: "2013/01/souliss-goes-wifi-2.html"
---

Once included the Microchip MRF24WB0MA core of the Olimex MOD-WIFI most of the job was done, the step after was the Olimex AVR-T32U4 shown in the picture.

The T32U4 is a small microcontroller board with [UEXT](https://www.olimex.com/Products/Modules/) socket powered by the ATmega32U4 that power also the Arduino Leonardo board. Just a bit of tuning on the SPI configuration and Souliss was running over it using the MRF24WB0MA radio to bring communication in it.

This Microchip WiFi controller offer a wireless IEEE 802.11 (WiFi) offering up to the MAC layer of the ISO/OSI, is Souliss runs over the uIP software stack offering same functionality of ENC28J60 but without cables.

An interesting feature is the ability to create [AdHoc networks](http://en.wikipedia.org/wiki/Wireless_ad-hoc_network), in such way "any" WiFi device can connect to the radio without going through an access point, so you can pair your smartphone running Souliss directly with the board. This is useful if you place the board in a place that is not covered by your WLAN and you won't bridge the board via IEEE 802.15.4 (a peer-to-peer 2.4 GHz radio like the supported [Freakduino Chibi](http://www.freaklabsstore.com/index.php?main_page=product_info&products_id=187)).
That's the theory, because most of the Android devices have the AdHoc connection locked by default and you need root access of your phone to get this goal, rather all PCs allow AdHoc connection and you can get a Modbus speaking without using router or cables.

This WiFi module is more expensive than an equivalent wired Ethernet one or a 2.4 GHz wireless, for example Olimex itself offers at half price a wired Ethernet module based on ENC28J60 (~14 Euros) and a IEEE 802.15.4 Bee-like radio (~12 Euros), but for small networks or in case of few added nodes may be the right one.
The wired solution need cables and the relevant dirty work, rather the 2.4 GHz radio require a bridge to Ethernet if you will to connect your phone.

Next step will be the MOD-IO2, this is an I/O module that use an I2C protocol. It can be used together with  MOD-WIFI via UEXT but it will require a custom IDC10 cable to connect both the modules, this because MOD-IO2 has two connectors but extend only the I2C to build a chain of I/O devices.

So, still some weeks to have the first Souliss module based on Olimex hardware.

Stay tuned,
Dario.