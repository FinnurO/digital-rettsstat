# Endringslogg

Følger prinsippene fra [Keep a Changelog](https://keepachangelog.com/). Versjonering er foreløpig uformell (`v0` = utkastfasen).

## [Ikke utgitt]

### Lagt til
- `docs/07-standarder-og-sporbarhetskjeden.md` — hvor vi trenger standarder (adoptere/profilere/utvikle, med de bindende hullene i skjøtene); sporbarhetskjeden lov→vedtak som en kjede av versjonerte pekere (ELI → hjemmelspeker → provenansrecord); point-in-time; hvordan informasjon augmenteres som lenkede påstander uten å røre kilden; hvordan endringer fanges via strukturerte `<effect>`-data og lovspeilet.
- `docs/06-regellaget.md` — Lag 2: hvordan rettskilde blir kjørbar regel med hjemmelssporing; oversettelsesgapet og at én regel binder alle framtidige saker; grensen regel/skjønn (bundet vs. fritt skjønn, prinsipp 4) med stopp-/avklaringssteget som arkitektur (NAV behandlingssteg, nav.no automatisk behandling); regeltaksonomi og prinsipp 9 i praksis (NAVs prosessregelverk); standarder/verktøy (DMN/FLINT/OpenFisca/NRML, rulemapping.org, LEOS vs. policy-as-code-editor); styring via lovspeilet, event sourcing/Behandlingskatalogen, testing (barnehage), åpen kildekode.
- `docs/04-norske-case.md` — Case D: Alkoholfloken (Helsedirektoratets utredning 2025 + Stimulab «digital tvilling»); fragmentering i nasjonal skala, ikke-digital høringskjede, ex-ante-simulering, og grensen KI-simulator vs. autoritativ avgjørelse. Oppsummering oppdatert til fire case.
- `docs/05-kildelaget-og-lovprosessen.md` — hvordan en lov blir til og hvor den slutter å være digital; at den autoritative kilden er en PDF (Lovtidend) mens struktureringen er privat/proprietær (Lovdata, Gyldendal Rettsdata); Schartums lovspeil; forslag om strukturert-fra-start + felles åpen standard eid av kilde-eier (UK/EU/USA); NAV-rettssikkerhetsrapporten.
- `docs/04-norske-case.md` — to norske case: besøksbidrag (Fase 1-pilot) og den forkastede fritidsbolig-verdsettelsen.
- `docs/03-kunnskapsgrunnlag.md` — syntese av Rules as Code / Better Rules-samlingen, koblet til rammeverket.
- `CONTRIBUTING.md` — hvordan bidra, filkonvensjon og commit-meldinger.
- `CHANGELOG.md` — denne loggen.

### Endret
- `docs/06-regellaget.md` — lagt til underavsnitt «‘Regel’ betyr tre ulike ting» (rettsregel/beslutningsregel/kjørbar regel; hvordan kjeden adresserer flertydigheten med felles hjemmelsanker, mellomspråk og tverrfaglighet).
- `docs/02-veikart.md` — ny seksjon «Egnethet, byrde og prioritering» (egnethet per bestemmelse via regel/skjønn; Pareto-prioritering etter byrde; Tysklands byråkratiindeks (Wagner/ESMT) vs. byrde-/kostnadsindeks; byrde som suksessmål; per-lov-gjennomgang parkert).
- `docs/05-kildelaget-og-lovprosessen.md` — ny del 3.3 «Strukturert høring» (Schartums e-høringsprototype ~2007 med «Lovspeil»-fane; LEOS/EdiT i interservice-høring; Alkoholflokens postgang-eksempel); Schartum-lovspeilet oppgradert fra «venter på primærkilde» til offentlig kilde (CompLex 1/2025 + Lov&Data 2025, «regelvask»); kildefot oppdatert.
- `docs/03-kunnskapsgrunnlag.md` — LEOS verifisert mot brukermanual v5.0.3 (AKN4EU, versjonering, auto-oppdaterte referanser, EdiT i interservice-høring); KI-seksjonen utvidet med simulator-vs-avgjørelsesmotor-linja og Alkoholfloken; Rulemapping lagt til; Norske case og kildetabell oppdatert (fire case, Helsedir/Rulemapping/NAV som verifiserte offentlige kilder).
- `docs/04-norske-case.md` — intro og oppsummering oppdatert fra tre til fire case.
- `README.md` — strukturtabell oppdatert med `docs/06-regellaget.md` og `docs/07-standarder-og-sporbarhetskjeden.md`.
- `docs/01-rammeverk.md` — lagt til «Regeltaksonomi: delte vs. fagspesifikke regler (etterlevelsesmodellen)» og prinsipp 9 («Modellér delte regler én gang»), basert på Politiets etterlevelsesmodell.
- `docs/04-norske-case.md` — lagt til Case C: tilskudd til private barnehager (regelen som regneark, med formelfeil); oppdatert oppsummering til tre case.
- `README.md` — strukturtabell oppdatert med docs 03–05.
- `docs/03-kunnskapsgrunnlag.md` — lagt til avsnitt «Verifisert mot norsk praksis»; besøksbidrag-pilotdelen flyttet til `04-norske-case.md`; kildetabell oppdatert.

## v0 — Første utkast

### Lagt til
- `README.md` — rammeverkets formål, struktur og status.
- `docs/00-problemanalyse.md` — fem hull i dagens norske rettsinfrastruktur.
- `docs/01-rammeverk.md` — lagdelt modell (kilde/regel/data/tjeneste) og charter på åtte prinsipper.
- `docs/02-veikart.md` — fire faser fra forankring til skalering.
- `LISENS.md` — anbefaling for lisensiering av tekst og kode.
