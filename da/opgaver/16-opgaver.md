# Opgaver — Kapitel 16: Forstærkning

## Opgave 16.1 — Spændingsforstærkning
En forstærker har $U_{ind} = 50$ mV og $U_{ud} = 4$ V. Find forstærkningen $A_U$ i tal og dB.

<details><summary>💡 Løsning</summary>

$A_U = 4/0{,}05 = 80$
$A_U[dB] = 20 \log(80) ≈ 38 \text{ dB}$
</details>

---

## Opgave 16.2 — Inverterende op-amp
En inverterende op-amp har $R_f = 100$ kΩ og $R_{ind} = 10$ kΩ. Find forstærkningen.

<details><summary>💡 Løsning</summary>

$$A_U = -\frac{R_f}{R_{ind}} = -\frac{100k}{10k} = -10$$

Forstærkning på 10 gange, med faseskift 180° (minus-tegn).
</details>

---

## Opgave 16.3 — Ikke-inverterende op-amp
En ikke-inverterende op-amp har $R_f = 47$ kΩ og $R_1 = 1$ kΩ. Find forstærkningen.

<details><summary>💡 Løsning</summary>

$$A_U = 1 + \frac{R_f}{R_1} = 1 + 47 = 48$$
</details>

---

## Opgave 16.4 — dB-skala
Hvor mange gange forstærkning er +20 dB? +40 dB? −6 dB?

<details><summary>💡 Løsning</summary>

- +20 dB → $10^{20/20} = 10$ gange
- +40 dB → $10^{40/20} = 100$ gange
- −6 dB → $10^{-6/20} ≈ 0{,}5$ (halvering)
</details>

---

## Opgave 16.5 — Klasse-AB
Hvorfor foretrækkes klasse-AB-forstærker over klasse-A i lydforstærkere?

<details><summary>💡 Løsning</summary>

Klasse-AB har **højere virkningsgrad** (50-60 % mod 25 % for klasse-A) og forvrængning der kan holdes lav. To transistorer (NPN+PNP) deler arbejdet — én tager den positive, én den negative halvdel. Den lille hvilestrøm (bias) eliminerer crossover-forvrængning.
</details>

---

⬅ [Kap 16](../kapitler/16-forstaerkning.md) | [Næste →](../kapitler/17-ensretning.md)
