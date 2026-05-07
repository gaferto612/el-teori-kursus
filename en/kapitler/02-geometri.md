# Chapter 2 — Geometry

**Language:** [🇩🇰 Dansk](../../da/kapitler/02-geometri.md) · **🇬🇧 English** · [🇸🇦 العربية](../../ar/kapitler/02-geometri.md)

## 🎯 Learning goals

- Calculate area and perimeter of the most important shapes
- Calculate surface area and volume of solids
- Use the Pythagorean theorem
- Understand angles and their properties

---

## 2.1 Angles

| Type | Range |
|------|-------|
| Acute angle | 0° < v < 90° |
| Right angle | v = 90° |
| Obtuse angle | 90° < v < 180° |
| Straight angle | v = 180° |
| Full angle | v = 360° |

**Sum of angles in a triangle**: always 180°.
$$\angle A + \angle B + \angle C = 180°$$

---

## 2.2 Plane figures — area and perimeter

### Triangle

- Perimeter: $P = a + b + c$
- Area: $A = \dfrac{1}{2} \cdot h \cdot b$ (where h = height, b = base)

### Rectangle

- Perimeter: $P = 2(a + b)$
- Area: $A = a \cdot b$

### Square

- Perimeter: $P = 4a$
- Area: $A = a^2$

### Circle

- Circumference: $C = 2\pi r = \pi d$
- Area: $A = \pi r^2$

> 💡 $\pi$ = 3.14159... is used in all circle calculations.

### Parallelogram

- Perimeter: $P = 2(a + b)$
- Area: $A = a \cdot h$

### Trapezoid

- Area: $A = \dfrac{a + b}{2} \cdot h$

---

## 2.3 The Pythagorean theorem

> **For a right triangle**:
> $$a^2 + b^2 = c^2$$
> where c is the hypotenuse (the longest side, opposite the right angle).

### Example

A right triangle has legs of length 3 and 4. Find the hypotenuse:
$$c = \sqrt{3^2 + 4^2} = \sqrt{9 + 16} = \sqrt{25} = 5$$

> ⚡ **Electrical relevance**: Pythagoras is used directly in AC calculations to find **apparent power** (S) from real power (P) and reactive power (Q):
> $$S^2 = P^2 + Q^2$$

---

## 2.4 Solids (3D figures)

### Cube / box

- Volume: $V = a \cdot b \cdot c$
- Surface area: $S = 2(ab + bc + ac)$

### Cylinder

- Volume: $V = \pi r^2 \cdot h$
- Surface (sides + top + bottom): $S = 2\pi r h + 2\pi r^2$

### Sphere

- Volume: $V = \dfrac{4}{3} \pi r^3$
- Surface area: $S = 4\pi r^2$

### Cone

- Volume: $V = \dfrac{1}{3} \pi r^2 h$

---

## 2.5 Why is geometry important in electrical engineering?

| Application | Example |
|-------------|---------|
| **Cross-sectional area** of conductor | Determines resistance: $R = \rho \cdot \dfrac{l}{A}$ |
| **Coil windings** | Core area affects inductance |
| **Power triangle** | $S = \sqrt{P^2 + Q^2}$ (Pythagoras) |
| **Phase shift** | Angles in vector diagrams |

---

## 📌 Summary

- **Area of a circle** = π × r², **circumference** = 2πr.
- **Area of a triangle** = ½ × base × height.
- **Pythagorean theorem**: a² + b² = c² (in a right triangle).
- **Volume of cylinder** = πr²h, **volume of sphere** = 4/3 πr³.
- In electrical engineering: geometry is used to calculate cross-sectional area and in the power triangle (S² = P² + Q²).

---

## ➡️ Next steps

- 📝 [Exercises for chapter 2](../opgaver/02-opgaver.md)
- ➡️ [Chapter 3 — Trigonometry](03-trigonometri.md)
