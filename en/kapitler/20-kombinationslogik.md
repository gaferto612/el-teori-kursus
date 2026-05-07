# Chapter 20 — Combinational logic

**Language:** [🇩🇰 Dansk](../../da/kapitler/20-kombinationslogik.md) · **🇬🇧 English** · [🇸🇦 العربية](../../ar/kapitler/20-kombinationslogik.md)

## 🎯 Learning goals

- Understand logic levels (0 / 1, low / high)
- Know the basic logic gates: AND, OR, NOT
- Apply NAND, NOR, XOR, XNOR
- Read and construct truth tables
- Understand Boolean algebra and simplification

---

## 20.1 Digital systems

In automation, two-state systems are used:

| Mechanical | Electronic |
|------------|------------|
| Contact **closed** = ON | Logical **1** (HIGH) |
| Contact **open** = OFF | Logical **0** (LOW) |

### Voltage levels

| Family | Supply | Logical 0 | Logical 1 |
|--------|--------|-----------|-----------|
| **TTL** | 5 V | 0–0.8 V | 2.0–5.0 V |
| **CMOS** | 3–18 V | 0–30% of V | 70–100% of V |
| **3.3V CMOS** | 3.3 V | 0–0.8 V | 2.0–3.3 V |

> 💡 **Inputs must never "float"** (be unconnected). Use a pull-up or pull-down resistor to ensure a defined logic level.

---

## 20.2 The basic gates

### NOT gate (inverter)

| A | Y |
|---|---|
| 0 | 1 |
| 1 | 0 |

Symbol:
```
   A ──[>○──── Y    (circle = inversion)
```

Function: $Y = \overline{A}$

### AND gate

| A | B | Y |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

Symbol: D-shaped
$$Y = A \cdot B$$

> 💡 **AND** = "BOTH A AND B must be ON".

### OR gate

| A | B | Y |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

Symbol: shield-shaped
$$Y = A + B$$

> 💡 **OR** = "AT LEAST ONE of A or B must be ON".

---

## 20.3 Combined gates

### NAND (NOT AND)

| A | B | Y |
|---|---|---|
| 0 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | **0** |

$$Y = \overline{A \cdot B}$$

> ⚙ **NAND is the most flexible gate** — you can build ALL other logic functions using only NAND gates!

### NOR (NOT OR)

| A | B | Y |
|---|---|---|
| 0 | 0 | **1** |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 0 |

$$Y = \overline{A + B}$$

### XOR (Exclusive OR)

| A | B | Y |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | **0** |

$$Y = A \oplus B$$

> 💡 XOR is **1** when the inputs are **different**.

### XNOR (Exclusive NOR)

| A | B | Y |
|---|---|---|
| 0 | 0 | 1 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

XNOR is **1** when the inputs are **the same** = "equal" detector.

---

## 20.4 Comparison table

| Gate | Symbol shape | Function (HIGH when...) |
|------|--------------|-------------------------|
| AND | D | All inputs are HIGH |
| OR | shield | At least one input is HIGH |
| NOT | triangle + circle | Input is LOW |
| NAND | D + circle | At least one input is LOW |
| NOR | shield + circle | All inputs are LOW |
| XOR | shield with extra arc | Inputs are different |
| XNOR | XOR + circle | Inputs are the same |

> 🛠 [Use the interactive tool — Logic gates](../../interaktiv/logik-gates.html)

---

## 20.5 Boolean algebra

### Basic rules

| Rule | Algebra |
|------|---------|
| Identity | $A + 0 = A$, $A \cdot 1 = A$ |
| Annulment | $A + 1 = 1$, $A \cdot 0 = 0$ |
| Idempotence | $A + A = A$, $A \cdot A = A$ |
| Complement | $A + \overline{A} = 1$, $A \cdot \overline{A} = 0$ |
| Double negation | $\overline{\overline{A}} = A$ |
| Commutative | $A + B = B + A$, $A \cdot B = B \cdot A$ |
| Associative | $(A+B)+C = A+(B+C)$ |
| Distributive | $A(B+C) = AB + AC$ |

### De Morgan's laws

> **Important** — used constantly in simplification:
>
> $$\overline{A \cdot B} = \overline{A} + \overline{B}$$
> $$\overline{A + B} = \overline{A} \cdot \overline{B}$$

