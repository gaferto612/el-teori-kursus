# Chapter 16 — Amplification

**Language:** [🇩🇰 Dansk](../../da/kapitler/16-forstaerkning.md) · **🇬🇧 English** · [🇸🇦 العربية](../../ar/kapitler/16-forstaerkning.md)

## 🎯 Learning goals

- Understand the concept of amplification and gain
- Know the basic transistor amplifier configurations
- Understand connections such as common emitter, common collector, common base
- Apply DC amplifiers in control systems
- Get an overview of the operational amplifier (op-amp)

---

## 16.1 What is an amplifier?

An **amplifier** increases the amplitude or power of a signal.

### Gain

Three forms:
- **Voltage gain**: $A_U = \dfrac{U_{out}}{U_{in}}$
- **Current gain**: $A_I = \dfrac{I_{out}}{I_{in}}$
- **Power gain**: $A_P = \dfrac{P_{out}}{P_{in}}$

### Decibel (dB)
Gain is often expressed in dB (logarithmic scale):
$$A[dB] = 20 \cdot \log\left(\frac{U_{out}}{U_{in}}\right)$$

| Factor | dB |
|--------|----|
| 2 | 6 dB |
| 10 | 20 dB |
| 100 | 40 dB |
| 1,000 | 60 dB |

> 💡 +3 dB = doubling of **power**, +6 dB = doubling of **voltage/current**.

---

## 16.2 DC amplifiers

In control systems **DC amplifiers** are used in many places:

| Application | Function |
|-------------|----------|
| **Sensor amplifier** | Conditions sensor signal for the logic |
| **Driver circuit** | Amplifies the logic signal to drive a relay/motor |
| **Measurement amplifier** | Amplifies small measurement voltages |
| **Control amplifier** | In PID controllers |

### Example — driver circuit

The logic delivers 12 V and 1 mA. To activate a relay with 50 mA coil current, a transistor is used as a switch:

```
   +12 V
      │
      [relay]
      │
      ─┤├─ ← diode (free-wheel diode against inductive spike)
      │
   ───┤  ← C
   logic──[R₁]──┤  ← B (NPN)
       (12 V) ───┤
                 ↓ E
                ───
                 ⏚
```

With transistor current gain $h_{FE} = 200$:
$$I_B = I_C / h_{FE} = 50/200 = 0.25 \text{ mA}$$

The logic can easily supply 0.25 mA → the circuit works.

---

## 16.3 Transistor configurations

There are 3 basic BJT configurations, defined by which terminal is **common** to input and output:

### Common Emitter (CE)
**The most-used amplifier configuration**.

| Property | Value |
|----------|-------|
| Voltage gain | High (10–1000) |
| Current gain | High (β) |
| Input impedance | Medium (~kΩ) |
| Output impedance | High (~10 kΩ) |
| Phase shift in→out | **180°** |

### Common Collector (CC — Emitter follower)
| Property | Value |
|----------|-------|
| Voltage gain | ≈1 (no amplification!) |
| Current gain | High |
| Input impedance | **Very high** |
| Output impedance | **Very low** |
| Phase shift | 0° |

> 💡 Used as a **buffer** or for impedance matching — e.g. between a high-impedance sensor and a low-impedance load.

### Common Base (CB)
| Property | Value |
|----------|-------|
| Voltage gain | High |
| Current gain | ≈1 |
| Input impedance | **Very low** |
| Output impedance | Very high |
| Phase shift | 0° |

> 📡 Used in RF circuits and high-frequency amplification.

---

## 16.4 Operating point

To amplify an **AC signal** without distortion, the transistor must be biased to an **operating point** in the middle of its linear region.

```
   I_C
    │
    │     /  <- saturation
    │    /
    │   X     <- operating point
    │  /
    │ /
    │/
    └──────────  V_CE
       ↑
     cut-off
```

Bias resistors on the base set a small DC current that places the operating point correctly.

---

## 16.5 The operational amplifier (op-amp)

An **op-amp** is a high-gain DC amplifier in IC form. **The most important analogue component** in modern electronics after the MOSFET.

### Properties (ideal)
- **Gain**: extremely high (~10⁵ – 10⁶)
- **Input impedance**: very high (infinite)
- **Output impedance**: very low (0)
- Two inputs: **+** (non-inverting) and **−** (inverting)
- One output

### Symbol
```
        ┌───────┐
   + ───┤        \
        │         ├── out
   - ───┤        /
        └───────┘
```

### Golden rule (with negative feedback)
1. The output adjusts so that the two inputs have the **same voltage**
2. **No current** flows into the inputs

---

## 16.6 Common op-amp circuits

### Inverting amplifier

```
        Rf
   ┌────[▭]────┐
   │           │
   ├──[▭]──┤-  │
   U_in    │  ├─── U_out
   ┌──────┤+  │
   │       └───┘
   ⏚
```

**Gain**:
$$A_U = -\frac{R_f}{R_{in}}$$

(minus = inverts the phase)

### Non-inverting amplifier

```
   U_in ──┤+
          │ ├─── U_out
       ┌──┤-
       │  │
   ┌───┴─[Rf]─── out
   │
  [R₁]
   │
   ⏚
```

**Gain**:
$$A_U = 1 + \frac{R_f}{R_1}$$

### Voltage follower (buffer)
Special case of non-inverting: $A_U = 1$.
Used for **impedance isolation** without amplification.

### Summing amplifier
Adds several inputs together, weighted.

### Difference amplifier
Amplifies the difference between two signals — used for instrumentation amplifiers, sensor signal conditioning.

### Comparator
Compares two voltages — output is ON or OFF (digital):
- If $U_+ > U_-$ → output HIGH
- If $U_+ < U_-$ → output LOW

> 🔍 Used in alarms, level detectors, A/D converters.

---

## 16.7 Common op-amp ICs

| IC | Description |
|----|-------------|
| LM741 | Classic general-purpose op-amp — old but still useful |
| LM358 | Dual op-amp, single supply (5 V) |
| TL081/82/84 | JFET input, low noise |
| LM324 | Quad op-amp in one package |
| OP07 | Low-offset, precision |
| INA128 | Instrumentation amplifier |

---

## 16.8 Push-pull / class AB amplifier

Two transistors (NPN + PNP) share the work:
- NPN handles the positive half of the signal
- PNP handles the negative

> 🔊 Used in audio amplifiers — better efficiency than class A. Class AB is the standard choice in hi-fi.

| Class | Efficiency | Distortion |
|-------|-----------|------------|
| A | 25% | Low |
| AB | 50–60% | Low (with crossover) |
| B | 78% | Higher |
| D (switching) | 90+% | Very low (modern) |

---

## 📌 Summary

- **Amplification** = increase in signal amplitude. Calculated as a ratio (Aᵤ = U_out / U_in) or in decibels.
- **3 basic transistor configurations**:
  - **CE (common emitter)**: most popular amplifier, 180° inversion.
  - **CC (common collector / emitter follower)**: gain ~1, very high input impedance, very low output — used as an impedance converter.
  - **CB (common base)**: for high frequencies.
- **The operational amplifier (op-amp)**: high-gain integrated amplifier with very high input impedance.
- **Basic op-amp circuits**: inverting, non-inverting, voltage follower, summing, differential, comparator.
- **Use in PLCs**: amplifying a sensor signal before it enters digital logic.

---

## ➡️ Next steps

- 📝 [Exercises for chapter 16](../opgaver/16-opgaver.md)
- ➡️ [Chapter 17 — Rectification](17-ensretning.md)
