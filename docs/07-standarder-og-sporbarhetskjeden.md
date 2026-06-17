# 07 — Standarder og sporbarhetskjeden

*Dette dokumentet svarer på to spørsmål som viser seg å være ett: hvor trenger vi å utvikle standarder, og hvordan henger de strukturerte formatene sammen slik at vi får sporbarhet hele veien fra lov til vedtak? Svaret på det første følger av det andre — de standardene vi mest mangler er de **bindende**, fordi det er i skjøtene mellom [kildelaget](05-kildelaget-og-lovprosessen.md) og [regellaget](06-regellaget.md), og videre ut til vedtaket, at sporbarheten skapes eller går tapt.*

## 1. Hvor trenger vi standarder?

Det viktigste først: de fleste *formatene* finnes allerede internasjonalt. Oppgaven er sjelden å finne opp noe nytt, men å **adoptere, profilere og binde sammen**. Behovene faller i tre kategorier.

### A. Adoptere og mandatere (finnes — mangler norsk vedtak)
- **Lovtekst som åpen XML.** Akoma Ntoso (OASIS LegalDocML) finnes, med EU-profilen AKN4EU og britenes CLML→AKN. Norge mangler en **nasjonal profil** («AKN-NO») og — viktigere — mandatet til at kilde-eier (Stortinget, departementer, Lovdata, kommuner) *publiserer* i den. Dette er det største enkelthullet, jf. [`05`](05-kildelaget-og-lovprosessen.md): i dag er den autoritative kilden en PDF og struktureringen privat.
- **Stabile identifikatorer.** ELI for regelverk og ECLI for rettspraksis finnes; Norge må fastsette sitt **URI-mønster** og bruke det konsekvent. Identifikatoren er ryggraden i all sporing — uten den finnes ingen peker å spore langs.

### B. Velge og profilere (finnes — må standardiseres for gjenbruk på tvers)
- **Regelrepresentasjon.** Ikke ett format, men et lite, interoperabelt sett: DMN for beslutningslogikk; FLINT/NRML/OpenFisca for rettslogikk og simulering. Hullet er ikke å lage et format, men å **velge et sett og en profil** slik at regler er portable mellom etater i stedet for at NAVs format ≠ Skatteetatens (prinsipp 9).
- **Felles begreper (semantikk).** Et governert vokabular for dataene reglene opererer på — «inntekt», «bosted», «barn», «bevilling» — bygd på Felles datakatalog/SKOS, slik at «inntekt» betyr det samme i NAV og hos Skatt. Uten dette laget er regler portable i form, men ikke i mening.

### C. Utvikle (de reelle hullene — de bindende standardene)
- **Strukturerte endringer.** Britene representerer endringer som `<effect>`-data; Norge har dem som prosa («i § X skal …»). En standard for **maskinlesbare endringer** gjør at systemet *vet* nøyaktig hvilken bestemmelse som endret seg og hvordan (jf. strukturert høring i [`05` §3.3](05-kildelaget-og-lovprosessen.md)).
- **Hjemmelsbinding / lovspeil-format.** En standardisert måte å uttrykke koblingen *regel ↔ bestemmelse (versjon)*. Dette finnes ikke ferdig: DMN og FLINT kan referere, men ingen avtalt norsk konvensjon binder en kjørbar regel til den versjonerte bestemmelsen den utleder. Lovspeilet ([`05`](05-kildelaget-og-lovprosessen.md), [`06` §6](06-regellaget.md)) er denne bindingen gjort til data.
- **Skjønnsmarkering.** En typet markør i regel-artefaktet som sier «her stopper regelen, her begynner mennesket» — avklaringssteget fra [`06` §3](06-regellaget.md) som en standardisert elementtype, ikke ad hoc unntakshåndtering.
- **Provenansrecord for vedtak.** En standard for hva et automatisert vedtak *må* registrere for å være etterprøvbart: regelversjon, kildeversjon (ELI), inndata-snapshot, logikk-/modellversjon, og hvor et menneske grep inn. Dette er hullet den nye forvaltningsloven lot stå åpent (hull 3 i [`00`](00-problemanalyse.md)).

**Meta-poenget:** hullene i kategori C ligger alle i *skjøtene* mellom lagene. Det er ingen tilfeldighet — det er nettopp der sporbarheten bor.

## 2. Sporbarhetskjeden i praksis — fra lov til vedtak

Sporbarhet er ikke et dokument man skriver i etterkant; det er en **kjede av stabile, versjonerte pekere** som vedlikeholdes i hver skjøt:

