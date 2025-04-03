# Actividad 11

```
let words = [
  ["El viento", "La luna", "Un susurro", "La sombra", "Un recuerdo"],
  ["baila sobre", "ilumina", "acaricia", "oculta", "abraza"],
  ["las olas", "el bosque", "la niebla", "las estrellas", "el horizonte"],
  ["con un suspiro", "en la eternidad", "como un eco", "sin despedida", "en el olvido"]
];

let fontSizes = [24, 32, 40, 48];
let colors = ["#FFC857", "#E9724C", "#C5283D", "#255F85", "#481E14"];
let fonts = ["Georgia", "Arial", "Courier New", "Times New Roman", "Verdana"];

function setup() {
  createCanvas(600, 400);
  noLoop(); // Solo dibuja una vez
  generateText();
}

function draw() {}

function generateText() {
  background(30);
  
  let x = 50;
  let y = 80;
  
  for (let i = 0; i < words.length; i++) {
    let phrase = random(words[i]);
    let font = random(fonts);
    let fontSize = random(fontSizes);
    let col = random(colors);

    fill(col);
    textFont(font);
    textSize(fontSize);
    text(phrase, x, y);
    
    y += fontSize + 10;
  }
}

function mousePressed() {
  generateText();
}
```

![image](https://github.com/user-attachments/assets/6d732526-1039-4ec9-b71c-498ff8625f94)

