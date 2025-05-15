# Actividad 4

## Inputs a Simular


Acelerómetro - movimiento general de la mesa (comensales)
Touch en la mesa	- Interacciones individuales de los comensales
Control del host	- Cambios globales de estado o ambiente visual


## Método de Simulación

### Acelerómetro
Tipo de dato: Número (float), por eje (x, y, z)

Rango esperado: -1.0 a 1.0 por eje

Método: noise() para cambios suaves y continuos

Implementación:

```
let ax = noise(t) * 2 - 1;
let ay = noise(t + 1000) * 2 - 1;
let az = noise(t + 2000) * 2 - 1;
t += 0.01;
```
Comportamiento buscado: fluctuaciones lentas y orgánicas, como si la mesa se moviera ligeramente por la actividad.

### Touch en la mesa
Tipo de dato: Coordenadas (x, y) + presión (0.0 a 1.0)

Método: interacción manual con el mouse + random() para picos de presión simulados

Implementación:

Simulación manual: usar mouseX, mouseY

Simulación automática:

```
let touchX = noise(t) * width;
let touchY = noise(t + 500) * height;
let pressure = random(0.2, 1.0);
```
Comportamiento buscado: eventos táctiles que cambian la visual cuando un comensal toca su área; se puede usar para generar formas o reacciones locales.

### Control del Host

Tipo de dato: Texto (modo: "calma", "intenso", "intermedio")

Método: Selector manual en pantalla (botones)

Implementación:

```
let modo = "intermedio"; // cambia con botón
```
Comportamiento buscado: define la atmósfera visual general (colores más vibrantes, cantidad de elementos, ritmo visual).


