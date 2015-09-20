---
layout: article
title: "A new entry, Moteino boards are now supported in Souliss"
categories: articles
author: plinio_seniore
excerpt: "Small radio enabled Arduino compatible boards"
tags: [arduino, moteino, radio, 900 mhz]
modified: 2014-09-11
image:
  feature: 2014-09/moteino.jpg
  teaser: 2014-09/moteino-teaser.jpg
ads: false  
redirect_from: "2014/09/a-new-entry-moteino-boards-are-now.html"
---

Nowadays there are several Arduino based boards in the market, but still isn't easy find a small device that embed together a microcontroller and a communication interface into a single PCB, that's way I often spend some time over the Internet looking for boards that may be useful for Souliss' users.
This time I've been through [LowPowerLab](http://lowpowerlab.com/) and their Moteino boards, that has been offered as a set of three boards to integrate them in Souliss. In the picture, from top to bottom there is a Moteino Mega, a Moteino USB and a Moteino all are equipped with an HopeRF RFM69HW radio at 868 MHz. An additional SPI flash memory can be added while purchasing the modules.

The best is that we got the boards few days ago and Kim is was yet able to get them working properly using a Microchip ENC28J60 to bridge the Moteino Mega to SoulissApp, having full control of the other Moteino over the air from its Android smartphone. Next step is try the range extender examples and the use of Wiznet W5100 and similar on the Mega.

Starting from release Alpha 6.1.1 [Moteino boards](https://lowpowerlab.com/shop/index.php?_route_=moteino-r4) will be publicly supported, the release date will be likely at end of November. You can even have a try right now getting the pre-release code from git into the *chiattillo branch*.

Enjoy Moteino!