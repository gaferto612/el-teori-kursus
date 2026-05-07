# Kapitel 6 — Måleenheder
> وحدات القياس

## 🎯 Læringsmål

- Kende SI-systemets grundenheder
- Bruge præfikser fra piko til tera
- Konvertere mellem enheder for længde, masse, tid, kraft, energi, tryk
- Forstå sammenhængen mellem energi, effekt og virkningsgrad

---

## 6.1 SI-systemet

**SI** (Système International d'Unités) er det internationale enhedssystem. Det har **7 grundenheder**:

| Størrelse | Symbol | Enhed | Forkortelse | بالعربية |
|-----------|--------|-------|-------------|----------|
| Længde | l | meter | m | متر |
| Masse | m | kilogram | kg | كيلوغرام |
| Tid | t | sekund | s | ثانية |
| Strøm | I | ampere | A | أمبير |
| Temperatur | T | kelvin | K | كلفن |
| Stofmængde | n | mol | mol | مول |
| Lysstyrke | I_v | candela | cd | كانديلا |

> 💡 Alle andre enheder er **afledede** af disse grundenheder.

---

## 6.2 Præfikser (البادئات)

| Præfiks | Symbol | Faktor | Decimal |
|---------|--------|--------|---------|
| Tera | T | 10¹² | 1.000.000.000.000 |
| Giga | G | 10⁹ | 1.000.000.000 |
| Mega | M | 10⁶ | 1.000.000 |
| Kilo | k | 10³ | 1.000 |
| Hekto | h | 10² | 100 |
| Deka | da | 10¹ | 10 |
| **(grund)** | — | 10⁰ | 1 |
| Deci | d | 10⁻¹ | 0,1 |
| Centi | c | 10⁻² | 0,01 |
| Milli | m | 10⁻³ | 0,001 |
| Mikro | μ | 10⁻⁶ | 0,000.001 |
| Nano | n | 10⁻⁹ | 0,000.000.001 |
| Piko | p | 10⁻¹² | 0,000.000.000.001 |

### El-tekniske eksempler

| Værdi | Skrivemåde | I grundenheder |
|-------|-----------|----------------|
| 2,2 kΩ | 2,2 kiloohm | 2.200 Ω |
| 470 μF | 470 mikrofarad | 0,000.470 F |
| 50 Hz | 50 hertz | 50 perioder/s |
| 230 V | 230 volt | 230 V |
| 3,3 MW | 3,3 megawatt | 3.300.000 W |
| 100 nF | 100 nanofarad | 0,000.000.100 F |

---

## 6.3 Længde (الطول)

| 1 km | = 1.000 m |
| 1 m | = 100 cm = 1.000 mm |
| 1 mm | = 1.000 μm |

### Areal (المساحة)

- 1 m² = 10.000 cm²
- 1 hektar (ha) = 10.000 m²
- 1 km² = 1.000.000 m² = 100 ha

### Rumfang (الحجم)

- 1 m³ = 1.000 dm³ = 1.000 liter
- 1 liter = 1 dm³ = 1.000 cm³ = 1.000 ml

---

## 6.4 Masse og kraft

| Masse | Symbol |
|-------|--------|
| 1 t (ton) | = 1.000 kg |
| 1 kg | = 1.000 g |
| 1 g | = 1.000 mg |

### Kraft (القوة) — Newton (N)

$$F = m \cdot a$$

- 1 N = den kraft der giver 1 kg en acceleration på 1 m/s²
- **Tyngdekraft**: $F = m \cdot g$ hvor g ≈ 9,81 m/s²
- En genstand på 1 kg "vejer" altså ca. 9,81 N

---

## 6.5 Tryk (الضغط) — Pascal (Pa)

$$p = \frac{F}{A}$$

| Enhed | Værdi |
|-------|-------|
| 1 Pa | 1 N/m² |
| 1 kPa | 1.000 Pa |
| 1 bar | 100.000 Pa = 100 kPa |
| 1 atmosfære (atm) | 101.325 Pa ≈ 1,013 bar |

> 🔥 **Kedelpasser-relevant**: Damptryk angives normalt i bar. Husk: arbejdstryk + 1 bar = absolut tryk (bruges ved opslag i damptabeller).

---

## 6.6 Energi og effekt

### Energi (الطاقة) — Joule (J)
$$1 \text{ J} = 1 \text{ N} \cdot 1 \text{ m} = 1 \text{ W} \cdot 1 \text{ s}$$

### Effekt (القدرة) — Watt (W)
$$P = \frac{E}{t} \quad \Rightarrow \quad 1 \text{ W} = \frac{1 \text{ J}}{1 \text{ s}}$$

I el-teknik:
$$P = U \cdot I$$

### Elektrisk energi
$$E = P \cdot t$$

Måles ofte i **kilowatttimer (kWh)**:
- 1 kWh = 1.000 W · 3.600 s = 3.600.000 J = 3,6 MJ

**Eksempel**: En elkedel på 2.000 W kører i 30 minutter:
$$E = 2 \text{ kW} \cdot 0{,}5 \text{ h} = 1 \text{ kWh}$$

---

## 6.7 Temperatur (درجة الحرارة)

| Skala | Frysepunkt vand | Kogepunkt vand |
|-------|----------------|----------------|
| Celsius (°C) | 0 °C | 100 °C |
| Kelvin (K) | 273,15 K | 373,15 K |
| Fahrenheit (°F) | 32 °F | 212 °F |

**Konvertering**:
- $T_K = T_C + 273{,}15$
- $T_C = (T_F - 32) \cdot \dfrac{5}{9}$

> 🇸🇦 **ملاحظة**: في الفيزياء، نستخدم كلفن (K) لأنها مقياس مطلق — لا توجد درجات سالبة.

---

## 6.8 Virkningsgrad (η)

$$\eta = \frac{P_{ud}}{P_{ind}} \quad \text{eller} \quad \eta\% = \frac{P_{ud}}{P_{ind}} \cdot 100\%$$

### Typiske værdier
| System | Virkningsgrad |
|--------|---------------|
| Glødepære | ~5 % |
| LED-pære | ~30–40 % |
| Elmotor (lille) | 70–80 % |
| Elmotor (stor industri) | 90–95 % |
| Transformer | 95–99 % |
| Forbrændingsmotor (bil) | 25–35 % |
| Kraftværk (kondens) | 35–45 % |
| Kraftvarmeværk | op til 90 % |

> ⚡ **El-relevant huskeregel**: Tab i en leder er $P_{tab} = I^2 \cdot R$. Det er derfor man overfører energi ved **høj spænding og lav strøm** på højspændingsnettet.

---

## 6.9 Vigtige el-enheder

| Størrelse | Enhed | Symbol | Definition |
|-----------|-------|--------|------------|
| Spænding | volt | V | J/C |
| Strøm | ampere | A | C/s |
| Modstand | ohm | Ω | V/A |
| Effekt | watt | W | V·A |
| Frekvens | hertz | Hz | 1/s |
| Kapacitet | farad | F | C/V |
| Induktans | henry | H | V·s/A |
| Magnetisk flux | weber | Wb | V·s |
| Magn. flux-tæthed | tesla | T | Wb/m² |
| Ladning | coulomb | C | A·s |

---

## 📌 Resumé på arabisk

- **نظام SI** هو الأساس: المتر، الكيلوغرام، الثانية، الأمبير، الكلفن.
- **البادئات** الأكثر استخداماً في الكهرباء: ميغا (M)، كيلو (k)، ميلي (m)، ميكرو (μ)، نانو (n)، بيكو (p).
- **العلاقة بين الطاقة والقدرة**: E = P · t. القدرة بالواط، الطاقة بالجول أو الكيلوواط ساعة (kWh).
- **الكفاءة** η = القدرة الخارجة ÷ القدرة الداخلة × 100%.
- **التحويل بين سيلسيوس وكلفن**: K = °C + 273,15.

---

## ➡️ Næste skridt

- 📝 [Opgaver til kapitel 6](../opgaver/06-opgaver.md)
- ➡️ [Kapitel 7 — Kemi](07-kemi.md)
