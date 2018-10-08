# Portable Hacking Station RPI
Station to perform WiFi network audits, using Raspberry Pi Zero W and Raspberry Pi 3, with connection from the BT or Mobile Data cell phone.

# Table of contents
* [Introduction](#introduction)
* [Materials](#materials)
* [Bt Module](#bt-module)
* [Raspberry Setup](#raspberry-setup)
* [Where should I start?](#where-should-i-start)
* [Future Rollout](#future-rollout)
* [References](#references)

## Introduction:

In today's world, computer security is one of the main concerns of people and companies, but we are certainly exposed to attacks by black hat hackers, who only seek to do evil and use their skills to do wrong to companies, people or even you.

So it occurred to me that it would be incredible to be able to perform security tests of wireless networks through a simple system such as a raspberry, however one of the great disadvantages of these is the need to use display systems such as HDMI screens and keyboards to insert the commands.

In this case the project explains how to make a system based on a Raspberry Pi Zero W with a Bluetooth Serial or WiFi SSH to a Smartphone, so that it is possible to write the commands on the console using the Smartphone.

## Materials:

* Raspberry Pi Zero W.
* Sd Card (min 8 Gb).
* Bluetooth module HC-06 (or similar).
* OTG adapter.
* PCB Breadboard.
* Female Header.
* USB cable to MicroUSB.
* Arduino or TTL serial interface
* Smartphone.
    - Android supports Bt serial and WiFi ssh.
    - iPhone supports only WiFi ssh.
* Powerbank 5v.
(min 2000 MAh to ensure the card can turn on at least 2 hours).
* Any external network card, I use an AirLink101 (AWLL3028).

(check if it is compatible with the Arimon-ng library of Aircrack-ng)

    https://www.aircrack-ng.org/doku.php?id=en:compatible_cards
    
Note: Check compatibility of your network card so that it is able to enter monitor mode, if it is not possible you can not continue with the tutorial.

## Bt Module:

The first thing to do would be the module for bluetooth communication with the raspberry, for this we must first configure the name and baud rate of the bluetooth module to 115200 baud, since the raspberry uses this transmission speed.

* We connect the serial ttl to the module Rx to Tx(Green), Tx to Rx(White), Vcc to Vcc(Red) and GND to GND (Black).

<img src="https://image.ibb.co/heMdg9/BT.png" width="800">

* Once connected we open the serial monitor that we have installed for example Putty (https://www.putty.org/).

<img src="https://image.ibb.co/bwzsPU/Captura_de_pantalla_de_2018_10_08_02_38_40.png" width="800">

* Once we connect to the interface at 9600 baud (Default Baud Rate), we have to send the following commands to the bluetooth, all commands are sent in uppercase and without NL or CR.

    - AT (to confirm that the module is receiving the commands.)
        - Answer: OK
    - AT+NAMEdevicename (to confirm that the module is receiving the commands.)
        - Answer: OKsetname
    - AT+PINyourpin
        - Answer: OKSetpin
    - AT+BAUD8 (115200 Baud Rate)
        - Answer: OK115200

Since we finished these configuration, we will do this through the UART port that has the raspberry, as shown in the following diagram.

<br/>
<img src="http://habrastorage.org/getpro/habr/post_images/cb2/2d0/1a5/cb22d01a5de84cbaaad999919a8a04bf.jpg" width="800">
<br/>

I recommend that you make the circuit on a breadboard PCB, as shown in the following 2 images, this in order that the module can be transported without cables being disconnected by movement.

| Hc-06 Connection Diagram                                      | Underface                                    | Upperface                                |
|-------------------------------------------------------|-------------------------------------------------------|-------------------------------------------------------|
|<img src="https://image.ibb.co/jU3uop/Hack.png" width="280">|<img src="https://image.ibb.co/duX4op/IMG_8265.jpg" width="280">|<img src="https://image.ibb.co/fwStg9/IMG_8264.jpg" width="280">|
    
## Raspberry Setup:



