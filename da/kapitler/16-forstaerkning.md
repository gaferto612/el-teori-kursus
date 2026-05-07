# Kapitel 16 — Forstærkning
> التضخيم

## 🎯 Læringsmål

- Forstå begrebet forstærkning og forstærknings-faktor
- Kende grundlæggende transistor-forstærkertyper
- Forstå koblinger som emitter-kobling, kollektor-kobling, basis-kobling
- Anvende DC-forstærkere i styringsanlæg
- Få overblik over operationsforstærkeren (op-amp)

---

## 16.1 Hvad er en forstærker?

En **forstærker** øger amplitude eller effekt af et signal.

### Forstærknings-faktor (gain)

Tre former:
- **Spændings-forstærkning**: $A_U = \dfrac{U_{ud}}{U_{ind}}$
- **Strøm-forstærkning**: $A_I = \dfrac{I_{ud}}{I_{ind}}$
- **Effekt-forstærkning**: $A_P = \dfrac{P_{ud}}{P_{ind}}$

### Decibel (dB)
Forstærkning udtrykkes ofte i dB (logaritmisk skala):
$$A[dB] = 20 \cdot \log\left(\frac{U_{ud}}{U_{ind}}\right)$$

| Faktor | dB |
|--------|----|
| 2 | 6 dB |
| 10 | 20 dB |
| 100 | 40 dB |
| 1.000 | 60 dB |

> 💡 +3 dB = fordobling af **effekt**, +6 dB = fordobling af **spænding/strøm**.

---

## 16.2 DC-forstærkere

I styringsanlæg bruges **DC-forstærkere** mange steder:

| Anvendelse | Funktion |
|-----------|----------|
| **Følerforstærker** | Tilpasser sensor-signal til logikken |
| **Driverkreds** | Forstærker logikkens signal til at drive relæ/motor |
| **Måleforstærker** | Forstærker små målespændinger |
| **Styringsforstærker** | I PID-regulatorer |

### Eksempel — driverkreds

Logikkredsen leverer 12 V og 1 mA. For at aktivere et relæ med spoleforbrug 50 mA bruges en transistor som switch:

```
   +12 V
      │
      [relæ]
      │
      ─┤├─ ← diode (fri-løbsdiode mod induktive spids)
      │
   ───┤  ← C
   logik──[R₁]──┤  ← B (NPN)
       (12 V) ───┤
                 ↓ E
                ───
                 ⏚
```

Med transistor strømforstærkning $h_{FE} = 200$:
$$I_B = I_C / h_{FE} = 50/200 = 0{,}25 \text{ mA}$$

Logikken kan let levere 0,25 mA → kredsen virker.

---

## 16.3 Transistor-koblinger

Der findes 3 grundkoblinger med en BJT, defineret af hvilket ben der er **fælles** for ind- og udgang:

### Emitter-kobling (CE — Common Emitter)
**Den mest brugte forstærkerkobling**.

| Egenskab | Værdi |
|----------|-------|
| Spændingsforstærkning | Stor (10–1000) |
| Strømforstærkning | Stor (β) |
| Indgangsimpedans | Mellem (~kΩ) |
| Udgangsimpedans | Høj (~10 kΩ) |
| Faseforskydning ind→ud | **180°** |

### Kollektor-kobling (CC — Common Collector / Emitter-følger)
| Egenskab | Værdi |
|----------|-------|
| Spændingsforstærkning | ≈1 (ikke forstærket!) |
| Strømforstærkning | Stor |
| Indgangsimpedans | **Meget høj** |
| Udgangsimpedans | **Meget lav** |
| Faseforskydning | 0° |

> 💡 Bruges som **buffer** eller impedans-tilpasning — fx mellem en højimpedans-sensor og en lavimpedans-last.

### Basis-kobling (CB — Common Base)
| Egenskab | Værdi |
|----------|-------|
| Spændingsforstærkning | Stor |
| Strømforstærkning | ≈1 |
| Indgangsimpedans | **Meget lav** |
| Udgangsimpedans | Meget høj |
| Faseforskydning | 0° |

> 📡 Bruges i RF-kredse og højfrekvent forstærkning.

---

## 16.4 Arbejdspunkt

For at forstærke et **AC-signal** uden forvrængning, skal transistoren være "biaset" til et **arbejdspunkt** (operating point) midt i sin lineære zone.

```
   I_C
    │
    │     /  <- mætning
    │    /
    │   X     <- arbejdspunkt
    │  /
    │ /
    │/
    └──────────  V_CE
       ↑
     cut-off
```

