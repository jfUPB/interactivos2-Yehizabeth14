# Actividad 5

 ## Blueprint – Unidad 6
 
### Concepto
Cena interactiva donde los visuales reaccionan al movimiento (acelerómetro), al touch en la mesa y al control del host. Todo en tiempo real, todo inmersivo.

### Inputs

Acelerómetro: mide la energía en la mesa → visuales más intensos si hay mucho movimiento.
Simulado con noise() para cambios suaves.

Touch en mesa: genera visuales donde se toca.
Simulado con mouseX, mouseY, y random() para presión.

Control del host: decide el mood ("calma", "intenso", "intermedio").
Simulado con botones.

### Proceso
Lee los inputs → ajusta intensidad, color y cantidad de visuales.
El host guía el estilo general, el touch genera efectos locales, y el acelerómetro modula la energía total.

### Outputs
Visuales generativos: partículas, ondas, luces.

Cambian en tiempo real, se sienten vivos.

Cada cena es única porque todo reacciona al momento.

### Notas
Simulación activa con usarSimulacion = true.

Todo centrado en responder a la interacción humana.

Host dirige la experiencia como si fuera el DJ visual.
