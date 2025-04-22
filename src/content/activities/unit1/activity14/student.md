# Actividad 14

## Prototipo 1 – Formas Aleatorias con Clic

### ¿Qué hace?
Este prototipo dibuja 20 formas (círculos, cuadrados o triángulos) en posiciones aleatorias cada vez que haces clic. Cada forma tiene un color y tamaño también aleatorio. Es como una especie de máquina de arte abstracto controlada por el mouse.

### Lo que salió bien
Es súper fácil de usar y entender: haces clic, ¡y listo! tienes una nueva composición.

La variedad en los colores y formas hace que siempre salga algo distinto, lo cual es muy divertido visualmente.

El código está limpio y es fácil de modificar si quiero añadir más formas o efectos.

### Lo que podría mejorar
A veces las formas se sobreponen o quedan muy juntas, y eso puede hacer que algunas composiciones se vean algo caóticas.

No hay animación, así que si no haces clic, no pasa nada. Podría tener una versión automática que cambie con el tiempo.

Le falta algo de control visual para que no sea demasiado aleatorio.

### Lo que aprendí

Jugar con la aleatoriedad puede ser muy creativo pero también algo impredecible.

Usar noLoop() con redraw() me ayudó a tener el control exacto de cuándo quiero que cambien las cosas.

Hacer algo interactivo no siempre requiere muchos botones ni complicaciones.

## Prototipo 2 – Rueda de color animada con segmentación

### ¿Qué hace?
Este prototipo crea una rueda de color (tipo mandala o flor) usando TRIANGLE_FAN. Puedes cambiar cuántos segmentos tiene la rueda con las teclas del 1 al 5, y los colores cambian con la posición del mouse. Muy visual y hipnótico.

### Lo que salió bien
 Usar HSB con mouseX y mouseY genera una rueda súper viva que reacciona al movimiento.

Los controles con el teclado permiten jugar con la forma muy fácilmente.

Da una sensación de visualización dinámica aunque en realidad no es una animación compleja.

### Lo que podría mejorar
No hay mucho feedback visual de qué tecla se presionó o en qué estado está, así que puede ser confuso si presionas varias sin notar diferencia.

Si no mueves el mouse, los colores se quedan planos. Tal vez podría animarse solo con el tiempo.

La función de guardar con "S" está bien, pero no todos saben que existe a menos que lo diga en pantalla.

### Lo que aprendí
TRIANGLE_FAN es genial para crear formas circulares con un centro definido.

La interacción con el teclado puede transformar un visual simple en algo mucho más flexible.

El sistema de color HSB es más intuitivo para generar gradientes coloridos que el RGB tradicional.

## Prototipo 3 – Generador de frases poéticas visuales

### ¿Qué hace?

Este prototipo genera frases poéticas a partir de palabras aleatorias agrupadas en diferentes listas. Cada frase aparece con una fuente, tamaño y color también aleatorio. Al hacer clic, se genera una nueva combinación de frases con un nuevo estilo visual. Es como un mini poema visual interactivo.

### Lo que salió bien

Las frases son evocadoras: Las combinaciones aleatorias dan resultados que a veces sorprenden o inspiran.

Visualmente tiene carácter: Los cambios de color, tipografía y tamaño le dan vida a algo que podría ser solo texto plano.

Súper simple de usar: Un clic y ya tienes un nuevo poema visual. Nada de complicaciones.

### Lo que podría mejorar

Algunas combinaciones pueden salir desbalanceadas visualmente, por ejemplo, si todas las frases tienen tamaños muy distintos o colores que no combinan tan bien.

A veces el texto se sale del lienzo si los tamaños son muy grandes o si la frase es muy larga. Se podría agregar ajuste de posición o tamaño máximo.

No hay animación ni transiciones suaves, por lo que los cambios se sienten un poco bruscos.

### Lo que aprendí

Es divertido mezclar texto con diseño visual usando cosas como fuentes, colores y tamaños aleatorios.

Usar arreglos de palabras es una forma simple pero poderosa de generar contenido único sin escribir demasiado.

La aleatoriedad puede ser una gran aliada creativa, pero necesita cierto control para mantener coherencia visual.



