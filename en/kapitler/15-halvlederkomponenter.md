# Chapter 15 — Semiconductor components

**Language:** [🇩🇰 Dansk](../../da/kapitler/15-halvlederkomponenter.md) · **🇬🇧 English** · [🇸🇦 العربية](../../ar/kapitler/15-halvlederkomponenter.md)

## 🎯 Learning goals

- Understand semiconductor materials (Si, Ge) and doping
- Know the diode, its characteristic and types
- Understand the transistor (BJT, FET)
- Know thyristor, triac and diac
- Understand applications in modern electronics

---

## 15.1 Semiconductor materials

**Semiconductors** have 4 valence electrons (group 14 of the periodic table):

| Element | Symbol | Use |
|---------|--------|-----|
| Silicon | Si | Almost all modern electronics |
| Germanium | Ge | Older transistors, RF |
| Gallium arsenide | GaAs | High-frequency, LEDs |

### The pure semiconductor (intrinsic)
At room temperature it is almost an insulator. With heat it becomes conductive — but not stable enough for practical use.

---

## 15.2 Doping

To make the semiconductor useful, **impurities** are added (doping):

### N-type (negative doping)
Add an element with **5 valence electrons** (e.g. phosphorus, antimony).
→ "extra" electrons = **free charge carriers**.

### P-type (positive doping)
Add an element with **3 valence electrons** (e.g. boron, indium).
→ "holes" (missing electron) = **positive charge carriers**.

> 💡 In N-type, electrons carry the current. In P-type, holes carry the current.

---

## 15.3 The PN junction — the diode

When P-type and N-type are joined, a **PN junction** is formed.

```
   ┌────────┬────────┐
   │   P    │    N   │
   │  + + + │ - - -  │
   └────────┴────────┘
        ↑
     Depletion layer (~0.01 mm)
```

### The depletion layer
At the boundary, electrons flow into the P-layer and holes into the N-layer. They **recombine** and leave a region without free charge carriers = the **depletion layer**.

### Forward biased (conducting)
- + on P-side, − on N-side
- Depletion layer shrinks → current flows
- The diode **conducts**
- Voltage drop: ~0.7 V (Si), ~0.3 V (Ge)

### Reverse biased (blocking)
- − on P-side, + on N-side
- Depletion layer grows → no current
- The diode **blocks**

> 💡 **The diode**: passes current in one direction only (from anode + to cathode −).

---

## 15.4 Diode characteristic

```
     I
     │      /
     │     /  Forward biased
     │    /
     │   /
─────┼──/────────  U
     │ │   ←─ ~0.7 V (Si)
     │ │
   ──┼─┘
     │ Reverse biased
     │ (small leakage current)
     │
   ──┼── ← breakdown voltage
     │
```

**Important values**:
- $U_F$ = forward voltage (~0.7 V)
- $U_R$ = reverse breakdown voltage (depends on type)
- $I_F$ = forward current (typically 100 mA – 100 A)

---

## 15.5 Diode types

| Type | Use |
|------|-----|
| Standard (rectifier) | Rectifying AC to DC |
| **Zener** | Voltage stabilisation — uses breakdown voltage deliberately |
| **LED** (light-emitting diode) | Light — Si-based + dopants give the colour |
| Schottky | Fast, small voltage drop (~0.3 V) |
| Photodiode | Generates current when exposed to light |
| Varicap | Variable capacitance with voltage |
| Tunnel diode | High-speed electronics |

### LED colours

| Material | Colour | $U_F$ |
|----------|--------|-------|
| GaAsP | Red | 1.8 V |
| GaP | Yellow/green | 2.0–2.2 V |
| InGaN | Blue/white | 3.0–3.3 V |

> 💡 **Calculating a series resistor for an LED**: $R = (U_{source} - U_F) / I_{LED}$

---

## 15.6 The transistor — BJT (Bipolar Junction Transistor)

Three semiconductor layers = **NPN** or **PNP** transistor.

```
   NPN:           PNP:

       C              C
       │              │
   B───┤              ├───B
       │              │
       E              E
```

### Three terminals
| Pin | Function |
|-----|----------|
| **Base (B)** | Control terminal — small current here controls a large current through C-E |
| **Collector (C)** | Main current input (NPN) |
| **Emitter (E)** | Main current output (NPN) |

