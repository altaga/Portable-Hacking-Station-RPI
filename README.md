# Portable-Hacking-Station-RPI
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

In this case the project explains how to make a system based on a Raspberry Pi Zero W with a bluetooth serial interface to a cell phone, so that it is possible to write the commands on the console using the cell phone.

## Materials:

* Raspberry Pi Zero W.
* Sd Card (min 8 Gb).
* Bluetooth module HC-06 (or similar).
* OTG adapter.
* PCB Breadboard.
* Female Header.
* USB cable to MicroUSB.
* Smartphone.
- Android supports Bt serial and WiFi ssh
- iPhone supports only WiFi ssh
* Powerbank 5v.
(min 2000 MAh to ensure the card can turn on at least 2 hours).
* Any external network card, I use an AirLink101 (AWLL3028).
(check if it is compatible with the Arimon-ng library of Aircrack-ng)
    ```
    https://www.aircrack-ng.org/doku.php?id=en:compatible_cards
    ```
    
Note: Check compatibility of your network card so that it is able to enter monitor mode, if it is not possible you can not continue with the tutorial.

## Bt Module:





