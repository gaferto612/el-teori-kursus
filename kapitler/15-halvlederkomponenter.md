# Kapitel 15 — Halvlederkomponenter
> مكونات أشباه الموصلات

## 🎯 Læringsmål

- Forstå halvledermateriale (Si, Ge) og dotering
- Kende dioden, dens karakteristik og typer
- Forstå transistorens virkemåde (BJT, FET)
- Kende thyristor, triac og diac
- Forstå anvendelser i moderne elektronik

---

## 15.1 Halvledermateriale

**Halvledere** har 4 valenselektroner (gruppe 14 i det periodiske system):

| Element | Symbol | Brug |
|---------|--------|------|
| Silicium | Si | Næsten al moderne elektronik |
| Germanium | Ge | Tidligere transistorer, RF |
| Galliumarsenid | GaAs | Højfrekvens, LED |

### Den rene halvleder (intrinsisk)
Ved stuetemperatur er den næsten en isolator. Ved opvarmning bliver den ledende — men ikke stabil nok til praktisk brug.

---

## 15.2 Dotering

For at gøre halvlederen brugbar tilsættes **urenheder** (dotering):

### N-type (negativ dotering)
Tilsæt grundstof med **5 valenselektroner** (fx fosfor, antimon).
→ "ekstra" elektroner = **frie ladningsbærere**.

### P-type (positiv dotering)
Tilsæt grundstof med **3 valenselektroner** (fx bor, indium).
→ "huller" (mangler en elektron) = **positive ladningsbærere**.

> 💡 I N-type leder elektroner strømmen. I P-type leder hullerne strømmen.

---

## 15.3 PN-overgangen — dioden

Når P-type og N-type forenes, dannes en **PN-overgang**.

```
   ┌────────┬────────┐
   │   P    │    N   │
   │  + + + │ - - -  │
   └────────┴────────┘
        ↑
     Spærrelag (ca. 0,01 mm)
```

### Spærrelaget
Ved grænsen flyder elektroner ind i P-laget og huller ind i N-laget. De **rekombinerer** og efterlader et område uden frie ladningsbærere = **spærrelaget**.

### Frem-spændt (gennemgang)
- + på P-side, − på N-side
- Spærrelaget formindskes → strømmen flyder
- Dioden **leder**
- Spændingsfald: ~0,7 V (Si), ~0,3 V (Ge)

### Bagudspændt (spærret)
- − på P-side, + på N-side
- Spærrelaget vokser → ingen strøm
- Dioden **spærrer**

> 🇸🇦 **الديود**: يسمح بمرور التيار في اتجاه واحد فقط (من الأنود + إلى الكاثود -).

---

## 15.4 Diodens karakteristik

```
     I
     │      /
     │     /  Frem-spændt
     │    /
     │   /
─────┼──/────────  U
     │ │   ←─ ca. 0,7 V (Si)
     │ │
   ──┼─┘
     │ Bagudspændt
     │ (lille lækstrøm)
     │
   ──┼── ← gennembrudsspænding
     │
```

**Vigtige værdier**:
- $U_F$ = forward voltage (~0,7 V)
- $U_R$ = reverse breakdown voltage (afhænger af type)
- $I_F$ = forward current (typisk 100 mA – 100 A)

---

## 15.5 Diodetyper

| Type | Anvendelse |
|------|-----------|
| Almindelig (rectifier) | Ensretning af AC til DC |
| **Zener** | Spændingsstabilisering — bruger gennembrudsspænding bevidst |
| **LED** (lysdiode) | Lys — Si-baseret + dopanter giver farve |
| Schottky | Hurtig, lille spændingsfald (~0,3 V) |
| Foto-diode | Genererer strøm ved lyspåvirkning |
| Varicap | Variabel kapacitet ved spændingsændring |
| Tunnel-diode | Højhastigheds-elektronik |

### LED-farver

| Materiale | Farve | $U_F$ |
|-----------|-------|-------|
| GaAsP | Rød | 1,8 V |
| GaP | Gul/grøn | 2,0–2,2 V |
| InGaN | Blå/hvid | 3,0–3,3 V |

> 💡 **Beregning af forskel-modstand til LED**: $R = (U_{kilde} - U_F) / I_{LED}$

---

## 15.6 Transistoren — BJT (Bipolar Junction Transistor)

Tre lag halvleder = **NPN** eller **PNP** transistor.

```
   NPN:           PNP:

       C              C
       │              │
   B───┤              ├───B
       │              │
       E              E
```

### Tre tilslutninger
| Ben | Funktion |
|-----|----------|
| **Basis (B)** | Styreben — lille strøm her styrer stor strøm gennem C-E |
| **Kollektor (C)** | Hovedstrømmens indgang (NPN) |
| **Emitter (E)** | Hovedstrømmens udgang (NPN) |

### Strømforstærkning
$$\beta = h_{FE} = \frac{I_C}{I_B}$$

Typisk: β = 50–500.

### Anvendelse
1. **Forstærker** — lille signal forstærkes til større
2. **Switch** — fuld ON/OFF — bruges som digital kontakt

