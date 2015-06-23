---
layout: article
title: "Getting Olimex Boards"
categories: articles
author: plinio_seniore
excerpt: "Olimex boards just arrived, the game start."
tags: [arduino, android, olimex, souliss]
modified: 2012-12-07
image:
  teaser: 2012-12/olimexhardware.jpg
ads: false  
redirect_from: "2012/12/getting-olimex-boards.html"
---

Two weeks ago we won the [18th Olimex's Friday Quiz](http://olimex.wordpress.com/2012/11/23/friday-free-board-quiz-issue-18-prize-is-avr-t32u4/): a twitter competition for Olimex boards, that for the case was an Arduino Leonardo like [AVR-T32U4](https://www.olimex.com/Products/Duino/AVR/AVR-T32U4).

This board is an entry level in the Olimex products with a really interesting price, to lower the cost it uses the ATmega32u4 (that includes USB) and has a standard linear 3.3V regulator instead of the switching DC/DC included with most of Olimex products.

At the begin of the project we were looking for an hardware partner and we tried, without success, to get Olimex support. After several months we decided, as a first step, to be in the contest; we won at first shot, even if it was really a simple question and [random.org](http://www.random.org/) was friendly that day.

As now we still don't have the Olimex support, but we're purchasing some extra boards in discount and they shall be used for a Stand-alone garage door to control via Souliss Android App.

 Hopefully we will convince them once included the [MOD-WIFI](https://www.olimex.com/Products/Modules/Ethernet/MOD-WIFI) and [MOD-IO2](https://www.olimex.com/Products/Modules/IO/) boards in Souliss supported hardware.

The stand-alone garage door control project **will use the MOD-WIFI as access point** to control the garare door with MOD-IO2 relays. The challange will be to use software TCP/IP stack with ATmega32u4 that, due to the integrated USB, has less RAM available for Souliss; furthermore the drivers for the WiFi module and I2C relay protocol shall be added.

The support of such Olimex hardware will not be foreseen from the release **Alpha 4, since it will be available shortly**, but most probably starting from 4.1.

Stay tuned,
Dario.