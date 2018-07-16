---
layout: article
title: "Getting Started with Souliss"
date: 2015-06-14T13:57:25-04:00
modified:
excerpt:
tags: [arduino, android, smart home, home automation, avr, esp8266, ethernet, wifi, rs485, wireless]
image:
  feature:
  teaser:
  thumb:
share: false
---

Souliss is build in three main parts, listed below:

* [The Arduino Networking Framework](https://github.com/souliss/souliss) : This is the code that runs on your Arduino and compatible boards (things). It networks your boards and is the base structure of your smart home system.

* [The Android Application](https://github.com/souliss/soulissapp) : This is an Android application that can communicate directly with your things, it learns from the nodes their features (light, door, windows or whatever they control) and allows you control them. For ease of distribution and updating, Soulisapp is currently made available on Play Store for free.

* [The openHAB Binding](https://github.com/souliss/bindingopenhab) : This bind your Souliss nodes with the openHAB automation supervision system, this provide you a server to control your automation and make advanced schedules. More with openHAB it lets you control multiple vendor system through an unique interface, so that you can use Souliss based devices togheter with other commercial ones.

Is at your option to decide to use the Android Application or the openHAB Binding, you can even use both at same time.

{% include toc.html %}

## Get Started

The first step in is a tour in the [wiki](https://github.com/souliss/souliss/wiki), this gives you a detailed understanding of Souliss' features and capabilities. 

<a href="https://github.com/souliss/souliss/wiki/Supported%20Hardware%20Platform" class="btn-info">Supported Hardware</a> <a href="https://github.com/souliss/souliss/wiki/Supported%20Network%20Architecture" class="btn-info">Network Architectures</a> <a href="https://github.com/souliss/souliss/wiki/Getting%20Started%20with%20Souliss" class="btn-info">Getting Started</a> <a href="https://github.com/souliss/souliss/wiki/Your%20First%20Upload" class="btn-info">Step by step upload</a> <a href="https://github.com/souliss/souliss/wiki/SoulissApp" class="btn-info">Use SoulissApp</a> 
 
### Required skills

Souliss is quite simple to use, but the following skills are required to get a network up and running. Consider that on average you can get a first node up and running in less than an hour,

* A general understanding of the Arduino world and its IDE to program the nodes,
* A basic knownledge of electronics and eletricity,
* A little knowledge of networking (basically the IP protocol).

## Build products based on Souliss

You can build nodes with Souliss pre-compiled and loaded, so that people can just install and use it. Souliss code is distributed under license GNU GPLv3, and there is no fee to use it, but you should contribute back if you are modifing the code as per license constrains.
At your option you can require us to re-license the code.

## Community

As an open-source project, Souliss is based on a community of people that share their work. You are suggested to join the [community](https://github.com/souliss/souliss/wiki/Community) to ask for support, share your results and encourage other users as well.

The following languages are available:
<a href="https://groups.google.com/forum/#!forum/souliss" class="btn-info">English</a> <a href="https://groups.google.com/forum/#!forum/souliss-it" class="btn-info">Italiano</a> <a href="https://groups.google.com/forum/#!forum/souliss-es" class="btn-info">Espanol</a>

**Be Aware:** The [**Community**](https://github.com/souliss/souliss/wiki/Community) is a mailing list of `volunteers` that help each others in improve their object and home empowered with Souliss. If you are using Souliss on a product, consider to get a `premium` support, [**contact us**](mailto:info@souliss.net) for details. 
{: .notice-warning}

## Contribute and Promote

You can contribute and promote Souliss in several ways, it isn't mandatory to be a programmer or an electronic designer/engineer:

* Share on social media ([twitter](https://twitter.com/soulissteam), [G+](https://plus.google.com/113934123042484468682/posts)) and with friends, show them your Souliss installation and help them to get started
* Partecipate in the [community](https://github.com/souliss/souliss/wiki/Community), help other people and share your results
* Fork the code and [contribute](https://github.com/souliss/souliss/wiki/Contribute) in the development
* [Donate](https://pledgie.com/campaigns/27771) to support the expenses and development

If you want to share your code, refer to [contribute](https://github.com/souliss/souliss/wiki/Contribute) page in the wiki.

**Support and Donations:** As all `community driven` project, also here all contribution to support the projects are welcome. [**Donations**](https://pledgie.com/campaigns/27771) are used to cover expenses.
{: .notice-success}

**Enjoy!**
