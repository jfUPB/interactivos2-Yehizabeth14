# Actividad 4


## ¿Qué es WebRTC?
WebRTC (Web Real-Time Communication) es una tecnología que permite que dos o más navegadores se comuniquen directamente en tiempo real para compartir datos, audio o video sin necesidad de servidores intermedios para el contenido.

## ¿Cómo funciona WebRTC?
WebRTC establece una conexión directa entre navegadores, pero primero los navegadores necesitan “descubrirse” y “entender cómo hablar entre ellos”. Ese proceso de conexión necesita varios pasos y componentes clave (¡ya vamos a eso!).

## ¿Qué es un Peer Connection?
Es la conexión directa entre dos usuarios (peers). En tu app, cada comensal y el host están conectados como "peers" en la misma sala usando p5LiveMedia, que crea estas conexiones debajo del capó.

## ¿Qué es un Data Channel?
Es un canal que WebRTC usa para enviar datos (no audio ni video) entre los peers. En tu app, los toques o movimientos se envían por un data channel como JSON, y eso alimenta los visuales en tiempo real.

## ¿Qué es un Media Stream?
Es un canal para enviar audio y video. Aunque tu app usa solo datos por ahora, podrías extenderla para transmitir video del host o de los comensales usando esta funcionalidad.

## ¿Qué es un ICE Server?
ICE (Interactive Connectivity Establishment) es el protocolo que WebRTC usa para saber cómo conectar a los peers, incluso si están detrás de firewalls o routers.

## ¿Qué es un STUN Server?
Es un tipo de servidor ICE que ayuda a un peer a descubrir su dirección pública en internet. Es como “¡hey, así me ve el mundo!”. p5LiveMedia usa STUN por detrás para ayudarte a conectarte sin que tengas que hacer nada.

## ¿Qué es un TURN Server?
Es como un STUN, pero con esteroides. Si la conexión directa entre peers no funciona (por firewalls estrictos), TURN actúa como puente o relé. Más lento, pero confiable. Tu app con p5LiveMedia lo usaría si es necesario, pero es transparente para ti.

## ¿Qué es un Signaling Server?
Es el servidor que los peers usan al principio para intercambiar info y coordinar la conexión (como “yo soy fulano y tengo esta IP, ¿nos conectamos?”). p5LiveMedia tiene su propio signaling integrado para que no tengas que manejarlo tú.

## ¿Cómo todo esto aplica a tu app?
Cuando abres tu sketch con p5LiveMedia, este usa WebRTC.

Se conecta a un signaling server de p5LiveMedia para encontrar otros en la misma sala.

Usa peer connections para conectar entre host y comensales.

Usa data channels para mandar los toques, acelerómetros, o comandos.

Y si la red es complicada, WebRTC con STUN/TURN se encarga del resto.
