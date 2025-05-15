# Actividad 2

## Inputs
| Fuente | Tipo de Dato	| Rango/Formato |	¿Simulación? | Conexión con el Storytelling  |
|-| - |-|-|-|
|Toque en pantalla (teléfono del comensal)| Texto / Comando | “mar”, “selva”, “desierto”, “italiano”, “japonés”… | no | Determina la temática del platillo y activa la ambientación correspondiente |
|  Movimiento de cubiertos (sensor IMU o acelerómetro) |	Número	0.0 - 1.0 (nivel de actividad)	| Sí (con valores aleatorios o sliders) |	Mide el nivel de interacción activa con el plato: gatilla cambios visuales en la mesa |
|Luz ambiental (sensor de luz)	| Número	0 - 1023 (intensidad de luz) |	Sí (sliders o simulación de día/noche)| Influye en la intensidad de proyecciones, simula el paso del día/noche|
| Control remoto del anfitrión |	Booleano / Selector	true/false o ID de escena |	No	 | Permite activar momentos clave: inicio del show, postre especial, etc.|
| Tiempo transcurrido desde el inicio |	Número |	Minutos/Segundos |	No| Define etapas de la experiencia (entrada, plato fuerte, postre…) |



## Algoritmo
1. Al iniciar, el comensal elige una temática (ej. "mar").

2.El sistema carga visuales, sonidos y colores asociados a esa temática.

### Durante la comida:

Si el movimiento de cubiertos aumenta, se generan visuales más dinámicos o con más partículas en la mesa.

Si la luz ambiental baja, se intensifican los brillos o la atmósfera cambia a nocturna.

El control remoto del anfitrión puede introducir sorpresas (una figura 3D de un pulpo en la temática marina, por ejemplo).

4. Cada cierto tiempo, se avanza de etapa: entrada, plato fuerte, postre, con transiciones visuales y sonoras.

5. Todo esto genera variaciones impredecibles pero coherentes: la experiencia nunca es idéntica, pero responde a los estímulos reales.

## Pseudocódigo básico:
```
SI input_tema CAMBIA:
   CARGAR ambientación visual y sonora según tema

SI movimiento_cubiertos > 0.5:
   AUMENTAR partículas / animaciones en la mesa

SI luz_ambiente < 300:
   CAMBIAR iluminación visual a modo nocturno

SI sonido_ambiente > umbral:
   DISMINUIR volumen general
   CAMBIAR música a tono relajado

SI control_remoto = true:
   ACTIVAR escena especial

CADA 10 minutos:
   TRANSICIÓN a siguiente etapa de la comida
  ```

## outputs

| Tipo | elemento	| propiedades dinamicas  | Conexión input |
|-| - |-|-|
| Visual	| Proyecciones sobre la mesa	| Formas, colores, animaciones, intensidad, velocidad	| Movimiento de cubiertos → más visuales en el plato |
| Visual | 	Elementos flotantes (mar, etc)| Opacidad, desplazamiento, aparición/desaparición	| Tema elegido → ambientación (olas, plantas, etc) |
| sonoro | Efectos sonoros especiales |	Activación por tiempo o control remoto	| Control remoto → sorpresa sonora (campanas, etc) |
| Luminotécnico |	Intensidad de luces proyectadas |	Brillo, color |	Luz ambiente → modo día/noche |
| Narrativo |	Cambios de escena	| Transiciones suaves o sorpresivas	| Tiempo o anfitrión → avanza la historia| 


