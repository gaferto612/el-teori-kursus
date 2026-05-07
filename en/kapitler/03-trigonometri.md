# Chapter 3 — Trigonometry

**Language:** [🇩🇰 Dansk](../../da/kapitler/03-trigonometri.md) · **🇬🇧 English** · [🇸🇦 العربية](../../ar/kapitler/03-trigonometri.md)

## 🎯 Learning goals

- Apply sin, cos, tan in right triangles
- Understand the relationship between angles and sides
- Use trigonometry for AC calculations

---

## 3.1 Sides of a triangle

In a **right triangle** (where one angle is 90°) the sides have specific names relative to a chosen acute angle **v**:

```
              |\
              | \
       opposite\  \ hypotenuse
       leg     |   \
              |    \
              |__v__\
              adjacent leg
```

| Side | Definition |
|------|------------|
| **Hypotenuse** | Opposite the right angle (longest) |
| **Opposite leg** | Opposite to angle v |
| **Adjacent leg** | Next to angle v |

---

## 3.2 The trigonometric functions

$$\sin(v) = \frac{\text{opposite}}{\text{hypotenuse}}$$

$$\cos(v) = \frac{\text{adjacent}}{\text{hypotenuse}}$$

$$\tan(v) = \frac{\text{opposite}}{\text{adjacent}}$$

### Mnemonic
**SOH-CAH-TOA**:
- **S**in = **O**pposite / **H**ypotenuse
- **C**os = **A**djacent / **H**ypotenuse
- **T**an = **O**pposite / **A**djacent

---

## 3.3 Special angles — values to memorise

| Angle | sin | cos | tan |
|-------|-----|-----|-----|
| 0° | 0 | 1 | 0 |
| 30° | 0.5 | 0.866 | 0.577 |
| 45° | 0.707 | 0.707 | 1 |
| 60° | 0.866 | 0.5 | 1.732 |
| 90° | 1 | 0 | ∞ |

> 💡 Note: $\sin(45°) = \cos(45°) = \dfrac{1}{\sqrt{2}} \approx 0.707$ — this value appears constantly in AC engineering (e.g. peak/RMS).

---

## 3.4 Application in electrical engineering

### AC formula
A sinusoidal AC voltage is described by:
$$u(t) = U_{peak} \cdot \sin(\omega t)$$

where $\omega = 2\pi f$ is the **angular frequency** (rad/s).

### Power factor (cos φ)
For an inductive load where current and voltage are phase-shifted by angle φ:

$$P = U \cdot I \cdot \cos(\varphi)$$

| cos φ | Load type |
|-------|-----------|
| 1.0 | Purely resistive (e.g. heating element) |
| 0.8 | Typical motor under load |
| 0.5 | Strongly inductive (idle motor) |
| 0 | Purely reactive (ideal coil/capacitor) |

### The power triangle

```
       S (VA - apparent power)
       /|
      / |
     /  |
    /   | Q (var - reactive power)
   /    |
  / φ   |
 /______|
   P (W - real power)
```

$$P = S \cdot \cos(\varphi)$$
$$Q = S \cdot \sin(\varphi)$$
$$S = \sqrt{P^2 + Q^2}$$

---

## 3.5 The relationship between Pythagoras and trigonometry

In every right triangle:
$$\sin^2(v) + \cos^2(v) = 1$$

This is Pythagoras applied to the unit circle.

---

## 📌 Summary

- **Basic ratios**: sin = opposite/hypotenuse, cos = adjacent/hypotenuse, tan = opposite/adjacent.
- **45° angle**: sin = cos ≈ 0.707 — important for calculating RMS values in AC.
- **Power factor** cos φ: links real power (P) to apparent power (S): P = U·I·cos φ.
- **Power triangle**: S² = P² + Q² (same as Pythagoras).

---

## ➡️ Next steps

- 📝 [Exercises for chapter 3](../opgaver/03-opgaver.md)
- ➡️ [Chapter 4 — Algebra](04-aritmetik.md)
