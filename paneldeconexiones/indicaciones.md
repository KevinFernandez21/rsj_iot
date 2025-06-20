# 🧩 Puzzle: Panel de Conexiones (Escape Room IA)

## 🎯 Objetivo del reto
Conectar correctamente los cables en un panel identificando los pares correctos (por color, símbolo o número). Al lograrlo, se activa un LED o un buzzer como señal de éxito. Forma parte del Escape Room: "Laboratorio Autónomo".

---

## 🧰 Materiales

| Cantidad | Material                        |
|----------|---------------------------------|
| 1        | Arduino UNO o Nano              |
| 1        | Protoboard (opcional)           |
| 4–6      | Borneras o conectores hembra    |
| 8–12     | Cables Dupont o de pinza        |
| 4–6      | Resistencias (220Ω – 10kΩ)      |
| 1        | LED verde                       |
| 1        | Buzzer (opcional)               |
| 1        | Cartón grueso o MDF (panel base)|
| -        | Pinturas o etiquetas de colores o símbolos |
| -        | Cinta doble cara / silicona     |

---

## 🛠️ Instrucciones de montaje

1. **Diseña el panel físico**  
   Usa cartón o MDF como base. Coloca conectores (borneras) en forma de fila o pareja. Haz etiquetas visibles en cada uno (ej: colores, números o símbolos).

2. **Distribuye los conectores en pares correctos**  
   Por ejemplo: 🔴 con 🔴, ⚡ con ⚡. Otros pares deben actuar como distractores. Por detrás, conecta los correctos al Arduino.

3. **Conecta el circuito eléctrico**  
   Cuando el jugador conecte el cable entre dos conectores correctos, se completa un circuito que Arduino detectará como "LOW".

---

## ⚡ Ejemplo de conexión básica

```text
(Panel frontal visible para el jugador)

 [🔴]   [🟢]   [🔵]   [⚪]
   |       |       |      |
--- Parte trasera del panel ---
   |       |       |      |
 Pin 2   Pin 3   Pin 4   GND (Arduino)

(LED conectado en el Pin 8 con resistencia a GND)
