# Chapter 6 — Units of measurement

**Language:** [🇩🇰 Dansk](../../da/kapitler/06-maaleenheder.md) · **🇬🇧 English** · [🇸🇦 العربية](../../ar/kapitler/06-maaleenheder.md)

## 🎯 Learning goals

- Know the SI base units
- Use prefixes from pico to tera
- Convert between units of length, mass, time, force, energy, pressure
- Understand the relationship between energy, power and efficiency

---

## 6.1 The SI system

**SI** (Système International d'Unités) is the international system of units. It has **7 base units**:

| Quantity | Symbol | Unit | Abbreviation |
|----------|--------|------|--------------|
| Length | l | metre | m |
| Mass | m | kilogram | kg |
| Time | t | second | s |
| Current | I | ampere | A |
| Temperature | T | kelvin | K |
| Amount of substance | n | mole | mol |
| Luminous intensity | I_v | candela | cd |

> 💡 All other units are **derived** from these base units.

---

## 6.2 Prefixes

| Prefix | Symbol | Factor | Decimal |
|--------|--------|--------|---------|
| Tera | T | 10¹² | 1,000,000,000,000 |
| Giga | G | 10⁹ | 1,000,000,000 |
| Mega | M | 10⁶ | 1,000,000 |
| Kilo | k | 10³ | 1,000 |
| Hecto | h | 10² | 100 |
| Deka | da | 10¹ | 10 |
| **(base)** | — | 10⁰ | 1 |
| Deci | d | 10⁻¹ | 0.1 |
| Centi | c | 10⁻² | 0.01 |
| Milli | m | 10⁻³ | 0.001 |
| Micro | μ | 10⁻⁶ | 0.000 001 |
| Nano | n | 10⁻⁹ | 0.000 000 001 |
| Pico | p | 10⁻¹² | 0.000 000 000 001 |

### Electrical examples

| Value | Written as | In base units |
|-------|-----------|---------------|
| 2.2 kΩ | 2.2 kilohm | 2,200 Ω |
| 470 μF | 470 microfarad | 0.000 470 F |
| 50 Hz | 50 hertz | 50 cycles/s |
| 230 V | 230 volt | 230 V |
| 3.3 MW | 3.3 megawatt | 3,300,000 W |
| 100 nF | 100 nanofarad | 0.000 000 100 F |

---

## 6.3 Length

| 1 km | = 1,000 m |
| 1 m | = 100 cm = 1,000 mm |
| 1 mm | = 1,000 μm |

### Area

- 1 m² = 10,000 cm²
- 1 hectare (ha) = 10,000 m²
- 1 km² = 1,000,000 m² = 100 ha

### Volume

- 1 m³ = 1,000 dm³ = 1,000 litres
- 1 litre = 1 dm³ = 1,000 cm³ = 1,000 ml

---

## 6.4 Mass and force

| Mass | Symbol |
|------|--------|
| 1 t (tonne) | = 1,000 kg |
| 1 kg | = 1,000 g |
| 1 g | = 1,000 mg |

### Force — Newton (N)

$$F = m \cdot a$$

- 1 N is the force that gives 1 kg an acceleration of 1 m/s²
- **Gravity**: $F = m \cdot g$ where g ≈ 9.81 m/s²
- An object of 1 kg therefore "weighs" approximately 9.81 N

---

## 6.5 Pressure — Pascal (Pa)

$$p = \frac{F}{A}$$

| Unit | Value |
|------|-------|
| 1 Pa | 1 N/m² |
| 1 kPa | 1,000 Pa |
| 1 bar | 100,000 Pa = 100 kPa |
| 1 atmosphere (atm) | 101,325 Pa ≈ 1.013 bar |

> 🔥 **Boiler-operator note**: Steam pressure is normally given in bar. Remember: gauge pressure + 1 bar = absolute pressure (used when looking up steam tables).

---

## 6.6 Energy and power

### Energy — Joule (J)
$$1 \text{ J} = 1 \text{ N} \cdot 1 \text{ m} = 1 \text{ W} \cdot 1 \text{ s}$$

### Power — Watt (W)
$$P = \frac{E}{t} \quad \Rightarrow \quad 1 \text{ W} = \frac{1 \text{ J}}{1 \text{ s}}$$

In electrical engineering:
$$P = U \cdot I$$

### Electrical energy
$$E = P \cdot t$$

Often measured in **kilowatt-hours (kWh)**:
- 1 kWh = 1,000 W · 3,600 s = 3,600,000 J = 3.6 MJ

**Example**: A 2,000 W kettle running for 30 minutes:
$$E = 2 \text{ kW} \cdot 0.5 \text{ h} = 1 \text{ kWh}$$

---

## 6.7 Temperature

| Scale | Water freezing | Water boiling |
|-------|----------------|---------------|
| Celsius (°C) | 0 °C | 100 °C |
| Kelvin (K) | 273.15 K | 373.15 K |
| Fahrenheit (°F) | 32 °F | 212 °F |

**Conversion**:
- $T_K = T_C + 273.15$
- $T_C = (T_F - 32) \cdot \dfrac{5}{9}$

> 💡 In physics we use Kelvin (K) because it is an absolute scale — there are no negative degrees.

---

## 6.8 Efficiency (η)

$$\eta = \frac{P_{out}}{P_{in}} \quad \text{or} \quad \eta\% = \frac{P_{out}}{P_{in}} \cdot 100\%$$

### Typical values
| System | Efficiency |
|--------|------------|
| Incandescent bulb | ~5% |
| LED bulb | ~30–40% |
| Small electric motor | 70–80% |
| Large industrial motor | 90–95% |
| Transformer | 95–99% |
| Combustion engine (car) | 25–35% |
| Power plant (condensing) | 35–45% |
| Combined heat and power | up to 90% |

> ⚡ **Memory aid**: Loss in a conductor is $P_{loss} = I^2 \cdot R$. That is why energy is transmitted at **high voltage and low current** on the high-voltage grid.

---

## 6.9 Important electrical units

| Quantity | Unit | Symbol | Definition |
|----------|------|--------|------------|
| Voltage | volt | V | J/C |
| Current | ampere | A | C/s |
| Resistance | ohm | Ω | V/A |
| Power | watt | W | V·A |
| Frequency | hertz | Hz | 1/s |
| Capacitance | farad | F | C/V |
| Inductance | henry | H | V·s/A |
| Magnetic flux | weber | Wb | V·s |
| Magnetic flux density | tesla | T | Wb/m² |
| Charge | coulomb | C | A·s |

---

## 📌 Summary

- **The SI system** is the foundation: metre, kilogram, second, ampere, kelvin.
- **Most-used prefixes in electrical engineering**: mega (M), kilo (k), milli (m), micro (μ), nano (n), pico (p).
- **Energy/power relationship**: E = P · t. Power in watts, energy in joules or kilowatt-hours (kWh).
- **Efficiency** η = P_out / P_in × 100%.
- **Celsius to Kelvin**: K = °C + 273.15.

---

## ➡️ Next steps

- 📝 [Exercises for chapter 6](../opgaver/06-opgaver.md)
- ➡️ [Chapter 7 — Chemistry](07-kemi.md)
