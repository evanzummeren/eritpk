---
title: Design Research: Work Journey [WIP]
date: "2019-09-07T18:14:14Z"
template: "post"
draft: false
slug: "/posts/work-journey"
category: "Design Research"
description: "If there is one question I dislike answering, then it's the question: What do you do? Working mostly as interaction designer and programmer, with an academic background in History and Journalism, it's often difficult to provide a clear answer. Calling myself a creative technologist does not make it much better."
socialImage: "/media/image-3.jpg"
---

## What do you do?

If there is one question I dislike answering, then it's the question: What do you do? Working mostly as interaction designer and programmer, with an academic background in History and Journalism, it's often difficult to provide a clear answer. Calling myself a creative technologist does not make it much better.

I feel that doctors and lawyers are in that sense rather lucky. The narratives they tell at parties are – although a little boring – clear and compelling. Not just in words, but also visually. I think the jobs that we aspire to do when we are children have a very similar quality. 

## The work journey

For the work journey I have been exploring a couple of different concepts (see notes for sketches). What I eventually found the most intr

I am curious towards the visual culture that are associated with these jobs. The ones we dream about as a kid are probably the ones that are visually quite intrueging. While the jobs we have difficulties explaining in words, are possibly also difficult to explain to images.

However, time is also an important part of the visuals. Just like the country someone is coming from. For instance an astronaut in the 60's (moon landing) has a different visual culture than one in the 80's (space shuttle). Just like a kosmonaut (a Russian astronaut) has very different visuals.

In a sense is that what we aspire to become, a storytelling trap that we fell into? The things that we aspire are the ones that might contain clear narratives and visuals.

## Creating the work journey
I want to create a video that shows the visual culture that are associated with the jobs that we do and that we aspire to become.
To do that I will do an automated Google Image search on the profession plus the year the person (e.g. fireman + 1995) was dreaming or actually doing this. I wrote a small script to make this a little easier. 

To make the emotions and actions of the people visible I want to record a small interview with both myself and the others and lay these on top of key moments.

### Work journey Katie

<iframe width="560" height="315" src="https://www.youtube.com/embed/wSQQpZftSm0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### My own work journey

<iframe width="560" height="315" src="https://www.youtube.com/embed/Pb0wHi-8hYk" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/wSQQpZftSm0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Step 1: Interviewing and filling in a spreadsheet
I tried to break up work/career journey is a couple of categories/questions to cover the entire:

* What did you want to become? [dreams]
* What did you do? [reality]
* What do you do? [reality]
* What do you want to do? [dreams]

### Step 2: Writing a script to perform the Google Image search
I will use Google Puppeteer for this.

### Step 3: Importing this stuff in After Effects

## Some discussions topics for the upcoming class


```javascript
"use strict";

const puppeteer = require('puppeteer');

module.exports = function(name, profession, year) {

  (async () => {
    const browser = await puppeteer.launch({
      headless: true,
      slowMo: 100
    });
    const page = await browser.newPage();
    await page.setViewport({
      width: 1920,
      height: 1080,
      deviceScaleFactor: 1,
    });

    const query = profession + '+' + year;
    await page.goto('https://www.google.com/search?q=' + query + '&sxsrf=ACYBGNSF8lP91SmxWUEmHhfu1E6nbKPUcQ:1567961726122&source=lnms&tbm=isch&sa=X&ved=0ahUKEwiovtPN2MHkAhWDbVAKHaABBrQQ_AUIEigB&biw=1680&bih=888');
    await page.keyboard.press('ArrowRight');

    for(var i = 0; i < 40; i++){
      await page.keyboard.down('Enter');
      await page.keyboard.press('ArrowRight');
      await page.screenshot({path: './screenshots/' + name + '/' + year + '_' + profession + '_' + i + '.png'}).catch(err => {console.log(err)});
    }

    await browser.close();
  })();

}
```

```javascript 
ffmpeg -framerate 1 -pattern_type glob -i '*.png' video_file.mp4
```

## Notes

Donec non enim in turpis pulvinar facilisis. Ut felis. Praesent dapibus, neque id cursus faucibus, tortor neque egestas augue, eu vulputate magna eros eu erat. Aliquam erat volutpat. Nam dui mi, tincidunt quis, accumsan porttitor, facilisis luctus, metus.

## Credits
[Piano Ticker](https://freesound.org/people/Jeanet_Henning/sounds/328910/) by [Jeanet Henning](https://freesound.org/people/Jeanet_Henning/), used under a Creative Commons license.

![Test SVG](/media/cpu.svg)