Bias-modstande på basis sætter en lille DC-strøm der placerer arbejdspunktet rigtigt.

---

## 16.5 Operationsforstærkeren (op-amp)

En **op-amp** er en højforstærket DC-forstærker i IC-form. **Det vigtigste analoge komponent** i moderne elektronik efter MOSFET.

### Egenskaber (ideal)
- **Forstærkning**: ekstremt høj (~10⁵ – 10⁶)
- **Indgangsimpedans**: meget høj (uendelig)
- **Udgangsimpedans**: meget lav (0)
- To indgange: **+** (ikke-inverterende) og **−** (inverterende)
- Én udgang

### Symbol
```
        ┌───────┐
   + ───┤        \
        │         ├── ud
   - ───┤        /
        └───────┘
```

### Den gyldne regel (med negativ tilbagekobling)
1. Udgangen ændres så de to indgange har **samme spænding**
2. Der løber **ingen strøm** ind i indgangene

---

## 16.6 Almindelige op-amp koblinger

### Inverterende forstærker

```
        Rf
   ┌────[▭]────┐
   │           │
   ├──[▭]──┤-  │
   U_ind   │  ├─── U_ud
   ┌──────┤+  │
   │       └───┘
   ⏚
```

**Forstærkning**:
$$A_U = -\frac{R_f}{R_{ind}}$$

(minus = inverterer fasen)

### Ikke-inverterende forstærker

```
   U_ind ──┤+
           │ ├─── U_ud
       ┌──┤-
       │  │
   ┌───┴─[Rf]─── ud
   │
  [R₁]
   │
   ⏚
```

**Forstærkning**:
$$A_U = 1 + \frac{R_f}{R_1}$$

### Spændings-følger (buffer)
Specialtilfælde af ikke-inverterende: $A_U = 1$.
Bruges til **impedans-isolation** uden forstærkning.

### Sumforstærker
Lægger flere indgange sammen vægtet.

### Differensforstærker
Forstærker forskellen mellem to signaler — bruges til instrumentforstærkere, sensor-tilpasning.

### Komparator
Sammenligner to spændinger — udgang er ON eller OFF (digital):
- Hvis $U_+ > U_-$ → udgang HIGH
- Hvis $U_+ < U_-$ → udgang LOW

> 🔍 Bruges i alarmer, niveau-detektorer, A/D-konvertere.

---

## 16.7 Almindelige op-amp ICs

| IC | Beskrivelse |
|----|-------------|
| LM741 | Klassisk almene op-amp — gammel men brugbar |
| LM358 | Dobbelt op-amp, single supply (5 V) |
| TL081/82/84 | JFET-indgang, lav støj |
| LM324 | 4 op-amps i én pakke |
| OP07 | Lav offset, præcision |
| INA128 | Instrumentforstærker |

---

## 16.8 Push-pull / klasse-AB forstærker

To transistorer (NPN + PNP) deler arbejdet:
- NPN tager den positive halvdel af signalet
- PNP tager den negative

> 🔊 Bruges i lydforstærkere — bedre virkningsgrad end klasse-A. Klasse-AB er standardvalget i hi-fi.

| Klasse | Virkningsgrad | Forvrængning |
|--------|--------------|--------------|
| A | 25 % | Lav |
| AB | 50–60 % | Lav (med crossover) |
| B | 78 % | Højere |
| D (switching) | 90+ % | Meget lav (moderne) |

---

## 📌 Resumé på arabisk

- **التضخيم** = زيادة سعة الإشارة. يُحسب كنسبة (Aᵤ = U_خرج / U_دخل) أو بالديسيبل.
- **3 توصيلات أساسية للترانزستور**:
  - **CE (الباعث المشترك)**: التضخيم الأشهر، انعكاس 180°.
  - **CC (المجمع المشترك / تابع الباعث)**: تضخيم ~1، ممانعة دخل عالية، خرج منخفضة — يُستخدم كمحوّل ممانعة.
  - **CB (القاعدة المشتركة)**: للترددات العالية.
- **مكبر العمليات (op-amp)**: مكبر متكامل بتضخيم هائل، ممانعة دخل عالية جداً.
- **توصيلات op-amp الأساسية**: عاكس، غير عاكس، تابع جهد، جامع، تفاضلي، مقارن.
- **استخدام في PLC**: مكبر إشارة من الحساس قبل دخوله إلى المنطق الرقمي.

---

## ➡️ Næste skridt

- 📝 [Opgaver til kapitel 16](../opgaver/16-opgaver.md)
- ➡️ [Kapitel 17 — Ensretning](17-ensretning.md)
