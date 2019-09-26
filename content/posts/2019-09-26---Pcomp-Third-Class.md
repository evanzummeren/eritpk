---
title: Pcomp [w3] - Digital and analog
date: "2019-09-26T20:07:42+00:00"
template: "post"
draft: false
slug: "/posts/pcomp-third-class"
category: "Physical Computing"
tags:
  - "Notes"
  - "Semester 1"
description: "This week covered microcontrollers, analog inputs, digital inputs and outputs and some programming to make this all work together."
socialImage: "/media/image-3.jpg"
---

This week covered microcontrollers, analog inputs, digital inputs and outputs and some programming to make this all work together.

## Creating some kind of morse music box thing

I initially wanted to create a device that would play something when I typed in 'Erik' through morse code. (Yes, rather narcissistic). So I dug in some of the basics of morse code, and I soon found the right combinations to make it work. While coding this I got a speaker to imitate the noises. I found out that the Arduino nano only has 32 kb of flash drive, so a playing a wav-file would turn out difficult. Instead I went for the standard Arduino tone function, which allows for playing a tone on a certain frequency and duration. For instance a morse dot (.) is 100 ms, while a dash (-) is 300 ms. They all played on the same frequency (1000hz).

Because of some time pressure I later on decided to create a music box that could record a melody and play it back. I also wasn't able to completely finish this either.

<iframe width="560" height="315" src="https://www.youtube.com/embed/8kv10XvlBnQ" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Interactive technology in public spaces

For this assignment I went with the NYC Citibike. A piece of interactive technology in public. The Citibike *affords* people to get to a relatively close locattion by using a rental bike. This affordance is communicated/signified in the sense that all the bikes look the same, at the stations there are also many of the same bikes.

Most users that I watched seem to be very familiar with the system. In the time I watched the station there wasn't anyone who was not familiar with the system. For those that aren't familiar (or not a member) there is a 'box' next to the station which shows customers how to use the system. The level of interactivity is limited. If you use the mobile phone app you get a code which you can enter next to the bicycle. 

What appears to take long is to sometimes get the bike back in it's place. You have to give the right amount of pressure to get it in. I personally also noticed in the past that I thought it was in the rack, but that it wasn't placed well. They put in this pretty nice system where you get an app notification when the bike isn't docked well. Getting the bike out of the rack seems to be very fluidly, and often doesn't take longer than 15 seconds.

Crawford wise I would say the amount of interaction is limited. The system listens to a couple of integers. It speaks to me through the app, but also in rather limited ways, but also quite helpful such as the example I gave in the previous paragraph.