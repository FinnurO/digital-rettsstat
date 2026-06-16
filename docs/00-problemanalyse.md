# 00 — Problemanalyse

*Hva mangler egentlig? Dette dokumentet beskriver gapet så presist som mulig, slik at rammeverket i [`01-rammeverk.md`](01-rammeverk.md) svarer på et reelt problem og ikke et antatt et.*

## Utgangspunkt: Norge har delene, men ikke kjeden

Norge skårer høyt internasjonalt på digitalisering og har solide byggeklosser: Lovdata som autoritativ kilde til lover og forskrifter, nasjonale felleskomponenter (ID-porten, Altinn, Maskinporten, Folkeregisteret, Enhetsregisteret, KRR), et etablert rettsinformatikkmiljø (SERI/AFIN), og en regjering med uttalt ambisjon om å bli «verdens mest digitaliserte land» innen 2030.

Likevel finnes det ikke en **sammenhengende, autoritativ og maskinlesbar kjede** fra rettskilde til levert tjeneste. Det er denne kjeden — og styringen av den — som er det grunnleggende hullet.

## De fem hullene

### 1. Loven finnes ikke som autoritativ, maskinlesbar kilde
Lovdata publiserer konsolidert regelverk for mennesker. Det finnes ikke en offisiell, versjonert, maskinlesbar representasjon av lover og forskrifter med stabile identifikatorer (jf. ELI) som er *rettskildemessig autoritativ* og fritt tilgjengelig som infrastruktur. Konsekvens: hver etat som vil automatisere må tolke og strukturere regelverket på nytt, hver for seg, uten et felles, etterprøvbart utgangspunkt.

### 2. Virkemidlene for digitaliseringsvennlig regelverk er veiledende, ikke forpliktende
Digdirs veileder skiller fornuftig mellom *digitaliseringsvennlig* og *automatiseringsvennlig* regelverk. Men den er, som påpekt i fagmiljøet, **rent veiledende** og neppe et tilstrekkelig virkemiddel for å realisere strategien om integrert lov- og tjenesteutvikling. Det finnes ingen forpliktende kobling mellom regelverksarbeid (utredningsinstruksen, Lovteknikkheftet) og krav til maskinlesbarhet, sporbarhet eller datagrunnlag.

### 3. Ny forvaltningslov åpner for automatisering — men setter ingen standard
Den nye forvaltningsloven (2025) lovfester at forvaltningen *kan* automatisere saksbehandling, og er bevisst teknologinøytral. Det er klokt som lovgivningsteknikk, men det betyr at loven ikke etablerer felles krav til:
- **sporbarhet** — hvilken versjon av hvilken rettskilde produserte dette vedtaket?
- **etterprøvbarhet og begrunnelse** — kan en part (og en klageinstans) forstå hvordan en regel ble anvendt?
- **skillet regel/skjønn** — hvor må mennesket beholde vurderingen?

Uten en standard risikerer vi en «black box»-forvaltning der hver regelmotor er en udokumentert øy. Dette er primært et **rettssikkerhetsproblem**, ikke et teknisk.

### 4. Hjemler for datadeling er den tilbakevendende propp
Arbeidet med sammenhengende tjenester rundt de sju livshendelsene viser samme mønster gang på gang: den tekniske integrasjonen er løsbar, men **rettsgrunnlaget for å dele opplysninger på tvers** (taushetsplikt, personvern, formålsbegrensning) er flaskehalsen. Once-Only-prinsippet forutsetter hjemler som er utformet med deling for øye fra start.

### 5. Standardfragmentering og uavklart eierskap
Det mangler en nasjonal baseline av åpne standarder for rettslig innhold (ELI/ECLI/Akoma Ntoso), et delt begrepsapparat/ontologi for rettslige begreper, og et felles identifikatorregime som binder regel → data → tjeneste sammen. Staten oppleves fortsatt som fragmentert; styring og finansiering av det tverrgående er svak. Det finnes ikke ett miljø med mandat til å oversette dette til operative standarder.

## Hvorfor nå

Tre forhold gjør dette til rett tidspunkt:
1. Ny forvaltningslov er vedtatt men *ikke ikraftsatt* — det finnes et vindu for å påvirke forskrifter og praksis.
2. Strategien «Fremtidens digitale Norge» etterspør eksplisitt en *nasjonal arkitektur for samhandling* og sterkere styring.
3. EU-rettsakter (Interoperable Europe Act, Single Digital Gateway, AI-forordningen) skaper både krav og drahjelp.

## Hva en løsning må svare på

En løsning er ikke «mer programvare». Den må levere: (a) en autoritativ datakjede fra rettskilde til tjeneste, (b) forpliktende standarder med et reelt eierskap, og (c) innebygd rettssikkerhet — sporbarhet og etterprøvbarhet — i automatiserte avgjørelser. Dette er hva rammeverket forsøker å strukturere.
