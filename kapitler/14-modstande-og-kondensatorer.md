# Kapitel 14 — Modstande og kondensatorer
> المقاومات والمكثفات

## 🎯 Læringsmål

- Kende forskellige modstandstyper og farvekoder
- Forstå kondensatorens opbygning og virkemåde
- Beregne resulterende kapacitet i serie og parallel
- Forstå anvendelsen af potentiometre, NTC, LDR mv.

---

## 14.1 Faste modstande

### Materialer

| Type | Princip | Anvendelse |
|------|---------|-----------|
| **Kulfilm** | Tyndt lag carbon på keramik | Almene formål, billige |
| **Metalfilm** | Tyndt lag metal | Præcise, lav støj |
| **Wirewound** | Modstandstråd viklet om kerne | Høje effekter |
| **SMD** | Surface mount, flade chip | Moderne elektronik |

### Vigtige parametre

| Parameter | Betydning |
|-----------|-----------|
| Modstandsværdi | Ω, kΩ, MΩ |
| **Tolerance** | ±1 %, ±5 %, ±10 % |
| **Effekt** | 1/8 W, 1/4 W, 1/2 W, 1 W, 5 W, 25 W |
| **Temperaturkoefficient** | ppm/°C |

---

## 14.2 Farvekoden — 4 ringe

```
  Bånd 1 │ Bånd 2 │ Multiplikator │ Tolerance
  ───────┼────────┼───────────────┼──────────
   Sort  │ 0      │ 1             │
   Brun  │ 1      │ ×10           │ ±1 %
   Rød   │ 2      │ ×100          │ ±2 %
   Orange│ 3      │ ×1k           │
   Gul   │ 4      │ ×10k          │
   Grøn  │ 5      │ ×100k         │ ±0,5 %
   Blå   │ 6      │ ×1M           │
   Violet│ 7      │ ×10M          │
   Grå   │ 8      │               │
   Hvid  │ 9      │               │
   Guld  │        │ ×0,1          │ ±5 %
   Sølv  │        │ ×0,01         │ ±10 %
```

### Eksempel — modstand med farverne **brun-sort-rød-guld**:
- 1. ring (brun) = 1
- 2. ring (sort) = 0
- 3. ring (rød) = ×100
- 4. ring (guld) = ±5 %

→ **10 × 100 = 1000 Ω = 1 kΩ ±5 %**

> 🇸🇦 **حفظ الأرقام**: أسود 0، بني 1، أحمر 2، برتقالي 3، أصفر 4، أخضر 5، أزرق 6، بنفسجي 7، رمادي 8، أبيض 9.

---

## 14.3 Justerbare modstande

### Potentiometer (الجهد المتغير)
3 terminaler. Kan bruges som:
- **Spændingsdeler** (3 ben tilkoblet)
- **Reostat** (2 ben — variabel modstand)

### Trimmer
Mindre potentiometer der kun justeres med skruetrækker — for fin-indstilling.

---

## 14.4 Specielle modstande (sensorer)

### NTC (Negative Temperature Coefficient)
- Modstand **falder** ved stigende temperatur
- Bruges i: temperaturmåling, indkoblingsstrøm-begrænsning

### PTC (Positive Temperature Coefficient)
- Modstand **stiger** ved stigende temperatur
- Bruges i: motorovervågning (PT100, PT1000), selvregulerende varmelegemer

### LDR (Light Dependent Resistor) / fotomodstand
- Modstand falder ved øget lysstyrke
- Bruges i: lyssensorer, tusmørkerelæer

### VDR (Voltage Dependent Resistor) / varistor
- Modstanden falder kraftigt over en bestemt spænding
- Bruges som **overspændingsbeskyttelse**

| Sensortype | Symbol-tegn | Anvendelse |
|------------|-------------|-----------|
| NTC | t° med pil ↘ | Temp.måling |
| PTC | t° med pil ↗ | Motorbeskyttelse |
| LDR | Pil mod modstand | Lys |
| VDR | U over modstand | Overspændings-beskyttelse |

---

## 14.5 Kondensatorer (المكثفات)

En **kondensator** består af to elektrisk ledende plader adskilt af et **isolerende dielektrikum**.

```
     ──┤├──
       ││
    plade  plade
    + isolator imellem
```

### Kapacitet (C)
Måles i **farad (F)**:
$$C = \frac{Q}{U}$$

| Faktor | Betydning |
|--------|-----------|
| Q | Ladning (coulomb) |
| U | Spænding (V) |

> 💡 1 F er en **stor** enhed. Typiske kondensatorer er i:
> - pF (pikofarad) — RF, oscillatorer
> - nF (nanofarad) — filtre
> - μF (mikrofarad) — strømforsyninger, motorer
> - mF–F (super-kondensatorer) — energilagring

