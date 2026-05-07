# Kapitel 3 — Trigonometri
> علم المثلثات

## 🎯 Læringsmål

- Anvende sin, cos, tan i retvinklede trekanter
- Forstå sammenhængen mellem vinkler og sider
- Bruge trigonometri til vekselstrømsberegninger

---

## 3.1 Trekantens sider

I en **retvinklet trekant** (hvor en vinkel er 90°) har siderne specielle navne i forhold til en valgt spids vinkel **v**:

```
              |\
              | \
   modstående |  \ hypotenuse
   katete     |   \
              |    \
              |__v__\
              hosliggende katete
```

| Side (DA) | Side (AR) | Definition |
|-----------|-----------|------------|
| **Hypotenuse** | الوتر | Modsat den rette vinkel (længst) |
| **Modstående katete** | الضلع المقابل | Modsat vinklen v |
| **Hosliggende katete** | الضلع المجاور | Ved vinklen v |

---

## 3.2 De trigonometriske funktioner

$$\sin(v) = \frac{\text{modstående}}{\text{hypotenuse}}$$

$$\cos(v) = \frac{\text{hosliggende}}{\text{hypotenuse}}$$

$$\tan(v) = \frac{\text{modstående}}{\text{hosliggende}}$$

> 🇸🇦 **حفظ النسب**: جا (sin) = المقابل/الوتر، جتا (cos) = المجاور/الوتر، ظا (tan) = المقابل/المجاور.

### Huskeregel (DA)
**S**ome **O**ld **H**ippie **C**aught **A**nother **H**ippie **T**rippin' **O**n **A**cid:
- **S**in = **O**pposite / **H**ypotenuse
- **C**os = **A**djacent / **H**ypotenuse
- **T**an = **O**pposite / **A**djacent

---

## 3.3 Specielle vinkler — værdier udenad

| Vinkel | sin | cos | tan |
|--------|-----|-----|-----|
| 0° | 0 | 1 | 0 |
| 30° | 0,5 | 0,866 | 0,577 |
| 45° | 0,707 | 0,707 | 1 |
| 60° | 0,866 | 0,5 | 1,732 |
| 90° | 1 | 0 | ∞ |

> 💡 Bemærk: $\sin(45°) = \cos(45°) = \dfrac{1}{\sqrt{2}} \approx 0{,}707$ — denne værdi dukker op konstant i AC-teknik (fx peak/RMS).

---

## 3.4 Anvendelse i el-teknik

### Vekselstrømsformel
En sinusformet vekselspænding beskrives ved:
$$u(t) = U_{peak} \cdot \sin(\omega t)$$

hvor $\omega = 2\pi f$ er **vinkelhastigheden** (rad/s).

### Effektfaktor (cos φ)
For en induktiv last, hvor strøm og spænding er fasforskudt med vinklen φ:

$$P = U \cdot I \cdot \cos(\varphi)$$

| cos φ | Type belastning |
|-------|-----------------|
| 1,0 | Rent ohmsk (fx varmelegeme) |
| 0,8 | Typisk motor under last |
| 0,5 | Kraftigt induktiv (motor i tomgang) |
| 0 | Rent reaktiv (ideel spole/kondensator) |

### Effekttrekanten

```
       S (VA - tilsyneladende effekt)
       /|
      / |
     /  |
    /   | Q (var - reaktiv effekt)
   /    |
  / φ   |
 /______|
   P (W - virkeeffekt)
```

$$P = S \cdot \cos(\varphi)$$
$$Q = S \cdot \sin(\varphi)$$
$$S = \sqrt{P^2 + Q^2}$$

---

## 3.5 Pythagoras' og trigonometriens forhold

I enhver retvinklet trekant gælder også:
$$\sin^2(v) + \cos^2(v) = 1$$

Det er Pythagoras anvendt på enhedscirklen.

---

## 📌 Resumé på arabisk

- **النسب الأساسية**: جا = المقابل/الوتر، جتا = المجاور/الوتر، ظا = المقابل/المجاور.
- **زاوية 45°**: sin = cos ≈ 0,707 — مهم في حساب القيمة الفعالة (RMS) للتيار المتردد.
- **معامل القدرة** cos φ: يربط القدرة الفعلية (P) بالقدرة الظاهرية (S): P = U·I·cos φ.
- **مثلث القدرة**: S² = P² + Q² (نفس قانون فيثاغورس).

---

## ➡️ Næste skridt

- 📝 [Opgaver til kapitel 3](../opgaver/03-opgaver.md)
- ➡️ [Kapitel 4 — Aritmetik](04-aritmetik.md)
