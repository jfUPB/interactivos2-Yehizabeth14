# Actividad 6
## Servidor (server.js)

```
const express = require('express');
const http = require('http');
const socketIO = require('socket.io');

const app = express();
const server = http.createServer(app);
const io = socketIO(server);
const port = 3000;

app.use(express.static('public'));

io.on('connection', (socket) => {
    console.log('New client connected');

    socket.on('message', (message) => {
        console.log(`Received message => ${message}`);
        socket.broadcast.emit('message', message);
    });

    socket.on('image', (imgData) => {
        console.log('Received an image');
        socket.broadcast.emit('image', imgData);
    });

    socket.on('disconnect', () => {
        console.log('Client disconnected');
    });
});

server.listen(port, () => {
    console.log(`Server is listening on http://localhost:${port}`);
});

```

## Cliente Desktop (p5.js)


```
let socket;
let circleX = 200;
let circleY = 200;
let receivedImg = null;

function setup() {
    createCanvas(400, 400);
    background(220);

    socket = io('https://obscure-space-guacamole-q5pg4q75rppcxqj-3000.app.github.dev/');

    socket.on('connect', () => console.log('Connected to server'));

    socket.on('message', (data) => {
        let parsedData = JSON.parse(data);
        if (parsedData.type === 'touch') {
            circleX = parsedData.x;
            circleY = parsedData.y;
        }
    });

    socket.on('image', (imgData) => {
        receivedImg = loadImage(imgData);
    });

    socket.on('disconnect', () => console.log('Disconnected from server'));
    socket.on('connect_error', (error) => console.error('Socket.IO error:', error));
}

function draw() {
    background(220);
    if (receivedImg) {
        image(receivedImg, 0, 0, width, height);
    } else {
        fill(255, 0, 0);
        ellipse(circleX, circleY, 50, 50);
    }
}

```

## Cliente Mobile (p5.js + Cámara y Archivos)

```
let socket;
let lastTouchX = null;
let lastTouchY = null;
const threshold = 5;
let imgData = null;

function setup() {
    createCanvas(400, 400);
    background(220);

    socket = io('https://obscure-space-guacamole-q5pg4q75rppcxqj-3000.app.github.dev/');

    socket.on('connect', () => console.log('Connected to server'));
    socket.on('disconnect', () => console.log('Disconnected'));
    socket.on('connect_error', (error) => console.error('Socket.IO error:', error));

    createButton('Capturar imagen').position(10, height + 10).mousePressed(captureImage);
    createFileInput(handleFile).position(150, height + 10);
}

function draw() {
    background(220);
    textAlign(CENTER, CENTER);
    textSize(18);
    fill(0, 255, 0);
    text('Toca para mover el círculo\n o envía una imagen', width / 2, height / 2);
}

function touchMoved() {
    if (socket.connected) {
        let dx = abs(mouseX - lastTouchX);
        let dy = abs(mouseY - lastTouchY);
        if (dx > threshold || dy > threshold) {
            socket.emit('message', JSON.stringify({
                type: 'touch',
                x: mouseX,
                y: mouseY
            }));
            lastTouchX = mouseX;
            lastTouchY = mouseY;
        }
    }
    return false;
}

function captureImage() {
    let video = createCapture(VIDEO);
    video.size(400, 300);
    video.hide();

    setTimeout(() => {
        image(video, 0, 0, width, height);
        imgData = canvas.toDataURL();
        socket.emit('image', imgData);
        video.remove();
    }, 2000);
}

function handleFile(file) {
    if (file.type === 'image') {
        socket.emit('image', file.data);
    }
}
```


### ¿Cómo se comunican los clientes con el servidor?
Los clientes establecen una conexión persistente con el servidor mediante Socket.IO, que encapsula WebSockets. Esto les permite intercambiar mensajes de manera bidireccional y en tiempo real.

### ¿Cómo se comunican los clientes entre sí?
No lo hacen directamente. En cambio, cada cliente se comunica con el servidor, que actúa como intermediario. Cuando un cliente envía una imagen o un evento táctil, el servidor lo retransmite a los demás usando socket.broadcast.emit().

### ¿Qué tipo de mensajes se envían?
Mensajes tipo JSON: contienen coordenadas (x, y) y tipo de evento ("touch").

Mensajes de imagen: cadenas codificadas en formato Base64 representando imágenes capturadas o cargadas.

### ¿Qué tipo de datos se envían?
Datos numéricos (coordenadas x, y)

Cadenas de texto largas (imágenes en base64)

Todos estos viajan encapsulados como texto dentro de eventos personalizados.

### ¿Qué tipo de eventos se generan?
connect: conexión al servidor

disconnect: desconexión

message: evento personalizado para coordenadas táctiles

image: evento personalizado para enviar/recibir imágenes

connect_error: error de conexión


### ¿Cómo es el flujo de datos entre los clientes?
La comunicación entre clientes es indirecta:

Cliente A realiza una acción (toca pantalla o envía imagen).

Cliente A emite el evento al servidor.

El servidor reenvía ese evento a los demás clientes (B, C, ...).

Los demás clientes procesan la imagen o mueven el círculo.

