# Kapitel 18 — Effektregulering
> تنظيم القدرة

## 🎯 Læringsmål

- Forstå forskellen mellem usynkroniseret og synkroniseret regulering
- Kende fasestyring og nulpunktstyring
- Forstå anvendelser i lys-, varme- og motorstyring
- Vurdere fordele og ulemper (radiostøj, harmoniske)

---

## 18.1 Effektregulering — hvad og hvorfor?

**Effektregulering** = at styre den effekt, der leveres til en last.

### Anvendelser
| Område | Eksempel |
|--------|----------|
| **Lys** | Dimmer (lampedæmper) |
| **Varme** | Termostatstyret elvarme, ovne |
| **Motorer** | Hastighedskontrol af AC-motorer, DC-motorer |
| **Industri** | Smelteovne, induktionsvarme |

### To overordnede principper
1. **Usynkroniseret** — regulator arbejder uden hensyn til netfrekvensen
2. **Synkroniseret** — regulator arbejder i takt med netfrekvensen

---

## 18.2 Usynkroniseret regulering

Regulator-elementet (typisk thyristor/triac) arbejder som ren **ON/OFF-statisk kontaktor**.

### Princip
- Last er fuldt tændt i en periode
- Helt slukket i næste periode
- Forholdet mellem ON- og OFF-tider styrer den **gennemsnitlige** effekt

> ⚠ Ulempe: store strømsving — kan flicker ved lysanlæg.

### Anvendelse
- Termostatstyret varmelegeme
- Strygejern, vandkogere
- Simpelt og billigt

---

## 18.3 Synkroniseret regulering

Reguleringen sker **synkront** med netfrekvensen. To hovedmetoder:

### A. Fasestyring (PWM-lignende på AC)
### B. Nulpunktstyring (zero-crossing)

---

## 18.4 Fasestyring

Triac eller thyristor tændes på et **bestemt sted** i hver halvbølge — indtil næste nul-gennemgang.

```
Fuld effekt:           Halv effekt (60° udløsning):
    /\    /\               _    _
   /  \  /  \              |\   |\
  /    \/    \             | \  | \
 ─                      ───┘  \─┘  \─
```

### Karakteristika
| Egenskab | Værdi |
|----------|-------|
| Trinløs regulering | ✅ Ja |
| Bruges til | Lys, varme, små motorer |
| **Ulempe** | Skaber **kraftig radiostøj** og harmoniske |
| Krav | Skal kombineres med EMC-filter |

### Komponenter
- **Triac** for AC (begge halvbølger)
- **Diac** som udløser (til triac-gate)
- **RC-kreds** sætter fasevinklen

```
   AC ──┬─[load]─────●─── AC tilbage
        │            │
        │    +───[R]─┤
        │    │       │
        │   [C]      │
        │    │   diac│
        │    └───►├──┴─── G (triac gate)
        │            │
        └────────────●  triac MT1/MT2
```

> ⚠ **Almindelig dimmer i hjemmet** = fasestyring. Det er derfor LED-pærer kan flimre eller ikke virke med gamle dimmere — de er designet til glødepærer.

---

## 18.5 Nulpunktstyring (zero-crossing)

Triacen tændes **kun i nul-gennemgangen** af spændingen — og leder dernæst hele halvbølger ad gangen.

### Princip
- Helt periode tændt eller slukket — aldrig "delvis"
- F.eks: 5 perioder ON / 5 perioder OFF = 50 % effekt

```
Indgang AC:   ╱╲╱╲╱╲╱╲╱╲╱╲
Udgang:       ╱╲╱╲╱╲      ╱╲
              ON ON ON  OFF OFF
```

### Karakteristika
| Egenskab | Værdi |
|----------|-------|
| Trinvis regulering | I praksis fin nok |
| Bruges til | **Varme** (langsomme termiske systemer) |
| Radiostøj | **Næsten ingen** |
| Egnet til lys/motorer | ❌ Nej (giver flicker / ujævn drift) |

> ✅ Nulpunktstyring er **fri for radiostøj** og foretrukken til varmeanlæg.

---

## 18.6 PWM — Pulsbreddemodulation

I moderne DC-systemer bruges **PWM** (Pulse Width Modulation):

```
Lav effekt:    ▮___▮___▮___▮___    (smal puls)
Mellem:        ▮▮__▮▮__▮▮__▮▮__
Høj effekt:    ▮▮▮▮_▮▮▮▮_▮▮▮▮_    (bred puls)
```

