# Kapitel 4 — Aritmetik
> الجبر / حساب البحتة

## 🎯 Læringsmål

- Løse førstegrads-ligninger med én ubekendt
- Isolere en variabel i en formel
- Regne med brøker og forhold
- Bruge ligefrem og omvendt proportionalitet

---

## 4.1 Ligninger med én ubekendt

En **ligning** (معادلة) er to udtryk forbundet med et lighedstegn.

Eksempel:
$$3x + 5 = 20$$

**Reglen**: Det vi gør på den ene side, skal vi også gøre på den anden side.

**Løsning**:
- Træk 5 fra på begge sider: $3x = 15$
- Divider begge sider med 3: $x = 5$

> 💡 Husk: Når man flytter et tal til den anden side af lighedstegnet, **skifter det fortegn**.

### Eksempel — el-teknik

Ohms lov: $U = R \cdot I$

Hvis vi vil isolere R:
$$R = \frac{U}{I}$$

Hvis vi vil isolere I:
$$I = \frac{U}{R}$$

---

## 4.2 Brøker (الكسور)

### Regneregler

**Addition/subtraktion** (kræver fælles nævner):
$$\frac{a}{c} + \frac{b}{c} = \frac{a + b}{c}$$

$$\frac{a}{b} + \frac{c}{d} = \frac{a \cdot d + c \cdot b}{b \cdot d}$$

**Multiplikation**:
$$\frac{a}{b} \cdot \frac{c}{d} = \frac{a \cdot c}{b \cdot d}$$

**Division**:
$$\frac{a}{b} : \frac{c}{d} = \frac{a}{b} \cdot \frac{d}{c} = \frac{a \cdot d}{b \cdot c}$$

> 🇸🇦 **القاعدة الذهبية**: عند قسمة كسر على كسر، اقلب الثاني واضرب.

### Forkortelse
$$\frac{12}{18} = \frac{12 : 6}{18 : 6} = \frac{2}{3}$$

---

## 4.3 Forhold og proportioner

### Forhold (النسبة)

Et forhold mellem a og b skrives:
$$a : b \quad \text{eller} \quad \frac{a}{b}$$

### Ligefrem proportionalitet (التناسب الطردي)

Når den ene størrelse stiger, stiger den anden tilsvarende:
$$y = k \cdot x$$

**Eksempel** — Ohms lov med konstant R:
- Spændingen fordobles → strømmen fordobles
- $U \propto I$

### Omvendt proportionalitet (التناسب العكسي)

Når den ene stiger, falder den anden:
$$y = \frac{k}{x}$$

**Eksempel** — Ohms lov med konstant U:
- Modstanden fordobles → strømmen halveres
- $I \propto \dfrac{1}{R}$

---

## 4.4 Procent (النسبة المئوية)

$$x\% = \frac{x}{100}$$

### Procent af et tal
"Find 25 % af 80":
$$80 \cdot 0{,}25 = 20$$

### Procent fra én værdi til en anden
"Hvor mange procent stiger 50 til 65?":
$$\frac{65 - 50}{50} \cdot 100\% = 30\%$$

### Anvendelse — virkningsgrad (η, efficiency)

$$\eta = \frac{P_{ud}}{P_{ind}} \cdot 100\%$$

En motor har virkningsgrad 85 %, hvis den afgiver 850 W når den optager 1000 W.

---

## 4.5 Formelregning — isolering af variable

### Effektformel
$$P = U \cdot I$$

| Skal isoleres | Formel |
|---------------|--------|
| U | $U = \dfrac{P}{I}$ |
| I | $I = \dfrac{P}{U}$ |

### Effekt med modstand
$$P = U \cdot I = I^2 \cdot R = \frac{U^2}{R}$$

| Skal isoleres | Formel |
|---------------|--------|
| R fra $P = I^2 R$ | $R = \dfrac{P}{I^2}$ |
| U fra $P = \dfrac{U^2}{R}$ | $U = \sqrt{P \cdot R}$ |

> 💡 Når man isolerer ud af en kvadrat, får man **kvadratrod**.

---

## 4.6 Andengradsligninger (kort)

En ligning på formen:
$$ax^2 + bx + c = 0$$

løses med diskriminant-formlen:
$$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$

> ⚡ Bruges sjældent direkte i grundlæggende el-teori, men kan dukke op ved beregning af resonansfrekvens og optimum.

---

## 📌 Resumé på arabisk

- **حل المعادلة**: ما يُفعل في طرف يُفعل في الآخر.
- **عند نقل عدد** عبر علامة المساواة، تتغير إشارته.
- **التناسب الطردي**: y = k·x (مثل: U = R·I عند R ثابت).
- **التناسب العكسي**: y = k/x (مثل: I = U/R عند U ثابت).
- **النسبة المئوية للكفاءة**: η = (P_خرج / P_دخل) × 100%.

---

## ➡️ Næste skridt

- 📝 [Opgaver til kapitel 4](../opgaver/04-opgaver.md)
- ➡️ [Kapitel 5 — Binær regning](05-binaer-regning.md)
