# Chapter 10 — DC theory

**Language:** [🇩🇰 Dansk](../../da/kapitler/10-jaevnstroemsteori.md) · **🇬🇧 English** · [🇸🇦 العربية](../../ar/kapitler/10-jaevnstroemsteori.md)

## 🎯 Learning goals

- Apply Ohm's law in different circuits
- Use Kirchhoff's two laws
- Calculate equivalent resistance in series and parallel circuits
- Understand voltage and current dividers

---

## 10.1 Ohm's law — recap

$$U = R \cdot I \qquad I = \frac{U}{R} \qquad R = \frac{U}{I}$$

**Proportionality**:
- Constant R: U and I are **directly proportional** (U up → I up)
- Constant U: I and R are **inversely proportional** (R up → I down)

---

## 10.2 Kirchhoff's laws

### Kirchhoff's 1st law — current law (KCL)
> **The sum of currents flowing INTO a node = the sum of currents flowing OUT of the node.**

$$\sum I_{in} = \sum I_{out}$$

```
       I₁
       ↓
    ───●───
   I₂ ↗ ↘ I₃
```

Here: $I_1 = I_2 + I_3$

### Kirchhoff's 2nd law — voltage law (KVL)
> **In a closed loop, the sum of source voltages equals the sum of voltage drops.**

$$\sum U_{source} = \sum U_{drop}$$

---

## 10.3 Series connection

Two or more components are **in series** when they are placed end-to-end — current has only one path.

```
  ┌──[R₁]──[R₂]──[R₃]──┐
  │                    │
  +─────[ U ]──────────+
```

### Rules for series connection

1. **Current is the same everywhere**:
$$I = I_1 = I_2 = I_3$$

2. **Voltage is shared** across the resistors:
$$U = U_1 + U_2 + U_3$$

3. **Equivalent resistance** = sum of resistances:
$$R_{tot} = R_1 + R_2 + R_3$$

### Example
3 resistors of 10, 20 and 30 Ω connected in series across 60 V.

$R_{tot} = 10 + 20 + 30 = 60$ Ω
$I = 60 / 60 = 1$ A
$U_1 = 1 · 10 = 10$ V
$U_2 = 1 · 20 = 20$ V
$U_3 = 1 · 30 = 30$ V
**Check**: $10 + 20 + 30 = 60$ V ✓

> 💡 **Voltage divider**: In a series, voltage divides **proportionally to the resistances**.

$$U_x = U \cdot \frac{R_x}{R_{tot}}$$

---

## 10.4 Parallel connection

Two or more components are **in parallel** when they are connected between the same two points — current has multiple paths.

```
       ┌─[R₁]─┐
       │      │
  ──●──┼─[R₂]─┼──●──
       │      │
       └─[R₃]─┘
```

### Rules for parallel connection

1. **Voltage is the same** across all:
$$U = U_1 = U_2 = U_3$$

2. **Currents add up**:
$$I = I_1 + I_2 + I_3$$

3. **Equivalent resistance**:
$$\frac{1}{R_{tot}} = \frac{1}{R_1} + \frac{1}{R_2} + \frac{1}{R_3}$$

### Special case — two resistors in parallel
$$R_{tot} = \frac{R_1 \cdot R_2}{R_1 + R_2}$$

### Special case — n equal resistors in parallel
$$R_{tot} = \frac{R}{n}$$

### Example
Two resistors 30 Ω and 60 Ω in parallel across 12 V:

$R_{tot} = \dfrac{30 \cdot 60}{30 + 60} = \dfrac{1800}{90} = 20$ Ω
$I = 12 / 20 = 0.6$ A
$I_1 = 12/30 = 0.4$ A
$I_2 = 12/60 = 0.2$ A
**Check**: $0.4 + 0.2 = 0.6$ A ✓

> 💡 **Key point**: The equivalent resistance in a parallel connection is always **smaller than the smallest** of the individual resistances.

---

## 10.5 Combined circuits

Solve them **step by step** — always start by simplifying the innermost series or parallel group.

### Example
$R_1 = 10$ Ω, $R_2 = 20$ Ω in parallel — in series with $R_3 = 14$ Ω.

**Step 1**: Calculate $R_{12}$ (parallel):
$$R_{12} = \frac{10 \cdot 20}{10 + 20} = 6.67 \text{ Ω}$$

**Step 2**: $R_{12}$ in series with $R_3$:
$$R_{tot} = 6.67 + 14 = 20.67 \text{ Ω}$$

> 🛠 [Use the interactive tool — Series & parallel](../../interaktiv/serie-parallel.html)

---

## 10.6 Power in circuits

### General
$$P = U \cdot I = I^2 \cdot R = \frac{U^2}{R}$$

### Power in series
Total power = sum of individual powers:
$$P_{tot} = P_1 + P_2 + P_3$$

In series the current is the same, so:
$$P_x = I^2 \cdot R_x$$

→ **The largest resistor dissipates the most power**.

### Power in parallel
Voltage is the same, so:
$$P_x = \frac{U^2}{R_x}$$

→ **The smallest resistor dissipates the most power**.

> ⚡ **Practical consequence**: In a series-connected light string, the bulb with the lowest resistance shines weakest. In parallel, the lowest-resistance bulb shines brightest.

---

## 10.7 Current and voltage dividers

### Voltage divider (series)
$$U_x = U \cdot \frac{R_x}{R_{tot}}$$

### Current divider (parallel — two resistors)
$$I_1 = I \cdot \frac{R_2}{R_1 + R_2}$$
$$I_2 = I \cdot \frac{R_1}{R_1 + R_2}$$

> 💡 Note the **swap** — the current through $R_1$ is proportional to $R_2$ (the opposite resistance).

---

## 10.8 Practical applications

### Fuses in series
A fuse is always in series with the appliance. If the current exceeds the rated value, the fuse blows and the circuit is broken.

### Voltmeter with multiplier resistor
To measure higher voltages than the meter's range, place a large resistor **in series**:
$$R_{mult} = R_v \cdot (n - 1)$$

where n is the ratio of new to old measuring range.

### Ammeter with shunt
To measure higher currents, place a small resistor (shunt) **in parallel**:
$$R_{shunt} = \frac{R_a}{n - 1}$$

---

## 10.9 Voltage drop in conductors

In practice, **all** wires have some resistance. The voltage drop is:
$$\Delta U = 2 \cdot l \cdot \frac{\rho \cdot I}{A}$$

(factor 2 because the current flows there and back)

> ⚡ **Installation rule**: Voltage drop should be kept below ~3% of the nominal voltage (typically 230 V → max ~7 V).

---

## 📌 Summary

- **Kirchhoff's 1st law** (current): sum of currents in = sum of currents out at any node.
- **Kirchhoff's 2nd law** (voltage): sum of voltages around a closed loop = 0.
- **Series connection**: current constant, voltages add, resistances add.
- **Parallel connection**: voltage constant, currents add, resistances: 1/R = 1/R₁ + 1/R₂ + ...
- **Voltage divider rule**: Uₓ = U · (Rₓ / R_total)
- **Power in series**: largest resistance = most power. **In parallel**: smallest resistance = most power.

---

## ➡️ Next steps

- 📝 [Exercises for chapter 10](../opgaver/10-opgaver.md)
- 🧮 [Series & parallel calculator](../../interaktiv/serie-parallel.html)
- ➡️ [Chapter 11 — Magnetism](11-magnetisme.md)
