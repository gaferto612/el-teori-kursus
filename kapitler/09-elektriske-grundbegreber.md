# Kapitel 9 — Elektriske grundbegreber
> المفاهيم الكهربائية الأساسية

## 🎯 Læringsmål

- Forstå hvad elektricitet er på elektronniveau
- Skelne mellem jævnstrøm (DC) og vekselstrøm (AC)
- Definere spænding, strøm, modstand og effekt
- Læse simple kredsløbsdiagrammer
- Forstå sikkerhedsmæssige risici ved el

---

## 9.1 Hvad er elektricitet?

Ordet **elektricitet** kommer fra det græske ord *elektron* = rav. Det er et fysisk fænomen knyttet til **elektriske ladninger** — enten i hvile (elektrostatik) eller i bevægelse (elektrodynamik).

> 💡 **Elektrisk strøm** = bevægelse af elektroner gennem en leder.

### Måder at frembringe elektricitet på

| Form | Princip | Eksempel |
|------|---------|----------|
| **Statisk** | Gnidning | Pels mod glas |
| **Galvanisk** | Kemisk reaktion | Batteri |
| **Induceret** | Elektromagnetisme | Generator, dynamo |
| **Foto** | Lyspåvirkning | Solcelle |
| **Piezo** | Mekanisk tryk | Lighter, sensor |
| **Termo** | Varmepåvirkning | Termoelement |

---

## 9.2 Jævnstrøm vs. vekselstrøm

### Jævnstrøm (DC — Direct Current) (التيار المستمر)
- Strømmen løber **vedvarende i samme retning**
- Den ene klemme er altid + (positiv), den anden − (negativ)
- Kilder: batterier, solceller, ensretterstrømforsyninger

### Vekselstrøm (AC — Alternating Current) (التيار المتردد)
- Strømmen **skifter retning** med konstante tidsintervaller
- I Danmark: **50 Hz** (skifter retning 100 gange per sekund)
- Sinusformet
- Kilder: lysnettet, generatorer

> 🌍 I USA er netfrekvensen 60 Hz. I de fleste andre lande inkl. Danmark er det 50 Hz.

---

## 9.3 Spænding (U)

**Spændingen** er forskellen i elektrisk potentiale mellem to punkter — det "tryk" der driver strømmen.

| Symbol | Enhed | Måler |
|--------|-------|-------|
| U | volt (V) | Voltmeter |

### Voltmeter
Tilsluttes **parallelt** med komponenten man vil måle over:

```
   ─────●─── komponent ──●─────
         │              │
         └────[ V ]─────┘
              voltmeter
```

### Typiske spændingsniveauer

| Anvendelse | Spænding |
|-----------|----------|
| Knapcelle | 1,5 V DC |
| Bilbatteri | 12 V DC |
| Telefon-USB | 5 V DC |
| Stikkontakt DK | 230 V AC |
| Industri 3-fase | 400 V AC |
| Højspændingsfordeling | 10–20 kV |
| Højspændingstransmission | 132–400 kV |

> ⚡ **Lynhurtig forplantning**: Spændingen bevæger sig gennem leder med næsten lysets hastighed (~300.000 km/s). **Elektronerne** derimod driver kun med få mm/s.

---

## 9.4 Strøm (I)

**Elektrisk strøm** = mængden af ladning der passerer pr. sekund.

| Symbol | Enhed | Måler |
|--------|-------|-------|
| I | ampere (A) | Amperemeter |

$$I = \frac{Q}{t} \quad \text{(coulomb pr. sekund)}$$

### Amperemeter
Tilsluttes **i serie** med komponenten:

```
  ───[A]──── komponent ────
   amperemeter
```

> ⚠ **Aldrig** parallel-tilslut et amperemeter direkte over spændingskilden — det vil kortslutte!

### Typiske strømme

| Anvendelse | Strøm |
|-----------|-------|
| Mobilopladning | ~1 A |
| LED-pære | 0,05 A (50 mA) |
| Husholdnings stikkontakt | op til 13–16 A |
| Lille elmotor | 5–10 A |
| Industrimotor | 50–200 A |

---

## 9.5 Modstand (R)

**Modstanden** er materialets evne til at modsætte sig strømmen.

| Symbol | Enhed | Måler |
|--------|-------|-------|
| R | ohm (Ω) | Ohmmeter (eller multimeter) |

### Ledningsmodstand

$$R = \rho \cdot \frac{l}{A}$$

| Symbol | Betydning |
|--------|-----------|
| ρ | Resistivitet (Ω·mm²/m) — afhænger af materiale |
| l | Længde (m) |
| A | Tværsnitsareal (mm²) |

> 💡 **Konsekvens**: Lange og tynde ledere har høj modstand. Korte og tykke har lav.

### Resistivitet for almindelige metaller

| Materiale | ρ (Ω·mm²/m) |
|-----------|-------------|
| Sølv | 0,016 |
| Kobber | 0,0175 |
| Aluminium | 0,028 |
| Jern | 0,1 |
| Nikkelin (modstandstråd) | 0,4 |
| Konstantan | 0,49 |

