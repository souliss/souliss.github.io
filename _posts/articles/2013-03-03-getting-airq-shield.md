---
layout: article
title: "Getting AirQ Shield"
categories: articles
author: shine_angelic
excerpt: "Synch music and LED light."
tags: [arduino, android, led strip, led light]
modified: 2013-03-03
image:
  teaser: 2013-03/airq-shield.jpg
ads: false  
redirect_from: "2013/03/getting-airq-shield.html"
---

In the past weeks we went through AirQ Networks products, these are radio devices based on Texas Intrument C11100-F32 microcontroller with integrated 433 MHz radio, born along the concept of Internet of Things but applied to the industrial field.

Friday we received from them two samples AirQ Shields, to evaluate the integration between Souliss and their hardware, more interesting AirQ is near to release and I/O board (4 inputs and 4 relays) for domestic. The most interesting is the range of such transmitters, that due to 433 MHz can reach longer distances than 2.4 GHz ones.

As first activity we would include the AirQ radio into the supported medias, that will give us the opportunity to exchange MaCaco/vNet data over the 433 MHz link and build long range bridges.
The radio is not directly accessible, on the microcontroller there is a network firmware called sNET that should be used as carrier of vNet frames.

Based on the result, the future steps may include additional hardware from AirQ into the Souliss support, one important point is the CE marking available on all AirQ board, so these are product and not only development boards and could be certified for final installation without additional effort.

We hope to give be back with some result as soon.
