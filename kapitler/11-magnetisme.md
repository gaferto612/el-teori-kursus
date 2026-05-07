# Kapitel 11 — Magnetisme
> المغناطيسية

## 🎯 Læringsmål

- Forstå magnetiske felter og deres egenskaber
- Beregne magnetisk flux og fluxtæthed
- Forstå sammenhængen mellem el og magnetisme (elektromagnetisme)
- Anvende induktionsloven (Faraday)
- Forstå motorprincippet og generatorprincippet

---

## 11.1 Hvad er magnetisme?

Magnetisme stammer fra navnet på den lille by **Magnesia** i Asien, hvor man fandt jernmalm med naturlige magnetiske egenskaber.

### Hvilke materialer er magnetiske?

| Type | Materialer |
|------|-----------|
| Ferromagnetisk (stærk) | Jern (Fe), kobolt (Co), nikkel (Ni), legeringer |
| Paramagnetisk (svag) | Aluminium, platin |
| Diamagnetisk (frastøder) | Kobber, vand, kulstof |

> 💡 I el-tekniske komponenter (motorer, transformere) bruges hovedsagelig **siliciumlegeret elektrisk stål**.

---

## 11.2 Magnetfelt og feltlinjer

Et magnetfelt visualiseres med **feltlinjer**:
- Går fra **nordpol (N)** til **sydpol (S)** uden for magneten
- Inde i magneten: fra S til N
- Feltlinjer **krydser ikke hinanden**
- Tæthed af linjer = feltstyrke

### Jordmagnetisme
Jorden virker som en kæmpe stangmagnet:
- Geografisk **nordpol** = magnetisk **sydpol** (det er derfor en kompasnål peger nordpå)

---

## 11.3 Permanente magneter og elektromagneter

### Permanent magnet
- Beholder sin magnetisme uden tilført energi
- Bruges i højtalere, elmotorer, generatorer

### Elektromagnet
- Magnetisk felt opstår når **strøm går gennem en spole**
- Feltet kan slukkes/tændes
- Anvendelse: relæer, kontakter, kraner, transformere

---

## 11.4 Højrehåndsreglen

### For en ledning med strøm
> **Tommelfinger** = strømretning
> **Andre fingre** krummer sig om ledningen i feltretningen.

### For en spole
> **Fingrene** følger strømretningen i viklingerne
> **Tommelfingeren** peger mod spolens **nordpol**.

> 🇸🇦 **قاعدة اليد اليمنى**: الإبهام = اتجاه التيار، الأصابع تشير إلى اتجاه المجال المغناطيسي.

---

## 11.5 Magnetiske størrelser

### Magnetisk flux (Φ) — التدفق المغناطيسي
Mængden af magnetfelt gennem et areal. Måles i **Weber (Wb)**.

### Magnetisk fluxtæthed (B) — كثافة التدفق
Flux pr. arealenhed. Måles i **Tesla (T)**.

$$B = \frac{\Phi}{A}$$

| Felttype | B-værdi |
|----------|---------|
| Jordens magnetfelt | ~50 μT |
| Køleskabsmagnet | ~5 mT |
| MRI-scanner | 1,5–3 T |
| Stærkeste laboratorie-magnet | ~45 T |

### Magnetisk feltstyrke (H) — شدة المجال
$$H = \frac{N \cdot I}{l}$$

Hvor N = vindingsantal, I = strøm, l = magnetkredsens længde.

### Permeabilitet (μ) — النفاذية
Et materiales evne til at lede magnetisk flux:
$$\mu = \frac{B}{H}$$

For luft: $\mu_0 = 4\pi \cdot 10^{-7}$ H/m.

### Hysterese
Magnetiske materialer har en **hysteresekurve** — de "husker" tidligere magnetisering. Dette er grundlag for permanente magneter, men giver tab i transformere.

---

## 11.6 Elektromagnetisk induktion (Faradays lov)

> **Når en leder bevæges gennem et magnetfelt — eller et magnetfelt ændres omkring en leder — induceres en spænding i lederen.**

$$U_{ind} = -N \cdot \frac{d\Phi}{dt}$$

| Symbol | Betydning |
|--------|-----------|
| N | Antal vindinger i spolen |
| dΦ/dt | Hastighed hvormed fluxen ændres |

