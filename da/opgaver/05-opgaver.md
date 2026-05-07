# Opgaver — Kapitel 5: Binær regning

## Opgave 5.1
Konverter **156** til binær.

<details><summary>💡 Løsning</summary>

```
156 : 2 = 78  rest 0
 78 : 2 = 39  rest 0
 39 : 2 = 19  rest 1
 19 : 2 = 9   rest 1
  9 : 2 = 4   rest 1
  4 : 2 = 2   rest 0
  2 : 2 = 1   rest 0
  1 : 2 = 0   rest 1
```

Læs nedefra: **10011100**

Kontrol: $128 + 16 + 8 + 4 = 156$ ✓
</details>

---

## Opgave 5.2
Konverter **10110101**₂ til hex.

<details><summary>💡 Løsning</summary>

Del op i 4-bit grupper fra højre: `1011 0101`
- 1011 = B
- 0101 = 5

→ **B5**₁₆
</details>

---

## Opgave 5.3 — Binær addition
Beregn: $1011_2 + 1101_2$

<details><summary>💡 Løsning</summary>

```
   1011
 + 1101
 ──────
  11000
```

Kontrol: $11 + 13 = 24 = 11000_2$ ✓
</details>

---

## Opgave 5.4
Hvad er det største decimaltal man kan repræsentere med 8 bits (uden fortegn)?

<details><summary>💡 Løsning</summary>

$2^8 - 1 = 255$
</details>

---

## Opgave 5.5
Skriv decimaltallet **42** som BCD.

<details><summary>💡 Løsning</summary>

42 → 4 og 2 separat:
- 4 = 0100
- 2 = 0010

→ **0100 0010**
</details>

---

⬅ [Kap 5](../kapitler/05-binaer-regning.md) | [Næste →](../kapitler/06-maaleenheder.md)
