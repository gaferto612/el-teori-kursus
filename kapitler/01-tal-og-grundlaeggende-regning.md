# Kapitel 1 — Tal og grundlæggende regning
> الأرقام والحساب الأساسي

## 🎯 Læringsmål

Efter dette kapitel skal du kunne:
- Genkende og bruge de forskellige talmængder (N, Z, Q, R)
- Regne med fortegn (+ / −) i de fire regnearter
- Konvertere mellem decimal, binær og hexadecimal
- Bruge potens, rod og parenteser korrekt
- Forstå det græske alfabet i tekniske formler

---

## 1.1 Tal og talmængder

### Talmængder (مجموعات الأرقام)

| Symbol | Navn (DA) | Navn (AR) | Eksempel |
|--------|-----------|-----------|----------|
| **N** | Naturlige tal | الأعداد الطبيعية | 1, 2, 3, 4 ... |
| **Z** | Hele tal | الأعداد الصحيحة | ..., −2, −1, 0, 1, 2 ... |
| **Q** | Rationelle tal | الأعداد النسبية | ½, 0,75, −3,14 |
| **R** | Reelle tal | الأعداد الحقيقية | Alle tal ovenfor + irrationelle (π, √2) |

> 💡 Inden for elektroteknik arbejder vi næsten udelukkende med **reelle tal (R)** — og senere komplekse tal når vi når til vekselstrøm.

### Talsystemer (أنظمة الأرقام)

Vores normale talsystem er **10-talsystemet** (decimalsystemet) med cifrene 0–9.

Eksempel: Tallet **1994** betyder:
$$1 \cdot 10^3 + 9 \cdot 10^2 + 9 \cdot 10^1 + 4 \cdot 10^0$$

Inden for elektronik bruger vi også:

| System | Basis | Cifre | Bruges til |
|--------|-------|-------|------------|
| **Binær** (الثنائي) | 2 | 0, 1 | Digital elektronik, PLC |
| **Oktal** (الثماني) | 8 | 0–7 | Sjælden, ældre systemer |
| **Hexadecimal** (السادس عشر) | 16 | 0–9, A–F | Mikroprocessorer, hukommelse |

---

## 1.2 De fire regnearter

### Addition og subtraktion

**Addition** (الجمع): rækkefølgen er ligegyldig.
$$a + b = b + a$$

**Subtraktion** (الطرح): rækkefølgen er **ikke** ligegyldig.
$$a - b \neq b - a$$

### Multiplikation og division

**Multiplikation** (الضرب): rækkefølgen er ligegyldig.
$$a \cdot b = b \cdot a$$

**Division** (القسمة): rækkefølgen er **ikke** ligegyldig.
$$\frac{a}{b} \neq \frac{b}{a}$$

### Regning med fortegn

| Operation | Regel | Eksempel |
|-----------|-------|----------|
| (+) · (+) | = + | 3 · 4 = 12 |
| (+) · (−) | = − | 3 · (−4) = −12 |
| (−) · (−) | = + | (−3) · (−4) = 12 |
| (+) / (+) | = + | 12 / 4 = 3 |
| (+) / (−) | = − | 12 / (−4) = −3 |
| (−) / (−) | = + | (−12) / (−4) = 3 |

> 🇸🇦 **Huskeregel**: قاعدة الإشارات — متشابهان موجب، مختلفان سالب.

---

## 1.3 Parenteser og regnearternes rækkefølge

**Rækkefølgen** (ترتيب العمليات):
1. **Parenteser** (الأقواس) — `( )` først
2. **Potenser og rødder** (القوى والجذور) — `x²`, `√x`
3. **Multiplikation og division** — fra venstre mod højre
4. **Addition og subtraktion** — fra venstre mod højre

> 🇩🇰 Huskereglen i dansk: **PPMDAS** (Parentes, Potens, Multiplikation, Division, Addition, Subtraktion).

### Eksempel
$$3 + 4 \cdot (5 - 2)^2 = 3 + 4 \cdot 3^2 = 3 + 4 \cdot 9 = 3 + 36 = 39$$

---

## 1.4 Potens og rod

### Potens (القوى)

