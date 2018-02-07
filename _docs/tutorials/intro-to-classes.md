---
title: Introduction to Classess
category: Tutorials
order: 7
---
<script src="{{ "/scripts/p5.min.js" | prepend: site.baseurl }}"></script>

### Classes

Classes are a way to encapsulate functionality within objects and a way to address object individually. Class allow us to flexibly put objects onto the screen and encapsulate functionality within those objects.

Here we have three balls, a blue yellow and green ball. Each ball is a product of the Ball class. We define the Ball class with our own variables and functionalities. That's to say that instead of using pre-made object like rect or ellipse, we're creating our own.

```js
let ball1;
let ball2;
let ball3;

function setup() {
  createCanvas(800, 400);
  ball1 = new Ball(100, 100, 40, 40, "blue", 1);
  ball2 = new Ball(100, 200, 40, 40, "yellow", 3);
  ball3 = new Ball(100, 300, 40, 40, "green", 5);
}

function draw() {
  background(0);
  ball1.display();
  ball2.display();
  ball3.display();

  ball1.move();
  ball2.move();
  ball3.move();
}

class Ball{
    constructor(tempX, tempY, tempWidth, tempHeight, tempShade, tempSpeed){
        this.x = tempX;
        this.y = tempY;
        this.w = tempWidth;
        this.h = tempHeight;
        this.shade = tempShade;
        this.speed = tempSpeed;
    }

    display(){
        fill(this.shade);
        ellipse(this.x, this.y, this.w, this.h);
    }

    move(){
        this.x += this.speed;
        if(this.x > width){
            this.x = 0;
        }
    }
}
```
<div class="container">
  <div id="myContainer"></div>
</div>

<script>
let myContainer;
let ball1;
let ball2; 
let ball3;

function setup() {
  myContainer = createCanvas(800, 400);
  myContainer.parent("myContainer");
  ball1 = new Ball(100, 100, 40, 40, "blue", 1);
  ball2 = new Ball(100, 200, 40, 40, "yellow", 3);
  ball3 = new Ball(100, 300, 40, 40, "green", 5);
}

function draw() {
  background(0);

  ball1.display();
  ball2.display();
  ball3.display();

  ball1.move();
  ball2.move();
  ball3.move();
}

class Ball{
    constructor(tempX, tempY, tempWidth, tempHeight, tempShade, tempSpeed){
        this.x = tempX;
        this.y = tempY;
        this.w = tempWidth;
        this.h = tempHeight;
        this.shade = tempShade;
        this.speed = tempSpeed;
    }

    display(){
        fill(this.shade);
        ellipse(this.x, this.y, this.w, this.h);
    }

    move(){
        this.x += this.speed;
        if(this.x > width){
            this.x = 0;
        }
    }
}
</script>

