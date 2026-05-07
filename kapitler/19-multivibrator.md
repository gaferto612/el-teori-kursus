# Kapitel 19 — Multivibrator
> المتذبذبات (دوائر التذبذب)

## 🎯 Læringsmål

- Forstå hvad en multivibrator er
- Skelne mellem astabil, monostabil og bistabil
- Beregne frekvens og pulsbredde
- Forstå Schmitt-trigger
- Genkende anvendelser i styringer

---

## 19.1 Hvad er en multivibrator?

En **multivibrator** er et **digitalt** kredsløb der har én eller flere stabile tilstande, og kan skifte mellem dem.

> 🇸🇦 **المتذبذب**: دائرة إلكترونية لها حالات استقرار يمكن التبديل بينها — تُستخدم لتوليد نبضات.

### Tre typer

| Type | Stabile tilstande | Anvendelse |
|------|-------------------|-----------|
| **Astabil** | 0 | Pulsgenerator (oscillator) |
| **Monostabil** | 1 | Tids-forsinkelse, "one-shot" |
| **Bistabil** | 2 | Hukommelse (flip-flop) |

---

## 19.2 Astabil multivibrator — pulsgeneratoren

Har **ingen** stabil tilstand — kredsen oscillerer kontinuerligt mellem to tilstande.

### Anvendelser
- Blink på lamper (advarselslys)
- Periodisk ind- og udkobling af varmelegemer
- Hyletoner i alarmanlæg
- Ur og takt-signaler

### Princip
To switch-trin (transistorer eller logiske porte) er gensidig kapacitivt koblet:

```
     +Vcc ─[R₁]──●─────────[R₂]─── +Vcc
                  │              │
                  ●──[C₁]──●     ●
                  │        │     │
                ┤V₁├      ┤V₂├
                  │        │
                  └────●───┘
                       ⏚

   T1's kollektor ─── C → T2's basis
   T2's kollektor ─── C → T1's basis
```

- T1 ON → kondensator gennem T2 lader op → vipper T2 ON
- T2 ON → andre kondensator vipper T1 ON
- Kredsen "vipper" frem og tilbage

### Frekvens
For en symmetrisk astabil med $R_1 = R_2 = R$ og $C_1 = C_2 = C$:
$$f \approx \frac{1}{1{,}4 \cdot R \cdot C}$$

Periodetid:
$$T = 1{,}4 \cdot R \cdot C$$

### Eksempel
$R = 10$ kΩ, $C = 1$ μF:
$$T = 1{,}4 \cdot 10.000 \cdot 0{,}000.001 = 0{,}014 \text{ s} = 14 \text{ ms}$$
$$f = 1/0{,}014 ≈ 71 \text{ Hz}$$

---

## 19.3 Justerbar astabil med IC

Med 3 NOT-led (eller en 555-timer) kan man bygge en justerbar astabil:

```
      ┌──[R₂]──┐
      │        │
  ────┤NOT 1 ├─●──[R₁]──●──┤NOT 2├─●──┤NOT 3├─── ud
                          │
                         [C₁]
                          │
                          ⏚
```

- $R_1$, $C_1$ bestemmer frekvensen
- $R_2$ aflader RC-leddet
- IC3 fungerer som **Schmitt-trigger** for at få en ren firkant

### Periode
$$T \approx 1{,}4 \cdot R_1 \cdot C_1$$

---

## 19.4 555-timeren — den klassiske

**NE555** er en universel timer-IC. Næsten 50 år gammel og stadig brugt overalt.

### 8-bens IC

```
            ┌──┬──┐
        GND │1   8│ Vcc
       TRIG │2   7│ DISCH
        OUT │3   6│ THRES
       RST  │4   5│ CTRL
            └──────┘
```

### Astabil-konfiguration

```
Vcc ──[R₁]──●──[R₂]──●─── 7 (DISCH)
            │        │
            6        2 (THRES, TRIG)
            │
           [C]
            │
            ⏚
```

### Frekvens og tastforhold
$$f = \frac{1{,}44}{(R_1 + 2R_2) \cdot C}$$

Tid HIGH: $t_1 = 0{,}693 \cdot (R_1 + R_2) \cdot C$
Tid LOW: $t_2 = 0{,}693 \cdot R_2 \cdot C$

> 💡 555 er ekstremt fleksibel — kan også konfigureres som mono, PWM, niveau-detektor, etc.

---

## 19.5 Monostabil multivibrator

Har **én** stabil tilstand. Når triggeret skifter den til den anden tilstand i en bestemt tid og vender derefter tilbage.

### Anvendelser
- **Tids-forsinkelse** (fx udløsning efter X sekunder)
- **Pulsformer** (laver kort puls af lang)
- **Debouncing** af mekaniske kontakter
- "One-shot" timer

