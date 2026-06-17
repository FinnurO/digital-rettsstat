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
- **LEOS** (Legislation Editing Open Software) — EUs åpne verktøy for å skrive lovtekst i Akoma Ntoso-XML (AKN4EU) med sanntids samarbeid. **Verifisert mot brukermanual v5.0.3:** strukturerte dokumenter (lovtekst, begrunnelse, finansieringsnotat, vedlegg), versjonering med XML-eksport og sammenligning, sporing av (også strukturelle) endringer, interne referanser som oppdateres automatisk når strukturen endres, og import fra Official Journal/EUR-Lex. Kommisjonens instans «EdiT» håndterer dessuten kommentarer og endringsforslag i interservice-høringen som strukturerte artefakter.
- **OpenFisca** — åpen motor for å representere lovgivning som kjørbar kode (mikrosimulering); brukt i bl.a. LexImpact (Frankrike) for å simulere effekten av reformer før vedtak.
- **FLINT** — formelt språk (Nederland/TNO) for å tolke rettskilder til maskinlesbare normative rammeverk.
- **NRML** (Normalized Rule Model Language) — JSON-basert utvekslingsformat for maskinlesbare regler *(fra samlingen/samtalehistorikk — bør verifiseres mot spesifikasjon)*.

## Kunstig intelligens — dobbel rolle

1. **Som akselerator:** generativ KI kan hjelpe jurister å transformere lineær lovtekst til logiske modeller (f.eks. DMN/NRML).
2. **Behov for guardrails:** fordi LLM-er kan hallusinere, må *selve avgjørelsen* styres av deterministiske RaC-regler, ikke av modellen. Forskning på hybride tilnærminger: **XHAILe** (Københavns universitet) og **LEXplain** (UiB) *(begge venter på primærkilde)*. Et beslektet, verktøystøttet spor er **Rulemapping** (rulemapping.org, SPRIND-finansiert): en deterministisk regelkjerne der LLM-er bare brukes til å håndtere ustrukturerte data under menneske-i-løkka.

Dette er en viktig presisering for prinsipp 4 (skjønn forblir hos mennesker) og hull 3: KI kan assistere utforming og forklaring, men den autoritative regelen må være deterministisk og sporbar. Linja kan sies kort: **KI som simulator/utforsker — ja; KI som autoritativ avgjørelsesmotor — nei.** [Alkoholfloken](04-norske-case.md) (Case D) er en levende norsk demonstrasjon: en KI-drevet «digital tvilling» brukt til å *simulere* effekten av regelendringer, som eksplisitt ikke gir fasitsvar, og hvis eget risikobilde navngir nettopp hallusinering og overdreven tillit som farene — som er hvorfor avgjørelsen ikke kan ligge hos modellen.

## Kompetanse

**GRIP** — rammeverk for å utdanne tverrfaglige fagpersoner som forstår både juss og teknologi *(venter på primærkilde)*. Relevant for Fase 2 (institusjonalisering) i [veikartet](02-veikart.md).

## Verifisert mot norsk praksis

Innspill fra norsk forvaltning bekrefter og skjerper bildet. (Enkelte kilder er behandlet som bakgrunn; interne, ikke-offentlige operative detaljer er ikke gjengitt her.)

