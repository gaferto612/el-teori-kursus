# Chapter 17 — Rectification

**Language:** [🇩🇰 Dansk](../../da/kapitler/17-ensretning.md) · **🇬🇧 English** · [🇸🇦 العربية](../../ar/kapitler/17-ensretning.md)

## 🎯 Learning goals

- Understand why rectification is needed
- Know half-wave, centre-tap and bridge rectifiers
- Calculate no-load and loaded voltage
- Understand smoothing with a capacitor and ripple
- Know voltage stabilisation methods

---

## 17.1 Why rectification?

Most electronic circuits run on **direct current** (DC). Since the mains supplies **alternating current** (AC), it must be **rectified** first.

### Typical power supply
```
   AC mains ──[Transformer]──[Rectifier]──[Smoothing]──[Regulator]── DC out
   230 V                      ~                         Pure DC
```

**Each part has a role**:
1. **Transformer**: matches voltage + galvanic isolation
2. **Rectifier**: converts AC → pulsating DC
3. **Smoothing**: evens out the pulses (capacitor)
4. **Regulator**: keeps the voltage constant under varying load

---

## 17.2 Half-wave rectifier

The simplest rectifier — one diode in series.

```
       +───D──────●─── + out
   AC                  │
       -──────●───────●─── - out
                  load
```

### Operation
- Positive half-cycle: the diode conducts → current flows
- Negative half-cycle: the diode blocks → no current

```
Input AC:    /\    /\    /\
            /  \  /  \  /
       ──/────\/────\/────
                  
Output:        /\        /\
              /  \      /  \
       ─────/────────/───────
```

### Values
For a sine with peak voltage $U_{peak}$:

| Value | Formula |
|-------|---------|
| No-load voltage (peak) | $U_{peak} = U_{rms} \cdot \sqrt{2}$ |
| Average value (DC) | $U_{DC} = U_{peak}/\pi \approx 0.318 \cdot U_{peak}$ |
| Frequency of pulses | = mains frequency (50 Hz) |

> ⚠ **Only** half the period is used — poor efficiency. Rarely used except in very small applications.

---

## 17.3 Full-wave — centre-tap rectifier

Uses a transformer with a **centre tap** and two diodes.

```
   Top ───D₁───┐
               │
   Centre ─────●──── + out
               │
   Bottom ─D₂──┘
```

### Operation
- Positive half-cycle: D₁ conducts, D₂ blocks
- Negative half-cycle: D₂ conducts, D₁ blocks
- **Both** half-cycles are rectified!

```
Input:    /\    /\    /\
         /  \  /  \  /
       ──/────\/────\/───

Output:    /\  /\  /\  /\
          /  \/  \/  \/  \
       ──/────────────────
```

### Values
| Value | Formula |
|-------|---------|
| Average value (DC) | $U_{DC} = 2 \cdot U_{peak}/\pi \approx 0.637 \cdot U_{peak}$ |
| Pulse frequency | **2 × mains frequency** (100 Hz) |

> 💡 Requires a more expensive centre-tap transformer. Rare in modern circuits.

---

## 17.4 Bridge rectifier — the modern standard

**4 diodes** in a bridge configuration. Requires **no** centre tap.

```
              D₁         D₂
    AC ●────►├────●──────●
              D₃         D₄
       ●────►├────●──────●
                  ↑      ↓
              + out      - out
```

### Operation
For each half-cycle: 2 diodes conduct, 2 block — current is always drawn the **same way** through the load.

### Properties
- **Both** half-cycles rectified
- Efficient
- No-load voltage = peak − 2 · 0.7 V (two diodes in series)
- Ripple frequency = 100 Hz (with 50 Hz mains)

> ⚙ **By far the most-used rectifier** in power supplies, chargers, etc. Often available as a **single component** (bridge rectifier).

---

## 17.5 Three-phase rectification

For larger powers (motors, variable-frequency drives):

### 3-phase bridge (B6)
**6 diodes** — two per phase. The result is much smoother than single-phase:

