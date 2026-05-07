# Chapter 9 — Electrical fundamentals

**Language:** [🇩🇰 Dansk](../../da/kapitler/09-elektriske-grundbegreber.md) · **🇬🇧 English** · [🇸🇦 العربية](../../ar/kapitler/09-elektriske-grundbegreber.md)

## 🎯 Learning goals

- Understand what electricity is at the electron level
- Distinguish between direct current (DC) and alternating current (AC)
- Define voltage, current, resistance and power
- Read simple circuit diagrams
- Understand the safety risks of electricity

---

## 9.1 What is electricity?

The word **electricity** comes from the Greek word *elektron* = amber. It is a physical phenomenon related to **electric charges** — either at rest (electrostatics) or in motion (electrodynamics).

> 💡 **Electric current** = movement of electrons through a conductor.

### Ways to produce electricity

| Form | Principle | Example |
|------|-----------|---------|
| **Static** | Friction | Fur on glass |
| **Galvanic** | Chemical reaction | Battery |
| **Induced** | Electromagnetism | Generator, dynamo |
| **Photo** | Light | Solar cell |
| **Piezo** | Mechanical pressure | Lighter, sensor |
| **Thermo** | Heat | Thermocouple |

---

## 9.2 DC vs. AC

### Direct current (DC)
- The current flows **continuously in the same direction**
- One terminal is always + (positive), the other − (negative)
- Sources: batteries, solar cells, rectified power supplies

### Alternating current (AC)
- The current **changes direction** at constant intervals
- In Denmark: **50 Hz** (changes direction 100 times per second)
- Sinusoidal
- Sources: the mains, generators

> 🌍 In the USA, the mains frequency is 60 Hz. In most other countries including Denmark it is 50 Hz.

---

## 9.3 Voltage (U)

**Voltage** is the difference in electric potential between two points — the "pressure" that drives the current.

| Symbol | Unit | Measured with |
|--------|------|---------------|
| U | volt (V) | Voltmeter |

### Voltmeter
Connected **in parallel** with the component you are measuring across:

```
   ─────●─── component ──●─────
         │              │
         └────[ V ]─────┘
              voltmeter
```

### Typical voltage levels

| Application | Voltage |
|-------------|---------|
| Button cell | 1.5 V DC |
| Car battery | 12 V DC |
| USB phone charger | 5 V DC |
| Mains socket DK | 230 V AC |
| Industrial 3-phase | 400 V AC |
| HV distribution | 10–20 kV |
| HV transmission | 132–400 kV |

> ⚡ **Lightning-fast propagation**: Voltage propagates through a conductor at nearly the speed of light (~300,000 km/s). The **electrons themselves** drift at only a few mm/s.

---

## 9.4 Current (I)

**Electric current** = the amount of charge passing per second.

| Symbol | Unit | Measured with |
|--------|------|---------------|
| I | ampere (A) | Ammeter |

$$I = \frac{Q}{t} \quad \text{(coulombs per second)}$$

### Ammeter
Connected **in series** with the component:

```
  ───[A]──── component ────
   ammeter
```

> ⚠ **Never** connect an ammeter directly across a voltage source — that will short-circuit it!

### Typical currents

| Application | Current |
|-------------|---------|
| Phone charging | ~1 A |
| LED bulb | 0.05 A (50 mA) |
| Household socket | up to 13–16 A |
| Small electric motor | 5–10 A |
| Industrial motor | 50–200 A |

---

## 9.5 Resistance (R)

**Resistance** is a material's ability to oppose the flow of current.

| Symbol | Unit | Measured with |
|--------|------|---------------|
| R | ohm (Ω) | Ohmmeter (or multimeter) |

### Wire resistance

$$R = \rho \cdot \frac{l}{A}$$

| Symbol | Meaning |
|--------|---------|
| ρ | Resistivity (Ω·mm²/m) — depends on material |
| l | Length (m) |
| A | Cross-sectional area (mm²) |

> 💡 **Consequence**: Long, thin conductors have high resistance. Short, thick ones have low.

### Resistivity for common metals

| Material | ρ (Ω·mm²/m) |
|----------|-------------|
| Silver | 0.016 |
| Copper | 0.0175 |
| Aluminium | 0.028 |
| Iron | 0.1 |
| Nickelin (resistance wire) | 0.4 |
| Constantan | 0.49 |

