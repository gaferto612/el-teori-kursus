# Chapter 14 — Resistors and capacitors

**Language:** [🇩🇰 Dansk](../../da/kapitler/14-modstande-og-kondensatorer.md) · **🇬🇧 English** · [🇸🇦 العربية](../../ar/kapitler/14-modstande-og-kondensatorer.md)

## 🎯 Learning goals

- Know different resistor types and the colour code
- Understand the capacitor's structure and operation
- Calculate equivalent capacitance in series and parallel
- Understand the use of potentiometers, NTCs, LDRs etc.

---

## 14.1 Fixed resistors

### Materials

| Type | Principle | Use |
|------|-----------|-----|
| **Carbon film** | Thin layer of carbon on ceramic | General-purpose, cheap |
| **Metal film** | Thin layer of metal | Precise, low-noise |
| **Wirewound** | Resistance wire wound on a core | High power |
| **SMD** | Surface mount, flat chip | Modern electronics |

### Important parameters

| Parameter | Meaning |
|-----------|---------|
| Resistance value | Ω, kΩ, MΩ |
| **Tolerance** | ±1%, ±5%, ±10% |
| **Power rating** | 1/8 W, 1/4 W, 1/2 W, 1 W, 5 W, 25 W |
| **Temperature coefficient** | ppm/°C |

---

## 14.2 The colour code — 4 bands

```
  Band 1 │ Band 2 │ Multiplier │ Tolerance
  ───────┼────────┼────────────┼──────────
   Black │ 0      │ 1          │
   Brown │ 1      │ ×10        │ ±1%
   Red   │ 2      │ ×100       │ ±2%
   Orange│ 3      │ ×1k        │
   Yellow│ 4      │ ×10k       │
   Green │ 5      │ ×100k      │ ±0.5%
   Blue  │ 6      │ ×1M        │
   Violet│ 7      │ ×10M       │
   Grey  │ 8      │            │
   White │ 9      │            │
   Gold  │        │ ×0.1       │ ±5%
   Silver│        │ ×0.01      │ ±10%
```

### Example — resistor with colours **brown-black-red-gold**:
- 1st band (brown) = 1
- 2nd band (black) = 0
- 3rd band (red) = ×100
- 4th band (gold) = ±5%

→ **10 × 100 = 1000 Ω = 1 kΩ ±5%**

---

## 14.3 Adjustable resistors

### Potentiometer
3 terminals. Can be used as:
- **Voltage divider** (3 terminals connected)
- **Rheostat** (2 terminals — variable resistance)

### Trimmer
A small potentiometer adjusted only with a screwdriver — for fine-tuning.

---

## 14.4 Special resistors (sensors)

### NTC (Negative Temperature Coefficient)
- Resistance **decreases** as temperature rises
- Used in: temperature measurement, inrush-current limiting

### PTC (Positive Temperature Coefficient)
- Resistance **increases** as temperature rises
- Used in: motor monitoring (PT100, PT1000), self-regulating heaters

### LDR (Light Dependent Resistor)
- Resistance decreases as light intensity increases
- Used in: light sensors, twilight switches

### VDR (Voltage Dependent Resistor) / varistor
- Resistance drops sharply above a specific voltage
- Used as **overvoltage protection**

| Sensor type | Symbol mark | Use |
|-------------|-------------|-----|
| NTC | t° with arrow ↘ | Temp. measurement |
| PTC | t° with arrow ↗ | Motor protection |
| LDR | Arrow into resistor | Light |
| VDR | U over resistor | Overvoltage protection |

---

## 14.5 Capacitors

A **capacitor** consists of two conductive plates separated by an **insulating dielectric**.

```
     ──┤├──
       ││
    plate plate
    + insulator between
```

### Capacitance (C)
Measured in **farad (F)**:
$$C = \frac{Q}{U}$$

| Factor | Meaning |
|--------|---------|
| Q | Charge (coulomb) |
| U | Voltage (V) |

> 💡 1 F is a **large** unit. Typical capacitors are in:
> - pF (picofarad) — RF, oscillators
> - nF (nanofarad) — filters
> - μF (microfarad) — power supplies, motors
> - mF–F (super-capacitors) — energy storage

