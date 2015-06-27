---
layout: article
title: "Souliss RGB Strip Installation"
categories: articles
author: shine_angelic
excerpt: "Synch music and LED light."
tags: [arduino, android, led strip, led light]
modified: 2013-03-13
image:
  teaser: 2013-03/rgb-shield.jpg
ads: false  
redirect_from: "2013/03/souliss-rgb-strip-installation.html"
---

After some months of development, we are almost ready for real case scenarios. This node shows some of Souliss feature, including a simple gate, a light controlled by a wall switch, a temperature sensor and a RGB strip.

The node has been built inside an IP45 box, fit inside a small cabinet. The **node is wireless**, meaning that its only wired connection is 12V DC one (well, plus the one to wall switch). Data connection relies on chibiduino wireless, with this node acting as a peer of a bigger souliss network installation.

A RGB shield was placed on top of the board to ease RGB operations: it's basically a three channel MOSFET driven bridge to 12V Vin connection. A small relay board was placed inside the box to operate the gate and the floor light; an external 2A AC/DC powers everything up.

The resulting sketch is quite simple, using only native Souliss typicals, and is very similar to Example 12 one. SoulissApp ver. 1.1.6 was used, meaning that we could try music sync mode, too. It's still in development, but it partly works. After some clean-up, we recorded this short video:

<iframe width="420" height="315" src="https://www.youtube.com/embed/XZrO-O_d3rY" frameborder="0" allowfullscreen></iframe>