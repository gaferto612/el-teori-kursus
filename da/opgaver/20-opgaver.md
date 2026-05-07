# Opgaver — Kapitel 20: Kombinationslogik

## Opgave 20.1 — Sandhedstabel
Opstil sandhedstabellen for $Y = A \cdot \overline{B} + \overline{A} \cdot B$. Hvilken velkendt port er det?

<details><summary>💡 Løsning</summary>

| A | B | $\overline{A}$ | $\overline{B}$ | $A\overline{B}$ | $\overline{A}B$ | Y |
|---|---|----|----|---|---|---|
| 0 | 0 | 1 | 1 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 | 0 | 1 | 1 |
| 1 | 0 | 0 | 1 | 1 | 0 | 1 |
| 1 | 1 | 0 | 0 | 0 | 0 | 0 |

Det er **XOR** (eksklusiv-OR).
</details>

---

## Opgave 20.2 — De Morgan
Forenkl med De Morgans love: $\overline{A \cdot B} \cdot \overline{C}$

<details><summary>💡 Løsning</summary>

$$\overline{A \cdot B} = \overline{A} + \overline{B}$$
$$\overline{A \cdot B} \cdot \overline{C} = (\overline{A} + \overline{B}) \cdot \overline{C}$$

Distributiv lov:
$$= \overline{A} \cdot \overline{C} + \overline{B} \cdot \overline{C}$$
</details>

---

## Opgave 20.3 — Forenkling
Forenkl: $Y = A\overline{B} + AB$

<details><summary>💡 Løsning</summary>

$$Y = A(\overline{B} + B) = A \cdot 1 = A$$

Komplekst kredsløb reducerer til bare A.
</details>

---

## Opgave 20.4 — Praktisk logik
En motor må kun starte hvis:
- Sikkerhedsdør er lukket (S)
- Start-knap (K) er trykket
- Der er **ikke** nødstop (NS)

Skriv det boolske udtryk og tegn med standardporte.

<details><summary>💡 Løsning</summary>

$$M = S \cdot K \cdot \overline{NS}$$

Ladder-logic eller AND-port med 3 indgange (S, K, og NOT(NS)).

```
S ───┐
K ───┤AND├── M (motor start)
NS ──[NOT]──┘
```
</details>

---

## Opgave 20.5 — NAND-universalitet
Vis hvordan en NOT-funktion bygges med kun en NAND-port.

<details><summary>💡 Løsning</summary>

Sæt **begge indgange** på NAND'en sammen:
$$Y = \overline{A \cdot A} = \overline{A}$$

Det er derfor NAND kaldes en universel port — alle logiske funktioner kan bygges med blot NAND-porte.
</details>

---

⬅ [Kap 20](../kapitler/20-kombinationslogik.md) | [🧠 Logik-gates](../../interaktiv/logik-gates.html) | [Næste →](../kapitler/21-instrumenttyper.md)
