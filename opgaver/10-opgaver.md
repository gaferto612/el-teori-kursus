# Opgaver — Kapitel 10: Jævnstrømsteori

## Opgave 10.1 — Serieforbindelse
Tre modstande på 10, 22 og 47 Ω er forbundet i serie til en 12 V kilde.
a) Find resulterende modstand.
b) Find strømmen.
c) Find spændingsfaldet over hver modstand.

<details><summary>💡 Løsning</summary>

a) $R_{tot} = 10 + 22 + 47 = 79$ Ω
b) $I = 12/79 ≈ 0{,}152$ A
c) - $U_1 = 0{,}152 \cdot 10 = 1{,}52$ V
   - $U_2 = 0{,}152 \cdot 22 = 3{,}34$ V
   - $U_3 = 0{,}152 \cdot 47 = 7{,}14$ V
   - Sum: 12,00 V ✓
</details>

---

## Opgave 10.2 — Parallelforbindelse
To modstande på 100 Ω og 220 Ω er parallelforbundne til 24 V.
a) Find resulterende modstand.
b) Find strømmen i hver gren samt total.

<details><summary>💡 Løsning</summary>

a) $R_{tot} = (100 \cdot 220)/(100+220) = 22000/320 ≈ 68{,}75$ Ω
b) - $I_1 = 24/100 = 0{,}24$ A
   - $I_2 = 24/220 ≈ 0{,}109$ A
   - $I_{tot} = 24/68{,}75 ≈ 0{,}349$ A (= $I_1 + I_2$ ✓)
</details>

---

## Opgave 10.3 — Kombineret kreds
$R_1 = 10$ Ω i serie med en parallelforbindelse af $R_2 = 30$ Ω og $R_3 = 60$ Ω. Tilsluttes 12 V.
Find $R_{tot}$ og total strøm.

<details><summary>💡 Løsning</summary>

Først parallel: $R_{23} = (30 \cdot 60)/(30+60) = 20$ Ω
Så serie: $R_{tot} = 10 + 20 = 30$ Ω
Strøm: $I = 12/30 = 0{,}4$ A
</details>

---

## Opgave 10.4 — Spændingsfald i kabel
En 230 V belastning på 5 A forsynes via 50 m kobberkabel med tværsnit 1,5 mm² ($\rho = 0{,}0175$).
Find spændingsfaldet i kablet (frem og tilbage).

<details><summary>💡 Løsning</summary>

$$\Delta U = 2 \cdot l \cdot \frac{\rho \cdot I}{A} = 2 \cdot 50 \cdot \frac{0{,}0175 \cdot 5}{1{,}5} ≈ 5{,}83 \text{ V}$$

Det er ca. 2,5 % af 230 V — netop på grænsen af tilladt spændingstab.
</details>

---

## Opgave 10.5 — Effekt i serie og parallel
To modstande, 100 Ω og 200 Ω. Tilsluttes hver gang 12 V.
a) Hvilken afsætter mest effekt i seriekobling?
b) Hvilken afsætter mest effekt i parallelkobling?

<details><summary>💡 Løsning</summary>

a) **Serie**: strømmen er ens. $P = I^2 R$ → den **største** modstand (200 Ω) afsætter mest effekt.
b) **Parallel**: spændingen er ens. $P = U^2/R$ → den **mindste** modstand (100 Ω) afsætter mest effekt.
</details>

---

⬅ [Kap 10](../kapitler/10-jaevnstroemsteori.md) | [🧮 Serie/parallel](../interaktiv/serie-parallel.html) | [Næste →](../kapitler/11-magnetisme.md)
