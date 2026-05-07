# Kapitel 21 — Instrumenttyper
> أنواع أجهزة القياس

## 🎯 Læringsmål

- Kende analoge og digitale måleinstrumenter
- Forstå måleinstrumenters princip (drejespole, jernkerne osv.)
- Vælge rigtig instrumenttype til AC, DC og blandet måling
- Forstå nøjagtighedsklasser
- Bruge multimeter, oscilloskop, klemmeampere, isolationsmåler

---

## 21.1 Analog vs. digital

### Analoge instrumenter
- **Viser** med skala
- Trinløs visning
- Kan være intuitive for trends
- Følsomme for stød, vibration

### Digitale instrumenter
- **Tal-display**
- Præcise aflæsninger
- Auto-range, tilbehør, datalogning
- Standard i moderne elektroteknik

---

## 21.2 Drejespoleinstrumentet

Det klassiske analoge instrument til **DC**.

### Princip
En lille drejelig spole hænger i et permanent magnetfelt. Når strøm går gennem spolen, drejer den.

```
       ╱────────╲
      ╱  spole   ╲
     │     I      │   ← drejning ∝ I
     │   ╱   ╲    │
      ╲  ╲ ╱    ╱
       ╲────────╱
        magnetfelt
```

### Egenskaber
- **Følsomt** — kan måle små strømme
- **Lineær** skala
- **Kun DC** (eller pulserende DC efter ensretter)
- **Polariteten betyder** noget — forkert tilslutning slår viseren venstre

> 💡 Bruges også til **galvanometre** og laboratorieinstrumenter.

---

## 21.3 Jernkerneinstrumentet

Til **AC og DC**.

### Princip
Et bevægeligt jernstykke trækkes ind i en spole når strømmen øges (uanset polaritet).

### Egenskaber
- Måler **RMS-værdi** automatisk (ved AC)
- Kan måle **både AC og DC**
- **Ulineær** skala (ikke ligefordelt)
- Mindre nøjagtigt end drejespole

> ⚙ Bruges i industriprodukter — robust, billig, kan håndtere store strømme.

---

## 21.4 Elektrodynamisk instrument

### Princip
To spoler — én fast og én bevægelig. Strøm gennem begge giver kraft.

### Anvendelse
**Wattmeter** — måler effekt direkte (P = U · I · cos φ):
- Faste spoler tilsluttes som **strømmåling** (i serie med last)
- Bevægelig spole som **spændingsmåling** (parallel)
- Visning er proportional med effekten

---

## 21.5 Multimeter (multimeteret)

Det vigtigste alsidige instrument. Kan måle:

| Funktion | Symbol | Område |
|----------|--------|--------|
| DC-spænding | V⎓ | mV til kV |
| AC-spænding | V~ | mV til kV |
| DC-strøm | A⎓ | μA til A |
| AC-strøm | A~ | mA til A |
| Modstand | Ω | Ω til MΩ |
| Diode-test | →|⊢ | check fremspænding |
| Kontinuitet | •)) | hyletone hvis sluttet |
| Kapacitet | F | nF til mF |
| Frekvens | Hz | Hz til MHz |
| Temperatur | °C | med termoelement |

### Nøjagtighed
Angives typisk som "±(% af aflæsning + antal cifre)":
- Eksempel: "±(0,5 % + 2)" på 100,0 V → afvigelse højst 0,5 V + 0,2 V = ±0,7 V

> 🛠 **Almindelige multimetre**: Fluke 87V (professionel), Fluke 117 (el-installatør), UNI-T UT139C (hobby).

### Sikkerhed (CAT-kategorier)

| CAT | Anvendelse |
|-----|-----------|
| CAT II | Almindelige stikkontakter |
| CAT III | Fast installation, fordelingstavler |
| CAT IV | Forsyning fra netforbindelse, måler-bokse |

> ⚠ **Brug aldrig** et CAT II-multimeter på en hovedfordelingstavle — kortslutningsstrømme kan være dødelige.

---

## 21.6 Klemmeamperemeter (tang-amperemeter)

Måler **strøm uden at bryde kredsløbet** — klemmes om en enkelt leder.

### Princip
- **AC**: Måler magnetfeltet via en kerne (transformerprincip)
- **DC**: Bruger Hall-effekt sensor (kræver speciel type)

### Anvendelse
- Ideelt til at tjekke driftstrøm i installationer
- Ingen afbrydelse af kredsløb
- Kan måle store strømme (op til kA)

> 💡 **Vigtig regel**: Klem **kun én leder** — hvis du klemmer om både L og N, ophæver felterne hinanden, og du måler 0.

---

## 21.7 Isolationsmåler (megger)

