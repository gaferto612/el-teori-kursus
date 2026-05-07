# Opgaver — Kapitel 15: Halvlederkomponenter

## Opgave 15.1 — Diodens spændingsfald
En silicium-diode er sluttet i serie med en 470 Ω modstand til 5 V. Beregn strømmen.

<details><summary>💡 Løsning</summary>

Diodens fremspænding er ca. 0,7 V → $U_R = 5 - 0{,}7 = 4{,}3$ V
$$I = U_R / R = 4{,}3 / 470 ≈ 9{,}1 \text{ mA}$$
</details>

---

## Opgave 15.2 — Transistor som switch
En NPN-transistor med $h_{FE} = 100$ skal drive en relæspole der trækker 80 mA. Beregn nødvendig basisstrøm.

<details><summary>💡 Løsning</summary>

$$I_B = \frac{I_C}{h_{FE}} = \frac{80}{100} = 0{,}8 \text{ mA}$$

For sikker mætning bruges typisk **2-3 gange** mere → ca. 2 mA.
</details>

---

## Opgave 15.3 — Basismodstand
Til opgave 15.2: hvis logikken giver 5 V, og vi vil have 2 mA basisstrøm, hvor stor skal basismodstanden være? ($V_{BE} = 0{,}7$ V)

<details><summary>💡 Løsning</summary>

$$R_B = \frac{V_{logik} - V_{BE}}{I_B} = \frac{5 - 0{,}7}{0{,}002} = 2150 \text{ Ω}$$

Vælg 2,2 kΩ (standardværdi).
</details>

---

## Opgave 15.4 — LED-diode
En rød LED ($U_F = 1{,}8$ V, $I = 10$ mA) skal drives fra 5 V via en serie-modstand. Beregn modstanden.

<details><summary>💡 Løsning</summary>

$$R = \frac{5 - 1{,}8}{0{,}010} = 320 \text{ Ω}$$

Vælg 330 Ω.
</details>

---

## Opgave 15.5 — Hvad er et IGBT?
Forklar kort hvad en IGBT er, og hvor den bruges.

<details><summary>💡 Løsning</summary>

**IGBT** = Insulated Gate Bipolar Transistor.
Kombinerer fordelene fra MOSFET (hurtig spændingsstyret gate) og BJT (lavt mættet spændingsfald ved store strømme).
- Bruges til **store effekter** (typisk 100 V – 1.700 V, 10–1.000 A)
- Hovedanvendelse: **frekvensomformere** til 3-fasede motorer, solcelleinvertere, induktionsovne, eltogforsyning.
</details>

---

⬅ [Kap 15](../kapitler/15-halvlederkomponenter.md) | [Næste →](../kapitler/16-forstaerkning.md)
