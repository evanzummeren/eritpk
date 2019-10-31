 –---
title: Pcomp final – IoT bouncing balls
date: "2019-10-31T20:07:42+00:00"
template: "post"
draft: false
slug: "/posts/pcomp-final-idea"
category: "Physical Computing"
tags:
  - "Notes"
  - "Semester 1"
description: "Creating interactive bouncing balls"
socialImage: "/media/image-3.jpg"
---
As a child I loved bouncing balls. They are incredibly simple, but their behaviour is at the same time rather unpredictable. There's a wide variety of bouncing balls. Colored ones, rainbow colored ones, ones with flickering lights, with figures etc. I'll be trying to make my own interactive bouncing balls. The idea is simple, every bounce sends out a signal (communicating either through Wifi or Bluetooth). And that signal results in a bigger 'interaction'. 

Because it sounds ridiculous, I would like to call them IoT bouncing balls.

## Creating my own
On the web I found a tutorial for making your own bouncing balls. All I needed was some luke warm water, cups, [Elmer's liquid school glue](https://www.amazon.com/gp/product/B072MHQ9PZ/ref=ppx_yo_dt_b_asin_title_o02_s00?ie=UTF8&psc=1) and [Borax](https://www.amazon.com/gp/product/B017DLHWEK/ref=ppx_yo_dt_b_asin_title_o01_s00?ie=UTF8&psc=1). The results we're so so.


<iframe width="560" height="315" src="https://www.youtube.com/embed/B5EYkTFEVyg" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Prototyping further/fabrication
I bought some extra bouncing balls (60mm) and I will probably cut them open and make them partially hollow on the inside. The production will by far be the most challenging part.

I've been thinking about the following setup: ESP32 MCU module, a LiPo battery and something that detects bounces (tilt sensor? fast vibration sensor?). 

The LiPo battery is what worries me the most, as it might not be the safest option.

![Components](/media/pcomp/iotball_components.png)

## Types of interactions
I've been thinking about a couple of ways on how to make them interactive:

* Two teams, red vs blue, team one has a ball. There's a LED lamp that is either red or blue. The more one team bounces the ball the more red or blue it becomes.
* Small powers/Big powers. One bounce is only a small gesture, but what if it results in something much bigger. Like turning the lights on and off?
* Each bounce is one word. There's a video playing on one screen, every bounce makes it play one more word.

I would like to explore some more options which involve time. 

Here's an early sketch:

![Sketch](/media/pcomp/iotball_sketches.png)