### Capacitance for parallel-plate capacitor
$$C = \varepsilon_0 \cdot \varepsilon_r \cdot \frac{A}{d}$$

| Symbol | Meaning |
|--------|---------|
| $\varepsilon_0$ | Vacuum permittivity (8.854 · 10⁻¹² F/m) |
| $\varepsilon_r$ | Relative permittivity (dielectric constant) |
| A | Plate area (m²) |
| d | Plate spacing (m) |

---

## 14.6 Capacitor types

| Type | Dielectric | Capacitance | Use |
|------|-----------|-------------|-----|
| Ceramic | Ceramic | pF–μF | General, RF |
| Film (PE, PP, PS) | Plastic | nF–μF | Filters, motors |
| Electrolytic (Al, Ta) | Aluminium/tantalum oxide | μF–mF | Power supplies |
| Super-capacitor | Special | F–kF | Energy storage |

> ⚠ **Polarised**: Electrolytic capacitors **must** be connected the right way round — the negative side is normally marked with a stripe. Wrong polarity → can explode!

---

## 14.7 Capacitors in series and parallel

### Parallel
$$C_{tot} = C_1 + C_2 + C_3$$

(Opposite to resistors)

### Series
$$\frac{1}{C_{tot}} = \frac{1}{C_1} + \frac{1}{C_2} + \frac{1}{C_3}$$

(Also opposite to resistors)

> 💡 **Memory aid**: Capacitors combine **the opposite way** of resistors.

---

## 14.8 Charging and discharging a capacitor

When a capacitor is charged through a resistor R:

$$u_C(t) = U \cdot (1 - e^{-t/\tau})$$

where $\tau = R \cdot C$ is the **time constant**.

| Time | Charged to |
|------|------------|
| 1τ | 63% |
| 3τ | 95% |
| 5τ | ~99% (regarded as "fully charged") |

### Example
$R = 10$ kΩ, $C = 100$ μF:
$$\tau = 10{,}000 \cdot 100 \cdot 10^{-6} = 1 \text{ s}$$

→ Fully charged after about 5 seconds.

> ⚡ Used in **timing circuits**, RC filters, switch debouncing.

---

## 14.9 Energy stored in a capacitor

$$E = \frac{1}{2} C U^2$$

### Example
1,000 μF capacitor charged to 100 V:
$$E = \frac{1}{2} \cdot 0.001 \cdot 100^2 = 5 \text{ J}$$

> ⚠ Large capacitors (in power supplies, motor starters) **hold dangerous voltage** long after the power is removed. **Always discharge!**

---

## 14.10 Applications

| Application | How |
|-------------|-----|
| **Smoothing** | Reduces pulsating DC after a rectifier |
| **Coupling** | Lets AC pass, blocks DC |
| **Decoupling** | Filters noise from a power supply |
| **Timing** | RC circuits in oscillators |
| **Phase shift** | Start capacitor in single-phase motors |
| **Power-factor compensation** | Improves cos φ in industry |
| **Energy storage** | UPS, variable-frequency drives |

---

## 📌 Summary

- **Resistors**: the most common component. Specified by value, tolerance, and maximum power.
- **The colour code** on resistors: 4 bands — digit, digit, multiplier, tolerance.
- **Special resistors**:
  - NTC: decreases with temperature (for temperature measurement).
  - PTC: increases with temperature (motor protection).
  - LDR: decreases with light (light sensor).
- **The capacitor** stores charge: $C = Q/U$, measured in farads.
- **In parallel**: $C_{tot} = C_1 + C_2$. **In series**: $1/C_{tot} = 1/C_1 + 1/C_2$.
- **Time constant**: $\tau = R \cdot C$ — determines how fast it charges and discharges.
- **Warning**: large capacitors retain charge for a long time after power-off.

---

## ➡️ Next steps

- 📝 [Exercises for chapter 14](../opgaver/14-opgaver.md)
- ➡️ [Chapter 15 — Semiconductor components](15-halvlederkomponenter.md)
