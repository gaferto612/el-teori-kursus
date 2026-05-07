# Opgaver — Kapitel 1: Tal og grundlæggende regning

## Opgave 1.1 — Regnerækkefølge
Beregn:
$$5 + 3 \cdot (4 - 2)^2 - 6/3$$

<details><summary>💡 Vis løsning</summary>

Trinvis:
- Parentes: $4 - 2 = 2$
- Potens: $2^2 = 4$
- Multiplikation/division: $3 \cdot 4 = 12$, $6/3 = 2$
- Addition/subtraktion: $5 + 12 - 2 = 15$

**Svar: 15**
</details>

---

## Opgave 1.2 — Fortegn
Beregn:
$$(-3) \cdot (-4) + (-12)/3 - (-5)$$

<details><summary>💡 Vis løsning</summary>

- $(-3) \cdot (-4) = 12$
- $(-12)/3 = -4$
- $-(-5) = +5$
- Sum: $12 - 4 + 5 = 13$

**Svar: 13**
</details>

---

## Opgave 1.3 — Konvertering decimal → binær
Konverter **42** til binær.

<details><summary>💡 Vis løsning</summary>

```
42 : 2 = 21  rest 0
21 : 2 = 10  rest 1
10 : 2 = 5   rest 0
 5 : 2 = 2   rest 1
 2 : 2 = 1   rest 0
 1 : 2 = 0   rest 1
```

Læs nedefra: **101010**

**Kontrol**: $32 + 8 + 2 = 42$ ✓
</details>

---

## Opgave 1.4 — Konvertering binær → decimal
Hvad er **11010**₂ i decimal?

<details><summary>💡 Vis løsning</summary>

$$1 \cdot 16 + 1 \cdot 8 + 0 \cdot 4 + 1 \cdot 2 + 0 \cdot 1 = 26$$

**Svar: 26**
</details>

---

## Opgave 1.5 — Hex-konvertering
Konverter **A7** (hex) til decimal og binær.

<details><summary>💡 Vis løsning</summary>

**Til decimal**:
$$A7_{16} = 10 \cdot 16 + 7 = 167_{10}$$

**Til binær** (via 4-bit grupper): A = 1010, 7 = 0111 → **10100111**

**Kontrol**: $128 + 32 + 4 + 2 + 1 = 167$ ✓
</details>

---

⬅ [Tilbage til kapitel 1](../kapitler/01-tal-og-grundlaeggende-regning.md) | [Næste kapitel →](../kapitler/02-geometri.md)
