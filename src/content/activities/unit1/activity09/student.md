# Actividad 9

```
function setup() {
  createCanvas(600, 600);
  noLoop(); // Se puede comentar si quieres animación continua
}

function draw() {
  background(30);
  
  for (let i = 0; i < 20; i++) { // Dibujar 20 formas aleatorias
    let x = random(width);
    let y = random(height);
    let size = random(30, 100);
    let col = color(random(255), random(255), random(255), random(100, 255));
    
    fill(col);
    noStroke();
    
    let shapeType = int(random(3)); // Elegir entre 0, 1 o 2
    
    if (shapeType === 0) {
      ellipse(x, y, size, size); // Círculo
    } else if (shapeType === 1) {
      rect(x, y, size, size); // Cuadrado
    } else {
      triangle(
        x, y - size / 2,
        x - size / 2, y + size / 2,
        x + size / 2, y + size / 2
      ); // Triángulo
    }
  }
}

function mousePressed() {
  redraw(); // Genera nuevas formas al hacer clic
}
```
![image](https://github.com/user-attachments/assets/dbe5b595-b0f5-4410-b811-869c2cd88a49)

