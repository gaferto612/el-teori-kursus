# Kapitel 12 — 1-faset vekselstrømsteori
> نظرية التيار المتردد أحادي الطور

## 🎯 Læringsmål

- Forstå hvordan vekselspænding frembringes
- Skelne mellem peak-, peak-to-peak-, RMS- og middelværdi
- Beregne reaktans for spoler og kondensatorer
- Forstå impedans og effektfaktor
- Beregne aktiv, reaktiv og tilsyneladende effekt

---

## 12.1 Hvordan vekselstrøm opstår

Når en **ledersløjfe drejes** i et homogent magnetfelt, induceres en **sinusformet** vekselspænding:

$$u(t) = U_{peak} \cdot \sin(\omega t)$$

| Symbol | Betydning |
|--------|-----------|
| u(t) | Øjeblikkelig spænding (V) |
| $U_{peak}$ | Peak-værdi (toppunkt) |
| ω | Vinkelhastighed (rad/s) = $2\pi f$ |
| t | Tid (s) |

For hver omdrejning af sløjfen → 1 sinusperiode.

---

## 12.2 Frekvens og periodetid

### Frekvens (f)
Antal perioder pr. sekund. Måles i **Hertz (Hz)**.

I Danmark: **f = 50 Hz** (lysnettet).

### Periodetid (T)
Varighed af én periode:
$$T = \frac{1}{f}$$

Ved 50 Hz: $T = 1/50 = 20$ ms.

### Vinkelhastighed
$$\omega = 2\pi f$$

Ved 50 Hz: $\omega = 2\pi \cdot 50 ≈ 314$ rad/s.

> 🇸🇦 **التردد** (f): عدد الدورات في الثانية. في الدنمارك = 50 هرتز، أي زمن الدورة 20 ميلي ثانية.

---

## 12.3 Vekselstrømmens værdier

I modsætning til DC, hvor en spænding kun har **én** værdi, har AC flere karakteristiske størrelser:

### Peak-værdi (top-værdi) — $U_{peak}$ eller $\hat{U}$
Maksimal øjeblikkelig værdi.

### Peak-to-peak — $U_{pp}$
Forskel mellem positiv og negativ top:
$$U_{pp} = 2 \cdot U_{peak}$$

### RMS-værdi (effektivværdi) — $U_{rms}$ eller $U_{eff}$
Den DC-spænding der ville give samme **effekt** i en modstand.

For en **sinus**:
$$U_{rms} = \frac{U_{peak}}{\sqrt{2}} \approx 0{,}707 \cdot U_{peak}$$

> 💡 **Vigtigt**: Når vi siger "230 V" om netspænding, er det **RMS-værdien**. Peak-værdien er faktisk:
> $$U_{peak} = 230 \cdot \sqrt{2} ≈ 325 \text{ V}$$

### Middelværdi (gennemsnit)
For en halv periode:
$$U_{middel} = \frac{2 \cdot U_{peak}}{\pi} \approx 0{,}637 \cdot U_{peak}$$

> 🛠 [Vekselstrøm visualizer](../interaktiv/vekselstroem.html)

### Sammenfattende — formfaktorer

| Værdi | Formel | Faktor |
|-------|--------|--------|
| Peak | $U_{peak}$ | 1,000 |
| Peak-to-peak | $2 \cdot U_{peak}$ | 2,000 |
| RMS | $U_{peak} / \sqrt{2}$ | 0,707 |
| Middel (halv periode) | $2U_{peak}/\pi$ | 0,637 |

---

## 12.4 Faseforskel

To sinus-signaler kan være **forskudt** i tid — det måles som **fasevinkel φ**.

```
u₁: ─╲    ╱─╲    ╱─
       ╲ ╱   ╲  ╱
        ╳     ╳     forskudt med vinkel φ
       ╱ ╲   ╱  ╲
u₂: ─╱    ╲╱    ╲─
```

| Forhold | Beskrivelse |
|---------|-------------|
| φ = 0° | I fase |
| φ = 90° | 1/4 periode forskudt |
| φ = 180° | I modfase |

---

## 12.5 Komponenters opførsel ved AC

### Modstand (R) — ren ohmsk last
- U og I er **i fase** (φ = 0°)
- Følger Ohms lov: $I = U/R$
- Eksempel: glødelampe, varmelegeme

### Spole (L) — ren induktiv last
- Spolen modvirker strømændringer
- **Strømmen "sakker"** spændingen med 90°
- **Induktiv reaktans**:
$$X_L = \omega L = 2\pi f L$$

| Faktor | Betydning |
|--------|-----------|
| L | Induktans (henry) |
| f | Frekvens (Hz) |
| $X_L$ | Reaktans (ohm) |

### Kondensator (C) — ren kapacitiv last
- Kondensatoren oplader/aflader
- **Spændingen sakker** strømmen med 90°
- **Kapacitiv reaktans**:
$$X_C = \frac{1}{\omega C} = \frac{1}{2\pi f C}$$

| Faktor | Betydning |
|--------|-----------|
| C | Kapacitet (farad) |
| $X_C$ | Reaktans (ohm) |

