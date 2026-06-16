# 03 — Kunnskapsgrunnlag: Rules as Code og Better Rules

## Om dette dokumentet

Dette er en arbeidssyntese av en kildesamling om *Rules as Code* (RaC), *Better Rules* og digital lovgivning (~46 kilder, samlet i NotebookLM). Den er **avledet, ikke primær**: punkter merket «(venter på primærkilde)» bygger foreløpig på et sammendrag og bør verifiseres mot originaldokumentet før de brukes normativt, jf. [`CONTRIBUTING.md`](../CONTRIBUTING.md). Norske rettskilder er verifisert mot offentlige kilder og merkes deretter.

## Kjernetesen

RaC og Better Rules bygger bro mellom *lovtekst* og *digital utførelse*: regelverk utformes (eller etterbehandles) slik at den logiske strukturen blir eksplisitt og maskinlesbar, i tett samspill mellom jurist, utvikler og tjenestedesigner — i stedet for at utviklere tolker og oversetter teksten til kode måneder senere. Dette er presis den kjeden rammeverket vårt forsøker å institusjonalisere.

## De tre problemene — og hvor de treffer oss

Kildene peker på tre barrierer som er nær identiske med hullene i [`00-problemanalyse.md`](00-problemanalyse.md):

1. **«The translation gap»** — gapet mellom politisk intensjon og teknisk implementering. Jurist skriver tekst, utvikler koder den senere, og tolkningsfeil oppstår. → vårt hull 1 og 3.
2. **«Sorte bokser»** — regler gjemt i proprietær kildekode, uforståelig for både jurist og innbygger. → vårt hull 3 (manglende sporbarhet/etterprøvbarhet i automatiserte avgjørelser).
3. **Duplisert tolkning** — samme regelverk kodes på nytt i hver etat, dyrt og inkonsistent. → vårt hull 1 og 5.

Dette bekrefter at rammeverkets bærende krav — **sporbarhet fra vedtak til versjonert rettskilde** — treffer det internasjonale fagfeltet identifiserer som kjerneproblemet.

## Hvor RaC treffer den lagdelte modellen

| Lag i [rammeverket](01-rammeverk.md) | Tilsvarende i RaC-litteraturen |
|---|---|
| Kildelaget | ELI/ECLI for identifikasjon; Akoma Ntoso/LEOS for strukturert lovtekst |
| Regellaget | DMN, FLINT, OpenFisca, NRML — formalisert, etterprøvbar regellogikk |
| Datalaget | «Regulation as a Platform» — offisielle regler eksponert via API |
| Tjenestelaget | Innbyggerrettede svar på rettigheter direkte fra autoritative regler |
| Tverrgående | Forklarbarhet (XAI), guardrails for KI, GRIP-kompetanse |

## Standarder og verktøy

- **DMN** (Decision Model and Notation) — OMG-standard for å modellere beslutningslogikk; bro mellom forretningsregler og utførelse.
- **ELI** (European Legislation Identifier) — stabil, unik identifikator for rettsakter; grunnlaget for sporbarhet i kildelaget. **ECLI** er motstykket for rettsavgjørelser.
- **Akoma Ntoso / LegalDocML** — åpen XML-standard for rettslige dokumenter.
- **LEOS** — EUs åpne verktøy for samarbeid om lovtekst i Akoma Ntoso-XML *(venter på primærkilde: brukermanual i samlingen)*.
- **OpenFisca** — åpen motor for å representere lovgivning som kjørbar kode (mikrosimulering); brukt i bl.a. LexImpact (Frankrike) for å simulere effekten av reformer før vedtak.
- **FLINT** — formelt språk (Nederland/TNO) for å tolke rettskilder til maskinlesbare normative rammeverk.
- **NRML** (Normalized Rule Model Language) — JSON-basert utvekslingsformat for maskinlesbare regler *(fra samlingen/samtalehistorikk — bør verifiseres mot spesifikasjon)*.

## Kunstig intelligens — dobbel rolle

1. **Som akselerator:** generativ KI kan hjelpe jurister å transformere lineær lovtekst til logiske modeller (f.eks. DMN/NRML).
2. **Behov for guardrails:** fordi LLM-er kan hallusinere, må *selve avgjørelsen* styres av deterministiske RaC-regler, ikke av modellen. Forskning på hybride tilnærminger: **XHAILe** (Københavns universitet) og **LEXplain** (UiB) *(begge venter på primærkilde)*.

