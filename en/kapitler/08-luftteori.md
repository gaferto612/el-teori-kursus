# Chapter 8 — Air theory

**Language:** [🇩🇰 Dansk](../../da/kapitler/08-luftteori.md) · **🇬🇧 English** · [🇸🇦 العربية](../../ar/kapitler/08-luftteori.md)

## 🎯 Learning goals

- Know the composition of air
- Understand pressure, temperature and humidity
- Explain gas behaviour (general gas laws)
- Understand why air is treated as an insulator in electrical engineering

---

## 8.1 Composition of air

Atmospheric air consists mainly of:

| Gas | Volume-% |
|-----|----------|
| Nitrogen (N₂) | 78% |
| Oxygen (O₂) | 21% |
| Argon (Ar) | 0.9% |
| CO₂ + others | 0.1% |

> 💡 Humidity (water vapour) is added on top — can reach 4% in humid climates.

---

## 8.2 Pressure

### Atmospheric pressure
The weight of the air column above us produces a pressure of approximately:
$$p_{atm} \approx 1.013 \text{ bar} = 101.3 \text{ kPa} = 760 \text{ mm Hg}$$

### Relationship between pressure units

| 1 bar | = 100 kPa = 100,000 Pa |
| 1 atm | ≈ 1.013 bar |
| 1 m water column | ≈ 0.1 bar |

### Absolute vs. gauge pressure
- **Absolute pressure** = measured from absolute vacuum
- **Gauge pressure** = measured above atmospheric pressure

$$p_{abs} = p_{gauge} + p_{atm}$$

> 🔥 **Boiler-operator note**: Steam tables use **absolute pressure**. If the working pressure is 8 bar, look up 9 bar in the table.

---

## 8.3 Gas laws (qualitatively)

### Boyle–Mariotte's law
At constant temperature:
$$p_1 \cdot V_1 = p_2 \cdot V_2$$

i.e. pressure and volume are inversely proportional.

### Gay-Lussac's law
At constant volume, pressure rises proportionally with temperature (in Kelvin):
$$\frac{p_1}{T_1} = \frac{p_2}{T_2}$$

### The combined gas law
The combination of all:
$$\frac{p_1 \cdot V_1}{T_1} = \frac{p_2 \cdot V_2}{T_2}$$

> 🌡 **Important**: Temperature must always be in Kelvin (K), not Celsius!

---

## 8.4 Air as an insulator

Dry air has a high **dielectric strength**:
- ~30 kV/cm (homogeneous fields)
- This is why overhead lines work

**BUT**:
- Humid and contaminated air **dramatically reduces** insulation
- Lightning surges can break through many kilometres of air

### Use
| Application | Why air? |
|-------------|----------|
| High-voltage overhead lines | Air = natural insulator |
| Air circuit breakers | Arc extinguished in air (or SF₆ gas) |
| Cooling motors/transformers | Air as heat transport |

---

## 8.5 Humidity

### Absolute humidity
Amount of water vapour per m³ of air (g/m³).

### Relative humidity (RH)
How much water vapour the air contains compared to the **saturation** point:
$$RH = \frac{\text{actual water vapour}}{\text{maximum water vapour}} \cdot 100\%$$

| RH | Sensation |
|----|-----------|
| 30% | Dry (winter, heated rooms) |
| 50% | Comfortable |
| 80–100% | Humid (summer DK, bathroom) |

### Dew point
The temperature at which air's water vapour starts to condense. Critical in:
- Condensation in electrical panels (short circuits!)
- Dewing on cooling surfaces
- Corrosion on electronics

---

## 8.6 Combustion

> 🔥 **Boiler-operator note**: Combustion needs three things:
> 1. **Fuel** (e.g. oil, gas, biomass)
> 2. **Oxygen** (from air)
> 3. **Ignition temperature**

### Stoichiometric air
The **theoretical minimum** amount of air needed to burn the fuel completely.

In practice we need **excess air** (lambda > 1):

$$\lambda = \frac{\text{air supplied}}{\text{theoretical air requirement}}$$

| λ | Combustion type |
|---|-----------------|
| < 1 | Air deficit (unburned fuel — sooty) |
| = 1 | Stoichiometric |
| 1.1 – 1.3 | Optimal for oil/gas (in boilers) |
| > 2 | Large excess — large flue-gas losses |

> 💡 Lambda measurement in flue gas (typically via O₂ sensor) is used to optimise boiler performance.

---

## 8.7 Compressed air in industry (briefly)

Compressed air is a widely-used energy form in industry:
- Pressure: typically 6–8 bar
- Use: pneumatic valves, cylinders, tools
- **Drawback**: low efficiency (~10–20%)

> ⚙ In process plants, compressed air is often combined with PLC control (e.g. Siemens TIA Portal) to drive pneumatic valves and cylinders.

---

## 📌 Summary

- **Composition of air**: nitrogen 78%, oxygen 21%, other gases 1%.
- **Atmospheric pressure** ≈ 1 bar = 101.3 kPa.
- **In boilers**: use absolute pressure = working pressure + 1 bar.
- **Combined gas law**: P·V/T = constant (T in Kelvin).
- **Air is an excellent insulator** when dry, but humidity reduces insulation drastically.
- **Combustion** needs: fuel + oxygen + heat. The air-fuel ratio **lambda (λ)** must be greater than 1 for complete combustion.

---

## ➡️ Next steps

- 📝 [Exercises for chapter 8](../opgaver/08-opgaver.md)
- ➡️ [Chapter 9 — Electrical fundamentals](09-elektriske-grundbegreber.md)
