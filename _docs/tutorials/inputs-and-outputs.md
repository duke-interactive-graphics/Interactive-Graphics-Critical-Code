---
title: Inputs and Outputs
category: Tutorials
order: 5
---

<script src="{{ "/scripts/p5.min.js" | prepend: site.baseurl }}"></script>
<script src="{{ "/scripts/p5.dom.js" | prepend: site.baseurl }}"></script>

<script>
function setup() {
  var myCanvas = createCanvas(800, 200);
  myCanvas.parent('myContainer');
  var form = createInput('');
  form.select('#blah');
  form.input(myInputEvent);
}

function draw(){
  myInputEvent();
}

function myInputEvent() {
  text('you are typing: ', this.value(), width/2, height/2);
}
</script>

<div class="input"></div>
<div class="container">
  <div id="myContainer"></div>
</div>



```js
function setup() {
  var myCanvas = createCanvas(800, 200);
  myCanvas.parent('myContainer');
  var form = createInput('');
  form.select('#blah');
  form.input(myInputEvent);
}

function myInputEvent() {
  text('you are typing: ', this.value(), width/2, height/2);
}
```