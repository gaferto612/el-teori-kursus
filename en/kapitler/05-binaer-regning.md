# Chapter 5 — Binary arithmetic

**Language:** [🇩🇰 Dansk](../../da/kapitler/05-binaer-regning.md) · **🇬🇧 English** · [🇸🇦 العربية](../../ar/kapitler/05-binaer-regning.md)

## 🎯 Learning goals

- Understand why the binary number system is the foundation of all digital electronics
- Convert between binary, decimal, octal and hexadecimal
- Perform addition, subtraction and multiplication in binary
- Understand BCD code and 1's and 2's complement

---

## 5.1 Why binary?

In digital electronics there are only two states:
- **Voltage present** = 1 (HIGH, ON)
- **No voltage** = 0 (LOW, OFF)

The binary number system therefore fits electronics perfectly. It is used in:
- PLCs (Siemens TIA, Allen-Bradley)
- Microprocessors
- Memory (RAM, flash)
- Digital communication

---

## 5.2 Structure of number systems

### Decimal (base 10)
$$1994 = 1\cdot 10^3 + 9\cdot 10^2 + 9\cdot 10^1 + 4\cdot 10^0$$

### Binary (base 2)
$$1011_2 = 1\cdot 2^3 + 0\cdot 2^2 + 1\cdot 2^1 + 1\cdot 2^0 = 8 + 0 + 2 + 1 = 11_{10}$$

### Hexadecimal (base 16)
Uses 0–9 and A–F. Used because 1 hex digit = 4 bits (a "nibble").
$$2F_{16} = 2\cdot 16^1 + 15\cdot 16^0 = 32 + 15 = 47_{10}$$

---

## 5.3 Conversions — recipes

### Decimal → Binary (repeated division by 2)

**Example: 25 → binary**
```
25 : 2 = 12  remainder 1   ← LSB (least significant bit)
12 : 2 = 6   remainder 0
 6 : 2 = 3   remainder 0
 3 : 2 = 1   remainder 1
 1 : 2 = 0   remainder 1   ← MSB (most significant bit)
```

Read bottom-up: **25₁₀ = 11001₂**

### Binary → Decimal (weighted sum)

$$11001_2 = 1\cdot 16 + 1\cdot 8 + 0\cdot 4 + 0\cdot 2 + 1\cdot 1 = 25_{10}$$

### Binary ↔ Hex (shortcut via 4-bit groups)

| Binary | Hex |
|--------|-----|
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

**Example**: 11010110₂
- Split into 4-bit groups **from the right**: `1101 0110`
- Look up in the table: `D 6`
- Result: **D6**₁₆

---

## 5.4 Bit, nibble, byte, word

| Unit | Bits |
|------|------|
| Bit | 1 |
| Nibble | 4 |
| Byte | 8 |
| Word | 16 (or 32, 64) |

> 💡 1 byte can represent values from 0 to 255 (or −128 to +127 signed).

---

## 5.5 Binary addition

**Rules**:
| A | B | Sum | Carry |
|---|---|-----|-------|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | **1** |

**Example**: 1011 + 0110

```
  1011
+ 0110
------
  10001
```

Step by step (right to left):
- 1+0 = 1
- 1+1 = 0, carry 1
- 0+1+1 (carry) = 0, carry 1
- 1+0+1 (carry) = 0, carry 1
- 0+0+1 = 1

Result: **10001₂ = 17₁₀** (check: 11+6=17 ✓)

---

## 5.6 1's complement and 2's complement

To represent **negative numbers** in binary:

### 1's complement
Flip all bits.

$$5_{10} = 0101_2 \quad \rightarrow \quad -5 = 1010_2 \text{ (1's comp)}$$

### 2's complement — the standard in computers
Flip all bits **and add 1**.

$$5_{10} = 0101_2 \quad \rightarrow \quad -5 = 1011_2 \text{ (2's comp)}$$

**Why 2's complement?** Because subtraction becomes addition — and that simplifies the hardware enormously.

---

## 5.7 BCD code (Binary-Coded Decimal)

In BCD each decimal digit is represented **independently** by 4 bits:

| Decimal | BCD |
|---------|-----|
| 0 | 0000 |
| 5 | 0101 |
| 9 | 1001 |
| 10 | **0001 0000** (two nibbles) |
| 25 | 0010 0101 |

> ⚙️ BCD is used in digital displays (7-segment) and older PLC systems because it is easy to decode to human-readable digits.

---

## 5.8 Comparison table

| Decimal | Binary | Octal | Hex | BCD |
|---------|--------|-------|-----|-----|
| 0 | 0000 | 0 | 0 | 0000 |
| 5 | 0101 | 5 | 5 | 0101 |
| 8 | 1000 | 10 | 8 | 1000 |
| 10 | 1010 | 12 | A | 0001 0000 |
| 15 | 1111 | 17 | F | 0001 0101 |
| 16 | 10000 | 20 | 10 | 0001 0110 |

---

## 📌 Summary

- **Binary** is the foundation of all digital electronics (bit = 0 or 1).
- **Converting decimal → binary**: repeated division by 2, read remainders bottom-up.
- **Hex** is used to shorten bits: every 4 bits = one hex digit.
- **2's complement** is how computers represent negative numbers.
- **BCD**: encode each decimal digit with 4 bits — used in digital displays and older PLCs.

---

## ➡️ Next steps

- 📝 [Exercises for chapter 5](../opgaver/05-opgaver.md)
- 🧮 [Number-system converter (interactive)](../../interaktiv/talsystem-konverter.html)
- ➡️ [Chapter 6 — Units of measurement](06-maaleenheder.md)
