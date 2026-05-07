# Kapitel 13 — 3-faset vekselstrømsteori
> نظرية التيار المتردد ثلاثي الطور

## 🎯 Læringsmål

- Forstå hvordan 3-faset spænding frembringes
- Skelne mellem fasespænding og netspænding
- Forstå stjerne- (Y) og trekantkobling (Δ)
- Beregne effekt i 3-fasede systemer
- Forstå hvorfor 3-fase bruges til større belastninger

---

## 13.1 Hvorfor 3-faset?

Ved større belastninger tilsluttes 2 eller 3 faser i stedet for 1. Det giver:

1. **Mindre strøm** (samme effekt fordeles på flere ledere)
2. **Mindre kobbermængde** i kabler
3. **Konstant effekt** (i 1-faset svinger effekten — i 3-faset er den konstant)
4. **Roterende magnetfelt** (essentielt for asynkronmotorer!)

---

## 13.2 Generering af 3-faset spænding

I generatorens stator anbringes **3 ens viklinger** med **120° fysisk forskydning**.

Når rotoren drejer, induceres tre **sinusformede vekselspændinger** der er 120° elektrisk forskudt:

$$u_1 = U_{peak} \cdot \sin(\omega t)$$
$$u_2 = U_{peak} \cdot \sin(\omega t - 120°)$$
$$u_3 = U_{peak} \cdot \sin(\omega t - 240°)$$

```
   u₁ ─╲    ╱─╲    ╱─
       ╲╱   ╲╱
   u₂  ╱╲   ╱╲    forskudt 120°
       ╲ ╲ ╱ ╲
   u₃  ╲ ╳    ╲   forskudt 240°
       ╱ ╲   ╳
```

> 💡 **Vigtig egenskab**: Summen af de tre øjeblikkelige spændinger er **altid 0**:
> $$u_1 + u_2 + u_3 = 0$$

Det er **derfor** der ikke nødvendigvis skal en nulleder med ved 3-fasede laster.

---

## 13.3 Faseledere og betegnelser

I Danmark betegnes faserne:

| Fase | Farve | Eldokumentation |
|------|-------|-----------------|
| L1 | Brun | Tidligere "R" |
| L2 | Sort | Tidligere "S" |
| L3 | Grå | Tidligere "T" |
| Nul (N) | Blå | Neutral |
| Jord (PE) | Gul/grøn | Beskyttelses-jord |

---

## 13.4 Stjernekobling (Y)

De tre viklingers ene endeklemmer forbindes i et fælles **stjernepunkt** (nulpunkt).

```
       L1 ────●
              │
              ├──── N (nulleder)
              │
       L2 ────●
              │
       L3 ────●
```

### Spændinger i Y-kobling

To slags spændinger:

| Spænding | Symbol | Mellem |
|----------|--------|--------|
| **Fasespænding** | $U_f$ | Fase og N (eller stjernepunkt) |
| **Netspænding** | $U_n$ | To faser |

**Sammenhæng**:
$$U_n = \sqrt{3} \cdot U_f$$

I Danmark:
$$U_f = 230 \text{ V}, \quad U_n = 230 \cdot \sqrt{3} ≈ 400 \text{ V}$$

> 🇸🇦 **في الدنمارك**: جهد الطور 230 فولت، جهد الخط (بين فازين) 400 فولت.

### Strømme i Y-kobling
- $I_f = I_n$ (strømmen i fase = strømmen i nettet)
- I nullederen: vektorsum af de tre fasestrømme — ved symmetrisk last er den **0**.

---

## 13.5 Trekantkobling (Δ)

De tre viklinger forbindes i en **lukket trekant**:

```
       L1 ●─────●
          │     │
          │     │
          ●─────●
          L2    L3
```

### Spændinger og strømme i Δ

I trekantkobling:
- **Fasespænding = netspænding** ($U_f = U_n$)
- **Strømmene** er forskellige:
$$I_n = \sqrt{3} \cdot I_f$$

| | Stjerne (Y) | Trekant (Δ) |
|--|------------|-------------|
| Spænding | $U_n = \sqrt{3} \cdot U_f$ | $U_n = U_f$ |
| Strøm | $I_n = I_f$ | $I_n = \sqrt{3} \cdot I_f$ |

> 💡 **Pointe**: Stjerne = lavere spænding pr. vikling, men samme strøm. Trekant = højere spænding pr. vikling, men mindre strøm pr. vikling.

---

## 13.6 Effekt i 3-fasede systemer

Den samlede 3-fasede effekt:

### Aktiv effekt (P)
$$P = \sqrt{3} \cdot U_n \cdot I_n \cdot \cos(\varphi)$$

### Reaktiv effekt (Q)
$$Q = \sqrt{3} \cdot U_n \cdot I_n \cdot \sin(\varphi)$$

### Tilsyneladende effekt (S)
$$S = \sqrt{3} \cdot U_n \cdot I_n$$

