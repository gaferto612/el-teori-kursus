# Opgaver — Kapitel 21: Instrumenttyper

## Opgave 21.1 — Voltmeter eller amperemeter?
Du skal måle:
a) Spændingsfald over en pære
b) Strøm gennem en motor
c) Modstand i en kabelende (afkoblet)

Hvilket instrument og hvordan tilsluttes det?

<details><summary>💡 Løsning</summary>

a) **Voltmeter parallelt** med pæren.
b) **Amperemeter i serie** med motor (eller bedre: klemmeampere uden afbrydelse).
c) **Ohmmeter** — men husk at afkoble fra strømkilden først!
</details>

---

## Opgave 21.2 — Klemmeampere
Hvorfor skal man kun klemme én leder (fx kun fasen) når man bruger et klemmeamperemeter?

<details><summary>💡 Løsning</summary>

Hvis både fase og nul er i klemmen, ophæver de modsatrettede magnetfelter hinanden — instrumentet viser **0 A**, selvom der løber strøm. Klem **kun én** leder for at få et målbart magnetfelt.
</details>

---

## Opgave 21.3 — CAT-kategorier
Hvilken CAT-kategori bruges hvor?

<details><summary>💡 Løsning</summary>

- **CAT II** — almindelige stikkontakter (i hjemmet)
- **CAT III** — fast installation, gruppefordelinger, motortavler
- **CAT IV** — hovedfordelinger, før hovedsikringen, måleskab

Brug aldrig CAT II-multimeter på CAT IV-installation. Kortslutningsenergi kan være dødelig.
</details>

---

## Opgave 21.4 — Isolationsmåler
En motor måles med 500 V isolationsmåler — der vises 0,8 MΩ. Vurder.

<details><summary>💡 Løsning</summary>

0,8 MΩ er **for lavt** for en velholdt motor (kravet ligger typisk 1-10 MΩ minimum). Mulige årsager:
- Fugt i motorvikling
- Forurening (olie, støv)
- Begyndende isolationssvigt
- Defekt vikling

Foranstaltning: tør motor (varmluft eller kontrolleret opvarmning) og mål igen. Hvis stadig lav → vikling skal renoveres eller udskiftes.
</details>

---

## Opgave 21.5 — Indgangsmodstand
Hvorfor skal et voltmeter have høj indgangsmodstand?

<details><summary>💡 Løsning</summary>

Voltmeteret tilsluttes parallelt med komponenten, og enhver strøm gennem voltmeteret påvirker den målte spænding. Med høj indgangsmodstand (typisk 10 MΩ for digitale multimetre) trækkes næsten ingen strøm — målingen forstyrrer kredsen minimalt.

Tommelfingerregel: $R_v \geq 100 \cdot R_{måle}$. Ved måling på højimpedanskredse (sensorer, op-amp indgange) kan selv 10 MΩ være for lavt.
</details>

---

⬅ [Kap 21](../kapitler/21-instrumenttyper.md) | [Næste →](../kapitler/22-maaleprincipper.md)
