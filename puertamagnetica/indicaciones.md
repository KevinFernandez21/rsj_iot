# 🧲 Puzzle: Puerta Magnética Activada por Imán

## 🎯 Objetivo del reto
Usar un imán oculto para activar un sensor magnético (reed switch) escondido dentro de una estructura. Al hacerlo correctamente, un LED se enciende y/o se activa un servomotor que desbloquea una puerta o tapa secreta.

---

## 🧰 Materiales

| Cantidad | Material                             |
|----------|--------------------------------------|
| 1        | Reed switch (sensor magnético)       |
| 1        | Imán de neodimio (botón o disco)     |
| 1        | Arduino UNO o Nano                   |
| 1        | Servo motor SG90 (micro servo 9g)    |
| 1        | LED verde (opcional)                 |
| 1        | Resistencia (220Ω para el LED)       |
| 1        | Zumbador activo (buzzer) (opcional)  |
| -        | Cables Dupont / jumper               |
| -        | Protoboard (opcional)                |
| -        | Cinta doble cara o silicona caliente |
| -        | Cartón, MDF o acrílico (estructura)  |
| -        | Bisagras o cinta para simular compuerta |

---

## 🛠️ Instrucciones de montaje

1. **Monta la estructura física**  
   Utiliza cartón o MDF para crear una compuerta o caja con una tapa que pueda abrirse. Instala el servo de modo que actúe como pestillo o traba.

2. **Instala el reed switch**  
   Pégalo oculto dentro del cartón o bajo una superficie del panel. El jugador no debe verlo. Prueba que detecte el imán desde una distancia razonable.

3. **Conecta los componentes al Arduino**  
   Cuando el imán se acerque al reed switch, se cerrará el circuito, lo que el Arduino detectará para activar un LED, buzzer o el servo.

---

## ⚡ Esquema de conexiones

| Elemento     | Arduino Pin     |
|--------------|-----------------|
| Reed Switch  | Digital 2 (y GND con pull-up interno) |
| LED + Resistencia | Digital 8 |
| Servo        | Digital 9       |
| Buzzer (opcional) | Digital 10 |

---

## 💡 Código Arduino

```cpp
#include <Servo.h>

const int reedPin = 2;
const int ledPin = 8;
const int buzzerPin = 10;
Servo puerta;

void setup() {
  pinMode(reedPin, INPUT_PULLUP);
  pinMode(ledPin, OUTPUT);
  pinMode(buzzerPin, OUTPUT);
  puerta.attach(9);
  puerta.write(0); // posición cerrada
}

void loop() {
  if (digitalRead(reedPin) == LOW) {
    digitalWrite(ledPin, HIGH);
    digitalWrite(buzzerPin, HIGH);
    puerta.write(90); // abre la traba
    delay(1000);
    digitalWrite(buzzerPin, LOW);
  } else {
    digitalWrite(ledPin, LOW);
    puerta.write(0); // permanece cerrada
  }
}
