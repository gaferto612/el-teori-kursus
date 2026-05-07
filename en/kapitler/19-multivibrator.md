# Chapter 19 — Multivibrators

**Language:** [🇩🇰 Dansk](../../da/kapitler/19-multivibrator.md) · **🇬🇧 English** · [🇸🇦 العربية](../../ar/kapitler/19-multivibrator.md)

## 🎯 Learning goals

- Understand what a multivibrator is
- Distinguish between astable, monostable and bistable
- Calculate frequency and pulse width
- Understand the Schmitt trigger
- Recognise applications in control systems

---

## 19.1 What is a multivibrator?

A **multivibrator** is a **digital** circuit with one or more stable states that can switch between them.

> 💡 **Multivibrator**: an electronic circuit with stable states that can switch between them — used to generate pulses.

### Three types

| Type | Stable states | Use |
|------|---------------|-----|
| **Astable** | 0 | Pulse generator (oscillator) |
| **Monostable** | 1 | Time delay, "one-shot" |
| **Bistable** | 2 | Memory (flip-flop) |

---

## 19.2 Astable multivibrator — the pulse generator

Has **no** stable state — the circuit oscillates continuously between two states.

### Applications
- Blinking lights (warning lights)
- Periodic on/off of heating elements
- Beeping in alarm systems
- Clock and timing signals

### Principle
Two switching stages (transistors or logic gates) are mutually capacitively coupled:

```
     +Vcc ─[R₁]──●─────────[R₂]─── +Vcc
                  │              │
                  ●──[C₁]──●     ●
                  │        │     │
                ┤V₁├      ┤V₂├
                  │        │
                  └────●───┘
                       ⏚

   T1's collector ─── C → T2's base
   T2's collector ─── C → T1's base
```

- T1 ON → capacitor charges through T2 → flips T2 ON
- T2 ON → other capacitor flips T1 ON
- The circuit "flips" back and forth

### Frequency
For a symmetrical astable with $R_1 = R_2 = R$ and $C_1 = C_2 = C$:
$$f \approx \frac{1}{1.4 \cdot R \cdot C}$$

Period:
$$T = 1.4 \cdot R \cdot C$$

### Example
$R = 10$ kΩ, $C = 1$ μF:
$$T = 1.4 \cdot 10{,}000 \cdot 0.000{,}001 = 0.014 \text{ s} = 14 \text{ ms}$$
$$f = 1/0.014 \approx 71 \text{ Hz}$$

---

## 19.3 Adjustable astable with an IC

With 3 NOT gates (or a 555 timer) you can build an adjustable astable:

```
      ┌──[R₂]──┐
      │        │
  ────┤NOT 1 ├─●──[R₁]──●──┤NOT 2├─●──┤NOT 3├─── out
                          │
                         [C₁]
                          │
                          ⏚
```

- $R_1$, $C_1$ set the frequency
- $R_2$ discharges the RC network
- IC3 acts as a **Schmitt trigger** to give a clean square wave

### Period
$$T \approx 1.4 \cdot R_1 \cdot C_1$$

---

## 19.4 The 555 timer — the classic

**NE555** is a universal timer IC. Almost 50 years old and still used everywhere.

### 8-pin IC

```
            ┌──┬──┐
        GND │1   8│ Vcc
       TRIG │2   7│ DISCH
        OUT │3   6│ THRES
       RST  │4   5│ CTRL
            └──────┘
```

### Astable configuration

```
Vcc ──[R₁]──●──[R₂]──●─── 7 (DISCH)
            │        │
            6        2 (THRES, TRIG)
            │
           [C]
            │
            ⏚
```

### Frequency and duty cycle
$$f = \frac{1.44}{(R_1 + 2R_2) \cdot C}$$

Time HIGH: $t_1 = 0.693 \cdot (R_1 + R_2) \cdot C$
Time LOW: $t_2 = 0.693 \cdot R_2 \cdot C$

> 💡 The 555 is extremely flexible — can also be configured as monostable, PWM, level detector, etc.

---

## 19.5 Monostable multivibrator