### Forhold
$$S = \sqrt{P^2 + Q^2} \qquad \cos(\varphi) = \frac{P}{S}$$

> 📐 **Memo**: $\sqrt{3} ≈ 1{,}732$ er den karakteristiske faktor for 3-fase.

---

## 13.7 Eksempler

### Eksempel 1 — typisk industrimotor
En 3-faset motor er mærket: **400 V, 50 Hz, 5,5 kW, cos φ = 0,85, η = 0,9**

**Hvad er strømforbruget?**

Tilført effekt:
$$P_{ind} = \frac{P_{ud}}{\eta} = \frac{5500}{0{,}9} = 6111 \text{ W}$$

Strøm:
$$I = \frac{P_{ind}}{\sqrt{3} \cdot U_n \cdot \cos\varphi} = \frac{6111}{\sqrt{3} \cdot 400 \cdot 0{,}85} = 10{,}4 \text{ A}$$

### Eksempel 2 — Y/Δ-omskiftning til motorstart
En motor er typisk mærket fx **400/690 V**:
- Ved Y-kobling tåler den 690 V (= netspænding 690)
- Ved Δ-kobling tåler den 400 V (= netspænding 400)

I DK med 400 V net:
- **Y-kobling**: viklingen får kun $400/\sqrt{3} = 230$ V → nedsat startstrøm (1/3)
- **Δ-kobling**: viklingen får 400 V → fuld effekt

**Y/Δ-start**: motoren startes i Y for begrænset startstrøm, og kobles om til Δ ved fuld omdrejning.

> ⚙️ Y/Δ-start er en klassisk teknik — i moderne installationer bruges typisk **frekvensomformere** (VFD) i stedet, hvilket både er blødere og mere energieffektivt.

---

## 13.8 Roterende magnetfelt

En 3-faset motor (fx asynkronmotor) udnytter at de tre faser, anbragt med 120° fysisk forskydning, skaber et **roterende magnetfelt** i statoren.

### Synkron hastighed
$$n_s = \frac{60 \cdot f}{p}$$

| Symbol | Betydning |
|--------|-----------|
| $n_s$ | Synkron hastighed (omdr./min) |
| f | Frekvens (Hz) |
| p | Antal **polpar** |

| Polpar | Synkron hastighed ved 50 Hz |
|--------|----------------------------|
| 1 | 3.000 omdr./min |
| 2 | 1.500 omdr./min |
| 3 | 1.000 omdr./min |
| 4 | 750 omdr./min |

> 💡 Asynkronmotoren kører **lidt langsommere** end synkron hastighed (typisk 2-5 % slip under last).

---

## 13.9 Symmetrisk vs. usymmetrisk belastning

### Symmetrisk belastning
- Alle tre faser belastes **lige meget**
- Ingen strøm i nullederen (ideelt)
- Bruges til motorer, ovner

### Usymmetrisk belastning
- Faserne belastes ulige (fx mange enkeltfasede belastninger fordelt)
- Strøm i nullederen — **vigtigt** den dimensioneres korrekt

> ⚠ Dårlig fordeling af enfasede laster → kan overbelaste én fase eller nullederen. Elektrikeren skal fordele jævnt.

---

## 13.10 Industrielle stik

I Europa anvendes **CEE-stik** (rødfarvet for 400 V):

| Stik | Spænding | Strøm |
|------|----------|-------|
| Blå (1-faset) | 230 V | 16 A / 32 A |
| Rød (3-faset) | 400 V | 16 A / 32 A / 63 A / 125 A |

---

## 📌 Resumé på arabisk

- **النظام ثلاثي الطور**: ثلاث جهود جيبية متساوية بفارق 120° — يولّدها مولد بثلاث ملفات.
- **مجموع الجهود اللحظية = 0** — لذلك لا نحتاج دائماً لسلك محايد.
- **توصيل النجمة (Y)**: $U_n = \sqrt{3} \cdot U_f$. في الدنمارك: $U_f = 230$ V، $U_n = 400$ V.
- **توصيل المثلث (Δ)**: $U_f = U_n$، لكن $I_n = \sqrt{3} \cdot I_f$.
- **القدرة في النظام ثلاثي الطور**: $P = \sqrt{3} \cdot U_n \cdot I_n \cdot \cos\varphi$.
- **المجال الدوّار**: ثلاث ملفات بفارق 120° تخلق مجالاً دوّاراً — أساس عمل المحركات الحثية (asynkron).
- **السرعة المتزامنة**: $n_s = 60 \cdot f / p$. عند 50 هرتز و 2 زوج أقطاب = 1500 د/د.

---

## ➡️ Næste skridt

- 📝 [Opgaver til kapitel 13](../opgaver/13-opgaver.md)
- ➡️ [Kapitel 14 — Modstande og kondensatorer](14-modstande-og-kondensatorer.md)
