---
layout: article
title: "SoulissApp 1.3.3 available on Play Store"
categories: articles
author: shine_angelic
excerpt: "New release for SoulissApp for Android"
tags: [arduino, android, souliss, soulissapp, android smart home]
modified: 2015-01-19
ads: false  
redirect_from: "2015/01/soulissapp-133-available-on-play-store.html"
---

SoulissApp development goes on, both on back-end Souliss side and on front-end enhancements and updates. First **material-compliant** components have been added, to **swipe-refresh** nodes list and node detail.

Side menu has been reviewed, too, along with  widgets details. It is now possible to add a widget without commands, i.e. to show sensor values on device's home screen. Informations on launcher screen have been re-arranged to increase meaning and readability. Surprisingly, older list elements were already drawed on 'material sheets' projecting a shadow, so no substantial changes were made to them.

![](http://souliss.net/images/2015-01/soulissapp1.png?raw=true)

A new option to enable lights history has been added, in order to show some additional stats on typical detail panel. Every time a light is tured on or off, the app keeps track of the status change and logs it. Typical 31 is finally supported, even if its implementation is still in beta stage. **T1A is also available**, showing an array of 8 lights. This is the most efficient way to collect ON/OFF sensors, since a single typical can manage 8 devices.

![](http://souliss.net/images/2015-01/soulissapp2.png?raw=true)

Eclipse IDE has been abandoned, since Android development has moved to IntelliJ. Users shouldn't notice changes, but at least there is something We can blame if the app crashes.