### Pulsbredde
Med en RC-kreds:
$$t_p = 1{,}1 \cdot R \cdot C \quad \text{(555 mono)}$$

### Eksempel
Lyset skal være tændt i 30 sek efter en knap trykkes:
- Vælg $C = 100$ μF
- $R = t_p / (1{,}1 \cdot C) = 30 / (1{,}1 \cdot 100 \cdot 10^{-6}) ≈ 273$ kΩ → vælg 270 kΩ

---

## 19.6 Bistabil multivibrator (flip-flop)

Har **to** stabile tilstande. Skifter kun ved input — bliver i den valgte tilstand indtil næste trigger.

### Typer

| Type | Funktion |
|------|----------|
| **SR-flip-flop** | Set/Reset — den simpleste |
| **D-flip-flop** | Data — kopierer D til Q ved klok |
| **JK-flip-flop** | Universel — kan toggle |
| **T-flip-flop** | Toggle ved hver klokpuls |

### Anvendelser
- **Hukommelse** (1 bit)
- **Tællere** (binær tællekæde)
- **Skifteregistre** (shift registers)
- **Frekvensdelere** (T-flip-flop halverer frekvens)

```
   SR-flip-flop sandhedstabel:
   
   S | R | Q
   ──┼───┼──
   0 | 0 | hold (uændret)
   0 | 1 | 0 (reset)
   1 | 0 | 1 (set)
   1 | 1 | forbudt
```

> 💾 Et register på 8 bits = 8 flip-flops. RAM, CPU-register, alt digital hukommelse er bygget på flip-flops.

---

## 19.7 Schmitt-trigger

En Schmitt-trigger har **to forskellige tærskler** for skift:
- Skifter til HIGH ved en høj tærskel ($U_H$)
- Skifter til LOW ved en lav tærskel ($U_L$)
- $U_H > U_L$ = **hysterese**

```
     Indgang:  ──╱╲──╱╲──╲╱──╱╲──
   
     Schmitt:  ──┐  ┌──────┐  ┌──
                 └──┘      └──┘
              (rene firkanter, ingen flicker)
```

### Anvendelser
- Konvertere analoge sinussignaler til digitale firkanter
- Undgå flicker når input "svæver" omkring tærskelværdi
- Debounce mekaniske kontakter
- Pulsforming i støjede systemer

> 💡 Bruges i alarmkredse, fotoceller, kontakt-debouncing.

---

## 19.8 Pulsforming og pulsformere

I styringer skal signaler ofte **formes** før de sendes videre:

| Pulsformer | Funktion |
|-----------|----------|
| **Differentiator** (RC kort tidskonstant) | Laver smal puls af kant |
| **Integrator** (RC lang tidskonstant) | "Glatter" pulser |
| **Komparator** | Sammenligner med reference |
| **Schmitt-trigger** | Rene digitale flanker |

---

## 19.9 Anvendelse — eksempler

### Blinkerelæ til alarmlampe
- **Astabil** med 555 ved fx 1 Hz
- Output styrer transistor → relæ → lampe
- Periodisk blink

### Trappelysstyring
- Knap aktiverer **monostabil** med 3 minutters timer
- Lampen tænder, slukker automatisk efter 3 min

### PLC-input debouncing
- Mekaniske kontakter "studser" — flere mikropulser ved én tryk
- Schmitt-trigger filtrerer eller monostabil giver ren puls

---

## 📌 Resumé på arabisk

- **المتذبذب (Multivibrator)**: دائرة بثلاث أنواع رئيسية:
  - **غير مستقر (Astabil)**: لا حالة استقرار — يولد نبضات بشكل مستمر (مثل مولد إشارة).
  - **أحادي الاستقرار (Monostabil)**: حالة واحدة مستقرة — يطلق نبضة مؤقتة عند التشغيل (مؤقت).
  - **ثنائي الاستقرار (Bistabil / Flip-flop)**: حالتان مستقرتان — أساس الذاكرة الرقمية.
- **555 timer**: دائرة متكاملة كلاسيكية للمؤقتات — التردد $f = 1{,}44 / [(R_1 + 2R_2) \cdot C]$.
- **Schmitt-trigger**: مفتاح بعتبتين مختلفتين — يحول الإشارات الجيبية إلى مربعة نظيفة.
- **استخدامات**:
  - مولدات النبض، مؤقتات
  - وميض إنذار
  - إضاءة الدرج (مونوستابيل)
  - ذاكرة رقمية، عدّادات (فليب فلوب)

---

## ➡️ Næste skridt

- 📝 [Opgaver til kapitel 19](../opgaver/19-opgaver.md)
- ➡️ [Kapitel 20 — Kombinationslogik](20-kombinationslogik.md)
