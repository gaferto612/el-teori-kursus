# Kapitel 2 — Geometri
> الهندسة

## 🎯 Læringsmål

- Beregne areal og omkreds af de vigtigste figurer
- Beregne overflade og rumfang af legemer
- Bruge Pythagoras' læresætning
- Forstå vinkler og deres egenskaber

---

## 2.1 Vinkler (الزوايا)

| Type | Område | الزاوية |
|------|--------|---------|
| Spids vinkel | 0° < v < 90° | حادة |
| Ret vinkel | v = 90° | قائمة |
| Stump vinkel | 90° < v < 180° | منفرجة |
| Lige vinkel | v = 180° | مستقيمة |
| Hel vinkel | v = 360° | كاملة |

**Vinkelsum i en trekant**: altid 180°.
$$\angle A + \angle B + \angle C = 180°$$

---

## 2.2 Plane figurer — areal og omkreds

### Trekant (المثلث)

- Omkreds: $O = a + b + c$
- Areal: $A = \dfrac{1}{2} \cdot h \cdot g$ (hvor h = højde, g = grundlinje)

### Rektangel (المستطيل)

- Omkreds: $O = 2(a + b)$
- Areal: $A = a \cdot b$

### Kvadrat (المربع)

- Omkreds: $O = 4a$
- Areal: $A = a^2$

### Cirkel (الدائرة)

- Omkreds: $O = 2\pi r = \pi d$
- Areal: $A = \pi r^2$

> 💡 $\pi$ = 3,14159... bruges i alle cirkelberegninger.

### Parallellogram (متوازي الأضلاع)

- Omkreds: $O = 2(a + b)$
- Areal: $A = a \cdot h$

### Trapez (شبه المنحرف)

- Areal: $A = \dfrac{a + b}{2} \cdot h$

---

## 2.3 Pythagoras' læresætning

> **For en retvinklet trekant** gælder:
> $$a^2 + b^2 = c^2$$
> hvor c er hypotenusen (den længste side, modsat den rette vinkel).

نظرية فيثاغورس: في المثلث القائم الزاوية، مربع الوتر = مجموع مربعي الضلعين الآخرين.

### Eksempel

En retvinklet trekant har kateterne 3 og 4. Find hypotenusen:
$$c = \sqrt{3^2 + 4^2} = \sqrt{9 + 16} = \sqrt{25} = 5$$

> ⚡ **El-relevant**: Pythagoras bruges direkte i vekselstrømsberegninger til at finde **scheinleistung** (S) ud fra effektiv effekt (P) og reaktiv effekt (Q):
> $$S^2 = P^2 + Q^2$$

---

## 2.4 Legemer (rumfigurer)

### Terning / kasse (المكعب / متوازي المستطيلات)

- Rumfang: $V = a \cdot b \cdot c$
- Overfladeareal: $O = 2(ab + bc + ac)$

### Cylinder (الأسطوانة)

- Rumfang: $V = \pi r^2 \cdot h$
- Overflade (sider + bund + top): $O = 2\pi r h + 2\pi r^2$

### Kugle (الكرة)

- Rumfang: $V = \dfrac{4}{3} \pi r^3$
- Overflade: $O = 4\pi r^2$

### Kegle (المخروط)

- Rumfang: $V = \dfrac{1}{3} \pi r^2 h$

---

## 2.5 Hvorfor er geometri vigtig i el-teknik?

| Anvendelse | Eksempel |
|-----------|----------|
| **Tværsnitsareal** af leder | Bestemmer modstand: $R = \rho \cdot \dfrac{l}{A}$ |
| **Spole-vindinger** | Areal af kerne påvirker induktion |
| **Effekttrekant** | $S = \sqrt{P^2 + Q^2}$ (Pythagoras) |
| **Faseforskel** | Vinkler i vektordiagrammer |

---

## 📌 Resumé på arabisk

- **مساحة الدائرة** = π × r²، **محيطها** = 2πr.
- **مساحة المثلث** = ½ × القاعدة × الارتفاع.
- **نظرية فيثاغورس**: a² + b² = c² (في المثلث القائم).
- **حجم الأسطوانة** = πr²h، **حجم الكرة** = 4/3 πr³.
- في الكهرباء: تُستخدم الهندسة لحساب مساحة المقطع، وفي مثلث القدرة (S² = P² + Q²).

---

## ➡️ Næste skridt

- 📝 [Opgaver til kapitel 2](../opgaver/02-opgaver.md)
- ➡️ [Kapitel 3 — Trigonometri](03-trigonometri.md)
