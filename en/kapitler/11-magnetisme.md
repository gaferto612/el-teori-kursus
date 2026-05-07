# Chapter 11 — Magnetism

**Language:** [🇩🇰 Dansk](../../da/kapitler/11-magnetisme.md) · **🇬🇧 English** · [🇸🇦 العربية](../../ar/kapitler/11-magnetisme.md)

## 🎯 Learning goals

- Understand magnetic fields and their properties
- Calculate magnetic flux and flux density
- Understand the relationship between electricity and magnetism (electromagnetism)
- Apply Faraday's law of induction
- Understand the motor and generator principles

---

## 11.1 What is magnetism?

The word "magnetism" comes from the small town of **Magnesia** in Asia, where iron ore with natural magnetic properties was found.

### Which materials are magnetic?

| Type | Materials |
|------|-----------|
| Ferromagnetic (strong) | Iron (Fe), cobalt (Co), nickel (Ni), alloys |
| Paramagnetic (weak) | Aluminium, platinum |
| Diamagnetic (repelled) | Copper, water, carbon |

> 💡 In electrical components (motors, transformers) **silicon-alloyed electrical steel** is mainly used.

---

## 11.2 Magnetic field and field lines

A magnetic field is visualised with **field lines**:
- Go from **north pole (N)** to **south pole (S)** outside the magnet
- Inside the magnet: from S to N
- Field lines **never cross**
- Density of lines = field strength

### Earth's magnetism
The Earth acts as a giant bar magnet:
- The geographic **north pole** = magnetic **south pole** (which is why a compass needle points north)

---

## 11.3 Permanent magnets and electromagnets

### Permanent magnet
- Retains its magnetism without supplied energy
- Used in loudspeakers, electric motors, generators

### Electromagnet
- A magnetic field arises when **current passes through a coil**
- The field can be turned on/off
- Used in: relays, contactors, cranes, transformers

---

## 11.4 The right-hand rule

### For a current-carrying wire
> **Thumb** = current direction
> **Fingers** curl around the wire in the direction of the field.

### For a coil
> **Fingers** follow the current direction in the windings
> **Thumb** points to the **north pole** of the coil.

---

## 11.5 Magnetic quantities

### Magnetic flux (Φ)
The amount of magnetic field through an area. Measured in **Weber (Wb)**.

### Magnetic flux density (B)
Flux per unit area. Measured in **Tesla (T)**.

$$B = \frac{\Phi}{A}$$

| Field type | B value |
|------------|---------|
| Earth's magnetic field | ~50 μT |
| Fridge magnet | ~5 mT |
| MRI scanner | 1.5–3 T |
| Strongest laboratory magnet | ~45 T |

### Magnetic field strength (H)
$$H = \frac{N \cdot I}{l}$$

Where N = number of turns, I = current, l = length of the magnetic circuit.

### Permeability (μ)
A material's ability to conduct magnetic flux:
$$\mu = \frac{B}{H}$$

For air: $\mu_0 = 4\pi \cdot 10^{-7}$ H/m.

### Hysteresis
Magnetic materials have a **hysteresis curve** — they "remember" previous magnetisation. This is the basis for permanent magnets, but causes losses in transformers.

---

## 11.6 Electromagnetic induction (Faraday's law)

> **When a conductor moves through a magnetic field — or a magnetic field changes around a conductor — a voltage is induced in the conductor.**

$$U_{ind} = -N \cdot \frac{d\Phi}{dt}$$

| Symbol | Meaning |
|--------|---------|
| N | Number of turns in the coil |
| dΦ/dt | Rate at which flux changes |

> 🔑 **This is the foundation for**:
> - **The generator** (mechanical → electrical energy)
> - **The transformer** (voltage transformation)
> - **The induction motor**
> - **Coils (inductors)** in electronics

---

## 11.7 The generator principle

```
       N
   ┌───────┐    When the loop is rotated,
   │       │    an AC voltage is
   │  ↻ ↺  │    induced
   │       │
   └───────┘
       S
```

**Principle**: A conductor rotating in a magnetic field has a sinusoidal AC voltage induced in it.

- 1 revolution = 1 sine period
- Periods per second = **frequency** (Hz)
- In Denmark: 50 Hz → 3,000 rpm for a 2-pole generator

---

## 11.8 The motor principle

> **A current-carrying conductor in a magnetic field experiences a force.**

$$F = B \cdot I \cdot l$$

| Symbol | Meaning | Unit |
|--------|---------|------|
| F | Force | N |
| B | Flux density | T |
| I | Current | A |
| l | Length of the conductor in the field | m |

### Left-hand rule (motor)
> **Thumb** = direction of force
> **Index finger** = magnetic field (B)
> **Middle finger** = current direction (I)

> 💡 Right-hand rule = generator/induction. Left-hand rule = motor.

---

## 11.9 Coils (inductors)

A coil is a wire wound around a core.

### Inductance (L)
Measured in **Henry (H)**. The coil's ability to oppose changes in current:
$$U_L = L \cdot \frac{dI}{dt}$$

### Energy stored in a coil
$$E = \frac{1}{2} L \cdot I^2$$

> ⚡ Coils are used in: transformers, motors, filters, relays, chokes, inductive lasers.

---

## 11.10 The transformer

Two coils around the same iron core. AC in the primary creates a changing magnetic field, which induces a voltage in the secondary.

$$\frac{U_1}{U_2} = \frac{N_1}{N_2}$$

| If... | Result |
|-------|--------|
| $N_2 > N_1$ | Step-up (to higher voltage) |
| $N_2 < N_1$ | Step-down |
| $N_2 = N_1$ | 1:1 (e.g. galvanic isolation) |

### Power balance (ideal transformer)
$$P_1 = P_2 \quad \Rightarrow \quad U_1 \cdot I_1 = U_2 \cdot I_2$$

Note: high-voltage side → **low** current. That is **why** high-voltage networks are used to minimise wire losses ($P_{loss} = I^2 R$).

---

## 11.11 The magnetic circuit — Ohm's law analogy

| Electrical circuit | Magnetic circuit |
|--------------------|------------------|
| Voltage U | Magnetomotive force $F_m = N \cdot I$ |
| Current I | Flux Φ |
| Resistance R | Reluctance Rₘ |
| $U = R \cdot I$ | $F_m = R_m \cdot \Phi$ |

---

## 📌 Summary

- **The magnetic field**: lines from north pole (N) to south pole (S) outside the magnet.
- **Right-hand rule**: to find the direction of the field around a current-carrying wire.
- **Faraday's law of induction**: U = -N·(dΦ/dt) — this is the basis of generators and transformers.
- **Motor principle**: force F = B·I·l on a current-carrying wire in a magnetic field.
- **Transformer**: U₁/U₂ = N₁/N₂. Power is conserved (P₁ = P₂), so high voltage = low current.
- **Inductance (L)** in henries: opposition to changes in current in a coil.

---

## ➡️ Next steps

- 📝 [Exercises for chapter 11](../opgaver/11-opgaver.md)
- ➡️ [Chapter 12 — Single-phase AC theory](12-1-faset-vekselstroemsteori.md)
