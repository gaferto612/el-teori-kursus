# Chapter 1 — Numbers and basic arithmetic

**Language:** [🇩🇰 Dansk](../../da/kapitler/01-tal-og-grundlaeggende-regning.md) · **🇬🇧 English** · [🇸🇦 العربية](../../ar/kapitler/01-tal-og-grundlaeggende-regning.md)

## 🎯 Learning goals

After this chapter you should be able to:
- Recognise and use the different number sets (N, Z, Q, R)
- Calculate with signs (+ / −) in the four basic operations
- Convert between decimal, binary and hexadecimal
- Use powers, roots and parentheses correctly
- Recognise the Greek alphabet in technical formulas

---

## 1.1 Numbers and number sets

### Number sets

| Symbol | Name | Example |
|--------|------|---------|
| **N** | Natural numbers | 1, 2, 3, 4 ... |
| **Z** | Integers | ..., −2, −1, 0, 1, 2 ... |
| **Q** | Rational numbers | ½, 0.75, −3.14 |
| **R** | Real numbers | All of the above + irrationals (π, √2) |

> 💡 In electrical engineering we work almost exclusively with **real numbers (R)** — and later complex numbers when we reach AC theory.

### Number systems

Our usual number system is the **base-10** (decimal) system with digits 0–9.

Example: The number **1994** means:
$$1 \cdot 10^3 + 9 \cdot 10^2 + 9 \cdot 10^1 + 4 \cdot 10^0$$

In electronics we also use:

| System | Base | Digits | Used for |
|--------|------|--------|----------|
| **Binary** | 2 | 0, 1 | Digital electronics, PLC |
| **Octal** | 8 | 0–7 | Rare, older systems |
| **Hexadecimal** | 16 | 0–9, A–F | Microprocessors, memory |

---

## 1.2 The four basic operations

### Addition and subtraction

**Addition**: order does not matter.
$$a + b = b + a$$

**Subtraction**: order **does** matter.
$$a - b \neq b - a$$

### Multiplication and division

**Multiplication**: order does not matter.
$$a \cdot b = b \cdot a$$

**Division**: order **does** matter.
$$\frac{a}{b} \neq \frac{b}{a}$$

### Sign rules

| Operation | Rule | Example |
|-----------|------|---------|
| (+) · (+) | = + | 3 · 4 = 12 |
| (+) · (−) | = − | 3 · (−4) = −12 |
| (−) · (−) | = + | (−3) · (−4) = 12 |
| (+) / (+) | = + | 12 / 4 = 3 |
| (+) / (−) | = − | 12 / (−4) = −3 |
| (−) / (−) | = + | (−12) / (−4) = 3 |

> 💡 **Memory aid**: Same signs → positive. Different signs → negative.

---

## 1.3 Parentheses and order of operations

**Order**:
1. **Parentheses** — `( )` first
2. **Powers and roots** — `x²`, `√x`
3. **Multiplication and division** — left to right
4. **Addition and subtraction** — left to right

> Mnemonic: **PEMDAS** (Parentheses, Exponents, Multiplication, Division, Addition, Subtraction).

### Example
$$3 + 4 \cdot (5 - 2)^2 = 3 + 4 \cdot 3^2 = 3 + 4 \cdot 9 = 3 + 36 = 39$$

---

## 1.4 Powers and roots

### Power

$$a^n = \underbrace{a \cdot a \cdot a \cdot \ldots \cdot a}_{n \text{ times}}$$

**Rules:**
- $a^m \cdot a^n = a^{m+n}$
- $\dfrac{a^m}{a^n} = a^{m-n}$
- $(a^m)^n = a^{m \cdot n}$
- $a^0 = 1$ (when $a \neq 0$)
- $a^{-n} = \dfrac{1}{a^n}$

### Root

$$\sqrt[n]{a} = a^{1/n}$$

Square root: $\sqrt{a} = a^{1/2}$

> ⚡ In electrical theory the square root appears everywhere — for example when calculating **RMS values** ($U_{rms} = U_{peak} / \sqrt{2}$).

---

## 1.5 The Greek alphabet

Greek letters are used constantly in technical formulas. Here are the most important in electrical engineering:

| Letter | Upper | Lower | Used for |
|--------|-------|-------|----------|
| Alpha | Α | α | Angle, temperature coefficient |
| Beta | Β | β | Angle, transistor current gain |
| Gamma | Γ | γ | Conductivity |
| Delta | Δ | δ | Difference, change (ΔU = voltage drop) |
| Theta | Θ | θ | Angle, temperature |
| Lambda | Λ | λ | Wavelength, air-fuel ratio |
| Mu | Μ | μ | Micro (10⁻⁶), permeability |
| Pi | Π | π | 3.14159... (circle constant) |
| Rho | Ρ | ρ | Resistivity |
| Sigma | Σ | σ | Sum, conductivity |
| Phi | Φ | φ | Magnetic flux, phase angle |
| Omega | Ω | ω | Ohm (resistance), angular velocity |

---

## 1.6 Conversion between number systems

### Decimal → Binary

Divide repeatedly by 2 and note the remainders **read bottom-up**:

```
456 : 2 = 228  remainder 0
228 : 2 = 114  remainder 0
114 : 2 = 57   remainder 0
 57 : 2 = 28   remainder 1
 28 : 2 = 14   remainder 0
 14 : 2 = 7    remainder 0
  7 : 2 = 3    remainder 1
  3 : 2 = 1    remainder 1
  1 : 2 = 0    remainder 1
```

**Read bottom to top:** 456₁₀ = **111001000**₂

### Binary → Decimal

Multiply each digit by 2 raised to the corresponding power:

$$10101_2 = 1\cdot 2^4 + 0\cdot 2^3 + 1\cdot 2^2 + 0\cdot 2^1 + 1\cdot 2^0 = 16 + 4 + 1 = 21_{10}$$

### Hex table

| Decimal | Binary | Hex |
|---------|--------|-----|
| 0 | 0000 | 0 |
| 1 | 0001 | 1 |
| 5 | 0101 | 5 |
| 10 | 1010 | A |
| 15 | 1111 | F |

> 🛠 Use the interactive tool: [**Number-system converter**](../../interaktiv/talsystem-konverter.html)

---

## 📌 Summary

- **Numbers are split into:** Natural (N) ⊆ Integers (Z) ⊆ Rationals (Q) ⊆ Reals (R).
- **Number systems:** decimal (base 10), binary (2), hexadecimal (16) — binary is essential in digital electronics.
- **Sign rules in multiplication/division:** same signs = positive, different signs = negative.
- **Order of operations:** parentheses → powers → multiplication/division → addition/subtraction.
- **The Greek alphabet** is used heavily: Ω (ohm), π (pi), μ (micro), Δ (delta = difference).

---

## ➡️ Next steps

- 📝 [Exercises for chapter 1](../opgaver/01-opgaver.md)
- 🧮 [Number-system converter (interactive)](../../interaktiv/talsystem-konverter.html)
- ➡️ [Chapter 2 — Geometry](02-geometri.md)
