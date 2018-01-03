---
title: Making Noise
category: Tutorials
order: 5
---
<script src="{{ "/scripts/p5.min.js" | prepend: site.baseurl }}"></script>
<script src="{{ "/scripts/p5.sound.js" | prepend: site.baseurl }}"></script>

<script>
var mic;

function setup() {
  var myCanvas = createCanvas(800, 200);
  myCanvas.parent('myContainer');
  mic = new p5.AudioIn();
  mic.start();
}

function draw() {
  background(0);
  var vol = mic.getLevel();
  fill(210, 50, 103);
  noStroke();
  var h = map(vol, 0, 1, 50, 800);
  ellipse(width/2, height/2, h, h);
}
</script>

<div class="container">
  <div id="myContainer"></div>
</div>

```js
var mic;

function setup() {
  var myCanvas = createCanvas(800, 200);
  myCanvas.parent('myContainer');
  mic = new p5.AudioIn();
  mic.start();
}

function draw() {
  background(0);
  var vol = mic.getLevel();
  fill(210, 50, 103);
  noStroke();
  var h = map(vol, 0, 1, 50, 800);
  ellipse(width/2, height/2, h, h);
}
```