# Actividad 2

## ¿Qué es p5LiveMedia?
Es una librería para p5.js que permite compartir audio, video, datos y hasta el canvas entre múltiples usuarios en tiempo real usando WebRTC. Es ideal para proyectos colaborativos e interactivos en red.

## ¿Qué posibilidades ofrece

Puedes:

Compartir video y audio entre navegadores (tipo videollamada).

Enviar datos personalizados (posiciones, eventos, etc).

Sincronizar el canvas para experiencias visuales compartidas.

## Ejemplo explorado (envío de datos):

Probé un sketch que manda coordenadas x y y cuando haces click o arrastras el mouse. Lo abrí dos veces y vi cómo los movimientos se reflejan en ambas ventanas. Súper útil para sincronizar visuales entre usuarios.

Consideraciones para implementar en mi proyecto:

Hay que crear una sala con un ID único (ej. "w83C-S6DU").

Los datos se envían como strings, así que uso JSON.stringify() y JSON.parse().

El evento on('data') permite reaccionar cuando otro usuario manda algo.

Ideal para conectar los inputs del host y los comensales en tiempo real.
