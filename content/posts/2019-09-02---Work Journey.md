---
title: Design Research - Work Journey
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

For my work journey I am curious towards the visual culture that are associated with these jobs. The ones we dream about as a kid are probably the ones that are visually quite intrueging. While the jobs that are difficult to explain in words, are possibly also difficult to explain to images.

However, time is also an important part of the visuals. Just like the country someone is coming from. For instance an astronaut in the 60's (moon landing) has a different visual culture than one in the 80's (space shuttle). Just like a kosmonaut (a Russian astronaut) has very different visuals.

For the work journey I created a video that shows the Google Images results for the work that we did or wanted to do in a specific year. For instance, if I wanted to become a policeman in 1995, I used the search query 'police man + 1995', or in a Dutch version: 'Politieagent + 1995')

To do this I made a spreadsheet that has a year and work column. I then exported it as a csv and wrote a node.js script (primarily using the puppeteer library) to do a for-loop based on the csv data. For every year the script 'navigated' through 40 different thumbnails and made a png screenshot of every view. I then stitched all these images together with ffmpeg. The next step was to import this in Adobe Premiere, change the FPS and do some final editing.

I made two videos, one of myself and one of my friend Katie. I did a seperate interview with Katie and put the audio tracks on top of her video. To add some extra drama I also put a soundtrack underneath it.

As usually I underestimated how much time this would cost, so I didn't have the time to put my own thoughts on my own video. Therefor I start with Katie her video, which is much more refined than mine.

### Work journey Katie

(There are some issues with the code which sometimes captures the same frame multiple times, therefor the timing seems to be off at times)

<iframe width="560" height="315" src="https://www.youtube.com/embed/wSQQpZftSm0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### My own work journey

<iframe width="560" height="315" src="https://www.youtube.com/embed/Pb0wHi-8hYk" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Technical stuff

Still a bit of a mess...
[Github repo](https://github.com/evanzummeren/designresearch-week2)

**Grab.js**
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
#!/usr/bin env node

"use strict";

const grab = require("./grab.js");
const csv = require('csvtojson');
const fs = require('fs');
const path = require('path');

var args = require("minimist")(process.argv.slice(2), {
    boolean: ['help'],
    string: ['file']
});

if (args.help) {
    printHelp();
} else if (args.file) {
    let filepath = path.resolve(args.file);
    processFile(filepath);
} else {
    error("Incorrect usage", true)
}

// ***************
function error(msg, includeHelp = false) {
    console.log(msg)
    if (includeHelp) {
        console.log('');
        printHelp();
    }
}

function printHelp() {
    console.log('index usage:');
    console.log('   index --help');
    console.log('');
    console.log('   --help                         print this help');
    console.log('   --file                         specify the file (csv)');
    console.log('');
}

function processFile(filepath) {

    fs.readFile(filepath, function onContents(err, contents){
        if (err) {
            error(err.toString());
        } else {
            processCsv(filepath);
        }
    })
}

function processCsv(filepath) {
    csv()
    .fromFile(filepath)
    .then((jsonObj)=>{
        jsonObj.forEach(function (careerYear, i) {
            setTimeout(function(){
                grab(careerYear.name, careerYear.profession, careerYear.year);
                // console.log(el);
            }, 60000 * (i + 1));
        });
    })
}
```

```javascript 
ffmpeg -framerate 1 -pattern_type glob -i '*.png' video_file.mp4
```

## Credits
[Piano Ticker](https://freesound.org/people/Jeanet_Henning/sounds/328910/) by [Jeanet Henning](https://freesound.org/people/Jeanet_Henning/), used under a Creative Commons license.
Google Puppeteer
