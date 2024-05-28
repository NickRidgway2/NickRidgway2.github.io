---
title: "Design Three"
date: 2024-05-28 00:00:00 +0800
categories: [Post 3]
tags: [Post 3]
---

# Design Three

![design one](https://github.com/NickRidgway2/NickRidgway2.github.io/assets/147518493/aab736a7-71df-49f2-b34d-06b70a00121c)

This design focuses on a creating a star. There is a constant movement, of the outside collapsing in on the core, then releasing back out. There are 3 inner, and 5 outer stars. These ‘stars’ are ellipses at the end of each colour ray. I like this design because it is both fun and unique. As it is constantly moving in a random state, it is never the same each time you look at it. Although the colours are nice, I want to change them in the next design to see the difference.

```
let outerAmount = 5;
let outerStars = [];

let innerAmount = 3;
let innerStars = [];

function setup() {
  createCanvas(600, 600);
  colorMode(HSB, 160, 100, 100);
  strokeWeight(50);

  for (let i = 0; i < outerAmount; i++) {
    outerStars.push(new Star(30, (TWO_PI / outerAmount) * i, -0.003));
  }

  for (let i = 0; i < innerAmount; i++) {
    innerStars.push(new Star(10, (TWO_PI / innerAmount) * i, 0.005));
  }
	
	describe('A colorful oscillating star.');
}

function draw() {
  background(10);

  translate(width / 2, height / 2);

  for (let star of outerStars) {
    star.update();
  }

  for (let star of innerStars) {
    star.update();
  }

  for (let [i, outStar] of outerStars.entries()) {
    for (let inStar of innerStars) {
      stroke((360 / outerStars.length) * i, 100, 100, 0.5);
      push();
      blendMode(SCREEN);
      line(outStar.x, outStar.y, inStar.x, inStar.y);
      pop();
    }
  }
}

class Star {
  constructor(initialR, a, delta) {
    this.initialR = initialR;
    this.a = a;
    this.delta = delta;
  }

  update() {
    this.a += this.delta;
    this.r = this.initialR * sin(this.a * 5) * 8 + this.initialR;
    this.x = this.r * cos(this.a);
    this.y = this.r * sin(this.a);
  }
}

```

Looking at the code, the four variables are initialised. In the function setup, the colour mode is set to HSB, resulting in an RGB effect. OuterStars has 5 stars, each spaced evenly around the circle with the initial radius being 30. On the other hand, InnterStars had 3 stars, each spaced evenly as well however with an initial radius of 10. Line 26 is used to move to the centre of the canvas. A nested loop is used to iterate over each pair of both outer and inner stars whilst drawing lines between them.

The star class is used to initialise a star with an initial radius. In addition, update is used to update the angle of the star and recalculate the position of the star.

![design two](https://github.com/NickRidgway2/NickRidgway2.github.io/assets/147518493/8abe7a2d-bcef-4bf3-af5f-c46caceb9c4c)

This design is identical to the first, however I have changed the colour. I was able to do this by changing the colourmode from HSB to HSB with additional values. This was a simple and easy adjustment, and I like the difference between the two designs.

![design 3](https://github.com/NickRidgway2/NickRidgway2.github.io/assets/147518493/e86c725d-299e-4155-8257-7f5b07d2e43a)


This design represents a much darker atmosphere. The star moves in a slower and less predictable pattern. As a result, this design in comparison to the first is very different and both represent different artistic styles.
