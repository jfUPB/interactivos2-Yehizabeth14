# Actividad 16

### Logros: ¿Qué he aprendido?
En esta unidad, he profundizado en la generación de gráficos y sonido en tiempo real con p5.js y p5.sound, además de explorar la manipulación de imágenes y la interacción con sensores del micro:bit. Algunos logros específicos incluyen:

-  Generación de formas geométricas aleatorias, experimentando con colores, posiciones y tamaños.
-  Manipulación de imágenes en p5.js, aplicando efectos visuales interactivos basados en la posición del mouse.
-  Uso de p5.sound para crear sonidos dinámicos, explorando diferentes tipos de onda (senoidal, triangular, cuadrada, sierra) y ajustando parámetros en tiempo real.
- Integración de datos del micro:bit con p5.js, estableciendo comunicación y utilizando sensores para modificar gráficos y sonidos.

Estos aprendizajes han sido fundamentales para avanzar en el desarrollo de una experiencia interactiva generativa en tiempo real, alineada con los objetivos del curso.

### Dificultades y cómo las he superado

1. Comunicación entre el micro:bit y p5.js

Problema: Al principio, hubo dificultades en la transmisión de datos en serie entre el micro:bit y p5.js.
Solución: Probé diferentes enfoques, como usar ASCII y binario, y realicé pruebas para identificar cuál era más eficiente y estable.
2. Control de la latencia en visualizaciones interactivas

Problema: Al trabajar con sistemas de partículas y manipulación de imágenes, noté que el rendimiento podía degradarse si la cantidad de elementos era demasiado alta.
Solución: Optimizé el código utilizando noLoop() cuando no era necesario redibujar constantemente y reduciendo la cantidad de píxeles procesados en cada frame.
3. Ruido en los datos del micro:bit

Problema: La información de los sensores (acelerómetro, luz) podía ser inestable, lo que generaba movimientos erráticos en las visualizaciones.
Solución: Implementé un suavizado de datos utilizando promedios móviles para reducir fluctuaciones.

### Áreas de mejora y próximos pasos

#### Optimización del rendimiento en sistemas de partículas

Seguir explorando estrategias para mejorar la eficiencia de los gráficos en tiempo real, como usar buffers de píxeles o limitar la cantidad de partículas activas.

#### Mejor integración entre sonido y gráficos

Profundizar en cómo los sonidos generativos pueden interactuar con elementos visuales de manera más orgánica, creando una experiencia multisensorial más inmersiva.

#### Exploración de nuevas técnicas de interacción

Investigar formas más avanzadas de interacción, como el uso de machine learning o reconocimiento de gestos para enriquecer la experiencia generativa.