### Temperature dependence of resistance
For metals, resistance rises with temperature:
$$R_T = R_{20} \cdot (1 + \alpha \cdot \Delta T)$$

where α is the **temperature coefficient**:
- Copper: 0.004 /K
- Aluminium: 0.004 /K

---

## 9.6 Ohm's law

> **The most important formula in electrical engineering:**
> $$U = R \cdot I$$

Can be rearranged to:
$$I = \frac{U}{R} \quad \text{or} \quad R = \frac{U}{I}$$

### Examples

**Example 1**: How much current flows through a 100 Ω resistor at 12 V?
$$I = \frac{U}{R} = \frac{12}{100} = 0.12 \text{ A} = 120 \text{ mA}$$

**Example 2**: What is the resistance of an incandescent bulb that draws 0.3 A at 230 V?
$$R = \frac{U}{I} = \frac{230}{0.3} \approx 767 \text{ Ω}$$

> 🛠 Use the interactive tool: [**Ohm's law calculator**](../../interaktiv/ohms-lov.html)

---

## 9.7 Power (P)

**Electric power** = energy per time.

| Symbol | Unit |
|--------|------|
| P | watt (W) |

### Power formulas
$$P = U \cdot I$$
$$P = I^2 \cdot R$$
$$P = \frac{U^2}{R}$$

### Examples
- A 60 W incandescent bulb at 230 V draws: $I = P/U = 60/230 \approx 0.26$ A
- A 2,000 W kettle = 2 kW
- A 5.5 kW motor = 5,500 W

### Power vs. energy
**Power** is how quickly energy is used. **Energy** is the total amount:
$$E = P \cdot t$$

Often measured in kWh: 1 kWh = 1,000 W for 1 hour = 3.6 MJ.

---

## 9.8 Circuits and symbols

### The electrical circuit
Three required parts:
1. **Voltage source** (battery, generator)
2. **Load** (lamp, motor, resistor)
3. **Connecting wires**

```
    ┌──[ R ]──┐
    │         │
   (V)        │
    │         │
    └─────────┘
```

### Common symbols

| Component | Symbol |
|-----------|--------|
| Battery / DC | ─┤├─ |
| AC source | ~ |
| Resistor | ─[▭]─ or ─/\\/\\─ |
| Lamp | ─⊗─ |
| Switch | ─ /─ |
| Fuse | ─[▭]─ |
| Voltmeter | ─(V)─ |
| Ammeter | ─(A)─ |
| Earth | ⏚ |

---

## 9.9 Earth and potential

**Potential** = voltage relative to earth.
- Earth is taken as the reference = 0 V
- In a safe installation, all metal enclosures are connected to earth (earth conductor, yellow/green)

> ⚠ **Safety**: Touching 230 V while standing on the ground = potentially lethal electric shock.

---

## 9.10 Electrical safety — briefly

### Current through the body
| Current | Effect on body |
|---------|----------------|
| < 1 mA | Not felt |
| 1–10 mA | Felt, muscle control retained |
| 10–30 mA | Cramp, cannot let go |
| > 50 mA | Heart fibrillation, life-threatening |
| > 100 mA | High risk of death |

### Protection
- **RCD/GFCI relay**: trips at 30 mA fault current
- **Fuses**: protect against overcurrent
- **Earthing**: leads fault current safely to earth
- **Double insulation** (Class II appliances): symbol ⊡

---

## 📌 Summary

- **DC**: flows always in one direction (e.g. batteries).
- **AC**: changes direction continuously. In Denmark the frequency is 50 Hz.
- **Voltage (U)** is measured in volts (V) — the voltmeter is connected **in parallel**.
- **Current (I)** is measured in amperes (A) — the ammeter is connected **in series**.
- **Resistance (R)** is measured in ohms (Ω). Depends on material, length, and cross-section.
- **Ohm's law**: U = R · I
- **Power**: P = U · I = I²·R = U²/R
- **Safety**: 30 mA can stop the heart — always use RCDs and earthing.

---

## ➡️ Next steps

- 📝 [Exercises for chapter 9](../opgaver/09-opgaver.md)
- 🧮 [Ohm's law calculator (interactive)](../../interaktiv/ohms-lov.html)
- ➡️ [Chapter 10 — DC theory](10-jaevnstroemsteori.md)
