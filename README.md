# 🚦 Traffic Light Control System using 555 Timer IC

A fully **hardware-based** traffic light control system built using dual **NE555 Timer ICs**, simulating the real-world Red → Green → Yellow → Red sequence — with no microcontroller and no code involved.

> Course Project | B.Tech Electronics & Computer Engineering | St. Joseph's College of Engineering & Technology, Palai | April 2025

---

## 📖 Overview

Traffic signals play a crucial role in regulating vehicle and pedestrian flow, ensuring safety and preventing accidents on the road. This project designs and constructs a functional traffic light system using two 555 Timer ICs configured in **astable mode**, where the first astable circuit powers the second — creating a self-sustaining, automated light sequence entirely through analog timing circuitry.

## ⚡ Working Principle

- Two astable 555 timer circuits are cascaded — the second 555 IC is powered only when the output of the first is ON.
- The **Red LED** turns ON only when the output of the first 555 IC is at 0V.
- The **Green LED** turns ON whenever the output of the second 555 IC is at positive voltage.
- The **Yellow LED** turns ON during the discharge phase of the second 555 IC.
- Immediately after power-on, the first IC's output is ON (since the trigger pin voltage is below 1/3 of supply voltage) — so the Red LED stays off initially while the Green LED turns on.
- As the capacitor of the second 555 IC charges past 2/3 of the supply voltage, and the first IC's capacitor reaches 2/3 before the second reaches 1/3, the Yellow LED briefly turns on before the Red LED activates.
- This charge-discharge cycle repeats continuously, producing the classic traffic light sequence.

## 🧰 Components Used

| Component | Specification | Purpose |
|---|---|---|
| NE555 Timer IC | ×2 | Astable oscillators for timing control |
| LEDs | 1 Red, 1 Yellow, 1 Green | Signal indicators |
| Resistors | 100KΩ, 47KΩ, 2×330Ω, 180Ω | Timing control & current limiting |
| Capacitors | 100µF ×2 | Charge/discharge timing elements |
| Breadboard / PCB | — | Circuit prototyping / permanent build |
| Jumper Wires | — | Breadboard connections |
| Power Supply | 5–12V | Circuit power source |

## 🔌 Circuit Diagram

The main circuit uses two NE555 ICs in astable configuration:
- **IC1** (100KΩ resistor, 100µF capacitor) → drives the Red LED and powers IC2
- **IC2** (47KΩ resistor, 100µF capacitor) → drives the Yellow and Green LEDs
- 330Ω resistors limit current to Red/Yellow LEDs; 180Ω resistor limits current to the Green LED

*(See `circuit-diagram.png` in this repo for the full schematic.)*

## 🧪 Result

The circuit was successfully simulated and tested, producing a repeating, synchronized Red–Green–Yellow–Red light sequence that mimics real-world traffic signal behavior — entirely through analog timer circuitry, without any digital programming.

## 🎯 Key Highlights

- ✅ 100% hardware-based — no microcontroller, no firmware
- ✅ Demonstrates astable multivibrator timing circuits
- ✅ Low-cost, beginner-friendly analog electronics build
- ✅ Adjustable timing via resistor/capacitor value changes

## 🔮 Future Enhancements

- Add pedestrian crossing signal integration
- Introduce adjustable timing via potentiometers
- Migrate to a microcontroller-based version (e.g., Arduino/ESP32) for programmable timing and IoT connectivity
- Design and etch a permanent PCB for durability

Department of Electronics & Computer Engineering, St. Joseph's College of Engineering & Technology, Palai (APJ Abdul Kalam Technological University)

## 📄 License

This project was developed as an academic course project and is shared for educational and portfolio purposes.
