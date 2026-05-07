# Opgaver — Kapitel 19: Multivibrator

## Opgave 19.1 — Symmetrisk astabil
En astabil multivibrator har $R_1 = R_2 = 22$ kΩ og $C_1 = C_2 = 1$ μF. Find frekvens og periodetid.

<details><summary>💡 Løsning</summary>

$$T = 1{,}4 \cdot R \cdot C = 1{,}4 \cdot 22000 \cdot 0{,}000001 = 0{,}0308 \text{ s}$$
$$f = 1/T ≈ 32{,}5 \text{ Hz}$$
</details>

---

## Opgave 19.2 — 555 i astabil
En 555-timer er konfigureret som astabil med $R_1 = 1$ kΩ, $R_2 = 10$ kΩ, $C = 100$ nF. Find frekvens.

<details><summary>💡 Løsning</summary>

$$f = \frac{1{,}44}{(R_1 + 2R_2) \cdot C} = \frac{1{,}44}{(1000 + 20000) \cdot 100 \cdot 10^{-9}} = \frac{1{,}44}{21000 \cdot 10^{-7}} ≈ 686 \text{ Hz}$$
</details>

---

## Opgave 19.3 — Monostabil timer
En 555 i monostabil mode skal give 30 sek puls. Hvis $C = 100$ μF, hvor stor skal R være?

<details><summary>💡 Løsning</summary>

$$t_p = 1{,}1 \cdot R \cdot C \Rightarrow R = \frac{t_p}{1{,}1 \cdot C} = \frac{30}{1{,}1 \cdot 100 \cdot 10^{-6}} ≈ 273 \text{ kΩ}$$

Vælg 270 kΩ (standard) eller juster med trimmer.
</details>

---

## Opgave 19.4 — Hvad gør en Schmitt-trigger?
Forklar hvorfor en Schmitt-trigger er bedre end en simpel komparator til at konvertere et støjet sinussignal til firkant.

<details><summary>💡 Løsning</summary>

En **simpel komparator** vil "vibrere" omkring tærsklen når input nærmer sig grænsen — pga. støj. Output svinger flere gange før det stabiliseres.

En **Schmitt-trigger** har **to forskellige tærskler** (hysterese):
- Skifter til HIGH ved $U_H$
- Skifter ikke tilbage før input falder under $U_L < U_H$

Det giver **rene flanker** uden falske skift.
</details>

---

## Opgave 19.5 — Anvendelse
Du skal bygge et trappelys der tænder ved knap-tryk og slukker selv efter 2 minutter. Hvilken multivibrator-type vælger du, og hvorfor?

<details><summary>💡 Løsning</summary>

**Monostabil** multivibrator (one-shot).
- Den har én stabil tilstand (slukket)
- Ved tryk skifter den til den anden tilstand i en bestemt tid
- Vender automatisk tilbage til slukket

Realisering: 555 i monostabil mode med $t_p ≈ 120$ s. Vælg $C = 220$ μF og $R ≈ 500$ kΩ.
</details>

---

⬅ [Kap 19](../kapitler/19-multivibrator.md) | [Næste →](../kapitler/20-kombinationslogik.md)
