# Actividad 13

```
let osc;
let waveType = 'sine'; // Default waveform
let freqSlider, ampSlider;
let waveSelector;

function setup() {
  createCanvas(400, 200);
  textAlign(CENTER, CENTER);
  
  // Oscilador básico
  osc = new p5.Oscillator(waveType);
  osc.start();
  osc.amp(0.5);
  osc.freq(440);
  
  // Slider de frecuencia (20Hz - 2000Hz)
  freqSlider = createSlider(20, 2000, 440);
  freqSlider.position(20, 160);
  freqSlider.style('width', '150px');
  
  // Slider de amplitud (0 - 1)
  ampSlider = createSlider(0, 1, 0.5, 0.01);
  ampSlider.position(220, 160);
  ampSlider.style('width', '150px');
  
  // Selector de forma de onda
  waveSelector = createSelect();
  waveSelector.position(160, 20);
  waveSelector.option('sine');
  waveSelector.option('triangle');
  waveSelector.option('square');
  waveSelector.option('sawtooth');
  waveSelector.selected('sine');
  waveSelector.changed(changeWave);

```

