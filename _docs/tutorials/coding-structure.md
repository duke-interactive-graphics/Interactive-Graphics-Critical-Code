---
title: Javascript Structure
category: Tutorials
order: 6
---
<script src="{{ "/scripts/p5.min.js" | prepend: site.baseurl }}"></script>

### If Statement

If statements state that "if something (is equal, less-than, greater-than, true etc.)", execute the code inside the statement. For instance, in the statement below, if the mouses X position is greater than 400, draw a red rectangle.

```js
function setup() {
  createCanvas(800, 200);
}

function draw() {
  background(0);
  if(mouseX > 400){
      fill(255, 0, 0);
      rectMode(CENTER);
      rect(400, 100, 40, 40);
  }
}
```
<div class="container">
  <div id="myContainer"></div>
</div>

<script>
var t = function( p ){
    p.setup = function(){
     p.createCanvas(800, 200);
    }

    p.draw = function() {
    p.background(0);
    if(p.mouseX > 400){
        p.fill(255, 0, 0);
        p.rectMode(p.CENTER);
        p.rect(400, 100, 40, 40);
    }
  }
}
var myp5 = new p5(t, 'myContainer');
</script>



### If-Else Statement

If-else statements state that "if something (is equal, less-than, greater-than, true etc.)", execute the code inside the "if" statement brackets, otherwise, execute the code "else" statement brackets. For instance, in the statement below, if the mouses X position is less than than 50, draw a rectangle, otherwise, draw and ellipse.

```js
function setup(){
    createCanvas(800, 200)
}
function draw(){
    if (mouseX < 50){
        rect(300, 300, 20, 20);
    }else{
        ellipse(300, 300, 20, 20);
    }
}

```

<div class="container">
  <div id="otherContainer"></div>
</div>

<script>
var s = function( p ){
    p.setup = function() {
        p.createCanvas(800, 200);
    }

    p.draw = function(){
    p.background(0);
    if(p.mouseX > 400){
        p.fill(255, 0, 0);
        p.rectMode(p.CENTER);
        p.rect(400, 100, 40, 40);
    }else{
        p.fill(0, 0, 255);
        p.ellipseMode(p.CENTER);
        p.ellipse(400, 100, 40, 40);
    }
  }
}
var myp5 = new p5(s, 'otherContainer');
</script>

### For-Loop

For statements are a bit more obtuse, but if you follow the initial logic, everything should fall into place. For-loops work by "looping" over a variable, until that variable reaches a certain value. As you can see a for loop is comprised of three initial smaller statements: `var i=0; i < 255; i++`

Lets break down these statements so that we understand them individually.

 We'll start by defining a variable. Traditionally, this variable is "i", but ultimately it can be anything you want.  Here, we'll set an integer variable "i" equal to 0.
`var i=0`

The next two statements act much like an "if" statement. Here if "i" is less than 255, then "i++". What is `i++`? `i++` is a shortened syntax for "add 1 to the value" or i+1. So we're saying, "if i is less than 255, add 1 to i"
`i < 255; i++`

If we consider the for-loop below, we are starting with the variable "i" equalling zero, and the code inside of the for-loop will be executed every time until "i" is equal to or greater than 255.

So this for-loop will draw an ellipse 255 times. We can use the "i" variable to add some space between each ellipse by adding that i variable times whatever distance we would like (here 40px) and adding it to the x position of the ellipse.

```js
for (var i=0; i < 50; i++){
      ellipse(10+i*40, 300, 30, 30);
}
```

<div class="container">
  <div id="lastContainer"></div>
</div>

<script>
var r = function( p ){
    p.setup = function() {
        p.createCanvas(800, 200);
    }

    p.draw = function(){
        p.background(0);
        p.fill(255, 0, 0);
     for(var i=0; i < 50; i++){
        p.ellipse(10+i*40, 100, 40, 40);
     }
  }
}
var myp5 = new p5(r, 'lastContainer');
</script>

Similarly, we can "nest" for-loops inside of each other to iterate over them multiple times. Here we have two for-loops and we're iterating over an ellipse with both and shifting each on the x and y position.

```js
for (var i=0; i < 50; i++){
    for(var j=0; j < 50; j++){
      ellipse(10+i*40, 0+j*40, 30, 30);
    }
}
```

<div class="container">
  <div id="verylastContainer"></div>
</div>

<script>
var q = function( p ){
    p.setup = function() {
        p.createCanvas(800, 200);
    }

    p.draw = function(){
        p.background(0);
        p.fill(255, 0, 0);
     for(var i=0; i < 50; i++){
       for(var j=0; j < 50; j++){
        p.ellipse(10+(i*40), 0+(j*40), 40, 40);
       }
     }
  }
}
var myp5 = new p5(q, 'verylastContainer');
</script>


