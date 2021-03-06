---
title: Visualizing Data
category: Tutorials
order: 8
---

<p>Visualizing Data</p>

 <p>Here is what the CSV looks like:</p>

| x   | y   | diameter| name   |emotino     |
|-----|-----|---------|--------|------------|
| 160 | 103 | 43      | 19838  | Happy      |
| 372 | 137 | 52      | 42526  | Sad        |
| 273 | 235 | 61      | 14072  | Joyous     |
| 121 | 179 | 44      | 758068 | Melancholy |

```js
// An Array of Bubble objects
var bubbles;
// A Table object
var table;

function preload() {
  table = loadTable("data/data.csv", "header");
}

function setup() {
  createCanvas(480, 270);
  loadData();
}

function draw() {
  background(255);
  // Display all bubbles
  for (var i = 0; i < bubbles.length; i++) {
    bubbles[i].display();
    bubbles[i].rollover(mouseX, mouseY);
  }

}

function loadData() {
  // Load CSV file into a Table object
  // "header" option indicates the file has a header row

  // The size of the array of Bubble objects is determined by the total number of rows in the CSV
  bubbles = []; 

  // You can access iterate over all the rows in a table
  for (var i = 0; i < table.getRowCount(); i++) {
    var row = table.getRow(i);
    // You can access the fields via their column name (or index)
    var x = row.get("x");
    var y = row.get("y");
    var d = row.get("diameter");
    var n = row.get("name");
    // Make a Bubble object out of the data read
    bubbles[i] = new Bubble(x, y, d, n);
  }
}

class Bubble {
  constructor(x, y, diameter, s) {
    this.x = Number(x);
    this.y = Number(y);
    this.diameter = Number(diameter);
    this.name = s;
    this.over = false;
  }

  // Checking if mouse is over the Bubble
  rollover(px, py) {
    var d = dist(px, py, this.x, this.y);
    if (d < this.diameter/2) {
      this.over = true;
    } else {
      this.over = false;
    }
  }

  // Display the Bubble
  display() {
    stroke(0);
    strokeWeight(2);
    noFill();
    ellipse(this.x, this.y, this.diameter, this.diameter);
    if (this.over) {
      textAlign(CENTER);
      noStroke();
      fill(0);
      text(this.name, this.x, this.y + this.diameter/2 + 20);
    }
  }
}
```