### Modstandens temperaturafhængighed
For metaller stiger modstanden med temperaturen:
$$R_T = R_{20} \cdot (1 + \alpha \cdot \Delta T)$$

hvor α er **temperaturkoefficienten**:
- Kobber: 0,004 /K
- Aluminium: 0,004 /K

---

## 9.6 Ohms lov

> **Den vigtigste formel i el-teknik:**
> $$U = R \cdot I$$

Kan omformes til:
$$I = \frac{U}{R} \quad \text{eller} \quad R = \frac{U}{I}$$

> 🇸🇦 **قانون أوم**: الجهد = المقاومة × التيار. هذا هو القانون الأساسي في كل علم الكهرباء.

### Eksempler

**Eksempel 1**: Hvor stor en strøm går der gennem en modstand på 100 Ω ved 12 V?
$$I = \frac{U}{R} = \frac{12}{100} = 0{,}12 \text{ A} = 120 \text{ mA}$$

**Eksempel 2**: Hvor stor er modstanden i en glødepære, når den ved 230 V optager 0,3 A?
$$R = \frac{U}{I} = \frac{230}{0{,}3} \approx 767 \text{ Ω}$$

> 🛠 Brug det interaktive værktøj: [**Ohms lov-beregner**](../interaktiv/ohms-lov.html)

---

## 9.7 Effekt (P)

**Elektrisk effekt** = energi pr. tid.

| Symbol | Enhed |
|--------|-------|
| P | watt (W) |

### Effektformler
$$P = U \cdot I$$
$$P = I^2 \cdot R$$
$$P = \frac{U^2}{R}$$

### Eksempler
- En glødepære på 60 W ved 230 V trækker: $I = P/U = 60/230 ≈ 0{,}26$ A
- En elkedel på 2.000 W = 2 kW
- En motor på 5,5 kW = 5.500 W

### Effekt vs. energi
**Effekt** er hvor hurtigt energien bruges. **Energi** er den samlede mængde:
$$E = P \cdot t$$

Måles ofte i kWh: 1 kWh = 1.000 W i 1 time = 3,6 MJ.

---

## 9.8 Kredsløb og symboler

### Det elektriske kredsløb
Tre nødvendige dele:
1. **Spændingskilde** (batteri, generator)
2. **Forbrugsgenstand** (lampe, motor, modstand)
3. **Forbindelsesledninger**

```
    ┌──[ R ]──┐
    │         │
   (V)        │
    │         │
    └─────────┘
```

### Almindelige symboler

| Komponent | Symbol |
|-----------|--------|
| Batteri / DC | ─┤├─ |
| Vekselspændingskilde | ~ |
| Modstand | ─[▭]─ eller ─/\\/\\─ |
| Lampe | ─⊗─ |
| Afbryder | ─ /─ |
| Sikring | ─[▭]─ |
| Voltmeter | ─(V)─ |
| Amperemeter | ─(A)─ |
| Jordforbindelse | ⏚ |

---

## 9.9 Jordforbindelse og potentiale

**Potentialet** = spændingen i forhold til jord.
- Jord regnes som referencepunkt = 0 V
- I sikker installation forbindes alle metalkapper til jord (jordledning, gul/grøn)

> ⚠ **Sikkerhed**: Berøring af 230 V mens man står på jord = potentielt livsfarligt strømstød.

---

## 9.10 El-sikkerhed — kort

### Strøm gennem mennesket
| Strøm | Effekt på krop |
|-------|----------------|
| < 1 mA | Mærkes ikke |
| 1–10 mA | Føles, kan kontrollere muskler |
| 10–30 mA | Muskelkramper, kan ikke slippe |
| > 50 mA | Hjerteflimren, livsfare |
| > 100 mA | Højrisiko for død |

### Beskyttelse
- **HFI/HPFI-relæ**: udløser ved 30 mA fejlstrøm
- **Sikringer**: beskytter mod overstrøm
- **Jordforbindelse**: leder fejlstrøm sikkert til jord
- **Dobbelt isolation** (klasse II-apparater): symbol ⊡

---

## 📌 Resumé på arabisk

- **التيار المستمر (DC)**: يتدفق في اتجاه واحد دائماً (مثل البطاريات).
- **التيار المتردد (AC)**: يغير اتجاهه باستمرار. في الدنمارك التردد 50 هرتز.
- **الجهد (U)** يُقاس بالفولت (V) — الفولت متر يُوصل **بالتوازي**.
- **التيار (I)** يُقاس بالأمبير (A) — الأمبير متر يُوصل **بالتسلسل**.
- **المقاومة (R)** تُقاس بالأوم (Ω). تعتمد على المادة، الطول، والمقطع.
- **قانون أوم**: U = R · I
- **القدرة**: P = U · I = I²·R = U²/R
- **سلامة**: تيار 30 mA يكفي لإيقاف القلب — استخدم دائماً مقاطع HFI والتأريض.

---

## ➡️ Næste skridt

- 📝 [Opgaver til kapitel 9](../opgaver/09-opgaver.md)
- 🧮 [Ohms lov-beregner (interaktiv)](../interaktiv/ohms-lov.html)
- ➡️ [Kapitel 10 — Jævnstrømsteori](10-jaevnstroemsteori.md)