- **Flere etater er allerede i gang — hver for seg.** NAV og Skatteetaten har drøftet «digitaliserings- og automatiseringsvennlig regelverk», med gode erfaringer fra bl.a. oppgjør etter dødsfall, eResept og koronatiltak. DIBK har undersøkt modellering av TEK17 som RaC (DMN), Imdi har anskaffet et regelmotorverktøy, og Brønnøysundregistrene har erfaring siden 2009. Mønsteret bekrefter hull 5: kompetansen finnes, men er fragmentert uten felles standard.
- **Lovdata dekker ikke kildelagets behov.** Lovdata er bare delvis digital *som data*: mangler annoteringer og toveis referanser (forskrift→lov finnes, men ikke lov→forskrift), og er dessuten en privat stiftelse. Tilgang til rettskilder som åpne data har også vært rettslig omstridt (Lovdata mot rettspraksis.no, 2018–2019). Dette underbygger hull 1.
- **Regeltyper å skille mellom (regellaget):** interaksjonsregler, konverterings-/transformasjonsregler, juridiske regler (rettskilder), forretningsregler (f.eks. DMN), verifiseringsregler og regelstyringsobjekter (krav, tiltak, konklusjon).
- **Kvalitetskrav for tverrlaget:** sporbarhet, etterrettlighet, transparens (med begrunnelse), tilgjengelighet, tillit, risikoreduksjon, endringstakt/effektivitet, etterlevelse, rettssikkerhet og likebehandling — målt opp mot rene effektivitetstall som saksbehandlingstid og automatiseringsgrad.
- **To veier til digitalt regelverk:** (1) endre lov-/forskriftsprosessen slik at digitale lovverk leveres av tverrfaglige team fra start, eller (2) la rettsanvenderen oversette vedtatt lov til en digital versjon med annoteringer og forretningsregler. Ikke alle lover egner seg for RaC, men alle kan bli «digitale tvillinger».
- **Internasjonale forbilder:** New Zealand (opphav til Better Rules), Australia (åpen RaC-plattform, «Regulation as a Platform») og Nederland (DSO — full digital omlegging av miljøforvaltningen, med standardene STTR/IMTR/STOP og DMN+Drools i kjernen). OECD/OPSI «Cracking the Code» er det samlende referanseverket.

## Norske case

Fire norske case forankrer rammeverket empirisk. Se [`04-norske-case.md`](04-norske-case.md):

- **Lov om besøksbidrag** — kandidat for Fase 1-pilot (vedtatt, i kraft 1.7.2026, forskrift fortsatt under arbeid → levende vindu).
- **Ny verdsettelsesmodell for fritidsboliger** — forkastet av Finansdepartementet i 2026 etter flere års arbeid (PwC, Skatteetaten, Kartverket, SSB); illustrerer hva fravær av ex-ante regelmodellering koster.
- **Tilskudd til private barnehager** — regelen som regneark med latent formelfeil, kopiert til ~300 kommuner; duplisert tolkning i renform.
- **Alkoholfloken** — Helsedirektoratets utredning (2025) + Stimulab-prosjekt med en KI-drevet «digital tvilling»; fragmentering, ex-ante-simulering, og et konkret eksempel på grensen KI-simulator vs. autoritativ avgjørelse.

## Kilder (utvalg fra samlingen)

| # | Tittel | Type | Status |
|---|---|---|---|
| 1 | Cracking the Code: Rulemaking for humans and machines | OECD/OPSI-rapport | Offentlig — kan hentes |
| 4 | Digital-ready Policymaking | EU-portal | Offentlig — kan hentes |
| 11 | GRIP on Agile law implementation | Rammeverk (PDF) | Venter på opplasting |
| 14 | LEOS v5.0.3 User Manual | Manual (PDF) | **Verifisert** (Europakommisjonen, CC BY 4.0) |
| 19 | LexImpact (Assemblée nationale) | Verktøy (FR) | Offentlig — kan hentes |
| 20 | Lov om besøksbidrag (LOV-2025-06-20-104) | Lovtekst | **Verifisert** |
| 21 | OECD Better Regulation 2025 | Rapport | Offentlig — kan hentes |
| 34 | Rules as Code – An Open approach | EU-artikkel | Offentlig — kan hentes |
| — | Helsedirektoratet: Veien til en smidigere brukerreise (alkohol) | Utredning | **Verifisert** (offentlig, 2025) |
| — | Rulemapping / Rulemap Builder | Verktøy (DE) | **Verifisert** (offentlig) |
| — | NAV: automatisk behandling, Behandlingskatalog, åpen kildekode | Praksis/kode | **Verifisert** (offentlig) |
| 357 | XHAILe (Københavns universitet) | Forskning | Venter på primærkilde |
| 369 | LEXplain (UiB) | Forskning | Venter på primærkilde |
| 435 | Rules as Code and Better Rules (UDI) | Presentasjon (PDF) | Lest — intern, ikke for publisering |
| 478 | Better Rules for Government Discovery Report | NZ-rapport | Offentlig — kan hentes |
| 490 | RaC: from complex rules to explainable interpretations | TNO-artikkel | Offentlig — kan hentes |
| 493 | Lov om besøksbidrag: Strategisk Blåkopi | Strategidokument (PDF) | **Prioritert opplasting** |
