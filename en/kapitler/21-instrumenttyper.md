# Chapter 21 — Instrument types

**Language:** [🇩🇰 Dansk](../../da/kapitler/21-instrumenttyper.md) · **🇬🇧 English** · [🇸🇦 العربية](../../ar/kapitler/21-instrumenttyper.md)

## 🎯 Learning goals

- Know analogue and digital measuring instruments
- Understand the principles of measuring instruments (moving coil, iron core, etc.)
- Choose the right instrument for AC, DC and mixed measurements
- Understand accuracy classes
- Use multimeter, oscilloscope, clamp meter, insulation tester

---

## 21.1 Analogue vs. digital

### Analogue instruments
- **Pointer** with scale
- Stepless display
- Can be intuitive for trends
- Sensitive to shock, vibration

### Digital instruments
- **Digital display**
- Precise readings
- Auto-range, accessories, data logging
- Standard in modern electrical engineering

---

## 21.2 The moving-coil instrument

The classic analogue instrument for **DC**.

### Principle
A small movable coil hangs in a permanent magnetic field. When current flows through the coil, it rotates.

```
       ╱────────╲
      ╱  coil    ╲
     │     I      │   ← rotation ∝ I
     │   ╱   ╲    │
      ╲  ╲ ╱    ╱
       ╲────────╱
        magnetic field
```

### Properties
- **Sensitive** — can measure small currents
- **Linear** scale
- **DC only** (or pulsating DC after a rectifier)
- **Polarity matters** — wrong connection deflects the pointer left

> 💡 Also used for **galvanometers** and laboratory instruments.

---

## 21.3 The iron-core instrument

For **AC and DC**.

### Principle
A movable iron piece is pulled into a coil as the current rises (regardless of polarity).

### Properties
- Measures the **RMS value** automatically (for AC)
- Can measure **both AC and DC**
- **Non-linear** scale (not evenly spaced)
- Less accurate than moving-coil

> ⚙ Used in industrial products — robust, cheap, can handle large currents.

---

## 21.4 Electrodynamic instrument

### Principle
Two coils — one fixed and one movable. Current through both produces a force.

### Use
**Wattmeter** — measures power directly (P = U · I · cos φ):
- Fixed coils connected as **current measurement** (in series with the load)
- Movable coil for **voltage measurement** (in parallel)
- Reading is proportional to power

---

## 21.5 Multimeter

The most important versatile instrument. Can measure:

| Function | Symbol | Range |
|----------|--------|-------|
| DC voltage | V⎓ | mV to kV |
| AC voltage | V~ | mV to kV |
| DC current | A⎓ | μA to A |
| AC current | A~ | mA to A |
| Resistance | Ω | Ω to MΩ |
| Diode test | →\|⊢ | check forward voltage |
| Continuity | •)) | beep if connected |
| Capacitance | F | nF to mF |
| Frequency | Hz | Hz to MHz |
| Temperature | °C | with thermocouple |

### Accuracy
Typically given as "±(% of reading + n digits)":
- Example: "±(0.5% + 2)" on 100.0 V → max deviation 0.5 V + 0.2 V = ±0.7 V

> 🛠 **Common multimeters**: Fluke 87V (professional), Fluke 117 (electrician), UNI-T UT139C (hobby).

### Safety (CAT categories)

| CAT | Use |
|-----|-----|
| CAT II | Ordinary mains sockets |
| CAT III | Fixed installations, distribution boards |
| CAT IV | Mains supply, meter boxes |

> ⚠ **Never use** a CAT II multimeter on a main distribution board — short-circuit currents can be lethal.

---

## 21.6 Clamp ammeter

Measures **current without breaking the circuit** — clamps around a single conductor.

### Principle
- **AC**: Measures the magnetic field via a core (transformer principle)
- **DC**: Uses a Hall-effect sensor (requires a special type)

### Use
- Ideal for checking operating current in installations
- No interruption of the circuit
- Can measure large currents (up to kA)