> 🇸🇦 **خلاصة**:
> - **مقاومة (R)**: التيار والجهد في الطور.
> - **ملف (L)**: التيار يتأخر عن الجهد بـ 90°.
> - **مكثف (C)**: التيار يتقدم على الجهد بـ 90°.

> 💡 **Memo-vise (DA)**: "ELI the ICE man" — i en spole (L) leder E (spænding) I'et; i en kondensator (C) leder I'et E.

---

## 12.6 Impedans (Z)

Den **samlede modstand** i et AC-kredsløb mod vekselstrømmen:

$$Z = \sqrt{R^2 + X^2}$$

hvor X er den resulterende reaktans.

For en serieforbindelse af R, L og C:
$$Z = \sqrt{R^2 + (X_L - X_C)^2}$$

### Ohms lov for AC
$$I = \frac{U}{Z}$$

---

## 12.7 Effekt i AC-kredsløb

Tre forskellige effektbegreber:

### Aktiv effekt (P) — virkeeffekt
Effekt der **rent faktisk omsættes** til arbejde, varme, lys.
- Måles i **W (watt)**
- $P = U \cdot I \cdot \cos(\varphi)$

### Reaktiv effekt (Q) — blindeffekt
Effekt der **pendler** mellem kilde og last (fra spoler/kondensatorer).
- Måles i **var (volt-ampere reaktiv)**
- $Q = U \cdot I \cdot \sin(\varphi)$

### Tilsyneladende effekt (S) — scheinleistung
**Total** effekt som kilden leverer.
- Måles i **VA (volt-ampere)**
- $S = U \cdot I$

### Effekttrekanten
$$S = \sqrt{P^2 + Q^2}$$

```
      S (VA)
       /|
      / |
     /  | Q (var)
    /   |
   / φ  |
  /_____|
    P (W)
```

### Effektfaktor (cos φ)
$$\cos(\varphi) = \frac{P}{S}$$

| cos φ | Betydning |
|-------|-----------|
| 1,0 | Ren ohmsk last (ideel) |
| 0,8–0,9 | Typisk industri (motorer) |
| 0 | Ren reaktiv (ingen virkeeffekt) |

> ⚡ **Hvorfor er cos φ vigtig?** Lav cos φ betyder at man overfører meget "blindstrøm" gennem kabler og transformere uden at lave nytte → ekstra tab. Industrien betaler ofte ekstra for dårlig cos φ → kompenseres med kondensatorer.

---

## 12.8 Resonans

Et serieforbundet R-L-C kredsløb har en **resonansfrekvens** hvor $X_L = X_C$:
$$f_0 = \frac{1}{2\pi \sqrt{LC}}$$

Ved resonans:
- $X_L - X_C = 0$
- $Z = R$ (kun ohmsk)
- Strømmen er **maksimal** (i serie)

> 📡 Bruges i radioafstemning, filtre, oscillatorer.

---

## 12.9 Praktisk eksempel

En motor med L = 0,5 H og R = 30 Ω er sluttet til 230 V, 50 Hz.

**Trin 1 — Reaktans**:
$$X_L = 2\pi \cdot 50 \cdot 0{,}5 = 157 \text{ Ω}$$

**Trin 2 — Impedans**:
$$Z = \sqrt{30^2 + 157^2} = \sqrt{900 + 24649} ≈ 160 \text{ Ω}$$

**Trin 3 — Strøm**:
$$I = \frac{230}{160} = 1{,}44 \text{ A}$$

**Trin 4 — Fasevinkel**:
$$\tan(\varphi) = \frac{X_L}{R} = \frac{157}{30} = 5{,}23$$
$$\varphi = 79{,}2°$$
$$\cos(\varphi) = 0{,}187$$

**Trin 5 — Effekter**:
- $S = 230 \cdot 1{,}44 = 331$ VA
- $P = 331 \cdot 0{,}187 = 62$ W
- $Q = 331 \cdot 0{,}982 = 325$ var

> 💡 Bemærk: motor i tomgang har dårlig cos φ. Under last forbedres det betydeligt.

---

## 📌 Resumé på arabisk

- **التيار المتردد** يُولد عند دوران ملف في مجال مغناطيسي. شكل الموجة جيبي.
- **القيمة الفعالة (RMS)** = القيمة العظمى ÷ √2. شبكة 230 فولت = القيمة العظمى ~325 فولت.
- **في الملف**: التيار يتأخر 90°. المعاوقة الحثية: $X_L = 2\pi f L$.
- **في المكثف**: التيار يتقدم 90°. المعاوقة السعوية: $X_C = 1/(2\pi f C)$.
- **الممانعة الكلية**: $Z = \sqrt{R^2 + (X_L - X_C)^2}$.
- **القدرة**: P (فعلية، W)، Q (تفاعلية، var)، S (ظاهرية، VA). $S^2 = P^2 + Q^2$.
- **معامل القدرة** cos φ = P/S — كلما اقترب من 1، كان الحمل أكثر كفاءة.

---

## ➡️ Næste skridt

- 📝 [Opgaver til kapitel 12](../opgaver/12-opgaver.md)
- 🌊 [Vekselstrøm visualizer (interaktiv)](../interaktiv/vekselstroem.html)
- ➡️ [Kapitel 13 — 3-faset vekselstrøm](13-3-faset-vekselstroemsteori.md)
