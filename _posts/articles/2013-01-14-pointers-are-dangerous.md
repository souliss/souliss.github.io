---
layout: article
title: "Pointers are so dangerous"
categories: articles
author: plinio_seniore
excerpt: "Diving in the world of C memory pointers."
tags: [arduino, android, olimex, souliss, enc28j60]
modified: 2013-01-14
image:
  teaser: 2013/01/Testing Olimex's board with Souliss.png
ads: false  
redirect_from: "2013/01/pointers-are-so-dangerous.html"
---

The screenshot on the top is the logging of a session with the WiFi MRF24WB0MA running Souliss with both MaCaco protocol over vNet and Modbus TCP, it was a long day looking around for a strange crash.

The Microchip MRF24WB0MA doesn't offer the IP stack in hardware, so I'm running that chip over the uIP stack, Souliss is running uIP from release A3 due to ENC28J60 support. This stack was for us a big headache but is now running really fine. So same should be for the WiFi module.

It was, but not at 100%. Souliss was running fine over WiFi, but some time the communication hang without reason, not so strange when including a new module, the driver may stopped to work.
But it doesn't, is still working and looks fine because the board is still alive and reply to pings without any problem, but MaCaco and Modbus stops after some minutes.

That's strange, MaCaco and Modbus are the same that runs over vNet and all its drivers, more the same stack is used for ENC28J60 where the problem doesn't occur, the morning goes testing but only with WiFi these protocols stops.

At first look the WiFi driver seems to work, otherwise ping wasn't available, so what happen? Just deeper in the stack MaCaco and Modbus stops because their listeners became crazy, the listened ports are changing randomly. So, some one is writing out of its boundaries.

Back to the drivers, they were working but didn't handle properly the uIP buffer, some more if() and now the WiFi is behaving correctly from almost one our.

Tomorrow I will let it run for more time, if it will not stop means that Souliss A4.1 is ready, there are just some minor bugfix on the logics and examples that shall be solved than it will be released.

Stay tuned,
Dario.