Dette er en viktig presisering for prinsipp 4 (skjønn forblir hos mennesker) og hull 3: KI kan assistere utforming og forklaring, men den autoritative regelen må være deterministisk og sporbar.

## Kompetanse

**GRIP** — rammeverk for å utdanne tverrfaglige fagpersoner som forstår både juss og teknologi *(venter på primærkilde)*. Relevant for Fase 2 (institusjonalisering) i [veikartet](02-veikart.md).

## Kandidat for Fase 1-pilot: Lov om besøksbidrag

Besøksbidragsloven er et nesten ideelt pilotområde for å bevise hele kjeden. Verifiserte fakta:

- Vedtatt av Stortinget sommeren 2025 (Prop. 96 L (2024–2025), Innst. 452 L, Lovvedtak 110). **Trer i kraft 1. juli 2026**; innkreving ventes første halvår 2027.
- **Forskrift om overnattingsavgift er fortsatt under arbeid** og skal tre i kraft samtidig — det gir et levende vindu for digital-ready utforming *mens* regelverket lages.
- Kommunal modell: kommuner med «særlig stor belastning fra reiselivet» kan innføre avgift (utgangspunkt tre prosent) for å finansiere reiselivsrelaterte fellesgoder.

Hvorfor den egner seg:

1. **Regel + skjønn i samme lov.** Klare satser og innkrevingsplikt (regel) side om side med terskelen «særlig stor belastning» og departementets godkjenning av kommunens plan (skjønn) — perfekt for å teste grensen i regellaget.
2. **«Leaky borders» er innebygd.** Avgiften følger kommunegrensen, mens fellesgodene og behovet ikke gjør det. Dette er nøyaktig duplisert-tolkning-problemet: uten felles regelinfrastruktur må hver kommune og hvert bookingsystem tolke loven hver for seg.
3. **Mange aktører som må implementere samme regel.** Kommunene, NFD, kommersielle overnattingssteder og plattformer (Airbnb, FINN.no m.fl.) pålegges roller. Det roper etter én delt, autoritativ regel framfor N private tolkninger.
4. **Tidsvinduet.** At loven er vedtatt men ikke i kraft, og forskriften ennå skrives, er den beste muligheten til å demonstrere RaC i praksis på norsk regelverk.

> Din egen «Strategisk Blåkopi» for besøksbidrag (#493 i samlingen) er trolig det mest verdifulle dokumentet å laste opp — den lar oss koble pilotforslaget til din strategiske tenkning.

## Kilder (utvalg fra samlingen)

| # | Tittel | Type | Status |
|---|---|---|---|
| 1 | Cracking the Code: Rulemaking for humans and machines | OECD/OPSI-rapport | Offentlig — kan hentes |
| 4 | Digital-ready Policymaking | EU-portal | Offentlig — kan hentes |
| 11 | GRIP on Agile law implementation | Rammeverk (PDF) | Venter på opplasting |
| 14 | LEOS v5.0.3 User Manual | Manual (PDF) | Venter på opplasting |
| 19 | LexImpact (Assemblée nationale) | Verktøy (FR) | Offentlig — kan hentes |
| 20 | Lov om besøksbidrag | Lovtekst | **Verifisert** |
| 21 | OECD Better Regulation 2025 | Rapport | Offentlig — kan hentes |
| 34 | Rules as Code – An Open approach | EU-artikkel | Offentlig — kan hentes |
| 357 | XHAILe (Københavns universitet) | Forskning | Venter på primærkilde |
| 369 | LEXplain (UiB) | Forskning | Venter på primærkilde |
| 435 | Rules as Code and Better Rules (UDI) | Presentasjon (PDF) | Venter på opplasting |
| 478 | Better Rules for Government Discovery Report | NZ-rapport | Offentlig — kan hentes |
| 490 | RaC: from complex rules to explainable interpretations | TNO-artikkel | Offentlig — kan hentes |
| 493 | Lov om besøksbidrag: Strategisk Blåkopi | Strategidokument (PDF) | **Prioritert opplasting** |
