# Opgaver — Kapitel 13: 3-faset vekselstrøm

## Opgave 13.1 — Y vs Δ
I Danmark er fasespænding 230 V. Hvor stor er netspænding (mellem to faser)?

<details><summary>💡 Løsning</summary>

$$U_n = \sqrt{3} \cdot U_f = \sqrt{3} \cdot 230 ≈ 400 \text{ V}$$
</details>

---

## Opgave 13.2 — Synkron hastighed
En 3-faset motor har 6 polpar (12 poler). Find synkronhastigheden ved 50 Hz.

<details><summary>💡 Løsning</summary>

$$n_s = \frac{60 \cdot f}{p} = \frac{60 \cdot 50}{6} = 500 \text{ omdr./min}$$
</details>

---

## Opgave 13.3 — Effekt i 3-fase
En 3-faset motor er mærket: 400 V, 16 A, cos φ = 0,87. Find tilført effekt.

<details><summary>💡 Løsning</summary>

$$P = \sqrt{3} \cdot U_n \cdot I_n \cdot \cos \varphi = \sqrt{3} \cdot 400 \cdot 16 \cdot 0{,}87 ≈ 9645 \text{ W} ≈ 9{,}6 \text{ kW}$$
</details>

---

## Opgave 13.4 — Strøm til motor
En 3-faset motor er mærket: 400 V, 7,5 kW, cos φ = 0,85, η = 0,9. Find motorens nominelle strøm.

<details><summary>💡 Løsning</summary>

Optaget effekt: $P_{ind} = P_{ud}/\eta = 7500/0{,}9 = 8333$ W
$$I = \frac{P_{ind}}{\sqrt{3} \cdot U_n \cdot \cos \varphi} = \frac{8333}{\sqrt{3} \cdot 400 \cdot 0{,}85} ≈ 14{,}1 \text{ A}$$

Vælg fx 16 A motorværn (nærmeste standard over).
</details>

---

## Opgave 13.5 — Y/Δ-start
En motor mærket 400/690 V tilsluttes et 400 V dansk net.
a) Hvilken kobling skal bruges til drift?
b) Hvad sker der ved Y-kobling?

<details><summary>💡 Løsning</summary>

a) **Δ-kobling** — så får hver vikling 400 V (svarende til mærkningen).
b) Ved Y-kobling får hver vikling kun $400/\sqrt{3} ≈ 230$ V — motoren kører med ca. 1/3 af nominel effekt og har **reduceret startstrøm**. Bruges som blød start (Y/Δ-start).
</details>

---

⬅ [Kap 13](../kapitler/13-3-faset-vekselstroemsteori.md) | [Næste →](../kapitler/14-modstande-og-kondensatorer.md)
