# Kapitel 10 — Jævnstrømsteori
> نظرية التيار المستمر

## 🎯 Læringsmål

- Anvende Ohms lov i forskellige kredsløb
- Bruge Kirchhoffs to love
- Beregne resulterende modstand i serie- og parallelkredse
- Forstå spændings- og strømdelere

---

## 10.1 Ohms lov — repetition

$$U = R \cdot I \qquad I = \frac{U}{R} \qquad R = \frac{U}{I}$$

**Proportionalitet**:
- Konstant R: U og I er **ligefrem proportionale** (U op → I op)
- Konstant U: I og R er **omvendt proportionale** (R op → I ned)

---

## 10.2 Kirchhoffs love

### Kirchhoffs 1. lov — strømsætningen
> **Summen af strømme der løber TIL et knudepunkt = summen af strømme der løber FRA knudepunktet.**

$$\sum I_{ind} = \sum I_{ud}$$

```
       I₁
       ↓
    ───●───
   I₂ ↗ ↘ I₃
```

Her gælder: $I_1 = I_2 + I_3$

### Kirchhoffs 2. lov — spændingssætningen
> **I et sluttet kredsløb er summen af de påtrykte spændinger lig summen af spændingsfald.**

$$\sum U_{kilde} = \sum U_{fald}$$

> 🇸🇦 **قوانين كيرشوف**:
> - **القانون الأول** (التيار): مجموع التيارات الداخلة لعقدة = مجموع التيارات الخارجة منها.
> - **القانون الثاني** (الجهد): مجموع الجهود في حلقة مغلقة = صفر.

---

## 10.3 Serieforbindelse

To eller flere komponenter er **serieforbundne** når de ligger i forlængelse af hinanden — strømmen har kun én vej.

```
  ┌──[R₁]──[R₂]──[R₃]──┐
  │                    │
  +─────[ U ]──────────+
```

### Regler for serieforbindelse

1. **Strømmen er ens overalt**:
$$I = I_1 = I_2 = I_3$$

2. **Spændingen fordeles** over modstandene:
$$U = U_1 + U_2 + U_3$$

3. **Resulterende modstand** = sum af modstande:
$$R_{tot} = R_1 + R_2 + R_3$$

### Eksempel
3 modstande på 10, 20 og 30 Ω forbundet i serie til 60 V.

$R_{tot} = 10 + 20 + 30 = 60$ Ω
$I = 60 / 60 = 1$ A
$U_1 = 1 · 10 = 10$ V
$U_2 = 1 · 20 = 20$ V
$U_3 = 1 · 30 = 30$ V
**Kontrol**: $10 + 20 + 30 = 60$ V ✓

> 💡 **Spændingsdeleren**: I serie deler spændingen sig **proportionalt med modstandene**.

$$U_x = U \cdot \frac{R_x}{R_{tot}}$$

---

## 10.4 Parallelforbindelse

To eller flere komponenter er **parallelforbundne** når de er forbundet mellem de samme to punkter — strømmen har flere veje.

```
       ┌─[R₁]─┐
       │      │
  ──●──┼─[R₂]─┼──●──
       │      │
       └─[R₃]─┘
```

### Regler for parallelforbindelse

1. **Spændingen er ens** over alle:
$$U = U_1 = U_2 = U_3$$

2. **Strømmene summerer**:
$$I = I_1 + I_2 + I_3$$

3. **Resulterende modstand**:
$$\frac{1}{R_{tot}} = \frac{1}{R_1} + \frac{1}{R_2} + \frac{1}{R_3}$$

### Specielt — to modstande parallelt
$$R_{tot} = \frac{R_1 \cdot R_2}{R_1 + R_2}$$

### Specielt — n ens modstande parallelt
$$R_{tot} = \frac{R}{n}$$

### Eksempel
To modstande på 30 Ω og 60 Ω parallelt til 12 V:

$R_{tot} = \dfrac{30 \cdot 60}{30 + 60} = \dfrac{1800}{90} = 20$ Ω
$I = 12 / 20 = 0{,}6$ A
$I_1 = 12/30 = 0{,}4$ A
$I_2 = 12/60 = 0{,}2$ A
**Kontrol**: $0{,}4 + 0{,}2 = 0{,}6$ A ✓

> 💡 **Pointe**: Resulterende modstand i parallelforbindelse er altid **mindre end den mindste** af de enkelte modstande.