> ⚙ Som switch styres transistoren mellem to tilstande:
> - Mætning (ON): $V_{CE} ≈ 0$ — leder fuldt
> - Cut-off (OFF): $I_C ≈ 0$ — spærrer

---

## 15.7 FET (Field Effect Transistor)

Spændingsstyret — tre tilslutninger:
- **Gate (G)** — styreben (høj impedans)
- **Drain (D)** — hovedstrømmens indgang
- **Source (S)** — hovedstrømmens udgang

### Typer

| Type | Forkort | Beskrivelse |
|------|---------|-------------|
| JFET | J | Junction FET — analoge formål |
| **MOSFET** | M | Metal-Oxide-Semiconductor — det dominerende i moderne elektronik |
| IGBT | — | Insulated Gate Bipolar Transistor — store effekter (motorstyring, frekvensomformere) |

> 💡 **MOSFET** er fundamentet for alle moderne mikroprocessorer. Milliarder af MOSFET'er på en chip.

### MOSFET som power switch
Bruges meget i moderne effektelektronik:
- Solcelleinvertere
- DC/DC konvertere
- Motorstyringer (sammen med IGBT)
- Switching strømforsyninger (SMPS)

---

## 15.8 Thyristor

En **thyristor** (SCR — Silicon Controlled Rectifier) er en **styret** ensretter med 4 lag (PNPN) og 3 ben:
- **Anode (A)**
- **Katode (K)**
- **Gate (G)** — udløser

### Virkemåde
- Som diode i frem-retning, men spærrer **indtil** gate udløses
- Når gate'en får en kort strøm-puls, **tænder** thyristoren
- Holder sig tændt indtil strømmen falder til 0 (eller polariteten skifter)

> ⚙ Bruges i: motorstyring, lysdæmpning (lampe-dimmer), effektregulering, krafttoppe.

---

## 15.9 Triac

En **triac** er som to anti-parallelle thyristorer i én komponent. Kan styre **vekselstrøm** i begge halvbølger.

Bruges i:
- Lysdæmpere (almindelige dimmere)
- Hastighedsregulering af universalmotorer (boremaskiner)
- Varmeregulering

---

## 15.10 Diac

En **diac** er en spændingsfølsom omskifter — bruges typisk til at udløse triac/thyristor på et bestemt spændingsniveau. Brydespænding ca. ±30 V.

Bruges som **udløserkomponent** i triac-styringer.

---

## 15.11 Integrerede kredse (IC)

En **IC** indeholder mange transistorer + andre komponenter på en enkelt halvlederchip.

| Generation | Antal transistorer |
|------------|--------------------|
| SSI (1960'erne) | ~10 |
| MSI | ~100 |
| LSI | ~1.000 |
| VLSI | ~100.000 |
| ULSI | millioner |
| Moderne CPU | milliarder |

### Almindelige IC-typer
- **Operationsforstærker** (op-amp) — fx LM741, LM358
- **Spændingsregulator** — fx 7805, LM317
- **Logik-ICs** — TTL, CMOS familier
- **Mikrocontrollere** — Arduino, ESP32, PIC, STM32
- **Specielle** — timer (555), DAC, ADC, motor-drivere

---

## 15.12 Optokoblere

To komponenter i én pakke:
- LED + fototransistor adskilt af et glasvindue
- Galvanisk **isolation** mellem ind- og udgang
- Bruges til at koble lavspændingssignaler til højspændingsstyrkredse

> 🛡 Bruges meget i PLC ind- og udgange (Siemens TIA Portal m.m.) for at beskytte CPU'en mod fejlspændinger fra felt-sensorer.

---

## 📌 Resumé på arabisk

- **أشباه الموصلات** (Si, Ge): لها 4 إلكترونات تكافؤ. بإضافة شوائب نحصل على نوعي N (موصل بإلكترونات) و P (موصل بالثقوب).
- **الديود (PN)**: يمرر التيار في اتجاه واحد فقط — استخدامات: تقويم AC إلى DC.
- **الترانزستور (BJT)**: NPN أو PNP، بثلاث أطراف (B, C, E). يعمل كمضخم أو كمفتاح.
- **MOSFET**: الترانزستور الأكثر استخداماً اليوم — أساس كل المعالجات.
- **IGBT**: ترانزستور قوي يُستخدم في تحكم المحركات ومحولات التردد.
- **الثايرستور**: مقوّم مُتحكم به — يُشعّل بإشارة على الـ Gate ويبقى مشتعلاً حتى ينقطع التيار.
- **التراياك (Triac)**: مثل ثايرستورين معكوسين — يتحكم بالتيار المتردد في الاتجاهين.
- **الدائرة المتكاملة (IC)**: ملايين أو مليارات من الترانزستورات على شريحة واحدة.

---

## ➡️ Næste skridt

- 📝 [Opgaver til kapitel 15](../opgaver/15-opgaver.md)
- ➡️ [Kapitel 16 — Forstærkning](16-forstaerkning.md)