$$a^n = \underbrace{a \cdot a \cdot a \cdot \ldots \cdot a}_{n \text{ gange}}$$

**Regneregler:**
- $a^m \cdot a^n = a^{m+n}$
- $\dfrac{a^m}{a^n} = a^{m-n}$
- $(a^m)^n = a^{m \cdot n}$
- $a^0 = 1$ (når $a \neq 0$)
- $a^{-n} = \dfrac{1}{a^n}$

### Rod (الجذور)

$$\sqrt[n]{a} = a^{1/n}$$

Kvadratrod (الجذر التربيعي): $\sqrt{a} = a^{1/2}$

> ⚡ I el-teori dukker kvadratrod op overalt — fx ved beregning af **RMS-værdier** ($U_{eff} = U_{peak} / \sqrt{2}$).

---

## 1.5 Det græske alfabet

I tekniske formler bruges græske bogstaver konstant. Her er de vigtigste i el-faget:

| Bogstav | Stort | Lille | Bruges til |
|---------|-------|-------|------------|
| Alfa | Α | α | Vinkel, temperaturkoefficient |
| Beta | Β | β | Vinkel, transistor strømforstærkning |
| Gamma | Γ | γ | Konduktivitet |
| Delta | Δ | δ | Forskel, ændring (ΔU = spændingsfald) |
| Theta | Θ | θ | Vinkel, temperatur |
| Lambda | Λ | λ | Bølgelængde, luftfaktor |
| My | Μ | μ | Mikro (10⁻⁶), permeabilitet |
| Pi | Π | π | 3,14159... (kreds-tal) |
| Rho | Ρ | ρ | Resistivitet |
| Sigma | Σ | σ | Sum, ledningsevne |
| Phi | Φ | φ | Magnetisk flux, fasevinkel |
| Omega | Ω | ω | Ohm (modstand), vinkelhastighed |

---

## 1.6 Konvertering mellem talsystemer

### Decimal → Binær

Divider gentagne gange med 2 og noter resterne **bagfra**:

```
456 : 2 = 228  rest 0
228 : 2 = 114  rest 0
114 : 2 = 57   rest 0
 57 : 2 = 28   rest 1
 28 : 2 = 14   rest 0
 14 : 2 = 7    rest 0
  7 : 2 = 3    rest 1
  3 : 2 = 1    rest 1
  1 : 2 = 0    rest 1
```

**Læs nedefra og op:** 456₁₀ = **111001000**₂

### Binær → Decimal

Multiplicer hvert ciffer med 2 i den tilsvarende potens:

$$10101_2 = 1\cdot 2^4 + 0\cdot 2^3 + 1\cdot 2^2 + 0\cdot 2^1 + 1\cdot 2^0 = 16 + 4 + 1 = 21_{10}$$

### Hex-tabellen

| Decimal | Binær | Hex |
|---------|-------|-----|
| 0 | 0000 | 0 |
| 1 | 0001 | 1 |
| 5 | 0101 | 5 |
| 10 | 1010 | A |
| 15 | 1111 | F |

> 🛠 Brug det interaktive værktøj: [**Talsystem-konverter**](../interaktiv/talsystem-konverter.html)

---

## 📌 Resumé på arabisk — ملخص بالعربية

- **الأرقام تُقسم إلى:** طبيعية (N) ≤ صحيحة (Z) ≤ نسبية (Q) ≤ حقيقية (R).
- **أنظمة الأرقام:** العشري (الأساس 10)، الثنائي (2)، السادس عشر (16) — الثنائي مهم في الإلكترونيات الرقمية.
- **قواعد الإشارات في الضرب والقسمة:** متشابهان = موجب، مختلفان = سالب.
- **ترتيب العمليات:** أقواس → قوى → ضرب/قسمة → جمع/طرح.
- **الحرف اليوناني** يُستخدم كثيراً: Ω (أوم)، π (باي)، μ (ميكرو)، Δ (دلتا = الفرق).

---

## ➡️ Næste skridt

- 📝 [Opgaver til kapitel 1](../opgaver/01-opgaver.md)
- 🧮 [Talsystem-konverter (interaktiv)](../interaktiv/talsystem-konverter.html)
- ➡️ [Kapitel 2 — Geometri](02-geometri.md)
