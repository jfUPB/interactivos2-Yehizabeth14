# Actividad 5

```
// P_2_2_6_01
//
// Generative Gestaltung – Creative Coding im Web
// ISBN: 978-3-87439-902-9, First Edition, Hermann Schmidt, Mainz, 2018
// Benedikt Groß, Hartmut Bohnacker, Julia Laub, Claudius Lazzeroni
// with contributions by Joey Lee and Niels Poldervaart
// Copyright 2018
//
// http://www.generative-gestaltung.de
//
// Licensed under the Apache License, Version 2.0 (the "License");
// you may not use this file except in compliance with the License.
// You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0
// Unless required by applicable law or agreed to in writing, software
// distributed under the License is distributed on an "AS IS" BASIS,
// WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
// See the License for the specific language governing permissions and
// limitations under the License.

/**
 * A chain of linked pendulums. Each a little shorter and faster than the one it's linked to.
 * Each joint of the pendulum leaves behind its own trail.
 *
 * KEYS
 * 1                   : toggle pendulum
 * 2                   : toggle pendulum path
 * -                   : decrease speed relation
 * +                   : increase speed relation
 * arrow down          : decrease length of lines
 * arrow up            : increase length of lines
 * arrow left          : decrease joints
 * arrow right         : increase joints
 * del, backspace      : clear screen
 * s                   : save png
 *
 * CONTRIBUTED BY
 * [Niels Poldervaart](http://NielsPoldervaart.nl)
 */
'use strict';

var shape;

var joints = 5;
var lineLength = 100;
var speedRelation = 2;
var center;
var pendulumPath;
var angle = 0;
var maxAngle = 360;
var speed;

var showPendulum = true;
var showPendulumPath = true;

function setup() {
  createCanvas(windowWidth, windowHeight);
  colorMode(HSB, 360, 100, 100, 100);
  noFill();
  strokeWeight(1);

  center = createVector(width / 2, height / 2);

  startDrawing();
}

function startDrawing() {
  pendulumPath = [];
  // new empty array for each joint
  for (var i = 0; i < joints; i++) {
    pendulumPath.push([]);
  }

  angle = 0;
  speed = (8 / pow(1.75, joints - 1) / pow(2, speedRelation - 1));
}

function draw() {
  background(0, 0, 100);

  angle += speed;

  // each frame, create new positions for each joint
  if (angle <= maxAngle + speed) {
    // start at the center position
    var pos = center.copy();

    for (var i = 0; i < joints; i++) {
      var a = angle * pow(speedRelation, i);
      if (i % 2 == 1) a = -a;
      var nextPos = p5.Vector.fromAngle(radians(a));
      nextPos.setMag((joints - i) / joints * lineLength);
      nextPos.add(pos);

      if (showPendulum) {
        noStroke();
        fill(0, 10);
        ellipse(pos.x, pos.y, 4, 4);
        noFill();
        stroke(0, 10);
        line(pos.x, pos.y, nextPos.x, nextPos.y);
      }

      pendulumPath[i].push(nextPos);
      pos = nextPos;
    }
  }

  // draw the path for each joint
  if (showPendulumPath) {
    strokeWeight(1.6);
    for (var i = 0; i < pendulumPath.length; i++) {
      var path = pendulumPath[i];

      beginShape();
      var hue = map(i, 0, joints, 120, 360);
      stroke(hue, 80, 60, 50);
      for (var j = 0; j < path.length; j++) {
        vertex(path[j].x, path[j].y);
      }
      endShape();
    }
  }
}

function keyPressed() {
  if (key == 's' || key == 'S') saveCanvas(gd.timestamp(), 'png');

  if (keyCode == DELETE || keyCode == BACKSPACE) startDrawing();

  if (keyCode == UP_ARROW) {
    lineLength += 2;
    startDrawing();
  }
  if (keyCode == DOWN_ARROW) {
    lineLength -= 2;
    startDrawing();
  }
  if (keyCode == LEFT_ARROW) {
    joints--;
    if (joints < 1) joints = 1;
    startDrawing();
  }
  if (keyCode == RIGHT_ARROW) {
    joints++;
    if (joints > 10) joints = 10;
    startDrawing();
  }

  if (key == '+') {
    speedRelation += 0.5;
    if (speedRelation > 5) speedRelation = 5;
    startDrawing();
  }
  if (key == '-') {
    speedRelation -= 0.5;
    if (speedRelation < 2) speedRelation = 2;
    startDrawing();
  }

  if (key == '1') showPendulum = !showPendulum;
  if (key == '2') showPendulumPath = !showPendulumPath;
}
```
## Descripción del Código
Este código en p5.js genera una simulación de un sistema de péndulos encadenados. Cada péndulo está conectado al anterior, es ligeramente más corto y se mueve a una velocidad diferente en función de un factor de relación de velocidad. A medida que se mueven, los extremos de los péndulos dejan un rastro visual, creando patrones dinámicos y atractivos.

Parámetros Clave
joints: Número de péndulos en la cadena.
lineLength: Longitud de cada segmento del péndulo.
speedRelation: Relación de velocidad entre los péndulos sucesivos.
showPendulum: Alterna la visualización del péndulo.
showPendulumPath: Alterna la visualización de los rastros de los péndulos.

## Variacion 1
Variación con Mayor Número de Péndulos y Longitud Reducida

### Modificaciones:

Aumentar joints a 10.

Reducir lineLength a 50.

Mantener speedRelation en 2.

### Efecto:
Se generan trazos más intrincados y densos debido a la mayor cantidad de péndulos. Como la longitud de cada segmento es menor, el patrón es más compacto y detallado.

### Aplicación Potencial:
Este efecto podría usarse en fondos animados para videojuegos o en experiencias interactivas donde los jugadores puedan influir en los patrones generados.

## Variacion 2
Variación con Menos Péndulos y Mayor Velocidad Relativa

### Modificaciones:

Reducir joints a 3.

Mantener lineLength en 100.

Aumentar speedRelation a 4.

### Efecto:
Se crean patrones más amplios y dinámicos con trazos más espaciados. El movimiento es más pronunciado, generando curvas amplias y fluidas.

### Aplicación Potencial:
Esta variación podría usarse en instalaciones visuales interactivas, donde el movimiento del usuario controle parámetros como la velocidad o la dirección de los péndulos, creando una experiencia inmersiva.