> 🔑 **Dette er fundamentet for**:
> - **Generatoren** (mekanisk → elektrisk energi)
> - **Transformeren** (spændingsændring)
> - **Induktionsmotoren**
> - **Spoler** (induktanser) i elektronik

---

## 11.7 Generatorprincippet

```
       N
   ┌───────┐    Når sløjfen drejes
   │       │    induceres en
   │  ↻ ↺  │    AC-spænding
   │       │
   └───────┘
       S
```

**Princip**: En leder der drejes i et magnetfelt får induceret en sinusformet vekselspænding.

- 1 omdrejning = 1 sinusperiode
- Antal perioder pr. sek = **frekvensen** (Hz)
- I Danmark: 50 Hz → 3.000 omdr./min for 2-polede generatorer

---

## 11.8 Motorprincippet

> **En strømførende leder i et magnetfelt påvirkes af en kraft.**

$$F = B \cdot I \cdot l$$

| Symbol | Betydning | Enhed |
|--------|-----------|-------|
| F | Kraft | N |
| B | Fluxtæthed | T |
| I | Strøm | A |
| l | Lederens længde i feltet | m |

### Venstrehåndsreglen (motor)
> **Tommelfinger** = kraftretning
> **Pegefinger** = magnetfelt (B)
> **Langfinger** = strømretning (I)

> 💡 Højrehåndsregel = generator/induktion. Venstrehåndsregel = motor.

---

## 11.9 Spoler (induktanser)

En spole er en leder viklet om en kerne.

### Induktans (L) — المحاثة
Måles i **Henry (H)**. Spolens evne til at modvirke ændringer i strøm:
$$U_L = L \cdot \frac{dI}{dt}$$

### Energi lagret i en spole
$$E = \frac{1}{2} L \cdot I^2$$

> ⚡ Spoler bruges i: transformere, motorer, filtre, relæer, drosler, induktive lasere.

---

## 11.10 Transformeren

To spoler omkring samme jernkerne. Vekselstrøm i den primære skaber et skiftende magnetfelt, der inducerer en spænding i den sekundære.

$$\frac{U_1}{U_2} = \frac{N_1}{N_2}$$

| Hvis... | Resultat |
|---------|----------|
| $N_2 > N_1$ | Optransformerer (op til højere spænding) |
| $N_2 < N_1$ | Nedtransformerer |
| $N_2 = N_1$ | 1:1 (fx galvanisk skille) |

### Effekt-balance (ideel transformer)
$$P_1 = P_2 \quad \Rightarrow \quad U_1 \cdot I_1 = U_2 \cdot I_2$$

Bemærk: høj spænding side → **lav** strøm. Det er **derfor** højspændingsnet bruges til at minimere ledningstab ($P_{tab} = I^2 R$).

---

## 11.11 Magnetkredsen — Ohms lov-analogi

| Elektrisk kreds | Magnetisk kreds |
|-----------------|-----------------|
| Spænding U | Magnetomotorisk kraft $F_m = N \cdot I$ |
| Strøm I | Flux Φ |
| Modstand R | Reluctance Rₘ |
| $U = R \cdot I$ | $F_m = R_m \cdot \Phi$ |

> 🇸🇦 **مقارنة**: الدوائر المغناطيسية تشبه قانون أوم — القوة الدافعة المغناطيسية = المعاوقة المغناطيسية × التدفق.

---

## 📌 Resumé på arabisk

- **المجال المغناطيسي**: خطوط من القطب الشمالي (N) إلى الجنوبي (S) خارج المغناطيس.
- **قاعدة اليد اليمنى**: لمعرفة اتجاه المجال حول سلك يحمل تياراً.
- **قانون فاراداي للحث**: U = -N·(dΦ/dt) — هذا أساس المولدات والمحولات.
- **مبدأ المحرك**: قوة F = B·I·l على سلك يحمل تياراً في مجال مغناطيسي.
- **المحول**: U₁/U₂ = N₁/N₂. القدرة محفوظة (P₁ = P₂)، لذا الجهد العالي = تيار منخفض.
- **المحاثة (L)** بالهنري: المعاوقة لتغير التيار في الملف.

---

## ➡️ Næste skridt

- 📝 [Opgaver til kapitel 11](../opgaver/11-opgaver.md)
- ➡️ [Kapitel 12 — 1-faset vekselstrømsteori](12-1-faset-vekselstroemsteori.md)
