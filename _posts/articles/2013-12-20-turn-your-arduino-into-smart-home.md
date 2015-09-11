---
layout: article
title: "Turn your Arduino into a Smart Home product"
categories: articles
author: plinio_seniore
excerpt: "Autoconfiguration is now ready!"
tags: [arduino, kmp electronics, rs485, ethernet]
modified: 2013-12-20
image:
  feature: 
  teaser: 
ads: false  
redirect_from: "2013/12/turn-your-arduino-into-smart-home.html"
---

Is almost two year from the starting point of this project and for the first time it feels that we are near to a complete release, Souliss now include plug&play features as found in commercial product and turns most of the Arduino and derivatives into networked boards enabled for a smart home.

<iframe width="560" height="315" src="https://www.youtube.com/embed/AyYC38aNcfY" frameborder="0" allowfullscreen></iframe>

Yes, is still a DIY solution, because you are supposed to cable wires and fit boards and components around your home as an electrician does, but you can now have boards that just needs to be plugged-in, no configuration required, they will build the network and work out of the box.

The most, is that Souliss is fully open-source and documented, that gives to users a flexibility that even in commercial product isn't found at that time. You can combine features and let boards interact as you like, without having any server running 24h days or any cloud dependance. All communication works locally and goes out on internet only if you want and need it.

The activity around smart homing and diyers isn't new and lot of code before Souliss was releases even as open or closed source, but none was designed to turn boards into products and even Souliss took five release branch to get it. Now you can make your device live using wireless boards as Ethernet ones and even running a bus cable, mixing as you like and without any care of how to network those, all is behind Souliss and the virtualized network protocol (vNet) used with.

In the video there is a couple of KMP Electronics DINo II relay boards, once loaded with Souliss they just behave as plug&play. The boards discover themselves and Android smartphone (using SoulissApp) discover the boards, that is. It become a matter of wiring you electrical appliance and have control.
Souliss is the framework that makes every Arduino board designed for home automation a product and at same time is the starting point for any modification or hacking that move the interaction between the objects in your home at the next level.

Till the previous release, some effort was needed to have Souliss running over your boards and in two years we got more than seven hundred active users for SoulissApp, not bad considering that you need to wire-up you home, and now we hope to go further and having as much as possible boards that came to the user with Souliss pre-loaded, giving a real plug&play experience.

**What's next**
If the structure behind the "firmware" that runs the boards is mostly completed, there is still one focus point that actually we miss, the Internet of Things. We are working on several aspects to have an easy as plug&play connection to the internet when needed, some of those ideas are yet under working and was announced on the forum, but still we are far to a public release.
Mostly, there will be some heavy work on SoulissApp that in the year and half from the first release has been stable and faster and now need a new design to offer a better user-experience.

The best, is that all this work behind code and testing has been driven by the passion of people that are on this project, with the support of many hardware manufacturer that has offered us samples.

We don't know which of the next steps will really get out, but we are happy to say that Souliss is there and is working fine.

Stay tuned!