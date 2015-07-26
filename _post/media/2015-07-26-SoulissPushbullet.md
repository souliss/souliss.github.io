---
layout: Tutorial
title: "Souliss and Pushbullet"
categories: media
excerpt: "This will make a Pushbullet Notification with SoulissApp"
ads: false
share: true
author: lesjaw
image:
  feature: 
  teaser: 
  credit: 
  creditlink: 
---


Hello..Soulisser

This tutorial will make your Souliss ON/OFF Output Timer/T11 typicals Node capable to send notification to Pushbullet.

In teory it will work on all Souliss board, as long as Souliss Node connected to internet, but this tested on ESP8266 only.

Create the T11 Node as Souliss example, you can find a lot of example at Souliss github for many different board.

Then we add codes into the Arduino sketch, first we got to declare ThingSpeak API and ThingSpeak server, add this in top of your sketch

```c
// ThingSpeak API
const char* apiKey = "Your ThingSpeak API key";
const char* serverTS = "api.thingspeak.com";
```

In your Souliss Node sketch you should have a code to read the pin state..

```c
 int inputState = digitalRead(RELAY);
          if (inputState != oldInputState){
              sendInputState(inputState);
              oldInputState = inputState;
          } 
```

Put above code in void loop(), don't forget to define oldInputState as bool in top of the sketch

```c
  bool oldInputState;
``` 

Then in void setup you also should have oldInputState value, it easy, add this code below in void setup()  

```c  
  oldInputState = !digitalRead(RELAY);
```  

Now the last thing we should do in the Arduino sketch is create a function of sendInputState, put this after void loop(){}

```c
  // send data to ThingSpeak.com
  void sendInputState(bool inputState){
    Serial.println(inputState); 
 
       WiFiClient client;
       if(!client.connect(serverTS,80)) {  //   "184.106.153.149" or api.thingspeak.com
          Serial.println("Connection Fail!");
        }
        else {
          String postStr = apiKey;
                 postStr +="&field1=";
                 postStr += String(inputState);
                 postStr += "\r\n";
 
                 client.print("POST /update HTTP/1.1\n");
                 client.print("Host: api.thingspeak.com\n");
                 client.print("Connection: close\n");
                 client.print("X-THINGSPEAKAPIKEY: "+apiKey+"\n");
                 client.print("Content-Type: application/x-www-form-urlencoded\n");
                 client.print("Content-Length: ");
                 client.print(postStr.length());
                 client.print("\n\n");
                 client.print(postStr);
                 Serial.println("Send Relay State to Thingspeak");
 
        }
  client.stop();
  Serial.println("Client to send Stoped");
  
}
```

Now we need to setup ThingSpeak Channel, ThingHTTP and React.. but first you will need Pushbullet token, so create pushbullet account, then create ThingSpeak account..

Steps :

- Create New Channel in ThingSpeak, name it as you wish, in my case "PushbulletTriggerKamar"

- Make sure you have one field, use field 1 and name it as "Relay State"

![tskamar](https://cloud.githubusercontent.com/assets/12625575/8894408/3aa2d5ac-33e0-11e5-817b-2a2f449b289c.PNG)

- Click APPS in ThingSpeak, and click ThingHTTP app, create new ThingHTTP, this will send http request to pushbullet if the Light ON, fill the field as the picture

![ts2](https://cloud.githubusercontent.com/assets/12625575/8893826/d39051e2-33ca-11e5-9600-716a0502995a.PNG)

- Create another ThingHTTP for the Light OFF, follow the picture below..

![ts3](https://cloud.githubusercontent.com/assets/12625575/8894038/7bd7f5e2-33d2-11e5-8a86-7691a5e38469.PNG)

You can change the text body to fit your need, but it must be in json format.. I suggest just change this line

` 
{"type": "note", "title": "IoT Message", "body": "Lampu Teras ON"}
`

into something like this :

` 
{"type": "note", "title": "Message from Home", "body": "LIGHT ON"}
` 

- Back to ThingSpeak APPS, now click React app, create new React, this will execute ThingHTTP is some condition meet.. we create a new React for Light ON

![ts4](https://cloud.githubusercontent.com/assets/12625575/8893846/a40e9eaa-33cb-11e5-9e30-f60f7544a95d.PNG)

- Last step, create another React for Light OFF

![ts5](https://cloud.githubusercontent.com/assets/12625575/8893852/c9309792-33cb-11e5-8dae-3713ddfaa0d4.PNG)

You are done, now everytime you pressing ON OFF button in SoulissApp you should get notification in Pushbullet..

![lastts](https://cloud.githubusercontent.com/assets/12625575/8894006/5a3d35ec-33d1-11e5-8a17-ba911328b059.PNG)


