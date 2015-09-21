---
layout: article
title: "What's next? WiFi with ESP8266 and nRF24 based Battery Board"
categories: articles
author: plinio_seniore
excerpt: "Design is almost completed, WiFi with ESP8266 and nRF24 based Battery Board"
tags: [souliss, arduino, esp8266, wifi, rf24l01]
modified: 2015-05-16
image:
  feature: 
  teaser: 2015-05/batteryboard-teaser.jpg
ads: false  
redirect_from: "2015/05/whats-next-wifi-with-esp8266-and-nrf24.html"
---

Things are changing and mostly in a (nice) unpredicted way, for long time we keep out from PCB design and support for MCU different than AVRs, there was several good reason to didn't jump in these fields and mostly were time driven resons.

It happens suddenly that you find your self on a complete different way, like a month or more ago when Joosof joined our team sharing its own PCB design and spending his time on project related design. We focused on a battery operated board, designed to run for a years and more on a LiPo battery with support for Gove sensors and nRF24L01, a small a quick to use board to build mobile sensors or avoid to pull cables around you home.
The first design was so quick that in no time we were looking for partnership to build few prototype at a reasonable price, isn't easy build just a couple of fully assembled boards, only friend does, and we start looking around.

So lucky that one of Souliss best friend is KMP Electronics, their ProDINo relay board is widely used within Souliss automations and this has created a good relationship in the time. Once convinced, we started to move from the first design to the final one, looking in details for components and PCB layout, and after a couple of weeks we have now a final design to prototype some boards.

That's not the only good news, many of us are falling in love with the ESP8266, is actually mostly a bet, because we are sure that more and more products for DIYers will be based on this SoC with integrated WiFi.
The ESP8266 is our from a year or so, I've seen it and never been very enthusiast, but few weeks ago Saverio opened my mind and now we have a mostly full Souliss code that can run on this module. The Souliss code is no longer binded to AVR 8 bits architectures, and can now easily be ported to every MCU or SoC that has Arduino cores.

In the while, the friariello branch has been promoted to official release as Souliss v7 and for the first time a release is no longer marked as Alpha. The v7 is a compeltely new Souliss especially in the user space (that has been break) and slowly people are moving, but the results are good.
Gabriele is intensely using v7, contribuiting to consolidate the actual base code.

Those are a lot of new for a small team like us, stay tuned for the next ones!