# Actividad 7

## Reflexiona sobre el proceso de diseño:
- Lo más fácil fue definir los inputs porque ya tenía claro que usaría el acelerómetro, el touch de la mesa y el control del host. Ya estaban muy conectados con la idea central del proyecto, así que fluyó bien.
- Lo más retador fue conectar todo con el storytelling de manera clara. Tenía las ideas por separado, pero me costó integrarlas para que se sintiera como una experiencia narrativa y no solo hecha por hacer. Lo abordé volviendo al concepto base del proyecto y pensando en cómo cada input podía afectar emocional y simbólicamente la escena, no solo visualmente.
## Planifica los primeros pasos de implementacion

### Configurar el entorno básico de trabajo en p5.js
- Crea una carpeta de proyecto y dentro, los archivos index.html, sketch.js y style.css.

- En index.html, carga p5.js y p5LiveMedia (si planeas integrarlo desde el inicio o más adelante).

- En sketch.js, define las funciones básicas setup() y draw().

### Implementar simulación de los tres inputs

- En el acelerómetro crea valores que cambien suavemente con noise() para simular movimientos en X, Y y Z.
- En el touch de la mesa usa mousePressed() o mouseDragged() como input de contacto simulado.
- Control del host crea un slider o botones que simulen decisiones del host (modo, escena, etc).

### Implementar una primera visual básica conectando inputs

Crear un output visual que responda a cada uno de los inputs simulados.

Un conjunto de partículas o formas que:

- Se muevan con el "acelerómetro".

- Cambien color o tamaño al detectar "touch".

- Cambien de modo visual según el valor del control del host.
