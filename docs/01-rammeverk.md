# 01 — Rammeverk

*Den lagdelte modellen og prinsippene. Dette er forslaget til hvordan kjeden fra rettskilde til tjeneste bør struktureres og styres.*

## Grunnidé: loven som infrastruktur

Premisset er at rettskilder, regler og de felles komponentene de hviler på, bør behandles som **nasjonal infrastruktur** — på linje med veier eller folkeregister — med tilhørende krav til åpenhet, versjonering, eierskap og kvalitet. Ikke som dokumenter som hver etat tolker for seg.

## Den lagdelte modellen

```
┌─────────────────────────────────────────────────────────────┐
│  TVERRGÅENDE: Rettssikkerhet · Personvern · Styring          │
│  (sporbarhet, etterprøvbarhet, eierskap, finansiering)        │
├─────────────────────────────────────────────────────────────┤
│  4. TJENESTELAGET   sammenhengende tjenester, livshendelser   │
│  3. DATALAGET       registre, felleskomponenter, once-only    │
│  2. REGELLAGET      formalisert regellogikk ("regler som kode")│
│  1. KILDELAGET      autoritativ, maskinlesbar rettskilde      │
└─────────────────────────────────────────────────────────────┘
```

### Lag 1 — Kildelaget: «loven som data»
Autoritative rettskilder (lover, forskrifter, og på sikt rettspraksis og forarbeider) som åpne, versjonerte, maskinlesbare data med **stabile identifikatorer** (ELI for regelverk, ECLI for avgjørelser) og full proveniens. Dette er fundamentet: alt over må kunne peke nedover til en konkret, versjonert bestemmelse.

### Lag 2 — Regellaget: regler som kode, med sporbarhet
Formalisert regellogikk utledet fra kildelaget, der **hver regel eksplisitt refererer til hjemmelen** den bygger på. Krever en åpen metodikk og et styringsregime for: hvordan tekst blir kode, hvem som eier og vedlikeholder regelen, hvordan endringer i kilden forplanter seg, og — avgjørende — **hvor grensen mot skjønn går** (hvilke vurderinger som *må* forbli menneskelige). Regellaget er åpent og etterprøvbart, ikke en lukket motor i hver etat.

### Lag 3 — Datalaget: registre og felleskomponenter
De autoritative registrene og felleskomponentene (Folkeregister, Enhetsregister m.fl.) og infrastrukturen for sikker datadeling. Bygger på **once-only**: data hentes fra autoritativ kilde, ikke etterspørres på nytt. Forutsetter hjemler utformet for deling.

### Lag 4 — Tjenestelaget: sammenhengende tjenester
Brukerrettede tjenester organisert rundt livshendelser, bygget oppå lagene under. Konsistent brukeropplevelse og klart språk. Her realiseres gevinsten — men bare hvis lagene under henger sammen.

### Tverrgående — Rettssikkerhet, personvern og styring
Ikke et lag, men krav som gjelder hele stabelen: sporbarhet fra vedtak til versjonert kilde, retten til å forstå en avgjørelse, revisjon/logging, innebygd personvern, samt det vanskeligste — **eierskap, mandat og finansiering** for det tverrgående.

## Prinsippene (charter)

1. **Loven er infrastruktur.** Rettskilder og regellogikk er et felles gode som forvaltes deretter.
2. **Sporbarhet er ufravikelig.** Enhver automatisert avgjørelse skal kunne spores til en versjonert rettskilde.
3. **Åpne standarder og åpen kildekode som standardvalg.** Lukking krever begrunnelse.
4. **Skjønn forblir hos mennesker** der loven krever en vurdering. Automatisering avlaster, men erstatter ikke rettsanvendelse som krever skjønn.
5. **Innebygd rettssikkerhet og personvern** (by design og by default), ikke etterpåklokskap.
6. **Én gang-prinsippet.** Innbygger og næringsliv oppgir samme opplysning kun én gang.
7. **Tverrfaglighet fra start.** Jurist, utvikler og tjenestedesigner i samme rom fra dag én — i tråd med Digdirs egne anbefalinger.
8. **Forpliktende, ikke bare veiledende.** Standardene må forankres slik at de faktisk følges.

## Hva som gjør dette annerledes enn dagens tilstand

Dagens virkemidler er gode, men frittstående og veiledende. Rammeverket binder dem sammen til én kjede med ett krav som går igjen overalt: **sporbarhet nedover til autoritativ kilde** — og foreslår et eierskap som kan håndheve det.
