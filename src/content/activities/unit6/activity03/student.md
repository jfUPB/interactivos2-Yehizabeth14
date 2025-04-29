# Actividad 3

## inputs Extremos
### Escenario:

- El nivel de ruido del ambiente alcanza su máximo (restaurante muy bullicioso).

- No hay movimiento de cubiertos por parte de los comensales.

- El control remoto activa una escena especial.

### Comportamiento esperado del sistema:

- Se activa un modo de relajación visual y sonora (baja intensidad de proyecciones, música suave).

- Como no hay movimiento de cubiertos, los efectos visuales sobre los platos se mantienen estáticos o muy sutiles.

- La escena especial (por ejemplo, una criatura marina animada) aparece igual, pero con una atmósfera más calmada.

la falta total de movimiento podría hacer que la experiencia se sienta apagada. tendremos un estado de "mínima actividad" con movimientos suaves predeterminados para mantener algo de dinamismo.

## Cambio de Parámetro Interno
   
### Escenario:

- Se duplica la sensibilidad del sensor de movimiento de cubiertos, haciendo que pequeños movimientos generen efectos visuales máximos.

### Comportamiento esperado del sistema:

- Cualquier leve toque sobre los cubiertos activa una gran cantidad de partículas o animaciones en el plato.

- La atmósfera visual podría parecer demasiado caótica, incluso con interacción mínima.


 Esto rompe la escala natural de interacción → output.
 La solución sería usar una curva de sensibilidad más suave (exponencial o con umbrales por capas) para evitar respuestas desproporcionadas.

## Combinación de Inputs

### Escenario:

- Movimiento de cubiertos muy alto.

- Control remoto activado con escena “calma” (por ejemplo, atardecer en la playa).

### Comportamiento esperado del sistema:

Visuales de calma (colores cálidos, ondas suaves), pero agitación por las partículas que se generan con el movimiento.

Contraste entre el input individual (agitación) y el input general del evento (calma).


Podría usarse intencionalmente para representar una disonancia: “el comensal no está en sintonía con el momento grupal”.

## Falla de Input

### Escenario:

- El sensor de luz ambiental deja de enviar datos (desconexión o falla).

### Comportamiento esperado del sistema:

Si no hay un valor actualizado, el sistema podría quedarse congelado en su último estado de luz.
si el sistema espera un número y recibe null/undefined, puede lanzar errores o dejar de procesar.

Es necesario definir un estado por defecto o un valor de respaldo.
si no hay datos de luz, usar un valor medio por defecto y mostrar un pequeño indicador de “luz ambiental desactivada” solo al anfitrión.