### Current gain
$$\beta = h_{FE} = \frac{I_C}{I_B}$$

Typical: β = 50–500.

### Use
1. **Amplifier** — small signal amplified to a larger one
2. **Switch** — full ON/OFF — used as a digital switch

> ⚙ As a switch the transistor is operated between two states:
> - Saturation (ON): $V_{CE} \approx 0$ — fully conducting
> - Cut-off (OFF): $I_C \approx 0$ — blocking

---

## 15.7 FET (Field Effect Transistor)

Voltage-controlled — three terminals:
- **Gate (G)** — control terminal (high impedance)
- **Drain (D)** — main current input
- **Source (S)** — main current output

### Types

| Type | Abbrev. | Description |
|------|---------|-------------|
| JFET | J | Junction FET — analogue purposes |
| **MOSFET** | M | Metal-Oxide-Semiconductor — dominant in modern electronics |
| IGBT | — | Insulated Gate Bipolar Transistor — high power (motor control, VFDs) |

> 💡 **MOSFET** is the foundation of all modern microprocessors. Billions of MOSFETs on a single chip.

### MOSFET as power switch
Used heavily in modern power electronics:
- Solar inverters
- DC/DC converters
- Motor drives (together with IGBT)
- Switching power supplies (SMPS)

---

## 15.8 Thyristor

A **thyristor** (SCR — Silicon Controlled Rectifier) is a **controlled** rectifier with 4 layers (PNPN) and 3 terminals:
- **Anode (A)**
- **Cathode (K)**
- **Gate (G)** — trigger

### Operation
- Like a diode in the forward direction, but blocks **until** the gate is triggered
- When the gate gets a short current pulse, the thyristor **turns on**
- Stays on until the current falls to 0 (or polarity reverses)

> ⚙ Used in: motor control, light dimming (lamp dimmer), power regulation, surge handling.

---

## 15.9 Triac

A **triac** is like two anti-parallel thyristors in one component. Can control **AC** in both half-cycles.

Used in:
- Light dimmers (ordinary dimmers)
- Speed control of universal motors (drills)
- Heating control

---

## 15.10 Diac

A **diac** is a voltage-sensitive switch — typically used to trigger a triac/thyristor at a specific voltage level. Breakover voltage ~±30 V.

Used as a **trigger device** in triac control.

---

## 15.11 Integrated circuits (ICs)

An **IC** contains many transistors + other components on a single semiconductor chip.

| Generation | Number of transistors |
|------------|-----------------------|
| SSI (1960s) | ~10 |
| MSI | ~100 |
| LSI | ~1,000 |
| VLSI | ~100,000 |
| ULSI | millions |
| Modern CPU | billions |

### Common IC types
- **Operational amplifier** (op-amp) — e.g. LM741, LM358
- **Voltage regulator** — e.g. 7805, LM317
- **Logic ICs** — TTL, CMOS families
- **Microcontrollers** — Arduino, ESP32, PIC, STM32
- **Specials** — timer (555), DAC, ADC, motor drivers

---

## 15.12 Optocouplers

Two components in one package:
- LED + phototransistor separated by a glass window
- Galvanic **isolation** between input and output
- Used to couple low-voltage signals to high-voltage power circuits

> 🛡 Used heavily in PLC inputs and outputs (Siemens TIA Portal etc.) to protect the CPU from fault voltages from field sensors.

---

## 📌 Summary

- **Semiconductors** (Si, Ge): have 4 valence electrons. Adding impurities gives N-type (electron-conducting) and P-type (hole-conducting).
- **The diode (PN)**: passes current in one direction only — uses: AC-to-DC rectification.
- **The transistor (BJT)**: NPN or PNP, three terminals (B, C, E). Acts as amplifier or switch.
- **MOSFET**: today's most-used transistor — the foundation of every processor.
- **IGBT**: high-power transistor used in motor control and variable-frequency drives.
- **The thyristor**: controlled rectifier — triggered with a gate signal and stays on until the current is interrupted.
- **The triac**: like two reversed thyristors — controls AC in both directions.
- **The integrated circuit (IC)**: millions or billions of transistors on a single chip.

---

## ➡️ Next steps

- 📝 [Exercises for chapter 15](../opgaver/15-opgaver.md)
- ➡️ [Chapter 16 — Amplification](16-forstaerkning.md)