> 💡 **Important rule**: Clamp **only one conductor** — if you clamp around both L and N, the fields cancel and you read 0.

---

## 21.7 Insulation tester (megger)

Measures **insulation resistance** with a high DC voltage (typically 250 V, 500 V or 1,000 V).

### Use
- Checking insulation in installations
- Machine maintenance
- Required in electrical inspection / installation testing

### Reading
| Value | Verdict |
|-------|---------|
| > 1 GΩ | Excellent |
| > 100 MΩ | Good |
| > 10 MΩ | OK (required in new installation) |
| < 1 MΩ | **Faulty** — repair required |

> ⚠ **Disconnect everything** before measuring. The system is charged to the test voltage — discharge afterwards!

---

## 21.8 Oscilloscope

An oscilloscope visualises **voltage variation over time**. Indispensable in electronics troubleshooting.

### Main components
- **Display** with X (time) and Y (voltage) axes
- **Probe** (~10 MΩ input impedance)
- **Trigger** (synchronises the display)
- **Time/div** and **V/div** settings

### Use
- Measure frequency, period, peak value
- See noise, glitches, ringing
- Measure pulse width, rise times
- Compare signals (2 or 4 channels)

### Modern oscilloscopes
- Digital (DSO)
- Touch-screen
- Many channels (up to 8)
- Logic analyser function
- USB interface and PC software

> 🛠 **Common**: Rigol DS1054Z (beginner), Tektronix MSO46 (advanced), Picoscope (USB-based).

---

## 21.9 Other instruments

| Instrument | Measures |
|------------|----------|
| **Frequency counter** | Frequency with high accuracy |
| **LCR meter** | Inductance (L), capacitance (C), resistance (R) |
| **Function generator** | Generates sine, square, sawtooth |
| **Logic analyser** | Many digital signals simultaneously |
| **Spectrum analyser** | Frequency spectrum (RF, EMC) |
| **Lux meter** | Light intensity |
| **Pyrometer** | Temperature without contact (IR) |
| **Thermal imaging camera** | Thermal images |

---

## 21.10 Accuracy classes

Analogue instruments are divided into classes:

| Class | Tolerance | Use |
|-------|-----------|-----|
| 0.1 | ±0.1% | Laboratory, calibration |
| 0.2 | ±0.2% | Precision measurement |
| 0.5 | ±0.5% | Industry, precision |
| 1.0 | ±1% | General industry |
| 1.5 | ±1.5% | Panel mounting |
| 2.5 | ±2.5% | General use |

> 💡 The tolerance is given on **full scale**, not on the read value! A 1% instrument showing 50% of the scale may have ±2% error of the reading.

---

## 21.11 Input and output impedance

### Voltmeter
- Must have **high** input impedance (at least 10 MΩ)
- Low impedance → draws current → disturbs the circuit

### Ammeter
- Must have **low** impedance (a few mΩ)
- High impedance → voltage drop → disturbs the circuit

### Oscilloscope probe
- Standard 10 MΩ
- Use a "10×" probe for even less circuit loading and higher bandwidth

---

## 📌 Summary

- **The moving-coil instrument**: measures DC, sensitive, linear scale.
- **Iron-core instrument**: measures AC and DC, non-linear scale.
- **The multimeter**: the most-used instrument — measures voltage, current, resistance, capacitance, frequency, and continuity.
- **CAT safety classes**: use CAT III or IV for measurements in switchboards.
- **The clamp meter**: measures current without breaking the circuit — very useful for maintenance.
- **The insulation tester (megger)**: uses high voltage (500–1,000 V DC) to measure insulation resistance.
- **The oscilloscope**: shows voltage variation over time — fundamental in electronics diagnostics.
- **Accuracy class**: 1% or 1.5% for industrial instruments, 0.1% for laboratories.

---

## ➡️ Next steps

- 📝 [Exercises for chapter 21](../opgaver/21-opgaver.md)
- ➡️ [Chapter 22 — Measurement principles](22-maaleprincipper.md)
