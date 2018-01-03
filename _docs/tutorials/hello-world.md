---
title: Hello World
category: Tutorials
order: 2
---

<p>A "Hello, World!" program is a computer program that outputs or displays "Hello, World!" to a user. Being a very simple program in most programming languages, it is often used to illustrate the basic syntax of a programming language for a working program.[1] It is often the very first program people write when they are new to a language.</p>

<script src="{{ "/scripts/p5.min.js" | prepend: site.baseurl }}"></script>
<script>
function setup(){
  var myCanvas = createCanvas(800, 200);
  myCanvas.parent('myContainer');
}


function draw(){

    background(0);
    fill(255);
    rectMode(CENTER);
    
    rect(410,100,50,50);

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

    background(0);
    fill(255);
    rectMode(CENTER);
    
    rect(410,100,50,50);

}
```