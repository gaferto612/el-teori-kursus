# Opgaver — Kapitel 12: 1-faset vekselstrøm

## Opgave 12.1 — RMS, peak, peak-to-peak
For en netspænding på 230 V (RMS) ved 50 Hz, find:
a) Peak-værdi
b) Peak-to-peak
c) Periodetiden

<details><summary>💡 Løsning</summary>

a) $U_{peak} = 230 \cdot \sqrt{2} ≈ 325$ V
b) $U_{pp} = 2 \cdot 325 = 650$ V
c) $T = 1/50 = 20$ ms
</details>

---

## Opgave 12.2 — Induktiv reaktans
En spole med $L = 0{,}1$ H er tilsluttet 230 V, 50 Hz.
a) Find induktiv reaktans $X_L$.
b) Find strømmen.

<details><summary>💡 Løsning</summary>

a) $X_L = 2\pi f L = 2\pi \cdot 50 \cdot 0{,}1 = 31{,}4$ Ω
b) $I = U/X_L = 230/31{,}4 ≈ 7{,}33$ A
</details>

---

## Opgave 12.3 — Kapacitiv reaktans
En kondensator $C = 100$ μF tilsluttes 230 V, 50 Hz.
a) Find kapacitiv reaktans $X_C$.
b) Find strømmen.

<details><summary>💡 Løsning</summary>

a) $X_C = 1/(2\pi f C) = 1/(2\pi \cdot 50 \cdot 100 \cdot 10^{-6}) ≈ 31{,}8$ Ω
b) $I = 230/31{,}8 ≈ 7{,}23$ A
</details>

---

## Opgave 12.4 — RL-serie
En serieforbindelse af $R = 30$ Ω og $L = 0{,}1$ H tilsluttes 230 V, 50 Hz. Find:
a) Impedans Z
b) Strømmen
c) Fasevinkel φ
d) cos φ

<details><summary>💡 Løsning</summary>

a) $X_L = 31{,}4$ Ω. $Z = \sqrt{R^2 + X_L^2} = \sqrt{900 + 986} ≈ 43{,}4$ Ω
b) $I = 230/43{,}4 ≈ 5{,}30$ A
c) $\tan \varphi = X_L/R = 31{,}4/30 = 1{,}047 \Rightarrow \varphi ≈ 46{,}3°$
d) $\cos \varphi = 30/43{,}4 ≈ 0{,}69$
</details>

---

## Opgave 12.5 — Effekttrekant
En motor trækker 10 A ved 230 V og har $\cos \varphi = 0{,}8$. Find:
a) Tilsyneladende effekt S
b) Virkeeffekt P
c) Reaktiv effekt Q

<details><summary>💡 Løsning</summary>

a) $S = U \cdot I = 230 \cdot 10 = 2300$ VA
b) $P = S \cdot \cos \varphi = 2300 \cdot 0{,}8 = 1840$ W
c) $\sin \varphi = \sqrt{1 - 0{,}64} = 0{,}6$ → $Q = 2300 \cdot 0{,}6 = 1380$ var
   Kontrol: $\sqrt{P^2 + Q^2} = \sqrt{1840^2 + 1380^2} ≈ 2300$ VA ✓
</details>

---

⬅ [Kap 12](../kapitler/12-1-faset-vekselstroemsteori.md) | [🌊 Vekselstrøm](../interaktiv/vekselstroem.html) | [Næste →](../kapitler/13-3-faset-vekselstroemsteori.md)
