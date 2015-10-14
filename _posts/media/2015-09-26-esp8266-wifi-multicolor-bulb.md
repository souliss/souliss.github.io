---
layout: article
title: "LYT8226: an Arduino LED Bulb based on ESP8266 WiFi"
date: 2015-09-26
modified:
categories: media
excerpt: "Working to get Souliss on the ESP8266 in the LYT8266 bulb from Authometion"
author: plinio_seniore
ads: false
image:
  feature: 2015-09/lyt8266.jpg
  teaser: 2015-09/lyt8266-teaser.jpg
  credit: Authometion
  creditlink: http://authometion.com/
---

Working with the ESP8266 is always a great experience, it becomes just a matter of getting the proper I/O and then in few minutes your module is running. The introduction of the ESP8266 in the [supported SoC for Souliss](http://souliss.net/articles/preview-souliss-on-esp8266/) has open the world of **smart devices** to the DIYers and the very competitive price of this IC will [spread it into consumer products](http://souliss.net/articles/esp8266-in-commercial-product/).

In the last few days we have started working with [Authometion](http://authometion.com/) to support the new LYT8266, a variant of their RGBW LED Bulb that has an ESP8266 inside, so that you should program your sketches directly into the lamp (this is [in contrast with the approach used with LYT88](http://souliss.net/media/diy-your-philips-hue-led-bulb/)).

> Thanks to the [Arduino cores](https://github.com/esp8266/Arduino) for ESP8266 you can program this bulb directly from the Arduino IDE this include **OTA** (Over the Air) programming and any compatible library of framework, unsing Souliss you have direct access via SoulissApp or [openHAB](https://github.com/souliss/souliss/wiki/openHAB%20Binding).

![](http://souliss.net/images/2015-09/RGBWBulb_comparison.jpg?raw=true)

A side-to-side comparison show a LYT88 bulb (on the left side) with a LYT8266 (right one), the voltage regulation is based on a switching circuit (on top right, you can see the inductor and regulator) this is due to the high current required by the ESP8266 compared to a standard microcontroller with external RF radio (as on the left side).
The I/O is basically the same, with one mosfet for each channel used to sink the current from the LEDs powered at near 12 Vdc.

**LOAD YOUR SKETCH OverTheAir (OTA)**

Loading a new sketch has two option, using the cable or the **air**. The *Over the Air* programming is very simple and can be used right out-of-the-box if your bulb has Souliss pre-loaded.

You need the following pre-requisites to load a sketch:

* Install the Arduino IDE 1.6.5 (this is the supported release at time of writing)
* Install Python 2.7 and have it in your Windows path
* Install the [ESP8266 cores for Arduino](https://github.com/esp8266/Arduino), the cores are distributed via the Arduino IDE Board Manager and needs an URL for the distribution of the code. You can check the supported core [here](https://github.com/souliss/souliss/wiki/Supported%20Hardware#supported-cores)
* As today, the URL to be used is http://arduino.esp8266.com/staging/package_esp8266com_index.json into *Additional Board Manager URLs* field. You can add multiple URLs, separating them with commas.
* Install Souliss library on [Library Manager](https://github.com/souliss/souliss/wiki/Your%20First%20Upload) of Arduino IDE

Once you will power your bulb, if is the first time and has never been configured before, you will see an *Access Point* called **Souliss**, just connect and point your broweser to **http://192.168.4.1**

![](http://souliss.net/images/2015-09/WebConfig.png?raw=true)

You get a web interface from where you can configure the WiFi and IP parameters, and select the node as **Gateway** or **Peer**. Configure one bulb as **Gateway** and the others as **Peer**, they will build automatically a Souliss network and will be available in SoulissApp.

![](http://souliss.net/images/2015-09/SoulissApp.jpg?raw=true)

You bulbs has full features, but if you want to upload a new sketch you just need to go in the Arduino IDE and set the following parameters:

* Board as Generic ESP8266 Module
* Flash Mode QIO
* Flash Frequency 40 MHz
* Upload Using **OTA**
* CPU Frequency 80 MHz
* Flash Size 1M (64K SPIFFS)
* Upload Speed 115200

> In the Port sub-menu you will see the bulb and its IP address and you can upload a new sketch as it was connected via cable.

Is very important that you upload always an OTA enabled sketch, otherwise the next time you want be able to upload a new sketch over the air and you will need to connect via the cable. Start from the [**e02_LYT8266_WiFi_Bulb.ino**](https://github.com/souliss/souliss/blob/friariello/examples/LYTBulb/e02_LYT8266_WiFi_Bulb/e02_LYT8266_WiFi_Bulb.ino) to build your own sketch.

**LOAD YOUR SKETCH VIA USART CABLE**

Using the cable to connect via USART can be useful if you don't want OTA or if you have bricked your OTA sketch, more you can use the whole flash size (1 MByte) were on OTA you are able to use only 512 KBytes. All the previous prerequisite applies also for this case.

![](http://souliss.net/images/2015-09/ProgrammingConnector.png?raw=true)

Programming the LYT8266 is similar to any other ESP8266 based device, this [tutorial](http://souliss.net/media/how-to-load-a-sketch-on-ESP/) gives the basic to use the Arduino IDE and the ESP8266 cores. On board of the LYT8266 there is a programming connector, is very small and need an adaptor supplied with the dev kit, and expose the TX, RX togheter with GND and GPIO0 and others. You haven't the Vcc, so you should power the ESP8266 board connecting it to main 220 Vac (or 110 Vac), so be careful.

On the module there is an ESP-03, so on the Arduino IDE select the COM module as per your operating system and the following settings: 

* Board as Generic ESP8266 Module
* Flash Mode QIO
* Flash Frequency 40 MHz
* Upload Using **Serial**
* CPU Frequency 80 MHz
* Flash Size 1M (64K SPIFFS)
* Upload Speed 115200

As first step, you need to load the [**e02_LYT8266_WiFi_Erase**](https://github.com/souliss/souliss/blob/friariello/examples/LYTBulb/e02_LYT8266_WiFi_Erase/e02_LYT8266_WiFi_Erase.ino) sketch, this will clear the FLASH sector used as EEPROM from random data and later load the [**e02_LYT8266_WiFi_Bulb**](https://github.com/souliss/souliss/tree/friariello/examples/LYTBulb/e02_LYT8266_WiFi_Bulb) this will start the bulb as access point with a web configuration interface restoring the factory firmware.

The LYT8266 in our hands are actually prototypes that will be unvelived at Maker Faire Rome 2015 at the Authometion booth, there will be also a [workshop to have your hands on these devices](http://www.makerfairerome.eu/it/eventi/?ids=74). The sales will start after the faire, so a month or so before having them available on the market.

Enjoy!


