# Chapter 13 — Three-phase AC theory

**Language:** [🇩🇰 Dansk](../../da/kapitler/13-3-faset-vekselstroemsteori.md) · **🇬🇧 English** · [🇸🇦 العربية](../../ar/kapitler/13-3-faset-vekselstroemsteori.md)

## 🎯 Learning goals

- Understand how 3-phase voltage is generated
- Distinguish between phase voltage and line voltage
- Understand star (Y) and delta (Δ) connections
- Calculate power in 3-phase systems
- Understand why 3-phase is used for larger loads

---

## 13.1 Why 3-phase?

For larger loads, 2 or 3 phases are connected instead of 1. This gives:

1. **Lower current** (the same power is shared across more conductors)
2. **Less copper** in cables
3. **Constant power** (in 1-phase the power oscillates — in 3-phase it is constant)
4. **Rotating magnetic field** (essential for asynchronous motors!)

---

## 13.2 Generating 3-phase voltage

The generator's stator has **3 identical windings** with **120° physical offset**.

When the rotor turns, three **sinusoidal AC voltages** are induced 120° apart electrically:

$$u_1 = U_{peak} \cdot \sin(\omega t)$$
$$u_2 = U_{peak} \cdot \sin(\omega t - 120°)$$
$$u_3 = U_{peak} \cdot \sin(\omega t - 240°)$$

```
   u₁ ─╲    ╱─╲    ╱─
       ╲╱   ╲╱
   u₂  ╱╲   ╱╲    shifted 120°
       ╲ ╲ ╱ ╲
   u₃  ╲ ╳    ╲   shifted 240°
       ╱ ╲   ╳
```

> 💡 **Important property**: The sum of the three instantaneous voltages is **always 0**:
> $$u_1 + u_2 + u_3 = 0$$

That is **why** a neutral conductor is not always required for 3-phase loads.

---

## 13.3 Phase conductors and labels

In Denmark, the phases are labelled:

| Phase | Colour | Old name |
|-------|--------|----------|
| L1 | Brown | Formerly "R" |
| L2 | Black | Formerly "S" |
| L3 | Grey | Formerly "T" |
| Neutral (N) | Blue | Neutral |
| Earth (PE) | Yellow/green | Protective earth |

---

## 13.4 Star connection (Y)

One end of each of the three windings is joined at a common **star point** (neutral point).

```
       L1 ────●
              │
              ├──── N (neutral)
              │
       L2 ────●
              │
       L3 ────●
```

### Voltages in Y connection

Two kinds of voltage:

| Voltage | Symbol | Between |
|---------|--------|---------|
| **Phase voltage** | $U_p$ | Phase and N (or star point) |
| **Line voltage** | $U_l$ | Two phases |

**Relationship**:
$$U_l = \sqrt{3} \cdot U_p$$

In Denmark:
$$U_p = 230 \text{ V}, \quad U_l = 230 \cdot \sqrt{3} \approx 400 \text{ V}$$

### Currents in Y connection
- $I_p = I_l$ (phase current = line current)
- In the neutral conductor: vector sum of the three phase currents — for a symmetrical load it is **0**.

---

## 13.5 Delta connection (Δ)

The three windings are connected in a **closed triangle**:

```
       L1 ●─────●
          │     │
          │     │
          ●─────●
          L2    L3
```

### Voltages and currents in Δ

In delta:
- **Phase voltage = line voltage** ($U_p = U_l$)
- **Currents** differ:
$$I_l = \sqrt{3} \cdot I_p$$

| | Star (Y) | Delta (Δ) |
|--|---------|-----------|
| Voltage | $U_l = \sqrt{3} \cdot U_p$ | $U_l = U_p$ |
| Current | $I_l = I_p$ | $I_l = \sqrt{3} \cdot I_p$ |

> 💡 **Key point**: Star = lower voltage per winding, but same current. Delta = higher voltage per winding, but lower winding current.

---

## 13.6 Power in 3-phase systems

The total 3-phase power:

### Active power (P)
$$P = \sqrt{3} \cdot U_l \cdot I_l \cdot \cos(\varphi)$$

### Reactive power (Q)
$$Q = \sqrt{3} \cdot U_l \cdot I_l \cdot \sin(\varphi)$$