Has **one** stable state. When triggered it switches to the other state for a fixed time and then returns.

### Applications
- **Time delay** (e.g. trigger after X seconds)
- **Pulse shaping** (creates short pulse from long)
- **Debouncing** mechanical contacts
- "One-shot" timer

### Pulse width
With an RC circuit:
$$t_p = 1.1 \cdot R \cdot C \quad \text{(555 monostable)}$$

### Example
A light should be on for 30 sec after a button press:
- Choose $C = 100$ μF
- $R = t_p / (1.1 \cdot C) = 30 / (1.1 \cdot 100 \cdot 10^{-6}) \approx 273$ kΩ → choose 270 kΩ

---

## 19.6 Bistable multivibrator (flip-flop)

Has **two** stable states. Only switches on input — stays in the chosen state until the next trigger.

### Types

| Type | Function |
|------|----------|
| **SR flip-flop** | Set/Reset — the simplest |
| **D flip-flop** | Data — copies D to Q on clock |
| **JK flip-flop** | Universal — can toggle |
| **T flip-flop** | Toggles on every clock pulse |

### Applications
- **Memory** (1 bit)
- **Counters** (binary counter chain)
- **Shift registers**
- **Frequency dividers** (T flip-flop halves frequency)

```
   SR flip-flop truth table:
   
   S | R | Q
   ──┼───┼──
   0 | 0 | hold (unchanged)
   0 | 1 | 0 (reset)
   1 | 0 | 1 (set)
   1 | 1 | forbidden
```

> 💾 An 8-bit register = 8 flip-flops. RAM, CPU registers, all digital memory is built on flip-flops.

---

## 19.7 Schmitt trigger

A Schmitt trigger has **two different thresholds** for switching:
- Switches to HIGH at a high threshold ($U_H$)
- Switches to LOW at a low threshold ($U_L$)
- $U_H > U_L$ = **hysteresis**

```
     Input:  ──╱╲──╱╲──╲╱──╱╲──
   
     Schmitt:  ──┐  ┌──────┐  ┌──
                 └──┘      └──┘
              (clean square waves, no flicker)
```

### Applications
- Convert analogue sine signals to digital squares
- Avoid flicker when the input "floats" near the threshold
- Debounce mechanical contacts
- Pulse shaping in noisy systems

> 💡 Used in alarm circuits, photocells, switch debouncing.

---

## 19.8 Pulse shaping and shapers

In control systems, signals often need to be **shaped** before being passed on:

| Shaper | Function |
|--------|----------|
| **Differentiator** (RC short time constant) | Creates narrow pulse from edge |
| **Integrator** (RC long time constant) | "Smooths" pulses |
| **Comparator** | Compares to reference |
| **Schmitt trigger** | Clean digital edges |

---

## 19.9 Application examples

### Flash relay for an alarm lamp
- **Astable** with 555 at e.g. 1 Hz
- Output drives transistor → relay → lamp
- Periodic flashing

### Stairwell light timer
- Button activates **monostable** with 3-minute timer
- Lamp turns on, switches off automatically after 3 min

### PLC input debouncing
- Mechanical contacts "bounce" — multiple micro-pulses on a single press
- Schmitt trigger filters them, or a monostable produces a clean pulse

---

## 📌 Summary

- **Multivibrator**: a circuit in three main types:
  - **Astable**: no stable state — generates continuous pulses (like a signal generator).
  - **Monostable**: one stable state — issues a temporary pulse when triggered (timer).
  - **Bistable / flip-flop**: two stable states — the basis of digital memory.
- **555 timer**: classic timer IC — frequency $f = 1.44 / [(R_1 + 2R_2) \cdot C]$.
- **Schmitt trigger**: a switch with two different thresholds — turns sinusoidal signals into clean squares.
- **Applications**:
  - Pulse generators, timers
  - Alarm flashing
  - Stairwell lights (monostable)
  - Digital memory, counters (flip-flops)

---

## ➡️ Next steps

- 📝 [Exercises for chapter 19](../opgaver/19-opgaver.md)
- ➡️ [Chapter 20 — Combinational logic](20-kombinationslogik.md)
