---
title: Working with API's
category: Tutorials
order: 12
---

<p>API's allow us to work with external data from other sources. Here's a quick script showing how to read in JSON data from JSON Placeholder (https://jsonplaceholder) </p>

<script src="{{ "/scripts/p5.min.js" | prepend: site.baseurl }}"></script>
<script>
var json;

function preload() {
  json = loadJSON('https://jsonplaceholder.typicode.com/posts');
}

function setup() {
  createCanvas(800, 800);

  // Load the XML document
  var title = json[0].title;
  var body = json[0].body;
  background(255);
  fill(0);
  text(String(title), 10, 10, 180, 190);
  text(String(body), 600, 10, 180, 190);
}
</script>