### Egenskaber
- **Frekvens** typisk 1–20 kHz (ikke hørbart)
- Hurtig respons
- Lave tab — den koblende komponent (MOSFET/IGBT) er enten fuldt ON eller fuldt OFF

### Anvendelser
- DC-motorstyringer (fx aksedrev, robotter)
- LED-dimming
- Effektregulering i frekvensomformere
- Switching strømforsyninger (SMPS)

> 🇸🇦 **PWM**: تقنية تشغيل وإطفاء سريع — تتغير عرض النبضة لتنظيم القدرة. تُستخدم في تحكم المحركات وتعتيم LED.

---

## 18.7 Frekvensomformer (VFD)

For 3-fasede AC-motorer er **frekvensomformeren** (Variable Frequency Drive) den dominerende effektregulering:

```
   3-fase 50 Hz ──[ensretter]──[DC-mellemkreds]──[wechselrichter]── variabel frekvens
                   (B6 bro)        (kondensator)   (IGBT, PWM)
```

### Princip
- AC-input ensrettes til DC
- DC switches via IGBT'er med PWM tilbage til 3-faset AC
- **Frekvens** og **spænding** styres individuelt

### U/f-styring (skalær)
Spændingen ændres proportionalt med frekvensen for at holde fluxen konstant i motoren.

### Synkron hastighed
$$n_s = \frac{60 \cdot f}{p}$$

Ved at ændre f (typisk 0–100 Hz) styres motorens hastighed trinløst.

> ⚙ I moderne industri er VFD'er **standard**. Bruges til pumper, ventilatorer, transportbånd, kraner — alt hvor variabel hastighed er nyttig.

---

## 18.8 Sammenligning

| Metode | Anvendelse | Radiostøj | Trinløs |
|--------|-----------|-----------|---------|
| Usynkr. ON/OFF | Termostat | Lille | Nej (snap) |
| Fasestyring | Lys, varme, små motorer | **Høj** | Ja |
| Nulpunktstyring | **Varme** | Lav | Trinvis |
| PWM (DC) | DC-motorer, LED | Mellem (kan filtreres) | Ja, præcis |
| VFD (AC) | 3-fasede motorer | Mellem | Ja, præcis |

---

## 18.9 Praktiske eksempler

### Lampedæmper (1-faset, 230 V, glødepære 100 W)
- Kobling: triac med diac-udløser
- Fasestyring → trinløs lys
- **Problem med LED-pærer**: kun "dimbare" LED virker. Grunden: fasestyring giver pulserende strøm der ikke er kompatibel med simple LED-drivere.

### Ovnvarme i industriel kedel
- Kobling: nulpunktstyring (typisk solid-state-relæ — SSR)
- Termostat-input giver ON/OFF som SSR omsætter til hele halvbølger
- Ingen radiostøj — idéelt til kedelopvarmning

> 🔥 **Kedelpasser-relevant**: I elektriske kedler eller røggas-temperaturregulering bruges typisk nulpunktstyrede SSR'er kombineret med en PT100-måling og PID-regulator.

---

## 📌 Resumé på arabisk

- **تنظيم القدرة** يهدف للتحكم في الطاقة المُسلمة للحمل (إضاءة، تدفئة، محركات).
- **التحكم الطوري (Fasestyring)**: التراياك يفتح في زاوية معينة من كل نصف موجة — يُستخدم في المعتمات. ضوضاء راديوية عالية.
- **التحكم بنقطة الصفر (Nulpunktstyring)**: التراياك يفتح فقط عند مرور التيار بالصفر. لا ضوضاء، مناسب للتسخين.
- **PWM**: تشغيل/إطفاء سريع بنسبة دورة متغيرة — تُستخدم في تحكم محركات DC والإضاءة LED.
- **محول التردد (VFD)**: AC → DC → AC بتردد متغير. الطريقة الحديثة لتحكم محركات ثلاثية الطور.
- **في الغلايات الكهربائية**: عادة تُستخدم SSR (مرحلات الحالة الصلبة) بنقطة صفر.

---

## ➡️ Næste skridt

- 📝 [Opgaver til kapitel 18](../opgaver/18-opgaver.md)
- ➡️ [Kapitel 19 — Multivibrator](19-multivibrator.md)