### Apparent power (S)
$$S = \sqrt{3} \cdot U_l \cdot I_l$$

### Relationships
$$S = \sqrt{P^2 + Q^2} \qquad \cos(\varphi) = \frac{P}{S}$$

> 📐 **Memo**: $\sqrt{3} \approx 1.732$ is the characteristic factor of 3-phase.

---

## 13.7 Examples

### Example 1 — typical industrial motor
A 3-phase motor is rated: **400 V, 50 Hz, 5.5 kW, cos φ = 0.85, η = 0.9**

**What is its current draw?**

Input power:
$$P_{in} = \frac{P_{out}}{\eta} = \frac{5500}{0.9} = 6111 \text{ W}$$

Current:
$$I = \frac{P_{in}}{\sqrt{3} \cdot U_l \cdot \cos\varphi} = \frac{6111}{\sqrt{3} \cdot 400 \cdot 0.85} = 10.4 \text{ A}$$

### Example 2 — Y/Δ switching for motor start
A motor is typically rated e.g. **400/690 V**:
- In Y connection it can handle 690 V (= line voltage 690)
- In Δ connection it can handle 400 V (= line voltage 400)

In DK with a 400 V grid:
- **Y connection**: the winding sees only $400/\sqrt{3} = 230$ V → reduced inrush current (1/3)
- **Δ connection**: the winding sees 400 V → full power

**Y/Δ start**: the motor is started in Y for limited inrush, then switched to Δ at full speed.

> ⚙️ Y/Δ start is a classic technique — modern installations typically use **variable-frequency drives** (VFDs) instead, which are both softer and more energy-efficient.

---

## 13.8 Rotating magnetic field

A 3-phase motor (e.g. asynchronous motor) exploits the fact that the three phases, placed 120° apart physically, create a **rotating magnetic field** in the stator.

### Synchronous speed
$$n_s = \frac{60 \cdot f}{p}$$

| Symbol | Meaning |
|--------|---------|
| $n_s$ | Synchronous speed (rpm) |
| f | Frequency (Hz) |
| p | Number of **pole pairs** |

| Pole pairs | Synchronous speed at 50 Hz |
|------------|----------------------------|
| 1 | 3,000 rpm |
| 2 | 1,500 rpm |
| 3 | 1,000 rpm |
| 4 | 750 rpm |

> 💡 The asynchronous motor runs **slightly slower** than synchronous speed (typically 2–5% slip under load).

---

## 13.9 Symmetrical vs. asymmetrical loading

### Symmetrical loading
- All three phases are loaded **equally**
- No current in the neutral (ideally)
- Used for motors, ovens

### Asymmetrical loading
- Phases are loaded unequally (e.g. many single-phase loads distributed)
- Current flows in the neutral — it is **important** that the neutral is dimensioned correctly

> ⚠ Poor distribution of single-phase loads → can overload one phase or the neutral. The electrician must distribute evenly.

---

## 13.10 Industrial sockets

In Europe, **CEE plugs** are used (red for 400 V):

| Plug | Voltage | Current |
|------|---------|---------|
| Blue (single-phase) | 230 V | 16 A / 32 A |
| Red (3-phase) | 400 V | 16 A / 32 A / 63 A / 125 A |

---

## 📌 Summary

- **Three-phase**: three equal sinusoidal voltages 120° apart — generated by a generator with three windings.
- **Sum of instantaneous voltages = 0** — that is why a neutral conductor is not always required.
- **Star connection (Y)**: $U_l = \sqrt{3} \cdot U_p$. In Denmark: $U_p = 230$ V, $U_l = 400$ V.
- **Delta connection (Δ)**: $U_p = U_l$, but $I_l = \sqrt{3} \cdot I_p$.
- **Power in 3-phase systems**: $P = \sqrt{3} \cdot U_l \cdot I_l \cdot \cos\varphi$.
- **The rotating field**: three coils 120° apart create a rotating field — the foundation of induction (asynchronous) motors.
- **Synchronous speed**: $n_s = 60 \cdot f / p$. At 50 Hz with 2 pole pairs = 1,500 rpm.

---

## ➡️ Next steps

- 📝 [Exercises for chapter 13](../opgaver/13-opgaver.md)
- ➡️ [Chapter 14 — Resistors and capacitors](14-modstande-og-kondensatorer.md)
