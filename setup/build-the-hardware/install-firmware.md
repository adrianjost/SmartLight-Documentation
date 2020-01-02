---
description: 'Firmware Setup - https://github.com/adrianjost/SmartLight-Firmware'
---

# Install Firmware

{% hint style="warning" %}
**PREREQUISITES**: you should already know how to programm the ESP8266-01 with the Arduino IDE
{% endhint %}

## Step 1 - Download the Firmware

You can find the latest firmware version in the [releases section](https://github.com/adrianjost/SmartLight-Firmware/releases) of the [github repository](https://github.com/adrianjost/SmartLight-Firmware).

{% hint style="info" %}
Firmware V3 only works with the Web Client V3. It is not backwards compatible.
{% endhint %}

## Step 2 - Connect the PCB to your Computer

Use the M0 connector to connect the PCB to your computer using a programmer.

## Step 3 - Flash Firmware

After downloading the firmware, open `./SmartLight-Firmware/SmartLight-Firmware.ino` with the Arduino IDE.

Make sure that your ESP8266-01 is connected to your PC and you choose the right **Flash Size with at least 128KB SPIFS** for your ESP8266-01.

![My flash config for an ESP8266-01 with 1MB of Flash Storage.](../../.gitbook/assets/image%20%289%29.png)

#### Compile and Upload your Code.

{% hint style="warning" %}
* Hold down both push buttons during the compile step in the Arduino IDE
* release the RESET Button as soon as the IDE say "Upload"
* release the FLASH Button as soon as the upload has started and you see a progress in percent in the IDE
{% endhint %}

{% hint style="info" %}
Sometimes it is required to power off/disconnect the ESP/Programmer just before you upload the firmware.
{% endhint %}

## Step 3 - Setup

When you Power On the ESP8266-01 it tries \(for 5 minutes\) to connect to the saved WiFi Access Point. While doing so he is hosting his own Access Point called _"SmartLight - Setup"_. 

Connect to it with your PC or Smartphone and open the URL http://192.168.4.1. The Password is _"LightItUp"_ You must choose your WiFi there and can set up some other things like the type of LED-Strips you connected and what the hostname of the device in your WiFi should be.

{% hint style="success" %}
Don't worry. If you ever want to change the config, restart the ESP and hold down the FLASH Button for &gt;0.5s in the first 5s after restart. This will force the setup mode and opens the SmartLight Setup Access Point.
{% endhint %}

After Saving your settings, the ESP8266-01 should restart and the connected light should light up blue. When the ESP8266-01 established a connection to the given WiFi he will turn off all the lights and waits for your commands.

