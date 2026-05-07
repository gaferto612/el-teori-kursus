# Chapter 12 — Single-phase AC theory

**Language:** [🇩🇰 Dansk](../../da/kapitler/12-1-faset-vekselstroemsteori.md) · **🇬🇧 English** · [🇸🇦 العربية](../../ar/kapitler/12-1-faset-vekselstroemsteori.md)

## 🎯 Learning goals

- Understand how AC voltage is generated
- Distinguish between peak, peak-to-peak, RMS and average values
- Calculate reactance for coils and capacitors
- Understand impedance and power factor
- Calculate active, reactive and apparent power

---

## 12.1 How AC arises

When a **conductor loop is rotated** in a homogeneous magnetic field, a **sinusoidal** AC voltage is induced:

$$u(t) = U_{peak} \cdot \sin(\omega t)$$

| Symbol | Meaning |
|--------|---------|
| u(t) | Instantaneous voltage (V) |
| $U_{peak}$ | Peak value |
| ω | Angular frequency (rad/s) = $2\pi f$ |
| t | Time (s) |

For each rotation of the loop → 1 sine period.

---

## 12.2 Frequency and period

### Frequency (f)
Number of periods per second. Measured in **Hertz (Hz)**.

In Denmark: **f = 50 Hz** (mains).

### Period (T)
Duration of one period:
$$T = \frac{1}{f}$$

At 50 Hz: $T = 1/50 = 20$ ms.

### Angular frequency
$$\omega = 2\pi f$$

At 50 Hz: $\omega = 2\pi \cdot 50 \approx 314$ rad/s.

---

## 12.3 AC values

Unlike DC, where voltage has only **one** value, AC has several characteristic measures:

### Peak value — $U_{peak}$ or $\hat{U}$
Maximum instantaneous value.

### Peak-to-peak — $U_{pp}$
Difference between positive and negative peak:
$$U_{pp} = 2 \cdot U_{peak}$$

### RMS value (effective value) — $U_{rms}$
The DC voltage that would produce the same **power** in a resistor.

For a **sine wave**:
$$U_{rms} = \frac{U_{peak}}{\sqrt{2}} \approx 0.707 \cdot U_{peak}$$

> 💡 **Important**: When we say "230 V" for mains voltage, that's the **RMS value**. The peak value is actually:
> $$U_{peak} = 230 \cdot \sqrt{2} \approx 325 \text{ V}$$

### Average value
For a half period:
$$U_{avg} = \frac{2 \cdot U_{peak}}{\pi} \approx 0.637 \cdot U_{peak}$$

> 🛠 [AC visualizer](../../interaktiv/vekselstroem.html)

### Summary — form factors

| Value | Formula | Factor |
|-------|---------|--------|
| Peak | $U_{peak}$ | 1.000 |
| Peak-to-peak | $2 \cdot U_{peak}$ | 2.000 |
| RMS | $U_{peak} / \sqrt{2}$ | 0.707 |
| Average (half period) | $2U_{peak}/\pi$ | 0.637 |

---

## 12.4 Phase shift

Two sinusoidal signals can be **shifted** in time — measured as **phase angle φ**.

```
u₁: ─╲    ╱─╲    ╱─
       ╲ ╱   ╲  ╱
        ╳     ╳     shifted by angle φ
       ╱ ╲   ╱  ╲
u₂: ─╱    ╲╱    ╲─
```

| Relation | Description |
|----------|-------------|
| φ = 0° | In phase |
| φ = 90° | 1/4 period offset |
| φ = 180° | Out of phase (anti-phase) |

---

## 12.5 Component behaviour under AC

### Resistor (R) — pure resistive load
- U and I are **in phase** (φ = 0°)
- Follows Ohm's law: $I = U/R$
- Example: incandescent bulb, heating element

### Coil (L) — pure inductive load
- The coil opposes changes in current
- **Current "lags"** the voltage by 90°
- **Inductive reactance**:
$$X_L = \omega L = 2\pi f L$$

| Factor | Meaning |
|--------|---------|
| L | Inductance (henry) |
| f | Frequency (Hz) |
| $X_L$ | Reactance (ohm) |

### Capacitor (C) — pure capacitive load
- The capacitor charges/discharges
- **Voltage lags** the current by 90°
- **Capacitive reactance**:
$$X_C = \frac{1}{\omega C} = \frac{1}{2\pi f C}$$

