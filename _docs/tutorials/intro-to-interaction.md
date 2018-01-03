---
title: Intro to Interaction
category: Tutorials
order: 4
---

<script src="{{ "/scripts/p5.min.js" | prepend: site.baseurl }}"></script>

<script>
function setup(){
  var myCanvas = createCanvas(800, 200);
  myCanvas.parent('myContainer');
  background(0);
}

function draw(){
  fill(random(0, 255), random(0, 255), random(0, 255));
  ellipse(mouseX,mouseY,50,50);
}
</script>

<div class="container">
  <div id="myContainer"></div>
</div>

```js

function setup(){
  createCanvas(800, 200);
}

function draw(){
  fill(random(0, 255), random(0, 255), random(0, 255));
  ellipse(mouseX,mouseY,50,50);
}
```