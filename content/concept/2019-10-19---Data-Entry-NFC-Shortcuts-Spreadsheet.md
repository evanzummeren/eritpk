---
title: Simple data entry with NFC stickers, iOS Shortcuts and Google Spreadsheet
date: "2019-10-19T20:07:42+00:00"
template: "post"
draft: false
slug: "/posts/data-entry-nfc-shortcuts-spreadsheet"
category: "General"
tags:
  - "Notes"
  - "Semester 1"
description: "This week me and Nicole started working on the Halloween midterm project. The idea is to build a shower that resembles the famous shower scene in Hitchcock's Psycho."
socialImage: "/media/image-3.jpg"
---
The new iOS introduced me to Shortcuts, an IFTTT like application that let's you connect several apps and built in iOS functionalies together. What's really cool is that in iOS 13 you can trigger a shortcut with a NFC sticker. The shortcut app also allows you to write to a REST API, which you can then use to write to a Google Spreadsheet table. In this post I'm describing how you can do simple forms of data entry with NFC stickers, iOS Shortcuts and Google Spreadsheet. What I really like about this solution is that everything is happening through the native iOS interface, which makes it really fast.

# How it works
While Googling I came across this [post](https://benjamincongdon.me/blog/2019/02/12/iOS-Shortcuts-for-Data-Capture) by Benjamin Congdon which shows to ways of entering data into Google Spreadsheets through shortcuts. The first one is by using IFTTT webhooks, which works but is limited by entering a maximum of 3 values per row. The other one he proposed is by writing some code and directly talk to the Google Sheets API. This one however requires some more time and coding knowledge.

The one I am proposing here is to use a Google Sheets API wrapper called SheetsDB. SheetsDB turns the Google Sheets API in a simple REST API which you can directly communicate with through Shortcuts. It's free if you make less than 500 request a month (which should work out for most cases).

You can get the NFC stickers through Amazon. Within Shortcuts you use *Get Contents of URL*. "meal": ""}

# A simple use case: tracking calorie intake
For all these years I was lucky that I could eat as much without gaining too much weight. However now I am almost hitting the 30 it turns out that you can actually gain weight by eating too much.  like tracking some of my own data – such as width, calorie intake – 


