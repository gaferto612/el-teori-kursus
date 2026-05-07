# Kapitel 22 — Måleprincipper
> مبادئ القياس

## 🎯 Læringsmål

- Forstå korrekt tilslutning af instrumenter
- Beregne måleudvidelse (formodstand, shunt, måletransformator)
- Forstå målefejl og hvordan de minimeres
- Anvende sensorer (PT100, termoelement, tryksensor mv.)
- Forstå A/D- og D/A-konvertering

---

## 22.1 Korrekt tilslutning af instrumenter

### Voltmeter — parallel
$$\boxed{\text{Voltmeter tilsluttes ALTID parallelt med komponenten}}$$

```
   ─────●─── komponent ──●─────
         │              │
         └────[ V ]─────┘
```

**Hvorfor**: For at måle spændingsforskellen MELLEM to punkter må instrumentet være tilsluttet de samme to punkter.

### Amperemeter — i serie
$$\boxed{\text{Amperemeter tilsluttes ALTID i serie med kredsen}}$$

```
  ──[ A ]──── komponent ────
```

**Hvorfor**: Strømmen skal **gennem** instrumentet for at blive målt.

> ⚠ **Aldrig** parallelt-tilslut et amperemeter på spændingskilden! Det vil kortslutte med stor strøm — og kan ødelægge både instrumentet og brænder sikringen.

---

## 22.2 Måleområde-udvidelse

### Voltmeter med formodstand (forrige seriemodstand)

For at måle **højere** spændinger end voltmeterets nominelle område:

```
       R_form
   ●──[▭]───●─── voltmeter (R_v)
   │         │
   U_måle   ─┴─
```

$$R_{form} = R_v \cdot (n - 1)$$

hvor $n = U_{ny} / U_{instrument}$ er udvidelsesforholdet.

**Eksempel**: Et voltmeter med 100 V nominel og $R_v = 10$ kΩ skal udvides til 1000 V.
- $n = 1000/100 = 10$
- $R_{form} = 10.000 \cdot (10-1) = 90$ kΩ

### Amperemeter med shunt

For at måle **højere** strømme:

```
            shunt R_s
        ┌───[▭]───┐
        │          │
   ─────●          ●─────  målestrømmen passerer
        │          │
        └─[A]──────┘  (R_a)
```

$$R_s = \frac{R_a}{n - 1}$$

hvor $n = I_{ny} / I_{instrument}$.

**Eksempel**: Et amperemeter til 1 A med $R_a = 0{,}1$ Ω skal udvides til 10 A.
- $n = 10$
- $R_s = 0{,}1 / 9 ≈ 0{,}011$ Ω

> 💡 Shuntsmodstande er typisk **kalibreret** små metalstrips med præcis modstand.

---

## 22.3 Måletransformatorer

For meget store strømme og spændinger bruges **måletransformatorer**:

### Strømtransformator (CT)
- Primær: én tråd med stor strøm gennem
- Sekundær: ofte til 5 A eller 1 A
- Eksempel: 200/5 → 200 A primær = 5 A sekundær

> ⚠ **CRITIQUE**: En CT må **aldrig** drives med åben sekundærside! Det kan generere flere kV der kan dræbe og brænde isolering.

### Spændingstransformator (VT)
- Reducerer høj spænding til 100 V eller 110 V
- Eksempel: 10.000/100

> 🏭 Måletransformatorer er standard på højspændingsnet og industri-tavler over ~1.000 V.

---

## 22.4 Målefejl

### Systematiske fejl
- **Instrumentfejl**: kalibrering, klasse-tolerance
- **Tilslutningsfejl**: voltmeter trækker strøm, amperemeter har modstand
- **Aflæsningsfejl**: parallaks ved analoge

### Tilfældige fejl
- **Støj**, **temperatur-drift**
- Skal håndteres statistisk (gennemsnit af flere målinger)

### Voltmeter-fejl ved måling over R

```
    ●──[ R ]──●
    │         │
    └────V────┘  R_v
```

Voltmeteret tager en lille strøm gennem $R_v$ — det giver fejl hvis $R_v$ ikke er meget større end R.

