---
title: "Design Four"
date: 2024-05-28 00:00:00 +0800
categories: [Post 4]
tags: [Post 4]
---

# Design Four


![design one](https://github.com/NickRidgway2/NickRidgway2.github.io/assets/147518493/3c3d3ad1-c6c5-41a4-b892-fb86fdafd10d)

I like this design as it is very unique, and the user is able to interact with it by moving their mouse. The lower the mouse is to the bottom of the screen, the closer the points will appear. The design shows several bright colours, in a star field.

```
let victors = [];
let factor = 100;

function setup() {
  createCanvas(windowWidth, windowHeight);
  for (let i = 0; i < 500; i++) {
    victors[i] = createVector(
      random(-width * factor, width * factor),
      random(-height * factor, height * factor),
      random(width)
    );
  }
}

function draw() {
  background(0);

  translate(width / 2, height / 2);

  for (let v of victors) {
    let x = v.x / v.z;
    let y = v.y / v.z;
    let maxSize = map(mouseY, 0, height, 0, 50);
    let d = map(v.z, 0, width, maxSize, -5);

    fill(x, y, x * y, 2 * d);
    stroke(x, y, x * y);
    circle(x, y, d);
    arc(x, y, d, d, 0, PI + d / 2, PIE);
    
    
    v.z -= map(mouseX, 0, 400, -5, 5);
    if (v.z < 1) {
      v.x = random(-width * factor, width * factor);
      v.y = random(-height * factor, height * factor);
      v.z = random(width);
    }
  }
}
```

Looking at the code, we can see that the variables are declared, both victors and factor. Victor is an array containing objects representing the points. Factor is used to determine the starting position of the points. Each vector has their random coordinates distributed on the canvas. In addition, the z coordinate controls the depth of the point. Line 18 is used to move back to the centre of the canvas. The maxSize is used by mapping the Y position of the mouse, resulting in a range of circles, they will be larger when the mouse is lower. Line 32 is used to decrease the z value, resulting in the point moving towards the user. 

![design two](https://github.com/NickRidgway2/NickRidgway2.github.io/assets/147518493/46f7d322-a3a2-4423-9744-2fab4864c666)

I changed the value on line 32 from -5, 5 to -2, 2. This resulted in the colours being a solid colour when the mouse is moved to the bottom of the screen, however, remain normal otherwise.

![design Three](https://github.com/NickRidgway2/NickRidgway2.github.io/assets/147518493/03db8e5b-e402-4a69-b699-5dc6452fa310)


This design is identical to the first, however I have changed the colour. I was able to do this by changing the colourmode from HSB to HSB with additional values. This was a simple and easy adjustment, and I like the difference between the two designs.
