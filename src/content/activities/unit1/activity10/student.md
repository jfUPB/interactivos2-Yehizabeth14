# Actividad 10

### Ejemplo a deconstruir

```
'use strict';

var segmentCount = 360;
var radius = 300;

function setup() {
  createCanvas(800, 800);
  noStroke();
}

function draw() {
  colorMode(HSB, 360, width, height);
  background(360, 0, height);

  var angleStep = 360 / segmentCount;

  beginShape(TRIANGLE_FAN);
  vertex(width / 2, height / 2);

  for (var angle = 0; angle <= 360; angle += angleStep) {
    var vx = width / 2 + cos(radians(angle)) * radius;
    var vy = height / 2 + sin(radians(angle)) * radius;
    vertex(vx, vy);
    fill(angle, mouseX, mouseY);
  }

  endShape();
}

function keyPressed() {
  if (key == 's' || key == 'S') saveCanvas(gd.timestamp(), 'png');

  switch (key) {
  case '1':
    segmentCount = 360;
    break;
  case '2':
    segmentCount = 45;
    break;
  case '3':
    segmentCount = 24;
    break;
  case '4':
    segmentCount = 12;
    break;
  case '5':
    segmentCount = 6;
    break;
  }
}
```

### Reconstruccion

```

function setup() {
  createCanvas(800, 800);


function draw() {
    colorMode(HSB, 360, width, height)
  background(360,0,height);
}

var segmentos = 360;
var radio = 300;

var angulos = 360/ segmentos

 beginShape(TRIANGLE_FAN);
  vertex(width / 2, height / 2);

  for (var angle = 0; angle <= 360; angle += angulos) {
    var vx = width / 2 + cos(radians(angle)) * radio;
    var vy = height / 2 + sin(radians(angle)) * radio;
    vertex(vx, vy);
    fill(angle, mouseX, mouseY);
  }

  endShape();

function keyPressed() {
  if (key == 's' || key == 'S') saveCanvas(gd.timestamp(), 'png');

  switch (key) {
  case '1':
    segmentos = 360;
    break;
  case '2':
    segmentos = 45;
    break;
  case '3':
    segmentos = 24;
    break;
  case '4':
    segmentos = 12;
    break;
  case '5':
    segmentos = 6;
    break;
  }
}
}
´´´
