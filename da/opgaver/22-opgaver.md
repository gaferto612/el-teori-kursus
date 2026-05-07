# Opgaver — Kapitel 22: Måleprincipper

## Opgave 22.1 — Formodstand
Et voltmeter på 100 V med $R_v = 20$ kΩ skal udvides til at måle 600 V. Beregn formodstand.

<details><summary>💡 Løsning</summary>

$n = 600/100 = 6$
$$R_{form} = R_v(n-1) = 20.000 \cdot 5 = 100.000 \text{ Ω} = 100 \text{ kΩ}$$
</details>

---

## Opgave 22.2 — Shunt
Et amperemeter til 100 mA med $R_a = 1$ Ω skal udvides til 5 A. Beregn shuntsmodstand.

<details><summary>💡 Løsning</summary>

$n = 5/0{,}1 = 50$
$$R_s = \frac{R_a}{n-1} = \frac{1}{49} ≈ 0{,}0204 \text{ Ω} ≈ 20{,}4 \text{ mΩ}$$
</details>

---

## Opgave 22.3 — PT100
Hvad er modstanden i en PT100 ved 80°C? ($\alpha = 0{,}003851$/K)

<details><summary>💡 Løsning</summary>

$$R_T = R_0 (1 + \alpha \Delta T) = 100 \cdot (1 + 0{,}003851 \cdot 80) ≈ 130{,}8 \text{ Ω}$$
</details>

---

## Opgave 22.4 — 4-20 mA loop
En tryksensor måler 0-10 bar og giver 4-20 mA. Hvilket tryk svarer 12 mA til?

<details><summary>💡 Løsning</summary>

12 mA er $(12-4)/(20-4) = 8/16 = 50\%$ af måleområdet.
$$p = 50\% \cdot 10 \text{ bar} = 5 \text{ bar}$$
</details>

---

## Opgave 22.5 — ADC opløsning
En 10-bit ADC har 0-5 V indgangsområde. Hvad er opløsningen i mV?

<details><summary>💡 Løsning</summary>

Antal trin: $2^{10} = 1024$
$$\text{opløsning} = \frac{5\text{ V}}{1024} ≈ 4{,}88 \text{ mV/trin}$$

Det vil sige: hvert ADC-trin svarer til ca. 4,88 mV på indgangen. For højere præcision bruger man 12-bit (1,22 mV) eller 16-bit (76 μV).
</details>

---

## Opgave 22.6 — Wheatstone-bro
I en Wheatstone-bro med $R_1 = 100$ Ω, $R_2 = 100$ Ω, $R_3 = 470$ Ω. Find $R_x$ ved balance.

<details><summary>💡 Løsning</summary>

$$R_x = R_3 \cdot \frac{R_1}{R_2} = 470 \cdot \frac{100}{100} = 470 \text{ Ω}$$
</details>

---

🎓 **Tillykke! Du har gennemført alle opgaver i kurset.**

⬅ [Kap 22](../kapitler/22-maaleprincipper.md) | [📝 Tag quizzen](../../interaktiv/quiz.html) | [🏁 Tilbage til oversigt](../)
