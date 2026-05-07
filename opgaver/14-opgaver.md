# Opgaver — Kapitel 14: Modstande og kondensatorer

## Opgave 14.1 — Farvekode
En modstand har farverne **rød, violet, orange, guld**. Find værdi og tolerance.

<details><summary>💡 Løsning</summary>

- Rød = 2
- Violet = 7
- Orange = ×1k
- Guld = ±5%

→ **27 × 1.000 = 27.000 Ω = 27 kΩ ±5%**
</details>

---

## Opgave 14.2 — LED-formodstand
En LED skal trække 20 mA og har $U_F = 2{,}1$ V. Den forsynes fra 12 V.
Beregn nødvendig formodstand.

<details><summary>💡 Løsning</summary>

$$R = \frac{U_{kilde} - U_F}{I_{LED}} = \frac{12 - 2{,}1}{0{,}020} = \frac{9{,}9}{0{,}020} = 495 \text{ Ω}$$

Vælg næste standardværdi: **510 Ω** eller **560 Ω**.
</details>

---

## Opgave 14.3 — Kondensatorer i serie og parallel
Tre kondensatorer: 10 μF, 22 μF, 47 μF. Find resulterende kapacitet:
a) Parallelt
b) I serie

<details><summary>💡 Løsning</summary>

a) Parallelt: $C_{tot} = 10 + 22 + 47 = 79$ μF
b) Serie: $1/C_{tot} = 1/10 + 1/22 + 1/47 = 0{,}1 + 0{,}0455 + 0{,}0213 = 0{,}1668$
   → $C_{tot} = 1/0{,}1668 ≈ 6{,}0$ μF
</details>

---

## Opgave 14.4 — Tidskonstant
Et RC-led har $R = 47$ kΩ og $C = 4{,}7$ μF. Find tidskonstanten og tiden indtil kondensatoren er ca. fuldt opladet.

<details><summary>💡 Løsning</summary>

$$\tau = R \cdot C = 47.000 \cdot 4{,}7 \cdot 10^{-6} = 0{,}221 \text{ s}$$

Fuldt opladet (~99%) efter 5τ = ca. 1,1 sek.
</details>

---

## Opgave 14.5 — Energi i kondensator
En 220 μF kondensator oplades til 50 V. Hvor meget energi er lagret?

<details><summary>💡 Løsning</summary>

$$E = \frac{1}{2} C U^2 = \frac{1}{2} \cdot 220 \cdot 10^{-6} \cdot 50^2 = 0{,}275 \text{ J}$$
</details>

---

⬅ [Kap 14](../kapitler/14-modstande-og-kondensatorer.md) | [Næste →](../kapitler/15-halvlederkomponenter.md)