> 💡 **Tommelfingerregel**: $R_v \geq 100 \cdot R$ for forsvarlig måling.

### Amperemeter-fejl

Amperemeteret har sin egen modstand $R_a$, der **lægger sig i kredsen** og reducerer strømmen lidt.

> 💡 **Tommelfingerregel**: $R_a \leq R/100$.

---

## 22.5 Sensorer — at måle ikke-elektriske størrelser

### Temperatur

| Sensor | Princip | Område |
|--------|---------|--------|
| **PT100** | Pt-tråd, R = 100 Ω ved 0°C | -200 til +850°C |
| **PT1000** | Som PT100, men 1000 Ω | Bedre til lange ledninger |
| **NTC** | Halvleder, R falder ved varme | -50 til +150°C (typisk) |
| **Termoelement (J, K, T)** | Galvanisk spænding | -200 til +1200°C |
| **IR-pyrometer** | Måler IR-udstråling | Kontaktfri, op til 3000°C |

#### PT100 — beregning
$$R_T = R_0 \cdot (1 + \alpha \cdot \Delta T)$$

For PT100: α = 0,003851 /°C, $R_0 = 100$ Ω.

**Eksempel**: Ved 50°C:
$$R = 100 \cdot (1 + 0{,}003851 \cdot 50) = 119{,}3 \text{ Ω}$$

> 🔥 **Kedelpasser-relevant**: PT100 bruges overalt i kedler og industriprocesser. Standard i SCADA og PLC-systemer.

### Termoelement
To forskellige metaller dannes en lille spænding der afhænger af temperaturforskellen.

| Type | Materiale | Område | Følsomhed |
|------|-----------|--------|-----------|
| K | NiCr / NiAl | -200 til +1200°C | 41 μV/°C |
| J | Fe / NiCu | -40 til +750°C | 51 μV/°C |
| T | Cu / NiCu | -200 til +400°C | 43 μV/°C |
| S | Pt-Rh / Pt | 0 til +1600°C | 11 μV/°C |

> 💡 Termoelement er **billige**, robuste og tåler ekstreme temperaturer — derfor brugt i industriovne, fyringsanlæg.

### Tryk

| Sensor | Princip |
|--------|---------|
| **Piezoresistiv** | Trykker membran med strain gauges |
| **Kapacitiv** | Trykændring → kapacitetsændring |
| **Piezoelektrisk** | Krystaller giver spænding under tryk (kun dynamisk) |

Standard 4-20 mA udgang i industrien.

### Niveau, flow, position

| Måling | Sensor |
|--------|--------|
| Væskeniveau | Ultralyd, kapacitiv, vippe-flåd |
| Flow (gennemstrømning) | Turbine, magnetisk-induktiv, ultralyd |
| Position | Encoder, LVDT, potentiometer |

---

## 22.6 Standard signaler i industrien

### Strømsløjfe 4–20 mA
- **0 % af måleområde** = 4 mA
- **100 % af måleområde** = 20 mA
- Hvis sensor svarer < 4 mA = fejl detekteret

```
   PT100 ──[transmitter]──[4-20 mA loop]──[PLC]
              (lokal)         (kabel)        (CPU)
```

> ⚙ **Hvorfor 4-20 mA og ikke 0-10 V?** Strøm er **upåvirket** af ledningsmodstand og elektromagnetisk støj. Plus: 0 mA betyder fejl, ikke 0 % — let at detektere.

### Andre signaler

| Type | Område |
|------|--------|
| 0–10 V | Kortere afstande, billigere |
| 0–20 mA | Sjælden, ingen fejl-detektion |
| 4–20 mA HART | Som ovenfor + digital data overlejret |
| Fieldbus (Profibus, Profinet, EtherCAT) | Digital, mange enheder på samme bus |

---

## 22.7 Analog-til-digital konvertering (ADC)

Skal en analog sensor læses af en mikrocontroller eller PLC, går signalet gennem en **ADC**.

