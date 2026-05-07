# Kapitel 20 — Kombinationslogik
> المنطق التوافقي

## 🎯 Læringsmål

- Forstå logikniveauer (0 / 1, low / high)
- Kende de grundlæggende logiske porte: AND, OR, NOT
- Anvende NAND, NOR, XOR, XNOR
- Læse og opstille sandhedstabeller
- Forstå Bool-algebra og forenkling

---

## 20.1 Digitale systemer

I automatik bruges to-tilstands-systemer:

| Mekanisk | Elektronisk |
|----------|-------------|
| Kontakt **sluttet** = ON | Logisk **1** (HIGH) |
| Kontakt **afbrudt** = OFF | Logisk **0** (LOW) |

### Spændingsniveauer

| Familie | Forsyning | Logisk 0 | Logisk 1 |
|---------|-----------|----------|----------|
| **TTL** | 5 V | 0–0,8 V | 2,0–5,0 V |
| **CMOS** | 3–18 V | 0–30% af V | 70–100% af V |
| **3,3V CMOS** | 3,3 V | 0–0,8 V | 2,0–3,3 V |

> 💡 **Indgange skal aldrig "svæve"** (være ikke-tilsluttede). Brug pull-up eller pull-down modstand for at sikre defineret logisk niveau.

---

## 20.2 De grundlæggende porte

### NOT-led (inverter) — لا

| A | Y |
|---|---|
| 0 | 1 |
| 1 | 0 |

Symbol:
```
   A ──[>○──── Y    (cirkel = invertering)
```

Funktion: $Y = \overline{A}$

### AND-led — و

| A | B | Y |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

Symbol: D-formet
$$Y = A \cdot B$$

> 💡 **AND** = "BÅDE A og B skal være ON".

### OR-led — أو

| A | B | Y |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

Symbol: skjold-formet
$$Y = A + B$$

> 💡 **OR** = "MINDST EN af A eller B skal være ON".

---

## 20.3 Sammensatte porte

### NAND (NOT AND) — لا و

| A | B | Y |
|---|---|---|
| 0 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | **0** |

$$Y = \overline{A \cdot B}$$

> ⚙ **NAND er den mest fleksible port** — du kan bygge ALLE andre logiske funktioner alene med NAND-porte!

### NOR (NOT OR) — لا أو

| A | B | Y |
|---|---|---|
| 0 | 0 | **1** |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 0 |

$$Y = \overline{A + B}$$

### XOR (Eksklusiv OR) — أو الحصري

| A | B | Y |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | **0** |

$$Y = A \oplus B$$

> 💡 XOR er **1** når indgangene er **forskellige**.

### XNOR (Eksklusiv NOR)

| A | B | Y |
|---|---|---|
| 0 | 0 | 1 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

XNOR er **1** når indgangene er **ens** = "equal" detektor.

---

## 20.4 Sammenligningstabel

| Port | Symbol-form | Funktion (HIGH når...) |
|------|-------------|------------------------|
| AND | D | Alle indgange er HIGH |
| OR | skjold | Mindst én er HIGH |
| NOT | trekant + cirkel | Indgang er LOW |
| NAND | D + cirkel | Mindst én er LOW |
| NOR | skjold + cirkel | Alle er LOW |
| XOR | skjold med ekstra bue | Indgangene er forskellige |
| XNOR | XOR + cirkel | Indgangene er ens |

> 🛠 [Brug det interaktive værktøj — Logik-gates](../interaktiv/logik-gates.html)

---

## 20.5 Bool-algebra

### Grundregler

| Regel | Algebra |
|-------|---------|
| Identitet | $A + 0 = A$, $A \cdot 1 = A$ |
| Annullering | $A + 1 = 1$, $A \cdot 0 = 0$ |
| Idempotens | $A + A = A$, $A \cdot A = A$ |
| Komplement | $A + \overline{A} = 1$, $A \cdot \overline{A} = 0$ |
| Dobbelt-negation | $\overline{\overline{A}} = A$ |
| Kommutativ | $A + B = B + A$, $A \cdot B = B \cdot A$ |
| Associativ | $(A+B)+C = A+(B+C)$ |
| Distributiv | $A(B+C) = AB + AC$ |

### De Morgans love

> **Vigtigt** — bruges konstant ved forenkling:
>
> $$\overline{A \cdot B} = \overline{A} + \overline{B}$$
> $$\overline{A + B} = \overline{A} \cdot \overline{B}$$

I ord: "negation af en AND = OR af negationer", og omvendt.

### Eksempel — forenkling

Forenkl: $Y = A\overline{B} + AB$

Brug distributiv lov:
$$Y = A(\overline{B} + B) = A \cdot 1 = A$$

