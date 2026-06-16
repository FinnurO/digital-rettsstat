# 02 — Veikart

*Plan i faser. Tanken er å bevise kjeden på et smalt, reelt område før vi forsøker å institusjonalisere og skalere.*

## Fase 0 — Forankring og kartlegging
**Mål:** vite nøyaktig hva som finnes, hvem som eier hva, og hvor smertepunktene er.

- Kartlegg dagens tilstand: Lovdatas dataformater og tilgangsvilkår, Digdir-veilederen, og hvordan utvalgte etater (f.eks. NAV, Skatteetaten) faktisk bygger sine regelmotorer i dag.
- Kartlegg interessenter og eierskap: hvem ville hatt mandat for hvert lag?
- Avklar de juridiske rammene: hva tillater/krever ny forvaltningslov, personvernforordningen (særlig automatiserte avgjørelser) og relevante EU-rettsakter?
- Lever: en interessent- og tilstandsrapport + utkast til styringsmodell.

## Fase 1 — Standard og pilot
**Mål:** bevise hele kjeden på ett smalt område, ende til ende.

- Velg ett **regeltungt, høyvolums og avgrenset** område der reglene er relativt klare (egner seg for automatisering uten tungt skjønn).
- Demonstrer stabelen: ta et utvalg forskrifter inn i kildelaget med ELI-identifikatorer → formaliser regellogikken i regellaget med eksplisitt hjemmelssporing → koble på data → vis en tjeneste der et vedtak kan spores tilbake til versjonert bestemmelse.
- Skriv første utkast til de åpne standardene (identifikatorer, regellogikk-format, sporbarhetskrav).
- Lever: en fungerende referanseimplementasjon + standardutkast v0.1.

## Fase 2 — Institusjonalisering
**Mål:** gjøre standardene forpliktende og gi dem et hjem.

- Foreslå hvordan standardene forankres: kobling til utredningsinstruksen/Lovteknikkheftet, eventuelt forskrift til ny forvaltningslov, eller egen styringsstruktur.
- Avklar eierskap, mandat og **finansiering** for det tverrgående — det mest sannsynlige hinderet.
- Bygg kompetanse: rettsinformatikk/forvaltningsinformatikk som operativ disiplin, ikke bare akademisk.
- Lever: et politisk/forvaltningsmessig beslutningsunderlag.

## Fase 3 — Skalering
**Mål:** fra pilot til flere domener og livshendelser.

- Rull ut til flere regelområder og koble på de sammenhengende tjenestene.
- Etabler forvaltningsregime for versjonering: hvordan lovendring automatisk trigger gjennomgang av tilhørende regellogikk.
- Mål gevinst og rettssikkerhet — ikke bare effektivitet.

---

## Hva vi trenger nå (åpne spørsmål til avklaring)

1. **Primær adressat:** Er hoveddokumentet et *politisk* beslutningsunderlag, et *teknisk* standardforslag, eller et *gjennomføringsveikart* for etatene? (Påvirker tone, dybde og rekkefølge.)
2. **Ambisjonsnivå for v1:** Skal vi sikte mot et helhetlig posisjonsdokument, eller spisse oss mot pilotforslaget i Fase 1 først?
3. **Repo-navn og lisens** (se [`LISENS.md`](LISENS.md)).