1. **Rettskilde (Lag 1):** lov/forskrift som Akoma Ntoso-XML, der hver bestemmelse har en stabil **ELI** ned til versjonert nivå (point-in-time).
2. **Regel (Lag 2):** regel-artefaktet (DMN/FLINT/NRML) bærer en **hjemmelspeker** til ELI-en for bestemmelsen(e) det utleder, erklærer sine inndata i det **felles vokabularet**, og markerer **skjønnspunktene**.
3. **Behandling (Lag 3–4):** behandlingssteget (jf. NAV i [`06`](06-regellaget.md)) kjører regelen og skriver en **provenansrecord**: hvilken regelversjon (som igjen peker på hvilken kildeversjon), hvilke inndata (snapshot), hvilket utfall, og hvor saken ble rutet til et menneske.
4. **Vedtak:** vedtaket lenker til denne recorden. Fra vedtaket kan man dermed spore bakover: → regelversjon → bestemmelsesversjon (ELI) → den teksten som *var* lov da vedtaket ble truffet.

**Point-in-time er ufravikelig.** Et vedtak truffet på dato D må spore til loven slik den sto på D — ikke slik den står i dag. Derfor er hvert artefakt versjonert med gyldighetsdatoer (britenes point-in-time-modell), og vedtakssiden bygges med event sourcing slik at historikken kan spilles av på nytt.

**Provenansrecorden er «kvitteringen».** Mønsteret finnes: W3C PROV for proveniens, event sourcing for uavviselig logg. Den konkrete, offentlige instansen er NAVs Behandlingskatalog med inndata-snapshots og logging av kildekodeversjon ([`06` §6](06-regellaget.md)).

## 3. Hvordan informasjon augmenteres strukturert i kjeden

Nøkkelen: **hvert lag legger til, det erstatter aldri strukturen over.** Augmentering skjer som *typede lenker (assertions) festet på stabile identifikatorer*, ikke ved å redigere artefaktet oppstrøms.

- Kildelaget bærer den autoritative teksten + ELI. Det røres ikke av nedstrøms-lag.
- Regellaget *beriker* med en lenke «denne regelen implementerer bestemmelse X, versjon n», med inndata-begreper og med skjønnsmarkører — som metadata *om* opphavet, ikke som en endring av det.
- Tjenestelaget beriker med kjøretidskontekst (data, versjon, utfall, menneskesteg).

Mekanisk hviler dette på lenkede data: **ELI er RDF-basert**, og Akoma Ntoso har en `<meta>`-blokk nettopp for slik berikelse. Man legger altså til påstander som peker på en identifikator, framfor å skrive inn i kilden. Det er slik kilden forblir autoritativ og uendret mens laget over blir rikere.

## 4. Hvordan endringer fanges opp

- **Endring oppstår i kilden** og gir bestemmelsen en **ny ELI-versjon**.
- **Strukturerte endringer** (`<effect>`-data, ikke prosa) gjør endringen *maskindetekterbar* ved kilden — systemet vet hvilken bestemmelse som ble berørt og hvordan, i stedet for at noen må lese en proposisjon og gjette.
- **Lovspeilet** er den vedlikeholdte kryss-lags-koblingen (kildeversjon ↔ regelversjon). En endring i Lag 1 **tenner et varsel** på hver regel hvis hjemmelspeker traff den endrede bestemmelsen — på samme måte som LEOS oppdager en brutt intern referanse, men på tvers av lag (jf. [`06` §5](06-regellaget.md)). Varselet utløser en gjennomgang som enten oppdaterer regelen (ny versjon) eller bekrefter at ingen endring trengs.
- **Versjonering med gyldighetsdatoer** sørger for at gamle vedtak fortsatt spores til gammel lov, mens nye saker bruker ny regel. Ingenting overskrives; alt versjoneres.

Uten speilet er endringshåndtering en intensjon; med det, og med strukturerte endringer ved kilden, blir det en rutine som kan (semi-)automatiseres.

## 5. Hvorfor dette lukker hull 3

Den nye forvaltningsloven åpnet for automatisering, men satte ingen standard for sporbarhet, etterprøvbarhet eller skillet regel/skjønn ([`00`](00-problemanalyse.md), hull 3). Det denne standarden *er*, konkret, er nettopp det bindende settet i del 1C — identifikatorer, hjemmelsbinding, strukturerte endringer og provenansrecord — lagt oppå de formatene som allerede finnes. Sporbarhet fra lov til vedtak er ikke en funksjon man bygger til slutt; det er en egenskap ved at hver skjøt holder en versjonert peker til skjøten over.

---

*Kilder brukt i dette dokumentet: Akoma Ntoso/LegalDocML (OASIS) og AKN4EU; ELI og ECLI (EU); legislation.gov.uk for `<effect>`-data og point-in-time; DMN (OMG); FLINT (TNO), OpenFisca, NRML *(NRML venter på primærkilde)*; W3C PROV og SKOS; Digdirs Felles datakatalog; LEOS-brukermanual v5.0.3 (Europakommisjonen) for referanse-/endringsdeteksjon; NAVs Behandlingskatalog og offentlige beskrivelse av automatisk behandling. Bygger videre på `05` og `06`.*
