# Actividad 15

### Relación entre los conceptos aprendidos y el problema del curso
En esta unidad hemos explorado la generación de gráficos y sonidos en tiempo real utilizando p5.js y p5.sound, además de la manipulación de imágenes y el uso de sensores con el micro:bit. Estos conceptos son fundamentales para el diseño de una experiencia interactiva generativa, ya que permiten crear un sistema dinámico que responde a la entrada del usuario en tiempo real.

El problema del curso se centra en diseñar una experiencia interactiva generativa que reaccione a los sensores del micro:bit, por lo que la manipulación de gráficos, sonidos y datos sensoriales es clave para construir una respuesta visual y auditiva envolvente.

### Aplicaciones Potenciales
Visualización de datos del micro:bit en tiempo real

Se pueden utilizar los sensores de acelerómetro, temperatura o luz del micro:bit para modificar parámetros visuales como color, tamaño y posición de partículas en una animación generativa.
Ejemplo: Un sistema de partículas que cambia de forma y color dependiendo de la inclinación del micro:bit.
Generación de sonido interactivo

Mediante p5.sound, se pueden generar tonos que respondan a la aceleración o posición del micro:bit, creando una experiencia audiovisual inmersiva.
Ejemplo: Un generador de música algorítmica donde el usuario controla la melodía moviendo el micro:bit.
Manipulación de imágenes y glitch art en tiempo real

La interacción con el micro:bit podría modificar una imagen en pantalla aplicando distorsión, filtros o efectos glitch basados en los datos del sensor.
Ejemplo: Un retrato interactivo donde la imagen se distorsiona más a medida que el usuario mueve el micro:bit.

### Herramientas y técnicas útiles
p5.js para visualización generativa

Es fundamental para crear gráficos dinámicos basados en la entrada del micro:bit. Permite dibujar formas geométricas, trabajar con partículas y manipular píxeles.
p5.sound para diseño sonoro interactivo

La capacidad de generar y modificar sonidos en tiempo real es clave para construir una experiencia multisensorial.
Serial communication entre p5.js y micro:bit

Para recibir datos del micro:bit y traducirlos en visualizaciones interactivas.
Mapeo de valores sensoriales a parámetros gráficos y sonoros

Usar map() en p5.js permite transformar valores de los sensores en frecuencia de sonido, intensidad de color o velocidad de partículas.
Limitaciones y Desafíos
Latencia en la comunicación

La transmisión de datos entre el micro:bit y p5.js podría tener cierto retraso, lo que afectaría la fluidez de la interacción.
Rendimiento gráfico en tiempo real

Si el sistema de partículas o la manipulación de imágenes es muy complejo, el rendimiento podría degradarse. Es importante optimizar el código.
Precisión y ruido en los sensores

Los datos del micro:bit pueden ser ruidosos o fluctuantes, lo que puede generar movimientos erráticos en la visualización. Se podría aplicar suavizado de datos.
