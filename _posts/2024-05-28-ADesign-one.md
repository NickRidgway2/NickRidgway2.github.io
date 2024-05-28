---
title: "Design One"
date: 2024-05-28 00:00:00 +0800
categories: [Post 1]
tags: [Post 1]
---

# Design One

![Design One](/assets/lib/FIRSTDESIGN.png)

This design potrays a total of 150 circles, all which remain static, until one is pressed. In the scenario that one is pressed, it will move in a random direction. Moreover, if a circle is pressed, whilst another circle is overlaying it, they will all move into random directions at the same time. The colour green is shown when hovering over the circle. This is the first design, showing a basic concept, however a poor overall colour scheme.

```
let clickBlobs=[] 
let numBlobs=150

function setup() {
  createCanvas(400, 400);
  for (let i=0; i<numBlobs; i++){
    clickBlobs.push(new ClickBlob (random(width), random (height), 50))
  }
}
  
function draw() {
  background(220);
  clickBlobs.forEach(function(blob){
    blob.update()
    blob.show()
  })
}

function mousePressed(){
  clickBlobs.forEach(function (blob){
    blob.click()
  })
}

class ClickBlob{
constructor(x,y,s){ 
  this.tx=x
  this.ty=y 
  this.x=x
  this.y=y
  this.s=s
  this.hover=true
}
                   
click(){
  if(this.hover){
    this.tx=random(width)
    this. ty=random(height)
  }
}
                   
show(){ 
  stroke(0)
  fill(128)
  if(this.hover){
    fill(0, 200, 100)
  }
  ellipse(this.x, this.y, this.s)
}

update(){
this.x+=(this.tx-this.x)/20
this.y+=(this.ty-this.y)/20
let d=dist(this.x, this.y, mouseX, mouseY) 
this.hover = d<this.s/2
  }
}
```

Looking at the code, we can see that we declare both clickBlobs and numBlobs. We create the canvas, then if i<numBlobs then one will be added. This is where the number 150 is relevant, as changing this would change the number of blobs. Next, we use clickBlobs to ensure that blobs are created at the size of 50 and all will be in random locations. The code blob.update is used to update the properties of blob. mousePressed is used as a function that is automaticalled called when the mouse is pressed. For each blob in the clickBlobs array calls the click method. The class name ClickBlob is defined and a constructor is used with three parameters, being x, y and s. The code is used to represent the coordinates of the blob. In addition, this.hover is set to true to determine the blob being in a hover state.

The code checks if the hover property of the blob is true, if it is true, it will set tx and ty to random values. If the blob is being hovered over, it will fill colour to green (0,200,100). The click function allows the blob to move to a random position. 

![Design Two](/assets/lib/design2.png)

In the second design, I decided to change the colour of the circle and background, as well as the numBlobs to 10. This changes the number of Blobs to 10, which is drastically less then the 150 in my previous design. In addition, I have changed this.x and this.y to be divided by 10 and 100 rather than 20. When clicked, the circle will continue to fall for an additional few seconds, in comparison to the previous values.

![Design Three](/assets/lib/design3.png)

I have changed the ellipses to squares, changing the size of them to 15 rather than 50. However, I kept the numBlobs to 150. Other than that, the design remains the same. However, it looks drastically different. This is primary because of the combination of the size, and shape.

![Design Four](/assets/lib/design4.png)

I decided to make a design similar, however change the number of numBlobs to 2 rather than 150. In addition, I changed the colour to black, rather than grey, or previous colours I have used in my designs. I like this design as it looks somewhat basic prior to being clicked, but once hovered over, it will turn green and once again move to a random location on the canvas. I believe this is my favourite design of all four.
