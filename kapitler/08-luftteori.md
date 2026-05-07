# Kapitel 8 — Luftteori
> نظرية الهواء

## 🎯 Læringsmål

- Kende luftens sammensætning
- Forstå begreber som tryk, temperatur og fugtighed
- Forklare gassers adfærd (almene gaslove)
- Forstå hvorfor luft betragtes som isolator i el-teknik

---

## 8.1 Luftens sammensætning

Atmosfærisk luft består hovedsagelig af:

| Gas | Volumen-% |
|-----|-----------|
| Nitrogen (N₂) | 78 % |
| Oxygen (O₂) | 21 % |
| Argon (Ar) | 0,9 % |
| CO₂ + andre | 0,1 % |

> 💡 Fugtighed (vanddamp) tæller derudover — kan være op til 4 % i fugtigt klima.

---

## 8.2 Tryk

### Atmosfærisk tryk
Vægten af luftsøjlen over os giver et tryk på ca.:
$$p_{atm} \approx 1{,}013 \text{ bar} = 101{,}3 \text{ kPa} = 760 \text{ mm Hg}$$

### Forholdet mellem tryk-enheder

| 1 bar | = 100 kPa = 100.000 Pa |
| 1 atm | ≈ 1,013 bar |
| 1 m vandsøjle | ≈ 0,1 bar |

### Absolut vs. overtryk
- **Absolut tryk** = målt fra absolut vakuum
- **Overtryk** (manometertryk) = målt over atmosfæretryk

$$p_{abs} = p_{over} + p_{atm}$$

> 🔥 **Kedelpasser-vigtigt**: Ved opslag i damptabeller skal man bruge **absolut tryk**. Hvis arbejdstrykket er 8 bar, bruges 9 bar i tabellen.

---

## 8.3 Gassernes love (qualitativt)

### Boyle-Mariottes lov
Ved konstant temperatur:
$$p_1 \cdot V_1 = p_2 \cdot V_2$$

Dvs. tryk og volumen er omvendt proportionale.

### Gay-Lussacs lov
Ved konstant volumen stiger tryk proportionalt med temperatur (i Kelvin):
$$\frac{p_1}{T_1} = \frac{p_2}{T_2}$$

### Den almene gaslov
Kombinationen af alle:
$$\frac{p_1 \cdot V_1}{T_1} = \frac{p_2 \cdot V_2}{T_2}$$

> 🌡 **OBS**: Temperaturen skal altid være i Kelvin (K), ikke Celsius!

---

## 8.4 Luft som isolator

Tør luft har høj **gennemslagsstyrke**:
- ~30 kV/cm (homogene felter)
- Det er derfor frilednings-anlæg fungerer

**MEN**:
- Fugtig luft og forurening **sænker** isolationen kraftigt
- Lyn-overspændinger kan slå igennem mange km luft

### Anvendelse
| Anvendelse | Hvorfor luft? |
|-----------|---------------|
| Højspændings-frilednings | Luft = naturlig isolator |
| Luftafbrydere | Lysbuen slukkes i luft (eller SF₆-gas) |
| Køling af motorer/transformere | Luft som varmetransport |

---

## 8.5 Fugtighed

### Absolut fugtighed
Mængde vanddamp pr. m³ luft (g/m³).

### Relativ fugtighed (RH)
Hvor meget vanddamp luften indeholder i forhold til **mætnings**punktet:
$$RH = \frac{\text{aktuel vanddamp}}{\text{maksimal vanddamp}} \cdot 100\%$$

| RH | Fornemmelse |
|----|-------------|
| 30 % | Tør (vinter, opvarmede rum) |
| 50 % | Komfortabel |
| 80–100 % | Fugtig (sommer-DK, badeværelse) |

### Dugpunkt (نقطة الندى)
Den temperatur hvorved luftens vanddamp begynder at kondensere. Kritisk i:
- Kondensvand i el-tavler (kortslutning!)
- Tildugning på køleflader
- Korrosion på elektronik

---

## 8.6 Forbrænding (الاحتراق)

> 🔥 **Kedelpasser-vigtigt**: Forbrænding kræver tre ting:
> 1. **Brændstof** (fx olie, gas, biomasse)
> 2. **Ilt** (fra luft)
> 3. **Antændelsestemperatur**

### Stødiometrisk luft
Den **teoretisk minimale** luftmængde for at forbrænde brændstoffet fuldstændigt.

I praksis kræver vi **luftoverskud** (lambda > 1):

$$\lambda = \frac{\text{tilført luft}}{\text{teoretisk luftbehov}}$$

| λ | Forbrændingstype |
|---|-------------------|
| < 1 | Underskudsluft (uforbrændt brændsel — sodet) |
| = 1 | Stødiometrisk |
| 1,1 – 1,3 | Optimal for olie/gas (i kedler) |
| > 2 | Stort overskud — store røgtab |

> 💡 Lambda-måling i røggas (typisk via O₂-sonde) bruges til at optimere kedelydelsen.

---

## 8.7 Trykluft i industri (kort)

Trykluft er en udbredt energiform i industrien:
- Tryk: typisk 6–8 bar
- Anvendelse: pneumatiske ventiler, cylindre, værktøjer
- **Ulempe**: Lav virkningsgrad (~10–20 %)

> ⚙ I procesanlæg kobles trykluft ofte med PLC-styring (fx Siemens TIA Portal) til at styre pneumatiske ventiler og cylindre.

---

## 📌 Resumé på arabisk

- **تركيب الهواء**: نيتروجين 78%، أكسجين 21%، باقي الغازات 1%.
- **الضغط الجوي** ≈ 1 بار = 101,3 كيلوباسكال.
- **في الغلايات**: نستخدم الضغط المطلق = ضغط التشغيل + 1 بار.
- **قانون الغازات العام**: P·V/T = ثابت (T بالكلفن).
- **الهواء عازل ممتاز** عند الجفاف، لكن الرطوبة تُقلل العزل بشدة.
- **الاحتراق** يحتاج: وقود + أكسجين + حرارة. عامل الهواء **لامبدا (λ)** يجب أن يكون أكبر من 1 لحرق كامل.

---

## ➡️ Næste skridt

- 📝 [Opgaver til kapitel 8](../opgaver/08-opgaver.md)
- ➡️ [Kapitel 9 — Elektriske grundbegreber](09-elektriske-grundbegreber.md)