| Factor | Meaning |
|--------|---------|
| C | Capacitance (farad) |
| $X_C$ | Reactance (ohm) |

> 💡 **Memory aid**: "ELI the ICE man" — in a coil (L), E (voltage) leads I (current); in a capacitor (C), I leads E.

---

## 12.6 Impedance (Z)

The **total opposition** in an AC circuit to alternating current:

$$Z = \sqrt{R^2 + X^2}$$

where X is the resulting reactance.

For a series RLC circuit:
$$Z = \sqrt{R^2 + (X_L - X_C)^2}$$

### Ohm's law for AC
$$I = \frac{U}{Z}$$

---

## 12.7 Power in AC circuits

Three different power concepts:

### Active power (P) — real power
Power **actually converted** into work, heat, light.
- Measured in **W (watts)**
- $P = U \cdot I \cdot \cos(\varphi)$

### Reactive power (Q)
Power that **oscillates** between source and load (from coils/capacitors).
- Measured in **var (volt-ampere reactive)**
- $Q = U \cdot I \cdot \sin(\varphi)$

### Apparent power (S)
**Total** power delivered by the source.
- Measured in **VA (volt-amperes)**
- $S = U \cdot I$

### The power triangle
$$S = \sqrt{P^2 + Q^2}$$

```
      S (VA)
       /|
      / |
     /  | Q (var)
    /   |
   / φ  |
  /_____|
    P (W)
```

### Power factor (cos φ)
$$\cos(\varphi) = \frac{P}{S}$$

| cos φ | Meaning |
|-------|---------|
| 1.0 | Pure resistive load (ideal) |
| 0.8–0.9 | Typical industrial (motors) |
| 0 | Pure reactive (no real power) |

> ⚡ **Why does cos φ matter?** Low cos φ means a lot of "reactive current" is being transmitted through cables and transformers without doing useful work → extra losses. Industry often pays more for poor cos φ → compensated with capacitors.

---

## 12.8 Resonance

A series RLC circuit has a **resonance frequency** at which $X_L = X_C$:
$$f_0 = \frac{1}{2\pi \sqrt{LC}}$$

At resonance:
- $X_L - X_C = 0$
- $Z = R$ (purely resistive)
- The current is **maximum** (in series)

> 📡 Used in radio tuning, filters, oscillators.

---

## 12.9 Practical example

A motor with L = 0.5 H and R = 30 Ω is connected to 230 V, 50 Hz.

**Step 1 — reactance**:
$$X_L = 2\pi \cdot 50 \cdot 0.5 = 157 \text{ Ω}$$

**Step 2 — impedance**:
$$Z = \sqrt{30^2 + 157^2} = \sqrt{900 + 24649} \approx 160 \text{ Ω}$$

**Step 3 — current**:
$$I = \frac{230}{160} = 1.44 \text{ A}$$

**Step 4 — phase angle**:
$$\tan(\varphi) = \frac{X_L}{R} = \frac{157}{30} = 5.23$$
$$\varphi = 79.2°$$
$$\cos(\varphi) = 0.187$$

**Step 5 — powers**:
- $S = 230 \cdot 1.44 = 331$ VA
- $P = 331 \cdot 0.187 = 62$ W
- $Q = 331 \cdot 0.982 = 325$ var

> 💡 Note: an idle motor has poor cos φ. Under load it improves significantly.

---

## 📌 Summary

- **AC** is generated when a coil rotates in a magnetic field. The waveform is sinusoidal.
- **RMS value** = peak value / √2. A 230 V grid has a peak value of ~325 V.
- **In a coil**: current lags 90°. Inductive reactance: $X_L = 2\pi f L$.
- **In a capacitor**: current leads 90°. Capacitive reactance: $X_C = 1/(2\pi f C)$.
- **Total impedance**: $Z = \sqrt{R^2 + (X_L - X_C)^2}$.
- **Power**: P (real, W), Q (reactive, var), S (apparent, VA). $S^2 = P^2 + Q^2$.
- **Power factor** cos φ = P/S — closer to 1 means a more efficient load.

---

## ➡️ Next steps

- 📝 [Exercises for chapter 12](../opgaver/12-opgaver.md)
- 🌊 [AC visualizer (interactive)](../../interaktiv/vekselstroem.html)
- ➡️ [Chapter 13 — Three-phase AC](13-3-faset-vekselstroemsteori.md)
