# Opgaver — Kapitel 18: Effektregulering

## Opgave 18.1 — PWM duty cycle
En LED styres med PWM ved 1 kHz og 30 % duty cycle. Hvad er ON-tiden i ms?

<details><summary>💡 Løsning</summary>

Periode: $T = 1/1000 = 1$ ms
ON-tid: $t_{ON} = 0{,}3 \cdot 1 = 0{,}3$ ms
</details>

---

## Opgave 18.2 — Synkron hastighed via VFD
En 4-polet 3-faset motor styres af en frekvensomformer. Find synkronhastigheden ved frekvenser 50 Hz og 30 Hz.

<details><summary>💡 Løsning</summary>

4 poler = 2 polpar.
- Ved 50 Hz: $n_s = 60 \cdot 50 / 2 = 1500$ omdr/min
- Ved 30 Hz: $n_s = 60 \cdot 30 / 2 = 900$ omdr/min

Frekvensomformeren kan dermed køre motoren ned til ca. 60 % af nominel hastighed med fuldt drejningsmoment.
</details>

---

## Opgave 18.3 — Fasestyring vs nulpunktstyring
Hvilken effektregulering vælger du til:
a) En lampedimmer i stuen
b) Et elvarmelegeme i en kedel
c) En boremaskine med variabel hastighed

<details><summary>💡 Løsning</summary>

a) **Fasestyring** (triac+diac) — trinløs, men radiostøj kan optræde.
b) **Nulpunktstyring** med SSR — ingen radiostøj, fin nok til langsomme termiske systemer.
c) **Fasestyring** — universalmotorer responderer hurtigt og trinløst.
</details>

---

## Opgave 18.4 — PWM gennemsnitsspænding
En 24 V DC motor styres med PWM ved 50 % duty cycle. Hvad er gennemsnitsspændingen til motoren?

<details><summary>💡 Løsning</summary>

$$U_{gns} = U_{kilde} \cdot \text{duty} = 24 \cdot 0{,}5 = 12 \text{ V}$$

Motoren opfører sig (på grund af induktans) som om den var sluttet til 12 V DC.
</details>

---

## Opgave 18.5 — Hvorfor ikke fasestyring til LED-pærer?
Hvorfor virker gamle dimmere (fasestyring) ofte ikke godt med LED-pærer?

<details><summary>💡 Løsning</summary>

Fasestyring giver et **afhugget** sinussignal. LED-driverkredse skal omsætte dette til konstant DC, og mange simple LED-drivere kan ikke håndtere de bratte spændingsændringer:
- Flimmer ved lav effekt
- LED kan slet ikke tænde under en vis duty cycle
- "Surrende" støj fra spolen i driveren

Løsninger: **dim-bare LED'er** (med kompatibel driver), eller skift dimmer til **modern 0-10 V dimmer** eller PWM.
</details>

---

⬅ [Kap 18](../kapitler/18-effektregulering.md) | [Næste →](../kapitler/19-multivibrator.md)