### Kapacitet for plade-kondensator
$$C = \varepsilon_0 \cdot \varepsilon_r \cdot \frac{A}{d}$$

| Symbol | Betydning |
|--------|-----------|
| $\varepsilon_0$ | Vakuum-permittivitet (8,854 · 10⁻¹² F/m) |
| $\varepsilon_r$ | Relativ permittivitet (dielektrisk konstant) |
| A | Pladens areal (m²) |
| d | Pladeafstand (m) |

---

## 14.6 Kondensatortyper

| Type | Dielektrikum | Kapacitet | Anvendelse |
|------|--------------|-----------|-----------|
| Keramisk | Keramik | pF–μF | Almene, RF |
| Folie (PE, PP, PS) | Plast | nF–μF | Filtre, motorer |
| Elektrolyt (Al, Ta) | Aluoxid/tantaloxid | μF–mF | Strømforsyninger |
| Super-kondensator | Specielle | F–kF | Energilagring |

> ⚠ **Polariseret**: Elektrolyt-kondensatorer **skal** vendes rigtigt — minus-side er typisk markeret med en stribe. Forkert polaritet → kan eksplodere!

---

## 14.7 Kondensatorer i serie og parallel

### Parallel
$$C_{tot} = C_1 + C_2 + C_3$$

(Modsat modstande)

### Serie
$$\frac{1}{C_{tot}} = \frac{1}{C_1} + \frac{1}{C_2} + \frac{1}{C_3}$$

(Modsat modstande også)

> 💡 **Huskeregel**: Kondensatorer regner **omvendt** af modstande.

---

## 14.8 Op- og afladning af kondensator

Når en kondensator oplades gennem en modstand R:

$$u_C(t) = U \cdot (1 - e^{-t/\tau})$$

hvor $\tau = R \cdot C$ er **tidskonstanten**.

| Tid | Opladet til |
|-----|-------------|
| 1τ | 63 % |
| 3τ | 95 % |
| 5τ | ~99 % (regnes som "fuldt opladet") |

### Eksempel
$R = 10$ kΩ, $C = 100$ μF:
$$\tau = 10.000 \cdot 100 \cdot 10^{-6} = 1 \text{ s}$$

→ Fuldt opladet efter ca. 5 sekunder.

> ⚡ Bruges i **timing-kredse**, RC-filtre, debouncing af kontakter.

---

## 14.9 Energilagring i kondensator

$$E = \frac{1}{2} C U^2$$

### Eksempel
1.000 μF kondensator opladet til 100 V:
$$E = \frac{1}{2} \cdot 0{,}001 \cdot 100^2 = 5 \text{ J}$$

> ⚠ Store kondensatorer (i strømforsyninger, motorstartere) **holder farlig spænding** længe efter strømmen er afbrudt. **Aflad altid!**

---

## 14.10 Anvendelser

| Anvendelse | Hvordan |
|-----------|---------|
| **Glatning** | Reducerer pulserende DC efter ensretter |
| **Kobling** | Lader AC passere, blokerer DC |
| **Afkobling** | Filtrerer støj fra strømforsyning |
| **Timing** | RC-kredse i oscillatorer |
| **Faseforskydning** | Startkondensator i 1-fasede motorer |
| **Effektfaktorkompensation** | Forbedrer cos φ i industri |
| **Energilagring** | UPS, frekvensomformere |

---

## 📌 Resumé på arabisk

- **المقاومة**: العنصر الأكثر استخداماً. تُحدد بقيمة، تسامح، وقدرة قصوى.
- **شفرة الألوان** على المقاومات: 4 حلقات — رقم، رقم، مضاعف، تسامح.
- **مقاومات خاصة**:
  - NTC: تنخفض مع الحرارة (لقياس درجة الحرارة).
  - PTC: ترتفع مع الحرارة (حماية المحركات).
  - LDR: تنخفض مع الضوء (مستشعر الإضاءة).
- **المكثف** يخزن الشحنة: $C = Q/U$، يُقاس بالفاراد.
- **في التوازي**: $C_{tot} = C_1 + C_2$. **في التسلسل**: $1/C_{tot} = 1/C_1 + 1/C_2$.
- **ثابت الزمن**: $\tau = R \cdot C$ — يحدد سرعة الشحن والتفريغ.
- **تحذير**: المكثفات الكبيرة تحتفظ بالشحنة لفترة طويلة بعد فصل التغذية.

---

## ➡️ Næste skridt

- 📝 [Opgaver til kapitel 14](../opgaver/14-opgaver.md)
- ➡️ [Kapitel 15 — Halvlederkomponenter](15-halvlederkomponenter.md)
