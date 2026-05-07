# Opgaver — Kapitel 17: Ensretning

## Opgave 17.1 — Brokobling tomgangsspænding
En transformer leverer 12 V AC (RMS) og er sluttet til en brokoblet ensretter. Find tomgangsspændingen efter ensretteren (uden glatning).

<details><summary>💡 Løsning</summary>

Peak-spænding: $U_{peak} = 12 \cdot \sqrt{2} ≈ 17$ V
Minus 2 diodefald: $17 - 2 \cdot 0{,}7 ≈ 15{,}6$ V

→ Pulserende DC med top ca. 15,6 V.
</details>

---

## Opgave 17.2 — Ripple-spænding
En 1-faset brokobling med glatningskondensator $C = 1000$ μF leverer 0,5 A. Beregn ripple-spændingen.

<details><summary>💡 Løsning</summary>

Ved 1-faset bro: $f_{ripple} = 100$ Hz.
$$U_{rip} \approx \frac{I}{f \cdot C} = \frac{0{,}5}{100 \cdot 0{,}001} = 5 \text{ V}$$
</details>

---

## Opgave 17.3 — Kondensator størrelse
Hvor stor en glatningskondensator skal bruges hvis vi vil have max 1 V ripple ved 2 A belastning fra en brokobling?

<details><summary>💡 Løsning</summary>

$$C = \frac{I}{f \cdot U_{rip}} = \frac{2}{100 \cdot 1} = 0{,}02 \text{ F} = 20.000 \text{ μF}$$
</details>

---

## Opgave 17.4 — Fra AC til 5 V DC
Beskriv komponenterne i en typisk strømforsyning fra 230 V AC til 5 V DC.

<details><summary>💡 Løsning</summary>

1. **Transformer** 230/12 V (nedtransformerer + galvanisk skille)
2. **Brokoblet ensretter** (4 dioder) → pulserende DC ~15 V
3. **Glatningskondensator** (fx 2200 μF) → reducerer ripple
4. **Spændingsregulator** (fx 7805) → stabil 5 V udgang
5. **Udgangskondensator** (fx 100 nF) → undertrykker højfrekvent støj
</details>

---

## Opgave 17.5 — Hvorfor 3-faset bro?
Hvad er fordelen ved 3-faset brokobling (B6) over 1-faset?

<details><summary>💡 Løsning</summary>

- **Mindre ripple** allerede uden glatning (~4 % mod ~50 %)
- **Højere ripple-frekvens** (300 Hz vs 100 Hz) → mindre glatningskondensator nødvendig
- **Bedre udnyttelse** af transformer
- **Konstantere** DC

Bruges i alle større industri-strømforsyninger og frekvensomformere.
</details>

---

⬅ [Kap 17](../kapitler/17-ensretning.md) | [Næste →](../kapitler/18-effektregulering.md)
