# Activity 4
### Codigo
´´´
float angle = 0.0;
float xpos;
float ypos;
float scalar = 100;


void setup() {
  size(400, 400);
  background(15, 28, 45);
}

void draw() {

  float valorSeno = sin (angle);
  xpos++;
  ypos++;

  float grises = map(valorSeno, -1, 1, 200, 255);
  
  stroke(grises, 30);
  strokeWeight(random(1, 5));
  noFill();
  ellipse(xpos, ypos, random(1, 2)*scalar, random(1, 2)*scalar);

  if ((xpos > width+120) && (ypos > height+120)) {
    ypos = 0;
    xpos = 0;
  }

  scalar += 0.09;
  angle += 0.5;
}

´´´
### descripcion 

Este código en Processing genera un dibujo en el que un círculo se mueve a lo largo de la pantalla mientras cambia de tamaño y color en escala de grises. Los elementos generativos incluyen:

Formas: Se generan elipses de tamaños variables basadas en el valor de scalar.
Colores: Se usa la función map() para asignar tonos de gris en función del valor del seno de angle.
Movimiento: La posición (xpos, ypos) se incrementa con cada frame, creando un desplazamiento diagonal.
Variabilidad: Se utiliza random() para generar variaciones en el tamaño de los círculos y el grosor del trazo.

### Modificacion 1
Cambio en la dirección del movimiento
En lugar de que el círculo se desplace en diagonal (hacia la parte inferior derecha), lo hacemos moverse en una dirección más dinámica utilizando una combinación de cos() y sin().

Cambio en el código:

´´´
xpos += cos(angle) * 2;
ypos += sin(angle) * 2;
´´´

Efecto: Ahora las elipses se distribuyen en un patrón más fluido y circular, en lugar de una simple diagonal.

### Modificacion 2

´´´
  let r = map(sin(angle), -1, 1, 100, 255);
  let g = map(cos(angle), -1, 1, 50, 200);
  let b = map(sin(angle * 1.5), -1, 1, 150, 255);
  stroke(r, g, b, 90);
´´´

### aprendizaje

A través de esta exploración, he aprendido:

Cómo utilizar funciones trigonométricas (sin() y cos()) para generar movimientos más orgánicos.
La importancia de map() para transformar valores en rangos útiles dentro de la composición.
Cómo pequeños cambios en parámetros como el color y la dirección del movimiento pueden alterar radicalmente la percepción de la obra generativa.
Estos experimentos permiten una mayor personalización y exploración de patrones dinámicos en arte generativo. 🚀


