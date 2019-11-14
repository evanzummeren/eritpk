---
title: Pcomp final - IoT bouncing balls WIP3
date: "2019-11-13T20:07:42+00:00"
template: "post"
draft: false
slug: "/posts/pcomp-final-wip-2"
category: "Physical Computing"
tags:
  - "Notes"
  - "Semester 1"
description: "The third week of working on some IoT bouncing balls"
socialImage: "/media/image-3.jpg"
---
In this second week I've been working on making some prototypes. I ordered some bouncing balls. Made them hollow on the inside and see if I could attach them to each other again. I also worked on teaching myself the very basics of Fusion 360 [https://www.youtube.com/channel/UCo29kn3d9ziFUZGZ50VKvWA](this is a great channel) and learn how to 3d print. I made 

## ESP32 W-room
I've been experimenting with the ESP32 board kit. I initially had some issues with the Arduino IDE not recognizing the USB serial port on a Mac, but I managed to fix this by installing the [USB to UART Bridge VCP drivers](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers).

## Serial port communication with Bluetooth and a Mac
There are several mobile apps available to communicate with the Bluetooth, however it turns out that serial communication with a Bluetooth device and a Mac terminal is actually quite easy [source](https://www.youtube.com/watch?v=0TzYDOIaDYA).

First you connect with the BT device like you would normally connect to power it on. Next you open the terminal and go to the dev folder with ```cd /dev```, there you find the name of the device. Next type in ```cat -v NAME_OF_THE_DEVICE```. You can send by ```echo -n -e '\xFE\x6C\x01' >  NAME_OF_THE_DEVICE```.

## Stuff that I still need to structure/Fabrication stuff
Apart from that I have also been doing a lot of research into the fabrication process, which remains the most difficult part of this project. I found this video of a guy working on 3d printed bouncing balls. Instead of PLA filament he uses TPU (Ninjatek Ninjaflex) which is much more elastic. Another important aspect of his video is the internal structure of the print.

I started experimenting with Meshmixer.

I have also been looking for ways to attach the two half balls with each othe

This weeks prototype still has a shell made of PLA. It contains the entire dev board and the LIS3DH. The power supply is still through the USB. The purpose for this prototype is to test the data that comes from the LIS3DH and to play test.

## Assignments
![Stuff](/media/pcomp/final/001.png)

[Bill of materials](https://docs.google.com/spreadsheets/d/1c_OfaC_WGtCPx2U4JoNNZVtHswnA67vDY4dKhqvmDu8/edit?usp=sharing)

