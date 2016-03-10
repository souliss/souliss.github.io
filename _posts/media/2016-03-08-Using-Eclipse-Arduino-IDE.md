
---
layout: article
title: "Using Eclipse Arduino IDE with Souliss"
categories: media
excerpt: "This is tutorial how to setup Eclipse Arduino IDE to compile sketches using Souliss."
ads: false
share: true
author: Damian Gołda
---

This is tutorial how to setup Eclipse Arduino IDE to compile sketches using Souliss.

I assume you use Windows (Windows 7 64-bit in my case) - for other operating systems there are minor differences.

## Download and install

### Download Arduino IDE Bundle

I recommend to download whole bundle: Eclipse + Arduino IDE plugin in stable version `V2.4_win64.2015-12-06_20-24-02`

http://eclipse.baeyens.it/stable-win.html

Select 32 or 64 bit version, according to your Windows version.

I choose 64-bit version and downloaded `V2.4_win64.2015-12-06_20-24-02.tar.gz` file.

### Unpack Eclipse Arduino IDE

Unpack `V2.4_win64.2015-12-06_20-24-02.tar.gz` using for example 7-zip, to any directory without spaces in name.

In my case it is: `C:\Apps\eclipseArduino-V2.4_win64.2015-12-06_20-24-02\`

### Download Arduino IDE 1.6.5

You need exactly that version - 1.6.5!

Page: https://www.arduino.cc/en/Main/OldSoftwareReleases#previous

I recommend Windows ZIP file for non admin install: 
http://arduino.cc/download_handler.php?f=/arduino-1.6.5-r5-windows.zip

So you need to unpack arduino-1.6.5-r5-windows.zip to any directory. 
In my case it is: `C:\Apps\arduino-1.6.5-r5\`

You can also use Windows installer, but remember to use correct Arduino installation path later.

### Download make.exe

Windows users need `make` utillity, because it is no more in Arduino.

Download from ftp://ftp.equation.com/make/32/make.exe and place on your `PATH` or in your Arduino IDE `hardware\tools\avr\bin` directory.
In my case it is: `c:\Apps\arduino-1.6.5-r5\hardware\tools\avr\bin`

## Configure Eclipse Arduino IDE

Launch `eclipseArduinoIDE.exe`

### Configure Arduino plugin
* Enter Preferences: Menu *Window*, *Preferences*
* select *Arduino* on the left tree
* Enter correct paths

  ![configure1](https://cloud.githubusercontent.com/assets/1191883/13628564/774e8604-e5d3-11e5-9396-c41c90aa51a1.png)

  You should see green text: `ide is supported`

  If `make.exe` is on your `PATH` you can check *test if make can be found* and you should see green `Make is found on your system`.

  If `make.exe` is in `hardware\tools\avr\bin` you will see `make is not found on your system` but it still should work.

* *Apply*

### Set the save before build option
* Enter Preferences: Menu *Window*, *Preferences*
* select *General*, *Workspace* on left tree
* Mark *Save automatically before build* checkbox
* *Apply*
![configure2](https://cloud.githubusercontent.com/assets/1191883/13628567/795c4d5a-e5d3-11e5-95a9-93861bf4a1f6.png)

### Add `.ino` and `.pde` as C++ Source
* Enter Preferences: Menu *Window*, *Preferences*
* Select *C/C++*, *File types* on left tree
  ![configure3a](https://cloud.githubusercontent.com/assets/1191883/13629289/68d5dbb8-e5d8-11e5-8643-ffc032ceed61.png)

* Press *New..*, enter `.ino` and select *C++ Source File*, *OK*
  ![configure3b](https://cloud.githubusercontent.com/assets/1191883/13628571/7f5b724e-e5d3-11e5-87b2-7a933b17dadb.png)

* Again press *New..*, enter `.pde` and select *C++ Source File*, *OK*
  ![configure3c](https://cloud.githubusercontent.com/assets/1191883/13628572/813f7006-e5d3-11e5-9376-7dde45133642.png)

* *Apply*


## Create and compile first Sketch

### Create new Arduino Sketch based on blink example

* Connect your Arduino board to computer
* Menu *File*, *New*, *New Arduino sketch* or press *New sketch* on toolbar

  ![newsketchbutton](https://cloud.githubusercontent.com/assets/1191883/13629563/261b70a6-e5da-11e5-95f3-28b06d33079b.png)

* Enter *Project name*, for example `hello`, *Next*
* Select your board and COM port, for example `Arduino/Genuino Uno`, `COM11`, *Next*
* In Select code choose: *Sample Sketch*. In Select Example code mark checkbox for `Blink` under `01.Basics`, *Next*
* *OK*

## Compile (Verify) your sketch
* Press *Verify* button on toolbar

  ![verifybutton](https://cloud.githubusercontent.com/assets/1191883/13629562/2618f010-e5da-11e5-9361-1e45d6398dcf.png)

On *Console* tab you should see many messages and at the end:
```
'Finished building target: hello'
Build Finished
```

![blinkcompiled](https://cloud.githubusercontent.com/assets/1191883/13628579/86aae28c-e5d3-11e5-8e7f-4cfd4d276e7a.png)

On *Problems* tab should be no red *Errors*

## Upload your sketch
* Press *Upload* button on toolbar

![uploadbutton](https://cloud.githubusercontent.com/assets/1191883/13629564/261d85a8-e5da-11e5-83ec-474452f33a00.png)

On *Console* Tab you can see messages like this:

```
Starting upload
using arduino loader
Starting reset using DTR toggle process
Flushing buffer
Toggling DTR
Continuing to use COM12
Ending reset using DTR toggle process