### Karakteristika
- **Opløsning**: angives i bits (10, 12, 16, 24)
  - 10 bits = 1024 trin
  - 12 bits = 4096 trin
  - 16 bits = 65.536 trin
- **Samplingsfrekvens**: hvor ofte signalet aflæses (Hz)
- **Indgangsområde**: 0–5 V, 0–10 V, ±10 V

### Konverteringsmetoder
- **Successive approximation** (SAR) — hurtig, mest brugt
- **Flash** — meget hurtig, men dyr
- **Sigma-delta** — meget høj opløsning, lavere hastighed

> 💡 Eksempel: 12-bit ADC med 10 V område → opløsning = 10/4096 ≈ 2,4 mV per trin.

### Nyquist-Shannon
For at gengive et signal korrekt skal samplingsfrekvensen være **mindst dobbelt** så høj som signalets højeste frekvens:
$$f_{sample} > 2 \cdot f_{max}$$

---

## 22.8 Digital-til-analog konvertering (DAC)

For at sende et **analogt signal ud** fra en digital kontroller bruges en **DAC**.

### Anvendelse
- Setpoint til regulator (4-20 mA ud)
- Hastighedsreference til frekvensomformer
- Lyd-output (DAC i hi-fi-systemer)

---

## 22.9 Måleprincippet "balanceret bro" (Wheatstone-bro)

Klassisk metode til præcis modstandsmåling.

```
       ●─[R₁]──●──[R₂]─●
       │       │       │
       U_in   V_måle   U_in (samme)
       │       │       │
       ●─[R_x]─●──[R₃]─●
```

Når broen er **i balance**: $V_{måle} = 0$ og:
$$\frac{R_1}{R_2} = \frac{R_x}{R_3}$$

→ $R_x = R_3 \cdot \dfrac{R_1}{R_2}$

> 🧪 Bruges i:
> - Strain gauges (vejning, deformationsmåling)
> - PT100-måling (3- eller 4-leder bro)
> - Lab-instrumenter

---

## 22.10 Kalibrering

> **Regelmæssig kalibrering** er nødvendig for nøjagtige målinger.

### Trinene
1. Sammenlign med **kendt reference** (kalibrator)
2. Justér instrumentet (hvis muligt)
3. Dokumentér med **kalibreringscertifikat**
4. Mærk instrumentet med dato og næste kalibrering

### Hyppighed
- **Procesinstrumenter**: 1 år
- **Lab-instrumenter**: 1-2 år (ISO 17025-akkrediteret)
- **Kritisk udstyr** (medicinsk, flyplade): efter brug

> 💡 I Danmark bruger industrien typisk **DANAK-akkrediteret** kalibrering.

---

## 📌 Resumé på arabisk

- **الفولتميتر** يُوصل دائماً **بالتوازي**، **الأمبيرميتر** دائماً **بالتسلسل**.
- **توسيع المدى**: مقاومة سلسلة (form) للفولت، مقاومة موازية (shunt) للأمبير.
- **محولات القياس**: لقياس التيارات والجهود الكبيرة في الصناعة. لا تترك ثانوي محول التيار مفتوحاً!
- **PT100**: مستشعر حرارة بمقاومة بلاتين 100 أوم عند 0°C — أساسي في الغلايات والصناعة.
- **مزدوجات حرارية (Termoelement)**: نوع K للأفران الصناعية — تتحمل درجات حرارة عالية.
- **حلقة 4-20 mA**: المعيار الصناعي للإشارات التناظرية. مقاوم للضوضاء، يكتشف الأعطال.
- **محول تناظري-رقمي (ADC)**: يحول الإشارة التناظرية لقراءتها بالميكروكنترولر أو PLC.
- **جسر ويتستون**: طريقة دقيقة لقياس المقاومة الصغيرة.

---

## 🎓 Tillykke — du har fuldført kurset!

Du har nu læst alle 22 kapitler. Næste trin:

- 📝 [Opgaver til kapitel 22](../opgaver/22-opgaver.md)
- 📝 [Quiz på tværs af alle kapitler](../../interaktiv/quiz.html)
- 🏁 [Tilbage til oversigt](../)
