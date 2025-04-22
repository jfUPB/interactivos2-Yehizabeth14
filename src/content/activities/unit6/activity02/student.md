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