Launching C:\Apps\arduino-1.6.5-r5\hardware\tools\avr/bin/avrdude -CC:\Apps\arduino-1.6.5-r5\hardware\tools\avr/etc/avrdude.conf -patmega328p -carduino -PCOM12 -b115200 -D -Uflash:w:C:\Apps\eclipseArduino-V2.4_win64.2015-12-06_20-24-02\workspace\hello/Release/hello.hex:i 
Output:

avrdude: AVR device initialized and ready to accept instructions

Reading | ################################################## | 100% 0.00s

avrdude: Device signature = 0x1e950f
avrdude: reading input file "C:\Apps\eclipseArduino-V2.4_win64.2015-12-06_20-24-02\workspace\hello/Release/hello.hex"
avrdude: writing flash (1030 bytes):

Writing | ################################################## | 100% 0.18s

avrdude: 1030 bytes of flash written
avrdude: verifying flash memory against C:\Apps\eclipseArduino-V2.4_win64.2015-12-06_20-24-02\workspace\hello/Release/hello.hex:
avrdude: load data flash data from input file C:\Apps\eclipseArduino-V2.4_win64.2015-12-06_20-24-02\workspace\hello/Release/hello.hex:
avrdude: input file C:\Apps\eclipseArduino-V2.4_win64.2015-12-06_20-24-02\workspace\hello/Release/hello.hex contains 1030 bytes
avrdude: reading on-chip flash data:

Reading | ################################################## | 100% 0.15s

avrdude: verifying ...
avrdude: 1030 bytes of flash verified

avrdude done.  Thank you.

avr/bin/avrdude finished
upload done
```

And your Arduino board should blink!

If uploading is very slow and you see on *Console* tab:
```
avrdude: stk500_recv(): programmer is not responding
avrdude: stk500_getsync() attempt 1 of 10: not in sync: resp=0x39
```
it meanse you have communication problems.

Double check your cables and COM port number.

You can change COM port (or even board type)

* Select in menu: *Project*, *Properties*
* Select *Arduino* on the left tree
* Correct your COM *port* and/or *board* type

![changeboard](https://cloud.githubusercontent.com/assets/1191883/13629561/261630be-e5da-11e5-9945-cf63662a1a5d.png)


## Create and compile Souliss sketch

## Download Souliss

Open https://github.com/souliss/souliss/ and Download zip (https://github.com/souliss/souliss/archive/friariello.zip)

## Unpack Souliss

Unpack `souliss-friariello.zip` to your Arduino library - the same you configured in *Configure Arduino plugin* step as *Private Library path*.
Rename `souliss-friariello` directory to just `souliss`.

### Create new Arduino Sketch based on Souliss example

* Connect your Arduino board to computer
* Press *New sketch* on toolbar

![newsketchbutton](https://cloud.githubusercontent.com/assets/1191883/13629563/261b70a6-e5da-11e5-95f3-28b06d33079b.png)

* Enter Project name, for example `souliss-test`, *Next*
* Select your *board* and COM *port*, for example `Arduino/Genuino Uno`, `COM11`, *Next*
* In Select code choose: *Sample Sketch*. In Select Example code mark checkbox for `e01_HelloWorld` under `souliss` and `ethernet`, *Next*
* *OK*

### Add libraries to your sketch

* Menu *Arduino*, *Add a library to the seleected project*
* Mark checkboxes on `souliss` and `SPI`, *Finish*

### Exclude some souliss file from compilation

**Because all souliss files (both .h and .cpp) are actually included in your sketch, compile must not compile .cpp files.
So you need to exclude them from compilation!**

In *Project Explorer*, expand your project, `Libraries`, `souliss`, select all directories from `base` to `webhook` 

![excludesoulissdirs1](https://cloud.githubusercontent.com/assets/1191883/13630567/44f2e95e-e5e0-11e5-86c5-ecd7bb5fc4cd.png)

Then select from context menu *Resource Configuration*,  *Exlude from builds*, *Select all*, *OK*

Directories `base`, `bconf`, ... `webhook` should be grayed out:

![excludesoulissdirs2](https://cloud.githubusercontent.com/assets/1191883/13630568/451d9550-e5e0-11e5-83e5-d2ce478b8ccb.png)

## Compile (Verify) your sketch
* Press *Verify* button on toolbar

Sketch should build without errors (but with many warnings - it's normal) and you can upload it to board.
