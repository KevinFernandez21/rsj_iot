# 🔺 Puzzle: Simón Dice (9 LEDs - 9 Botones)

## 🎯 Objetivo del reto
El jugador debe repetir una secuencia de luces usando 9 botones que corresponden a 9 LEDs. Si acierta la secuencia, se activa una señal de éxito (LED extra, sonido o desbloqueo de otra pista). Si falla, la secuencia reinicia.

Este juego es ideal para Escape Rooms con temática tecnológica o de inteligencia artificial.

---

## 🧰 Materiales

| Cantidad | Material                      |
|----------|-------------------------------|
| 1        | Arduino UNO o Nano            |
| 9        | LEDs (colores variados o iguales) |
| 9        | Resistencias de 220Ω (para LEDs) |
| 9        | Botones pulsadores            |
| 9        | Resistencias de 10kΩ (para los botones) |
| 1        | Protoboard grande o dos medianas |
| -        | Cables Dupont / jumpers       |
| -        | Cartón o base para fijar LEDs y botones |
| 1        | Zumbador (opcional, para feedback) |

---

## 🛠️ Esquema de conexión

- **LEDs** conectados del pin 2 al 10.
- **Botones** conectados del pin A0 al A8 (puedes usar pines digitales si prefieres).
- Cada botón debe ir a GND con una resistencia **pull-down** de 10kΩ.
- Los LEDs deben ir en serie con una resistencia de 220Ω y a GND.

```text
[LEDs] —> Pin 2 al 10
[Botones] —> Pin A0 al A8 (o 11–19 si usas Mega o cambias la configuración)
