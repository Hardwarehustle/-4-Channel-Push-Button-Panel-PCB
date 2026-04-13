# 🔘 4-Channel Push Button Panel PCB

> **Designed by:** Janardhan BV  
> **Tool:** EasyEDA  
> **Rev:** 1.0 | **Date:** November 2024  
> **Connects To:** Dispenser Main Board (P1–P4 → A0–A3)

---

## 📌 Project Overview

This is a compact **4-channel tactile push button breakout panel** designed as a plug-in input sub-board. It houses four **6×6×6mm tactile push buttons** (RESET1–RESET4), each wired to a dedicated **JST B2B-XH-A-M 2-pin connector** (P1–P4), allowing the buttons to be remotely mounted on an enclosure panel and connected back to the main control board via JST XH cables.

The board maps directly to the **Dispenser Main Board** analog inputs:

| Button | Connector | Main Board Signal |
|:---:|:---:|:---:|
| RESET1 (A0) | P1 | Analog Input A0 |
| RESET2 (A1) | P2 | Analog Input A1 |
| RESET3 (A2) | P3 | Analog Input A2 |
| RESET4 (A3) | P4 | Analog Input A3 |

---

## 🖼️ Project Visuals

### Schematic
![Schematic](images/SCH.jpg)

### 3D Top View
![3D Top View](images/TopView.jpg)

---

## 📊 Component BOM

| Ref | Component | Part | Qty |
|:---:|:---|:---|:---:|
| RESET1–RESET4 | Tactile Push Button | 6.0×6.0×6.0mm | 4 |
| P1–P4 | JST Connector | B2B-XH-A-M (2-pin) | 4 |

---

## 🔌 Circuit Operation

Each button circuit is identical and straightforward:

```
JST Connector (P1–P4)
  Pin 1 ──────┬──── Button (RESET1–RESET4) ──── Pin 2 (GND)
  (Signal)    │
              └──── To Main Board (A0 / A1 / A2 / A3)
```

- **Button open:** Signal pin reads HIGH (pulled up on main board)
- **Button pressed:** Signal pin pulled to GND → MCU detects LOW = button press
- **Pull-up resistor** is provided on the main control board side (not on this sub-PCB)

---

## 📐 PCB Design Highlights

- **EDA Tool:** EasyEDA
- **Board Shape:** Compact rectangular with rounded corners and 2 mounting holes
- **Button Spacing:** Evenly spaced 4× buttons in a row labeled A0–A3
- **Connectors:** JST XH 2-pin (B2B-XH-A-M) on top edge — one per button
- **Mechanical:** 2 mounting holes for panel/enclosure mounting

---

## 🔗 Connection to Main Board (Dispenser PCB)

Plug each JST cable from this panel into the corresponding connector on the **Dispenser Main Board**:

```
Button Panel               Dispenser Main Board
──────────────             ───────────────────
P1 (2-pin JST) ──────────► P1 (A0, GND)
P2 (2-pin JST) ──────────► P2 (A1, GND)
P3 (2-pin JST) ──────────► P3 (A2, GND)
P4 (2-pin JST) ──────────► P4 (A3, GND)
```

---

## 🧪 Testing

1. **Continuity check** — Verify each button pin 1 (signal) to connector pin 1 with multimeter
2. **Press test** — With button pressed, verify continuity between signal and GND
3. **Integration test** — Plug into Dispenser board, read A0–A3 in firmware, confirm button press = LOW

---

## 📁 Repository Structure

```
Push-Button-Panel/
├── images/
│   ├── SCH.jpg          ← Schematic
│   └── TopView.jpg      ← 3D board render
├── Gerber/
└── README.md
```

---

## 🏷️ GitHub Topics

```
push-button  pcb-design  easyeda  tactile-switch  input-panel
jst-connector  breakout-board  embedded-hardware  sub-pcb
```

**GitHub About (1 line):**
> Compact 4-channel tactile push button panel PCB with JST XH connectors — plugs directly into the Dispenser main board analog inputs A0–A3.

---

## 📄 License

© 2024 Janardhan BV — Open for educational and personal use.

---

## 🙋 Author

**Janardhan BV** | Embedded Hardware Engineer  
📍 Bengaluru, India  
*Designed in EasyEDA*
