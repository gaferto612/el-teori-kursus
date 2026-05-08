# Kapitel 17 — Ensretning
> التقويم

## 🎯 Læringsmål

- Forstå hvorfor ensretning er nødvendig
- Kende enkelt-, dobbelt- og brokoblede ensrettere
- Beregne tomgangs- og belastningsspænding
- Forstå glatning med kondensator og ripple
- Kende stabiliseringsmetoder

---

## 17.1 Hvorfor ensretning?

De fleste elektroniske kredse kører på **jævnspænding** (DC). Da forsyningsnettet leverer **vekselspænding** (AC), skal denne **ensrettes** først.

### Typisk strømforsyning
```
   AC net ──[Transformer]──[Ensretter]──[Glatning]──[Stabilisator]── DC ud
   230 V                     ~                       Ren DC
```

**Hver del har en rolle**:
1. **Transformer**: tilpasser spænding + galvanisk adskillelse
2. **Ensretter**: konverterer AC → pulserende DC
3. **Glatning**: udjævner pulserne (kondensator)
4. **Stabilisator**: holder spændingen konstant ved varierende belastning

---

## 17.2 Enkeltensretning (E-kobling)

Den simpleste ensretter — én diode i serie.

```
       +───D──────●─── + ud
   AC                  │
       -──────●───────●─── - ud
                  belastning
```

### Virkemåde
- Positiv halvbølge: dioden leder → strømmen passerer
- Negativ halvbølge: dioden spærrer → ingen strøm

```
Indgang AC:    /\    /\    /\
              /  \  /  \  /
       ─────/────\/────\/────
                  
Udgang:        /\        /\
              /  \      /  \
       ─────/────────/───────
```

### Værdier
For en sinus med peak-spænding $U_{peak}$:

| Værdi | Formel |
|-------|--------|
| Tomgangsspænding (peak) | $U_{peak} = U_{rms} \cdot \sqrt{2}$ |
| Middelværdi (DC) | $U_{DC} = U_{peak}/\pi ≈ 0{,}318 \cdot U_{peak}$ |
| Frekvens af pulser | = netfrekvensen (50 Hz) |

> ⚠ **Kun** halv periode udnyttet — dårlig effektivitet. Sjældent brugt undtagen i meget små anvendelser.

---

## 17.3 Dobbeltensretning — midt-tap kobling (M-kobling)

Bruger en transformer med **midteraftap** og to dioder.

```
   Top ───D₁───┐
               │
   Midt ───────●──── + ud
               │
   Bund ───D₂──┘
```

### Virkemåde
- Positiv halvbølge: D₁ leder, D₂ spærrer
- Negativ halvbølge: D₂ leder, D₁ spærrer
- **Begge** halvbølger ensrettes!

```
Indgang:    /\    /\    /\
           /  \  /  \  /
       ───/────\/────\/───

Udgang:    /\  /\  /\  /\
          /  \/  \/  \/  \
       ───/───────────────
```

### Værdier
| Værdi | Formel |
|-------|--------|
| Middelværdi (DC) | $U_{DC} = 2 \cdot U_{peak}/\pi ≈ 0{,}637 \cdot U_{peak}$ |
| Frekvens af pulser | **2 × netfrekvens** (100 Hz) |

> 💡 Kræver dyrere transformer med midt-tap. Sjælden i moderne kredse.

---

## 17.4 Brokobling (B-kobling) — den moderne standard

**4 dioder** i en bro-konfiguration. Kræver **ingen** midt-tap.

```
              D₁         D₂
    AC ●────►├────●──────●
              D₃         D₄
       ●────►├────●──────●
                  ↑      ↓
              + ud      - ud
```

### Virkemåde
Hver halvbølge: 2 dioder leder, 2 spærrer — strømmen tegnes **altid samme vej** gennem belastningen.

### Egenskaber
- **Begge** halvbølger ensrettes
- Effektiv udnyttelse
- Tomgangsspænding = peak − 2 · 0,7 V (to dioder i serie)
- Ripple-frekvens = 100 Hz (ved 50 Hz net)

> ⚙ **Den klart mest brugte ensretter** i strømforsyninger, opladere, etc. Findes ofte som **enkelt komponent** (bridge rectifier).

---

## 17.5 3-fase ensretning

Til større effekter (motorer, frekvensomformere):

### 3-faset brokobling (B6)
**6 dioder** — to pr. fase. Resultatet er meget jævnere end 1-faset:

```
Pulser pr. omdrejning: 6
Ripple: ca. 4 % uden glatning
Frekvens af pulser: 6 × 50 Hz = 300 Hz
```

