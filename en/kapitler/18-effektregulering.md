# Chapter 18 — Power regulation

**Language:** [🇩🇰 Dansk](../../da/kapitler/18-effektregulering.md) · **🇬🇧 English** · [🇸🇦 العربية](../../ar/kapitler/18-effektregulering.md)

## 🎯 Learning goals

- Understand the difference between unsynchronised and synchronised regulation
- Know phase control and zero-crossing control
- Understand applications in lighting, heating and motor control
- Assess advantages and disadvantages (radio noise, harmonics)

---

## 18.1 Power regulation — what and why?

**Power regulation** = controlling the power delivered to a load.

### Applications
| Area | Example |
|------|---------|
| **Lighting** | Dimmer (lamp dimmer) |
| **Heating** | Thermostat-controlled electric heating, ovens |
| **Motors** | Speed control of AC motors, DC motors |
| **Industry** | Smelting furnaces, induction heating |

### Two overall principles
1. **Unsynchronised** — the regulator works regardless of mains frequency
2. **Synchronised** — the regulator works in step with the mains frequency

---

## 18.2 Unsynchronised regulation

The control element (typically thyristor/triac) acts as a pure **ON/OFF static contactor**.

### Principle
- Load is fully ON for a period
- Fully OFF for the next period
- The ratio between ON and OFF times controls the **average** power

> ⚠ Drawback: large current swings — can cause flicker in lighting installations.

### Use
- Thermostat-controlled heating element
- Iron, kettle
- Simple and cheap

---

## 18.3 Synchronised regulation

Regulation happens **synchronously** with the mains frequency. Two main methods:

### A. Phase control (PWM-like on AC)
### B. Zero-crossing control

---

## 18.4 Phase control

The triac or thyristor is fired at a **specific point** in each half-cycle — until the next zero crossing.

```
Full power:           Half power (60° firing):
    /\    /\               _    _
   /  \  /  \              |\   |\
  /    \/    \             | \  | \
 ─                      ───┘  \─┘  \─
```

### Characteristics
| Property | Value |
|----------|-------|
| Stepless control | ✅ Yes |
| Used for | Lighting, heating, small motors |
| **Drawback** | Generates **strong radio noise** and harmonics |
| Requirement | Must be combined with EMC filter |

### Components
- **Triac** for AC (both half-cycles)
- **Diac** as trigger (to triac gate)
- **RC circuit** sets the phase angle

```
   AC ──┬─[load]─────●─── AC return
        │            │
        │    +───[R]─┤
        │    │       │
        │   [C]      │
        │    │   diac│
        │    └───►├──┴─── G (triac gate)
        │            │
        └────────────●  triac MT1/MT2
```

> ⚠ **Common home dimmer** = phase control. That is why LED bulbs can flicker or fail with old dimmers — those are designed for incandescent bulbs.

---

## 18.5 Zero-crossing control

The triac is fired **only at the zero crossing** of the voltage — and then conducts complete half-cycles at a time.

### Principle
- Whole period on or off — never "partial"
- E.g.: 5 cycles ON / 5 cycles OFF = 50% power

```
Input AC:    ╱╲╱╲╱╲╱╲╱╲╱╲
Output:      ╱╲╱╲╱╲      ╱╲
             ON ON ON  OFF OFF
```

### Characteristics
| Property | Value |
|----------|-------|
| Stepwise control | In practice fine enough |
| Used for | **Heating** (slow thermal systems) |
| Radio noise | **Almost none** |
| Suitable for lighting/motors | ❌ No (causes flicker / uneven operation) |

> ✅ Zero-crossing control is **free of radio noise** and preferred for heating systems.

---

## 18.6 PWM — Pulse-Width Modulation

In modern DC systems **PWM** is used:

```
Low power:     ▮___▮___▮___▮___    (narrow pulse)
Medium:        ▮▮__▮▮__▮▮__▮▮__
High power:    ▮▮▮▮_▮▮▮▮_▮▮▮▮_    (wide pulse)
```

### Properties
- **Frequency** typically 1–20 kHz (inaudible)
- Fast response
- Low losses — the switching component (MOSFET/IGBT) is either fully ON or fully OFF

### Applications
- DC motor drives (e.g. axis drives, robots)
- LED dimming
- Power regulation in variable-frequency drives
- Switching power supplies (SMPS)

> 💡 **PWM**: rapid switching technique — the pulse width changes to regulate the power. Used in motor control and LED dimming.

---

## 18.7 Variable frequency drive (VFD)

For 3-phase AC motors, the **variable frequency drive** (VFD) is the dominant power regulation:

```
   3-phase 50 Hz ──[rectifier]──[DC link]──[inverter]── variable frequency
                   (B6 bridge)   (capacitor)  (IGBT, PWM)
```

### Principle
- AC input is rectified to DC
- DC is switched by IGBTs with PWM back to 3-phase AC
- **Frequency** and **voltage** are controlled individually

### V/f control (scalar)
The voltage is changed proportionally with frequency to keep the flux in the motor constant.

### Synchronous speed
$$n_s = \frac{60 \cdot f}{p}$$

By varying f (typically 0–100 Hz) the motor speed is controlled steplessly.

> ⚙ In modern industry VFDs are **standard**. Used for pumps, fans, conveyors, cranes — anywhere variable speed is useful.

---

## 18.8 Comparison

| Method | Use | Radio noise | Stepless |
|--------|-----|-------------|----------|
| Unsync. ON/OFF | Thermostat | Small | No (snap) |
| Phase control | Lighting, heating, small motors | **High** | Yes |
| Zero-crossing | **Heating** | Low | Stepwise |
| PWM (DC) | DC motors, LEDs | Medium (can be filtered) | Yes, precise |
| VFD (AC) | 3-phase motors | Medium | Yes, precise |

---

## 18.9 Practical examples

### Lamp dimmer (single-phase, 230 V, 100 W incandescent bulb)
- Configuration: triac with diac trigger
- Phase control → stepless lighting
- **Problem with LED bulbs**: only "dimmable" LEDs work. Reason: phase control delivers pulsating current that is incompatible with simple LED drivers.

### Oven heating in an industrial boiler
- Configuration: zero-crossing (typically solid-state relay — SSR)
- Thermostat input gives ON/OFF, which the SSR converts to whole half-cycles
- No radio noise — ideal for boiler heating

> 🔥 **Boiler-operator note**: In electric boilers or flue-gas temperature control, zero-crossing SSRs combined with a PT100 measurement and PID controller are typical.

---

## 📌 Summary

- **Power regulation** aims to control the energy delivered to the load (lighting, heating, motors).
- **Phase control**: the triac fires at a specific angle of each half-cycle — used in dimmers. High radio noise.
- **Zero-crossing control**: the triac fires only when current crosses zero. No noise, suitable for heating.
- **PWM**: fast on/off with variable duty cycle — used in DC motor control and LED dimming.
- **VFD (variable frequency drive)**: AC → DC → AC at variable frequency. The modern method for 3-phase motor control.
- **In electric boilers**: SSRs (solid-state relays) with zero-crossing are typically used.

---

## ➡️ Next steps

- 📝 [Exercises for chapter 18](../opgaver/18-opgaver.md)
- ➡️ [Chapter 19 — Multivibrators](19-multivibrator.md)