In words: "negation of an AND = OR of negations", and vice versa.

### Example — simplification

Simplify: $Y = A\overline{B} + AB$

Use the distributive law:
$$Y = A(\overline{B} + B) = A \cdot 1 = A$$

→ A complex circuit reduces to **just A**!

---

## 20.6 Truth tables with multiple inputs

### 3-input AND
| A | B | C | Y |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 0 |
| 0 | 1 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 0 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 0 |
| 1 | 1 | 1 | 1 |

$$Y = A \cdot B \cdot C$$

### Number of combinations
For n inputs: $2^n$ rows.
- 2 inputs → 4 rows
- 3 inputs → 8 rows
- 4 inputs → 16 rows
- 8 inputs → 256 rows

---

## 20.7 Examples — from words to logic

### Example 1 — Pump control
The pump should start if:
- Level is low (LL)
- **AND** switch is closed (S)
- **AND** there is no alarm (¬AL)

$$P = LL \cdot S \cdot \overline{AL}$$

→ Use a 3-input AND gate.

### Example 2 — Alarm
The alarm should sound if:
- Fire detector (FI)
- **OR** smoke detector (SM)
- **OR** manual button (M)

$$ALARM = FI + SM + M$$

→ Use a 3-input OR gate.

### Example 3 — Safety interlock
The machine can start if:
- Guard is closed (G)
- **AND** there is **either** a start button (B) **or** auto start (A)
- **AND** no emergency stop (¬ES)

$$START = G \cdot (B + A) \cdot \overline{ES}$$

→ Combination of AND and OR.

---

## 20.8 Logic IC families

### Common TTL/CMOS ICs

| IC no. | Function |
|--------|----------|
| 7400 | Quad NAND |
| 7402 | Quad NOR |
| 7404 | Hex NOT |
| 7408 | Quad AND |
| 7432 | Quad OR |
| 7486 | Quad XOR |
| 4001 | Quad NOR (CMOS) |
| 4011 | Quad NAND (CMOS) |
| 4081 | Quad AND (CMOS) |

> 📦 "Quad" = 4 in one package. "Hex" = 6.

### More complex logic functions
- **74138** — 3-to-8 decoder
- **74148** — 8-to-3 priority encoder
- **7474** — D flip-flop
- **74161** — 4-bit binary counter
- **74181** — 4-bit ALU

---

## 20.9 Hardware vs. PLC software

### Earlier
Logic circuits were built with discrete ICs.

### Today
**Programmable Logic Controllers (PLCs)** have taken over in industry:
- Logic is programmed in software (Ladder Logic, FBD, ST)
- Flexible — change the program without rewiring
- Standard platforms: Siemens TIA Portal, Allen-Bradley, Beckhoff, CODESYS

### Example in Ladder Logic (Siemens)
```
   I0.0     I0.1            Q0.0
   ─┤├──────┤├──────────────( )
   start    safety           motor
```

→ Motor (Q0.0) turns on if Start (I0.0) **AND** Safety (I0.1).
→ It is just an AND gate in software form!

> 🛠 PLCs are everyday tools in automation, chemical plants, water utilities and combined heat and power plants.

---

## 📌 Summary

- **Digital logic** operates on two states: 0 (LOW) and 1 (HIGH).
- **The three basic gates**:
  - **AND**: output is 1 only if all inputs are 1.
  - **OR**: output is 1 if any input is 1.
  - **NOT**: inverter — flips 0 to 1 and vice versa.
- **Combined gates**: NAND, NOR, XOR (exclusive OR).
- **NAND is the universal gate** — all other logic can be built from it.
- **De Morgan's laws**: $\overline{AB} = \overline{A} + \overline{B}$ and $\overline{A+B} = \overline{A}\cdot\overline{B}$.
- **Today**: logic is implemented in PLCs (e.g. Siemens TIA) via Ladder Logic programming — simpler and more flexible than discrete gates.

---

## ➡️ Next steps

- 📝 [Exercises for chapter 20](../opgaver/20-opgaver.md)
- 🧮 [Logic-gate simulator (interactive)](../../interaktiv/logik-gates.html)
- ➡️ [Chapter 21 — Instrument types](21-instrumenttyper.md)