> ⚡ Bruges i: industrielle DC-strømforsyninger, frekvensomformere (input-side), kraftige opladere.

---

## 17.6 Glatning med kondensator

For at gøre den pulserende DC mere "jævn", parallel-kobles en stor **glatningskondensator** med belastningen.

```
      ┌──[ensretter]──┬──── + ud
                      │
                      │
                     [C]
                      │
      ────────────────┴──── - ud
```

### Virkemåde
- Når spændingen stiger, oplades C
- Når spændingen falder, **afgiver** C strøm til lasten
- Resultat: en mere jævn DC med en lille **ripple**

### Ripple-spænding
$$U_{rip} \approx \frac{I_{last}}{f_{ripple} \cdot C}$$

| Faktor | Betydning |
|--------|-----------|
| $I_{last}$ | Belastningsstrøm |
| $f_{ripple}$ | 100 Hz ved 1-faset brokobling |
| C | Glatningskondensator (F) |

### Eksempel
$I_{last} = 1$ A, $f = 100$ Hz, $C = 1.000$ μF:
$$U_{rip} = \frac{1}{100 \cdot 0{,}001} = 10 \text{ V}$$

For mindre ripple: større C eller lavere strøm.

> 💡 Ripple gør den jævne DC "småknudret" — utilfredsstillende for følsomme kredse, så følges af **stabilisator**.

---

## 17.7 Spændingsstabilisering

### Zenerdiode-stabilisator (simpel)

```
   U_ind ──[R]──●──── U_ud
                │
              ─┬├─  zener (vendt)
                │
                ⏚
```

Zenerdioden holder konstant spænding ved sin **gennembrudsspænding** $U_Z$.

> 💡 OK til små belastninger og simple kredse. Spilder energi i seriemodstanden.

### Lineær regulator (IC)

| Type | Spænding |
|------|----------|
| 7805 | +5 V |
| 7812 | +12 V |
| 7905 | -5 V |
| 7915 | -15 V |

Disse 3-bens regulatorer er ekstremt enkle at bruge:
- **Indgang**: 7-15 V (afhængigt af type)
- **GND**
- **Udgang**: stabiliseret spænding

### Switch-mode (SMPS)
Moderne strømforsyninger bruger **switching** med høj frekvens (50–500 kHz) og er meget mere energieffektive (90+%) end lineære.

> ⚙ Næsten alle moderne lader, computer-strømforsyninger, og industri-PSU'er er switch-mode.

---

## 17.8 Spænding fordoblers og multipliers (kort)

Specielle koblinger med dioder + kondensatorer kan **fordoble** eller **multiplicere** spændingen:

| Type | Resultat |
|------|----------|
| Fordobler | 2 × peak |
| Tripler | 3 × peak |
| Quadrupler | 4 × peak |

Bruges i: elektrostatiske rensere, elektronmikroskoper, tidligere TV (CRT-anodes ~25 kV).

---

## 17.9 Sammenligning af ensretter-typer

| Type | Dioder | Trafo | Ripple-frekvens | Effektivitet |
|------|--------|-------|-----------------|--------------|
| Enkelt (E) | 1 | Standard | 50 Hz | Ringe |
| Midttap (M) | 2 | Med midttap | 100 Hz | Bedre |
| Bro (B) | 4 | Standard | 100 Hz | God |
| 3-faset bro (B6) | 6 | 3-faset | 300 Hz | Fremragende |

---

## 📌 Resumé på arabisk

- **التقويم** = تحويل التيار المتردد إلى تيار مستمر باستخدام الديودات.
- **التقويم نصف الموجة** (E-kobling): ديود واحد، يستخدم نصف الموجة فقط — كفاءة منخفضة.
- **التقويم الموجي الكامل** (B-kobling): 4 ديودات في تركيبة جسر — يستخدم الموجة الكاملة، وهو الأكثر استخداماً.
- **التقويم ثلاثي الطور** (B6): 6 ديودات، تموج ضعيف جداً — للأحمال الكبيرة (محولات التردد).
- **مكثف التنعيم** يقلل التموج. كلما زادت السعة، قل التموج.
- **منظم الجهد** (مثل 7805): يحافظ على جهد ثابت رغم تغير الحمل.
- **مزود الطاقة الحديث** (SMPS): تبديل عالي التردد، كفاءة 90%+.

---

## ➡️ Næste skridt

- 📝 [Opgaver til kapitel 17](../opgaver/17-opgaver.md)
- ➡️ [Kapitel 18 — Effektregulering](18-effektregulering.md)
