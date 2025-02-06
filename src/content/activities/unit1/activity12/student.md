# Actividad 12


```
let img;
let gridSize = 10; // Tamaño del efecto pixelado
let colorShift = { r: 0, g: 0, b: 0 }; // Modificación del color

function preload() {
  img = loadImage("https://upload.wikimedia.org/wikipedia/commons/thumb/3/3c/IMG_logo_%282017%29.svg/512px-IMG_logo_%282017%29.svg.png"); // Carga la imagen
}

function setup() {
  createCanvas(600, 400);
  img.resize(width, height); // Ajusta el tamaño de la imagen al canvas
  noLoop(); // Solo se dibuja cuando se detecta una interacción
}

function draw() {
  background(0);
  img.loadPixels();

  for (let y = 0; y < img.height; y += gridSize) {
    for (let x = 0; x < img.width; x += gridSize) {
      let index = (x + y * img.width) * 4;
      let r = img.pixels[index] + colorShift.r;
      let g = img.pixels[index + 1] + colorShift.g;
      let b = img.pixels[index + 2] + colorShift.b;

      // Asegurar que los valores se mantengan en el rango 0-255
      r = constrain(r, 0, 255);
      g = constrain(g, 0, 255);
      b = constrain(b, 0, 255);

      let d = dist(mouseX, mouseY, x, y);
      let maxDist = 100; // Rango de interacción

      let offsetX = 0;
      let offsetY = 0;

      if (d < maxDist) {
        let glitchStrength = map(d, 0, maxDist, 10, 0);
        offsetX = random(-glitchStrength, glitchStrength);
        offsetY = random(-glitchStrength, glitchStrength);
      }

      if (mouseIsPressed && d < maxDist) {
        r = 255 - r;
        g = 255 - g;
        b = 255 - b;
      }

      fill(r, g, b, 200);
      noStroke();
      rect(x + offsetX, y + offsetY, gridSize, gridSize);
    }
  }
}

function mouseMoved() {
  redraw(); // Redibuja la imagen cuando el mouse se mueve
}

function mousePressed() {
  redraw(); // Permite la inversión de colores al hacer clic
}

function keyPressed() {
  let step = 15;
  if (key === 'R') colorShift.r += step;
  if (key === 'r') colorShift.r -= step;
  if (key === 'G') colorShift.g += step;
  if (key === 'g') colorShift.g -= step;
  if (key === 'B') colorShift.b += step;
  if (key === 'b') colorShift.b -= step;

  redraw(); // Se actualiza el color al presionar teclas
}
```
