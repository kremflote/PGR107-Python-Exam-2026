# PGR107-Python-Exam-2026
![Python](https://img.shields.io/badge/Python-blue?logo=python)
![Data Analysis](https://img.shields.io/badge/Data%20Analysis-green)
![NumPy](https://img.shields.io/badge/NumPy-013243?logo=numpy)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas)
![Matplotlib](https://img.shields.io/badge/Matplotlib-orange)

# Eksamen Programmering og Dataanalyse

### Python Programming, Algorithms, Matrix Operations and Grade Drift Analysis | Kristiania

**Emne:** PGR107 Python Programming
**Semester:** Vår-2026   
**Foreleser:** [Huamin Ren](https://www.linkedin.com/in/huamin-ren-660b3020/)

**Gruppemedlemmer:**

| Navn | GitHub |
|------|--------|
| Marius Kristensen | [@kremflote](https://github.com/kremflote) |
| Marius André Ellingsen | [@mariusaellingsen](https://github.com/mariusaellingsen) |

---

## Karakter

<p align="left">
  <img src="https://img.shields.io/badge/Karakter-A-green?style=for-the-badge" />
</p>

Sensor begrunnelse:  
Fremragende prestasjon som klart utmerker seg. Kandidaten viser svært godvurderingsevne og stor grad av selvstendighet.

---

## Oversikt

Dette prosjektet består av fem programmerings- og analyseoppgaver i Python. Oppgavene dekker rekursive/mønsterbaserte tallfølger, enkel spillogikk, geografiske beregninger, matriseoperasjoner og en større dataanalyse av standpunktkarakterer ved videregående skoler i Oslo.

Prosjektet bruker grunnleggende Python sammen med biblioteker som **NumPy**, **Pandas**, **Matplotlib** og **chardet** for databehandling, numeriske beregninger og visualisering.

---

## Problemoversikt

### Oppgave 1 – Supernacci-tallfølge

Implementerer en funksjon for å beregne en Supernacci-lignende tallfølge. Programmet genererer de første tolv verdiene for å verifisere mønsteret.

Løsningen bruker en liste til å lagre tidligere verdier og beregner neste verdi basert på en periodisk sum av tidligere elementer.

---

### Oppgave 2 – Terninggjettspill

Implementerer et enkelt spill hvor brukeren skal gjette tallet på en firesidet terning.

Programmet inneholder:

- tilfeldig terningkast med `random`
- input-validering
- maksimalt fire forsøk
- tilbakemelding etter hvert forsøk
- avsluttende melding dersom brukeren ikke gjetter riktig

---

### Oppgave 3 – Koordinater, byer og interessepunkter

Implementerer et geografisk søkeprogram som finner nærmeste by og nærmeste interessepunkt basert på brukerens koordinater.

Programmet bruker data for:

- Bergen
- Oslo
- Trondheim
- Nidarosdommen
- Vigelandsparken
- Operahuset
- Bryggen
- Universitetsmuseet
- Gamlehaugen

Videre utvides datastrukturen for byene med geografiske grenser, og interessepunkter knyttes til byer basert på om de ligger innenfor grensene.

Programmet beregner også:

- gjennomsnittlig POI-rating per by
- POI-er sortert etter avstand fra bysentrum
- nærmeste POI fra brukerens posisjon
- nærmeste by fra brukerens posisjon

---

### Oppgave 4 – Matrisespor med NumPy

Implementerer en manuell beregning av sporet til en matrise, altså summen av elementene på hoveddiagonalen.

Programmet kontrollerer først om matrisen er kvadratisk. Dersom matrisen ikke har like mange rader og kolonner, avbrytes trace-operasjonen.

Resultatet sammenlignes med `np.trace()` for å verifisere at den manuelle implementasjonen er korrekt.

---

### Oppgave 5 – Dataanalyse av standpunktkarakterer

Utfører en utforskende dataanalyse av karakterstatistikk fra Utdanningsdirektoratet for videregående skoler i Oslo.

Analysen undersøker om standpunktkarakterer har driftet oppover fra skoleåret 2020–21 til 2024–25, og om utviklingen varierer mellom fag- og programgrupper.

Programmet inkluderer:

- automatisk deteksjon av filencoding med `chardet`
- lasting av tab-separert CSV-fil
- filtrering til individuelle Oslo-skoler
- behandling av norske desimaltall
- håndtering av manglende og undertrykte verdier
- omforming fra bredt til langt dataformat
- vektede gjennomsnitt basert på antall elever
- gruppering av fag etter `Vurderingsfagkode`
- statistisk oppsummering per år og programgruppe
- visualisering med seks delplott

---

## Dataset

- **Kilde:** [Utdanningsdirektoratet – Karakterstatistikk for videregående skole](https://www.udir.no/tall-og-forskning/statistikk/statistikk-videregaende-skole/karakterer-vgs/)
- **Fil brukt:** `dataset.csv`
- **Område:** Oslo
- **Skolenivå:** Individuelle videregående skoler
- **Karaktertype:** Standpunkt
- **Periode:** 2020–21 til 2024–25
- **Måleverdi:** Snittkarakter
- **Vekting:** Antall elever

---

## Forskningsspørsmål

Har standpunktkarakterer ved videregående skoler i Oslo driftet oppover fra 2020–21 til 2024–25, og varierer mønsteret mellom ulike programgrupper?

---

## Hypoteser

- **H1 – Karakterdrift:** Gjennomsnittlige standpunktkarakterer ved Oslo videregående skoler har økt fra 2020–21 til 2024–25.
- **H2 – Færre svake resultater:** Andelen lavere karaktergjennomsnitt har gått ned i 2024–25 sammenlignet med 2020–21.

Siden datasettet inneholder gjennomsnittskarakterer og ikke individuelle karakterfordelinger, måles H2 som vektet andel skole-fag-gjennomsnitt på eller under 3.

---

## Visualiseringer

Analysen bruker flere visualiseringsteknikker:

- **Histogram:** Sammenligner karakterfordelingen i 2020–21 og 2024–25.
- **Error bars:** Viser samlet vektet gjennomsnittskarakter per år med standardavvik.
- **Linjeplot:** Viser utvikling i gjennomsnittskarakter per programgruppe.
- **Linjeplot for H2:** Viser andel skole-fag-gjennomsnitt på eller under 3.
- **Scatter plot med kontur:** Sammenligner skole/program-gjennomsnitt i første og siste år.
- **Stolpediagram:** Viser endring i lavere karakterandel per programgruppe.

---

## Konklusjon

Visualiseringene og de vektede beregningene tyder ikke på en tydelig systematisk økning i standpunktkarakterer ved Oslo videregående skoler fra 2020–21 til 2024–25. H1 støttes derfor ikke tydelig av analysen.

H2 får heller ikke sterk støtte. Noen programgrupper viser en reduksjon i lavere karaktergjennomsnitt, mens andre grupper beveger seg i motsatt retning. Resultatet peker derfor mot et blandet og relativt stabilt mønster heller enn en klar generell forbedring.

---

## Begrensninger

- Datasettet inneholder gjennomsnittskarakterer, ikke individuelle karakterer.
- H2 måles derfor med en proxy: skole-fag-gjennomsnitt på eller under 3.
- Programgrupperingen er laget manuelt basert på fagkodeprefikser og er ikke en offisiell Udir-klassifisering.
- Standpunktkarakterer måler skolefastsatte vurderinger, ikke eksamensresultater.
- Analysen kan vise korrelasjon og mønstre, men ikke årsakssammenhenger.

---

## Kilder

François, M., & De Witte, K. (2025). *A decade of grade inflation boosted by the COVID-19 pandemic: An empirical analysis of a top European university*. British Educational Research Journal, 51(5), 2271–2339. https://doi.org/10.1002/berj.4172

Goldhaber, D., & Young, M. G. (2023). *Course grades as a signal of student achievement: Evidence on grade inflation before and after COVID-19* (CALDER Research Brief No. 35-1123). Center for Analysis of Longitudinal Data in Education Research, American Institutes for Research. https://caldercenter.org/publications/course-grades-signal-student-achievement-evidence-grade-inflation-and-after-covid-19

Utdanningsdirektoratet. (n.d.). *Karakterstatistikk for videregående skole*. Retrieved May 27, 2026, from https://www.udir.no/tall-og-forskning/statistikk/statistikk-videregaende-skole/karakterer-vgs/

---

*PGR107 Avsluttende eksamen — Kristiania University College, 2026*