Måler **isolationsmodstand** med høj DC-spænding (typisk 250 V, 500 V eller 1.000 V).

### Anvendelse
- Kontrol af isolation i installationer
- Maskinvedligehold
- Krav i el-syn / installation-eftersyn

### Aflæsning
| Værdi | Vurdering |
|-------|-----------|
| > 1 GΩ | Fremragende |
| > 100 MΩ | God |
| > 10 MΩ | OK (krav i ny installation) |
| < 1 MΩ | **Defekt** — udbedring krævet |

> ⚠ **Frakobl alt** strømførende inden måling. Anlægget oplades til måle-spændingen — efter måling: aflad!

---

## 21.8 Oscilloskop

Et oscilloskop visualiserer **spændingens variation over tid**. Uundværlig i elektronik-fejlfinding.

### Hovedkomponenter
- **Skærm** med X (tid) og Y (spænding) akser
- **Probe** (~10 MΩ indgangsmodstand)
- **Trigger** (synkronisering af visning)
- **Time/div** og **V/div** indstillinger

### Anvendelse
- Måle frekvens, periodetid, peak-værdi
- Se støj, glitches, ringing
- Måle pulsbredde, stigningstider
- Sammenligne signaler (2 eller 4 kanaler)

### Moderne oscilloskoper
- Digitale (DSO)
- Touch-screen
- Mange kanaler (op til 8)
- Logic analyzer-funktion
- USB-interface og PC-software

> 🛠 **Almindelige**: Rigol DS1054Z (begynder), Tektronix MSO46 (avanceret), Picoscope (USB-baseret).

---

## 21.9 Andre instrumenter

| Instrument | Måler |
|-----------|-------|
| **Frekvensteller** | Frekvens med høj nøjagtighed |
| **LCR-meter** | Induktans (L), kapacitet (C), modstand (R) |
| **Funktion-generator** | Genererer sinus, firkant, savtak |
| **Logic analyzer** | Mange digitale signaler samtidig |
| **Spectrum analyzer** | Frekvens-spektrum (RF, EMC) |
| **Lux-meter** | Lysstyrke |
| **Pyrometer** | Temperatur uden kontakt (IR) |
| **Termografi-kamera** | Termiske billeder |

---

## 21.10 Nøjagtighedsklasser

Analoge instrumenter inddeles i klasser:

| Klasse | Tolerance | Anvendelse |
|--------|-----------|-----------|
| 0,1 | ±0,1 % | Laboratorium, kalibrering |
| 0,2 | ±0,2 % | Præcisionsmåling |
| 0,5 | ±0,5 % | Industri, præcision |
| 1,0 | ±1 % | Almindelig industri |
| 1,5 | ±1,5 % | Tavlemontering |
| 2,5 | ±2,5 % | Generelt brug |

> 💡 Toleranceren angives på **fuld skala**, ikke på aflæst værdi! Et 1 %-instrument der viser 50 % af skalaen kan have ±2 % fejl af aflæsningen.

---

## 21.11 Ind- og udgangsmodstand

### Voltmeter
- Skal have **høj** indgangsmodstand (mindst 10 MΩ)
- Lav modstand → trækker strøm → forstyrrer kredsen

### Amperemeter
- Skal have **lav** modstand (få mΩ)
- Høj modstand → spændingsfald → forstyrrer kredsen

### Oscilloskop-probe
- Standard 10 MΩ
- Brug "10×" probe for endnu mindre belastning af kredsen og højere båndbredde

---

## 📌 Resumé på arabisk

- **الجهاز ذو الملف الدوار** (drejespole): يقيس DC، حساس، تدريج خطي.
- **جهاز نواة الحديد** (jernkerne): يقيس AC و DC، تدريج غير خطي.
- **المالتيميتر**: الجهاز الأكثر استخداماً — يقيس الجهد، التيار، المقاومة، السعة، التردد، والاستمرارية.
- **فئات السلامة (CAT)**: استخدم CAT III أو IV للقياسات في اللوحات الكهربائية.
- **مقياس الكلامب** (klemmeampere): يقيس التيار دون قطع الدائرة — مفيد جداً للصيانة.
- **مقياس العزل** (Megger): يستخدم جهد عالي (500-1000 V DC) لقياس مقاومة العزل.
- **الأوسيلوسكوب**: يعرض تغير الجهد مع الزمن — أساسي في تشخيص الإلكترونيات.
- **فئة الدقة**: 1% أو 1,5% للأجهزة الصناعية، 0,1% للمختبرات.

---

## ➡️ Næste skridt

- 📝 [Opgaver til kapitel 21](../opgaver/21-opgaver.md)
- ➡️ [Kapitel 22 — Måleprincipper](22-maaleprincipper.md)
