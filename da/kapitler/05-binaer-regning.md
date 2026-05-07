# Kapitel 5 — Binær regning
> الحساب الثنائي

## 🎯 Læringsmål

- Forstå hvorfor det binære talsystem er fundamentet for al digital elektronik
- Konvertere mellem binær, decimal, oktal og hexadecimal
- Lave addition, subtraktion og multiplikation i binær
- Forstå BCD-kode og 1- og 2-komplement

---

## 5.1 Hvorfor binær?

I digital elektronik findes kun to tilstande:
- **Spænding tilstede** = 1 (HIGH, ON)
- **Ingen spænding** = 0 (LOW, OFF)

Det binære talsystem (الثنائي) passer derfor perfekt til elektronik. Det bruges i:
- PLC'er (Siemens TIA, Allen-Bradley)
- Mikroprocessorer
- Hukommelse (RAM, flash)
- Digital kommunikation

---

## 5.2 Talsystemets opbygning

### Decimal (basis 10)
$$1994 = 1\cdot 10^3 + 9\cdot 10^2 + 9\cdot 10^1 + 4\cdot 10^0$$

### Binær (basis 2)
$$1011_2 = 1\cdot 2^3 + 0\cdot 2^2 + 1\cdot 2^1 + 1\cdot 2^0 = 8 + 0 + 2 + 1 = 11_{10}$$

### Hexadecimal (basis 16)
Bruger 0–9 og A–F. Bruges fordi 1 hex-ciffer = 4 bits (en "nibble").
$$2F_{16} = 2\cdot 16^1 + 15\cdot 16^0 = 32 + 15 = 47_{10}$$

---

## 5.3 Konvertering — opskrifter

### Decimal → Binær (gentagen division med 2)

**Eksempel: 25 → binær**
```
25 : 2 = 12  rest 1   ← LSB (mindst betydende bit)
12 : 2 = 6   rest 0
 6 : 2 = 3   rest 0
 3 : 2 = 1   rest 1
 1 : 2 = 0   rest 1   ← MSB (mest betydende bit)
```

Læs nedefra og op: **25₁₀ = 11001₂**

### Binær → Decimal (vægtet sum)

$$11001_2 = 1\cdot 16 + 1\cdot 8 + 0\cdot 4 + 0\cdot 2 + 1\cdot 1 = 25_{10}$$

### Binær ↔ Hex (genvej via 4-bit grupper)

| Binær | Hex |
|-------|-----|
| 0000 | 0 |
| 0001 | 1 |
| 0010 | 2 |
| 0011 | 3 |
| 0100 | 4 |
| 0101 | 5 |
| 0110 | 6 |
| 0111 | 7 |
| 1000 | 8 |
| 1001 | 9 |
| 1010 | A |
| 1011 | B |
| 1100 | C |
| 1101 | D |
| 1110 | E |
| 1111 | F |

**Eksempel**: 11010110₂
- Del op i grupper á 4 bits **fra højre**: `1101 0110`
- Slå op i tabellen: `D 6`
- Resultat: **D6**₁₆

---

## 5.4 Bit, nibble, byte, word

| Enhed | Bits | الوحدة |
|-------|------|--------|
| Bit | 1 | بت |
| Nibble | 4 | نصف بايت |
| Byte | 8 | بايت |
| Word | 16 (eller 32, 64) | كلمة |

> 💡 1 byte kan repræsentere tal fra 0 til 255 (eller −128 til +127 med fortegn).

---

## 5.5 Binær addition

**Reglerne**:
| A | B | Sum | Mente |
|---|---|-----|-------|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | **1** |

**Eksempel**: 1011 + 0110

```
  1011
+ 0110
------
  10001
```

Trin for trin (højre mod venstre):
- 1+0 = 1
- 1+1 = 0, mente 1
- 0+1+1 (mente) = 0, mente 1
- 1+0+1 (mente) = 0, mente 1
- 0+0+1 = 1

Resultat: **10001₂ = 17₁₀** (kontrol: 11+6=17 ✓)

---

## 5.6 1-komplement og 2-komplement

For at repræsentere **negative tal** i binær:

### 1-komplement (المتمم الأحادي)
Vend alle bits.

$$5_{10} = 0101_2 \quad \rightarrow \quad -5 = 1010_2 \text{ (1-komp)}$$

### 2-komplement (المتمم الثنائي) — det normale i computere
Vend alle bits **og læg 1 til**.

$$5_{10} = 0101_2 \quad \rightarrow \quad -5 = 1011_2 \text{ (2-komp)}$$

**Hvorfor 2-komplement?** Fordi subtraktion bliver til addition — og det forenkler hardwaren enormt.

---

## 5.7 BCD-kode (Binary-Coded Decimal)

I BCD repræsenterer hvert decimalciffer **uafhængigt** af 4 bits:

| Decimal | BCD |
|---------|-----|
| 0 | 0000 |
| 5 | 0101 |
| 9 | 1001 |
| 10 | **0001 0000** (to nibbles) |
| 25 | 0010 0101 |

> ⚙️ BCD bruges i digitale displays (7-segments) og ældre PLC-systemer fordi det er let at afkode til menneskelæsbare tal.

---

## 5.8 Sammenligningstabel

| Decimal | Binær | Oktal | Hex | BCD |
|---------|-------|-------|-----|-----|
| 0 | 0000 | 0 | 0 | 0000 |
| 5 | 0101 | 5 | 5 | 0101 |
| 8 | 1000 | 10 | 8 | 1000 |
| 10 | 1010 | 12 | A | 0001 0000 |
| 15 | 1111 | 17 | F | 0001 0101 |
| 16 | 10000 | 20 | 10 | 0001 0110 |

---

## 📌 Resumé på arabisk

- **النظام الثنائي** = أساس كل الإلكترونيات الرقمية (بت = 0 أو 1).
- **التحويل من العشري إلى الثنائي**: قسمة متكررة على 2، ثم قراءة البواقي من الأسفل للأعلى.
- **السادس عشر (Hex)** يُستخدم لاختصار البتات: كل 4 بت = رقم سادس عشري واحد.
- **المتمم الثنائي (2-complement)** هو طريقة تمثيل الأرقام السالبة في الحاسوب.
- **BCD**: ترميز كل خانة عشرية بـ 4 بت — يُستخدم في الشاشات الرقمية و PLC القديمة.

---

## ➡️ Næste skridt

- 📝 [Opgaver til kapitel 5](../opgaver/05-opgaver.md)
- 🧮 [Talsystem-konverter (interaktiv)](../../interaktiv/talsystem-konverter.html)
- ➡️ [Kapitel 6 — Måleenheder](06-maaleenheder.md)