→ Komplekst kredsløb reducerer sig til **bare A**!

---

## 20.6 Sandhedstabeller med flere indgange

### 3-indgangs AND
| A | B | C | Y |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 0 |
| 0 | 1 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 0 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 0 |
| 1 | 1 | 1 | 1 |

$$Y = A \cdot B \cdot C$$

### Antal kombinationer
For n indgange: $2^n$ rækker.
- 2 indgange → 4 rækker
- 3 indgange → 8 rækker
- 4 indgange → 16 rækker
- 8 indgange → 256 rækker

---

## 20.7 Eksempler — fra ord til logik

### Eksempel 1 — Pumpestyring
Pumpen skal starte hvis:
- Niveau er lavt (NL)
- **OG** kontakten er sluttet (S)
- **OG** der er ingen alarm (¬AL)

$$P = NL \cdot S \cdot \overline{AL}$$

→ Brug en 3-indgangs AND-port.

### Eksempel 2 — Alarm
Alarmen skal lyde hvis:
- Branddetektor (BR)
- **ELLER** røgdetektor (RØG)
- **ELLER** manuel knap (M)

$$ALARM = BR + RØG + M$$

→ Brug en 3-indgangs OR-port.

### Eksempel 3 — Sikkerhedslås
Maskinen kan starte hvis:
- Skærmen er lukket (S)
- **OG** der er **enten** start-knap (K) **eller** automatisk start (A)
- **OG** ikke nødstop (¬NS)

$$START = S \cdot (K + A) \cdot \overline{NS}$$

→ Kombination af AND og OR.

---

## 20.8 Logik-IC familier

### Almindelige TTL/CMOS-IC

| IC nr. | Funktion |
|--------|----------|
| 7400 | Quad NAND |
| 7402 | Quad NOR |
| 7404 | Hex NOT |
| 7408 | Quad AND |
| 7432 | Quad OR |
| 7486 | Quad XOR |
| 4001 | Quad NOR (CMOS) |
| 4011 | Quad NAND (CMOS) |
| 4081 | Quad AND (CMOS) |

> 📦 "Quad" = 4 stk i én pakke. "Hex" = 6 stk.

### Mere komplekse logik-funktioner
- **74138** — 3-til-8 dekoder
- **74148** — 8-til-3 priority encoder
- **7474** — D-flip-flop
- **74161** — 4-bit binær tæller
- **74181** — 4-bit ALU

---

## 20.9 Hardware vs. PLC-software

### Tidligere
Logikkredsløb blev bygget med discrete IC'er.

### I dag
**Programmable Logic Controllers (PLC)** har overtaget i industrien:
- Logikken programmeres softwaremæssigt (Ladder Logic, FBD, ST)
- Fleksibel — man ændrer programmet uden at bygge om
- Standardplatforme: Siemens TIA Portal, Allen-Bradley, Beckhoff, CODESYS

### Eksempel i Ladder Logic (Siemens)
```
   I0.0     I0.1            Q0.0
   ─┤├──────┤├──────────────( )
   start    sikkerhed       motor
```

→ Motor (Q0.0) tænder hvis Start (I0.0) **OG** Sikkerhed (I0.1).
→ Det er bare en AND-port i softwareform!

> 🇩🇰 PLC'er er dagligdag i automatisering, kemiske anlæg, vandværker, og kraftvarmeværker.

---

## 📌 Resumé på arabisk

- **المنطق الرقمي** يعمل بحالتين: 0 (LOW) و 1 (HIGH).
- **البوابات الأساسية الثلاث**:
  - **AND (و)**: المخرج 1 فقط إذا كل المداخل 1.
  - **OR (أو)**: المخرج 1 إذا أي مدخل 1.
  - **NOT (لا)**: عاكس — يقلب 0 إلى 1 والعكس.
- **بوابات مركبة**: NAND، NOR، XOR (أو الحصري).
- **NAND هي البوابة العالمية** — يمكن بناء كل المنطق الآخر منها.
- **قوانين دي مورجان**: $\overline{AB} = \overline{A} + \overline{B}$ و $\overline{A+B} = \overline{A}\cdot\overline{B}$.
- **اليوم**: المنطق يُنفذ في PLC (مثل Siemens TIA) عبر برمجة Ladder Logic — أبسط وأكثر مرونة من البوابات المتقطعة.

---

## ➡️ Næste skridt

- 📝 [Opgaver til kapitel 20](../opgaver/20-opgaver.md)
- 🧮 [Logik-gate simulator (interaktiv)](../interaktiv/logik-gates.html)
- ➡️ [Kapitel 21 — Instrumenttyper](21-instrumenttyper.md)
