---
title: Hello World
category: Schedule
order: 1
---

![](//placehold.it/800x600)

<p>A "Hello, World!" program is a computer program that outputs or displays "Hello, World!" to a user. Being a very simple program in most programming languages, it is often used to illustrate the basic syntax of a programming language for a working program.[1] It is often the very first program people write when they are new to a language.</p>

//this should be an iframe

```
void setup(){

  size(820, 200);

}


void draw(){

    background(0);
    fill(255);
    rectMode(CENTER);
    
    rect(410,100,50,50);

}
```

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vitae ad enim impedit voluptatem adipisci, quos eius minus error illum odio tenetur labore exercitationem. Consectetur maiores atque deleniti, neque, praesentium consequuntur?

```
void setup(){

  float x = 100.0; 
  float y = 100; 
  float speed = 2.5; 

  size(820, 200);

}


void draw(){

    background(100);
    fill(1);

    x += speed; 

    if(x > width){
      x = 0; 
    }

    ellipse(x,y,50,50);

}
```