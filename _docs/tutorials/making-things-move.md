---
title: Making Things Move
category: Tutorials
order: 3
---
<p>Making things move</p>

<script src="{{ "/scripts/p5.min.js" | prepend: site.baseurl }}"></script>

<script>
var x = 100.0; 
var y = 100; 
var speed = 2.5; 

function setup(){
  var myCanvas = createCanvas(800, 200);
  myCanvas.parent('myContainer');
}

function draw(){
  background(0);
  fill(1);

  x += speed; 

  if(x > width){
    x = 0; 
  }
  fill(210, 30, 140);
  ellipse(x,y,50,50);
}
</script>

<div class="container">
  <div id="myContainer"></div>
</div>

```js
var x = 100.0; 
var y = 100; 
var speed = 2.5; 

function setup(){
  createCanvas(800, 200);
}

function draw(){
  background(0);
  fill(1);

  x += speed; 

  if(x > width){
    x = 0; 
  }
  fill(210, 30, 140);
  ellipse(x,y,50,50);
}
```