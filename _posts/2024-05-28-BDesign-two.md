---
title: "Design Two"
date: 2024-05-28 00:00:00 +0800
categories: [Post 2]
tags: [Post 2]
---

# Design Two

![design 1](https://github.com/NickRidgway2/NickRidgway2.github.io/assets/147518493/5a3ad1c1-b06d-4050-b8ab-a43ee457e866)

I created this design with the simple idea of having something incredibly basic, and seeing how much it can change, by using the same type of shapes. As a result, this is simply a black background with a white square positioned in the middle.

```
function setup() {
  createCanvas(400, 400);
  strokeWeight(5);
  stroke(255);
  }
  
function draw() {
  background(220);
  square(125, 100, 50, 200);
  }
```

The code here simply creates a white square at the location given. 

![design 2](https://github.com/NickRidgway2/NickRidgway2.github.io/assets/147518493/11226e88-1ad1-4ed6-9a7b-6c6c97921754)

Starting off, variables are declared including the minLineWidth, maxLineWidth and lineWidthChange. I decided to set the framerate to 1. In addition, line 15 is used to create a line width a random value between the minLineWidth and the maxLineWidth. I then decided to use a for loop to iterate the code. The code on line 17 is used to adjust the lineWidth by a random value.  Finally, the code on line 20 is used to draw a horizontal line centred on the canvas. This design is my favourite out of all four as it is the most well rounded and visually pleasing.

```
const minLineWidth = 0;
const maxLineWidth = 100;
let lineWidthChange = 10;

function setup() {
  createCanvas(300, 300);
  frameRate(1);
  strokeWeight(2);
  stroke(255);
}

function draw() {
  background(32);

  let lineWidth = random(minLineWidth, maxLineWidth);
  for(let lineY = 0; lineY < height; lineY++){
    lineWidth += random(-lineWidthChange, lineWidthChange);
    lineWidth = constrain(lineWidth, minLineWidth, maxLineWidth);

    line(width / 2 - lineWidth, lineY, width / 2 + lineWidth, lineY);
  }
}
```

![design three](https://github.com/NickRidgway2/NickRidgway2.github.io/assets/147518493/37b3c149-17c0-4bf6-b23e-5cb892e4c0c8)

Starting off, I adjusted the frame rate from 60 to 1. This means that it will refresh 60 times per second, rather than 1. Thus, making the lines appear 60 times quicker. I changed the +lineWidthChange to –. Although I’m not completely sure how it worked, it increased the size of the black margins and therefore made the centre white rectangle smaller. 

![design four](https://github.com/NickRidgway2/NickRidgway2.github.io/assets/147518493/31e28e86-17bc-40fc-8b3b-88964b83251e)

This time, I decided to make the design non-symmetrical. Shifting the white area to the left side. I was able to do this by change the width from being divided by 2 to 50 and the lineY width from 2 to 20 as well. Other than that, everything remained the same. 
