---
description: 'Firmware Setup - https://github.com/adrianjost/SmartLight-Firmware'
---

# device-setup

{% hint style="warning" %}
**PREREQUISITES**: you should already know how to programm the ESP8266-01 with the Arduino IDE
{% endhint %}

## Step 1 - Download the Firmware

You can find the latest firmware version in the [releases section](https://github.com/adrianjost/SmartLight-Firmware/releases) of the [github repository](https://github.com/adrianjost/SmartLight-Firmware).

{% hint style="info" %}
Firmware V3 is backwards compatible, but you can't use V1 with the Web-Client Version V3
{% endhint %}

## Step 2 - Flash Firmware

After downloading the firmware, open `./SmartLight-Firmware/SmartLight-Firmware.ino` with the Arduino IDE.

Make sure that your ESP8266-01 is connected to your PC and you choose the right **Flash Size with at least 128KB SPIFS** for your ESP8266-01.

#### Compile and Upload your Code.

## Step 3 - Setup

When you Power On the ESP8266-01 it tries \(for 5 minutes\) to connect to the saved WiFi Access Point. While doing so he is hosting his own Access Point called _"SmartLight - Setup"_. 

Connect to it with your PC or Smartphone and open the URL http://192.168.4.1. You can choose your WiFi there and can set up some other things like the type of LED-Strips you connected and what the hostname of the device in your WiFi should be.

After Saving your settings, the ESP8266-01 should restart and the connected light should light up blue. When the ESP8266-01 established a connection to the given WiFi he will turn off all the lights and waits for your commands.

