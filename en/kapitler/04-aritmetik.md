# Chapter 4 — Algebra

**Language:** [🇩🇰 Dansk](../../da/kapitler/04-aritmetik.md) · **🇬🇧 English** · [🇸🇦 العربية](../../ar/kapitler/04-aritmetik.md)

## 🎯 Learning goals

- Solve first-degree equations with one unknown
- Isolate a variable in a formula
- Calculate with fractions and ratios
- Use direct and inverse proportionality

---

## 4.1 Equations with one unknown

An **equation** is two expressions connected by an equals sign.

Example:
$$3x + 5 = 20$$

**The rule**: Whatever we do to one side, we must also do to the other.

**Solution**:
- Subtract 5 from both sides: $3x = 15$
- Divide both sides by 3: $x = 5$

> 💡 Remember: When you move a term to the other side of the equals sign, it **changes sign**.

### Example — electrical engineering

Ohm's law: $U = R \cdot I$

To isolate R:
$$R = \frac{U}{I}$$

To isolate I:
$$I = \frac{U}{R}$$

---

## 4.2 Fractions

### Rules

**Addition/subtraction** (requires a common denominator):
$$\frac{a}{c} + \frac{b}{c} = \frac{a + b}{c}$$

$$\frac{a}{b} + \frac{c}{d} = \frac{a \cdot d + c \cdot b}{b \cdot d}$$

**Multiplication**:
$$\frac{a}{b} \cdot \frac{c}{d} = \frac{a \cdot c}{b \cdot d}$$

**Division**:
$$\frac{a}{b} : \frac{c}{d} = \frac{a}{b} \cdot \frac{d}{c} = \frac{a \cdot d}{b \cdot c}$$

> 💡 **Golden rule**: When dividing a fraction by a fraction, flip the second and multiply.

### Reduction
$$\frac{12}{18} = \frac{12 : 6}{18 : 6} = \frac{2}{3}$$

---

## 4.3 Ratios and proportions

### Ratio

A ratio between a and b is written:
$$a : b \quad \text{or} \quad \frac{a}{b}$$

### Direct proportionality

When one quantity grows, the other grows proportionally:
$$y = k \cdot x$$

**Example** — Ohm's law with constant R:
- Voltage doubles → current doubles
- $U \propto I$

### Inverse proportionality

When one grows, the other shrinks:
$$y = \frac{k}{x}$$

**Example** — Ohm's law with constant U:
- Resistance doubles → current halves
- $I \propto \dfrac{1}{R}$

---

## 4.4 Percent

$$x\% = \frac{x}{100}$$

### Percent of a number
"Find 25% of 80":
$$80 \cdot 0.25 = 20$$

### Percentage change between two values
"What percentage increase from 50 to 65?":
$$\frac{65 - 50}{50} \cdot 100\% = 30\%$$

### Application — efficiency (η)

$$\eta = \frac{P_{out}}{P_{in}} \cdot 100\%$$

A motor has 85% efficiency if it outputs 850 W while drawing 1000 W.

---

## 4.5 Working with formulas — isolating variables

### Power formula
$$P = U \cdot I$$

| To isolate | Formula |
|------------|---------|
| U | $U = \dfrac{P}{I}$ |
| I | $I = \dfrac{P}{U}$ |

### Power with resistance
$$P = U \cdot I = I^2 \cdot R = \frac{U^2}{R}$$

| To isolate | Formula |
|------------|---------|
| R from $P = I^2 R$ | $R = \dfrac{P}{I^2}$ |
| U from $P = \dfrac{U^2}{R}$ | $U = \sqrt{P \cdot R}$ |

> 💡 When isolating from a square, you take the **square root**.

---

## 4.6 Quadratic equations (briefly)

An equation of the form:
$$ax^2 + bx + c = 0$$

is solved with the discriminant formula:
$$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$

> ⚡ Rarely used directly in basic electrical theory, but it can appear when calculating resonance frequency or optima.

---

## 📌 Summary

- **Solving an equation**: whatever you do to one side, you do to the other.
- **Moving a term** across the equals sign changes its sign.
- **Direct proportionality**: y = k·x (e.g. U = R·I with constant R).
- **Inverse proportionality**: y = k/x (e.g. I = U/R with constant U).
- **Efficiency** as percentage: η = (P_out / P_in) × 100%.

---

## ➡️ Next steps

- 📝 [Exercises for chapter 4](../opgaver/04-opgaver.md)
- ➡️ [Chapter 5 — Binary arithmetic](05-binaer-regning.md)