---

## 10.5 Kombinerede kredsløb

Man løser dem **trin for trin** — start altid med at forenkle de inderste serie- eller parallel-grupper.

### Eksempel
$R_1 = 10$ Ω, $R_2 = 20$ Ω parallel — i serie med $R_3 = 14$ Ω.

**Trin 1**: Beregn $R_{12}$ (parallel):
$$R_{12} = \frac{10 \cdot 20}{10 + 20} = 6{,}67 \text{ Ω}$$

**Trin 2**: $R_{12}$ i serie med $R_3$:
$$R_{tot} = 6{,}67 + 14 = 20{,}67 \text{ Ω}$$

> 🛠 [Brug det interaktive værktøj — Serie & parallel](../../interaktiv/serie-parallel.html)

---

## 10.6 Effekt i kredsløb

### Generel
$$P = U \cdot I = I^2 \cdot R = \frac{U^2}{R}$$

### Effekt i serie
Den samlede effekt = sum af enkelteffekter:
$$P_{tot} = P_1 + P_2 + P_3$$

I serie er strømmen ens, så:
$$P_x = I^2 \cdot R_x$$

→ **Den største modstand afsætter mest effekt**.

### Effekt i parallel
Spændingen er ens, så:
$$P_x = \frac{U^2}{R_x}$$

→ **Den mindste modstand afsætter mest effekt**.

> ⚡ **Praktisk konsekvens**: I en seriekoblet glødepære-lyskæde lyser den mindst ohmske svagest. I parallelkobling lyser den med mindst modstand kraftigst.

---

## 10.7 Strøm- og spændingsdeler

### Spændingsdeler (i serie)
$$U_x = U \cdot \frac{R_x}{R_{tot}}$$

### Strømdeler (i parallel — to modstande)
$$I_1 = I \cdot \frac{R_2}{R_1 + R_2}$$
$$I_2 = I \cdot \frac{R_1}{R_1 + R_2}$$

> 💡 Bemærk **byttet** — strømmen gennem $R_1$ er proportional med $R_2$ (den modsatte modstand).

---

## 10.8 Praktiske anvendelser

### Sikringer i serie
Sikringen er altid serieforbundet med apparatet. Hvis strømmen overstiger den nominelle værdi, brænder sikringen, og kredsløbet brydes.

### Voltmeter med formodstand
For at måle højere spændinger end voltmeterets område, sættes en stor modstand **i serie**:
$$R_{form} = R_v \cdot (n - 1)$$

hvor n er forholdet mellem ny og gammel måleområde.

### Amperemeter med shunt
For at måle højere strømme sættes en lille modstand (shunt) **parallelt**:
$$R_{shunt} = \frac{R_a}{n - 1}$$

---

## 10.9 Spændingstab i ledninger

I praksis har **alle** ledninger en lille modstand. Spændingstabet er:
$$\Delta U = 2 \cdot l \cdot \frac{\rho \cdot I}{A}$$

(faktor 2 fordi strømmen går frem og tilbage)

> ⚡ **Regel i el-installation**: Spændingstabet bør holdes under ~3 % af nominel spænding (typisk 230 V → max ~7 V).

---

## 📌 Resumé på arabisk

- **قانون كيرشوف الأول** (التيار): مجموع التيارات الداخلة = مجموع التيارات الخارجة لأي عقدة.
- **قانون كيرشوف الثاني** (الجهد): مجموع الجهود في الحلقة المغلقة = 0.
- **التوصيل على التسلسل**: التيار ثابت، الجهد يُجمع، المقاومات تُجمع.
- **التوصيل على التوازي**: الجهد ثابت، التيار يُجمع، المقاومات: 1/R = 1/R₁ + 1/R₂ + ...
- **قاعدة مجزّئ الجهد**: Uₓ = U · (Rₓ / R_total)
- **القدرة في التسلسل**: أكبر مقاومة = أكبر قدرة. **في التوازي**: أصغر مقاومة = أكبر قدرة.

---

## ➡️ Næste skridt

- 📝 [Opgaver til kapitel 10](../opgaver/10-opgaver.md)
- 🧮 [Serie & parallel beregner](../../interaktiv/serie-parallel.html)
- ➡️ [Kapitel 11 — Magnetisme](11-magnetisme.md)