```
Pulses per cycle: 6
Ripple: ~4% without smoothing
Pulse frequency: 6 × 50 Hz = 300 Hz
```

> ⚡ Used in: industrial DC power supplies, variable-frequency drives (input side), heavy chargers.

---

## 17.6 Smoothing with a capacitor

To make pulsating DC more "smooth", a large **smoothing capacitor** is connected in parallel with the load.

```
      ┌──[rectifier]──┬──── + out
                      │
                      │
                     [C]
                      │
      ────────────────┴──── - out
```

### Operation
- When voltage rises, C is charged
- When voltage falls, C **delivers** current to the load
- Result: smoother DC with a small **ripple**

### Ripple voltage
$$U_{rip} \approx \frac{I_{load}}{f_{ripple} \cdot C}$$

| Factor | Meaning |
|--------|---------|
| $I_{load}$ | Load current |
| $f_{ripple}$ | 100 Hz for single-phase bridge rectifier |
| C | Smoothing capacitor (F) |

### Example
$I_{load} = 1$ A, $f = 100$ Hz, $C = 1{,}000$ μF:
$$U_{rip} = \frac{1}{100 \cdot 0.001} = 10 \text{ V}$$

For less ripple: larger C or lower current.

> 💡 Ripple makes the smooth DC "lumpy" — unsatisfactory for sensitive circuits, so it is followed by a **regulator**.

---

## 17.7 Voltage stabilisation

### Zener diode regulator (simple)

```
   U_in ──[R]──●──── U_out
                │
              ─┬├─  zener (reversed)
                │
                ⏚
```

The Zener diode keeps a constant voltage at its **breakdown voltage** $U_Z$.

> 💡 OK for light loads and simple circuits. Wastes energy in the series resistor.

### Linear regulator (IC)

| Type | Voltage |
|------|---------|
| 7805 | +5 V |
| 7812 | +12 V |
| 7905 | -5 V |
| 7915 | -15 V |

These 3-pin regulators are extremely simple to use:
- **Input**: 7–15 V (depending on type)
- **GND**
- **Output**: regulated voltage

### Switch-mode (SMPS)
Modern power supplies use **switching** at high frequency (50–500 kHz) and are far more efficient (90+%) than linear regulators.

> ⚙ Almost all modern chargers, computer power supplies and industrial PSUs are switch-mode.

---

## 17.8 Voltage doublers and multipliers (briefly)

Special diode + capacitor circuits can **double** or **multiply** the voltage:

| Type | Result |
|------|--------|
| Doubler | 2 × peak |
| Tripler | 3 × peak |
| Quadrupler | 4 × peak |

Used in: electrostatic precipitators, electron microscopes, older TVs (CRT anode ~25 kV).

---

## 17.9 Comparison of rectifier types

| Type | Diodes | Transformer | Ripple frequency | Efficiency |
|------|--------|-------------|------------------|------------|
| Half-wave (E) | 1 | Standard | 50 Hz | Poor |
| Centre-tap (M) | 2 | Centre-tapped | 100 Hz | Better |
| Bridge (B) | 4 | Standard | 100 Hz | Good |
| 3-phase bridge (B6) | 6 | 3-phase | 300 Hz | Excellent |

---

## 📌 Summary

- **Rectification** = converting AC to DC using diodes.
- **Half-wave rectification**: one diode, uses only half the wave — low efficiency.
- **Full-wave rectification (bridge)**: 4 diodes in a bridge — uses the full wave, the most-used type.
- **Three-phase rectification (B6)**: 6 diodes, very low ripple — for large loads (variable-frequency drives).
- **Smoothing capacitor** reduces ripple. The larger the capacitance, the smaller the ripple.
- **Voltage regulator** (e.g. 7805): keeps the voltage constant despite load variations.
- **Modern power supplies (SMPS)**: high-frequency switching, 90%+ efficiency.

---

## ➡️ Next steps

- 📝 [Exercises for chapter 17](../opgaver/17-opgaver.md)
- ➡️ [Chapter 18 — Power regulation](18-effektregulering.md)
