# Actividad 4

## Datos

- Nivel de ruido ambiental (como si hubiese un micrófono).

- Movimiento de comensales (como si hubiera sensores de movimiento).

- Estado de ánimo general (como si fuese un input emocional del público).

## Método de Simulación

### Ruido ambiental (simulado con noise()):

Uso noise() para generar cambios suaves.

Multiplico el valor por 100 para simular un “nivel de ruido” entre 0–100.

let ruido = noise(frameCount * 0.01) * 100;

Comportamiento esperado:

Cambios lentos y naturales, como si la sala tuviera variaciones leves en el ambiente.

### Movimiento de comensales (simulado con random() y picos):

Uso random(0, 1) pero con picos ocasionales para simular movimiento repentino.

Cada cierto tiempo agrego un valor alto para imitar un “evento” (alguien se para o se mueve mucho).

Comportamiento esperado:

Valores bajos la mayoría del tiempo, pero con subidas inesperadas.

### Estado de ánimo (control manual con slider):

Slider en pantalla para controlar de forma visual el "mood" del grupo.

Rango del slider: 0 a 1.

Comportamiento esperado:

Permite probar cómo cambia la experiencia si el “ánimo” es alto o bajo.

#### Activación / Desactivación
Creo una variable booleana usarSimulacion = true;
Con ella puedo encender o apagar los datos simulados fácilmente para luego conectar inputs reales.

