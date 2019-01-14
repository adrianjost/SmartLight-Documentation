---
description: 'Build the Hardware - https://github.com/adrianjost/SmartLight-Hardware'
---

# build the Hardware

## Get the PCB

At first, you need the base PCB. You can find all plans needed here: [https://github.com/adrianjost/SmartLight-Hardware](https://github.com/adrianjost/SmartLight-Hardware)

I have ordered mine directly at [EasyEDA.com](https://easyeda.com).

![schematic](../.gitbook/assets/image.png)

![pcb](../.gitbook/assets/image%20%281%29.png)

## Assemble the PCB

The PCB itself is designed to be as modular as possible so you will most likely not need all the components.

### What you will definitely need:

1. **Connection for the power supply  \(must supply the same voltage that your led stripes need!\)** __You can choose one of the following options:
   1. micro-USB Port
   2. a classic 2.1mm Barrell Jack **\(wrongly connected in V1 of the PCB so you can't use it directly\)**
   3. 2 Pin Header Connector
2. **INPUT Voltage --&gt; 3V Converter** I used the [LD1117v33 ](https://www.conrad.de/de/spannungsregler-linear-typ78-stmicroelectronics-ld1117v33-to-220-positiv-fest-33-v-800-ma-147028.html)in a  TO-220-3 Package.
   1. According to the [Datasheet](http://www.produktinfo.conrad.com/datenblaetter/125000-149999/147028-da-01-en-LD1117V33_Spannungswandler_Datenbaltt.pdf) you also need 2 Capacitors C1: 100nF C2: 10uF
3. **Reset Button \(K1\) \(wrongly connected in PVB V1  so it won't work\)**
4. **Socket for ESP8266-01** \(2x4 Female Header Pins\)
5. **ESP8266-01** \( I recommend the black version with 1MB of Flash\)

Depending of the type of Strips you wan't to connect you need:

### + NeoPixel or other Stripes with _OneWire-Protocol_

The only additional thing you need is a Plug for CONN1 where you can connect your led stripes to.

### + cheap analog controllable RGB Stripes

The right part of the PCB is designed to be plugged underneath the left base pcb. You can place 3 MOSFETS \(one per channel\) to be able to control the 12V Strips with the 3V the ESP8266-01 outputs. Additionaly you need some male & female PIN Headers to connect both pcbs. \(or you could use some wires as well\)

