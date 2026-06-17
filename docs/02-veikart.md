# 02 — Veikart

*Plan i faser. Tanken er å bevise kjeden på et smalt, reelt område før vi forsøker å institusjonalisere og skalere.*

## Fase 0 — Forankring og kartlegging
**Mål:** vite nøyaktig hva som finnes, hvem som eier hva, og hvor smertepunktene er.

- Kartlegg dagens tilstand: Lovdatas dataformater og tilgangsvilkår, Digdir-veilederen, og hvordan utvalgte etater (f.eks. NAV, Skatteetaten) faktisk bygger sine regelmotorer i dag.
- Kartlegg interessenter og eierskap: hvem ville hatt mandat for hvert lag?
- Avklar de juridiske rammene: hva tillater/krever ny forvaltningslov, personvernforordningen (særlig automatiserte avgjørelser) og relevante EU-rettsakter?
- Lever: en interessent- og tilstandsrapport + utkast til styringsmodell.

## Egnethet, byrde og prioritering — hvilke rettskilder først?
Ikke alle rettskilder egner seg like godt for digitalisering, og man kan ikke ta alt på en gang. To spørsmål må besvares før piloten: *hvilke* rettskilder, og i *hvilken rekkefølge*.

**Egnethet** følger av grensen regel/skjønn (se [`06`](06-regellaget.md)): bestemmelser med stor grad av *bundet* rettsanvendelse — klare vilkår, høyt volum, stabil tekst — er gode kandidater. Tungt skjønnsbaserte, prinsipielle eller sjelden anvendte bestemmelser egner seg dårlig som kjørbar regel (men deres *bundne* deler kan modelleres, med skjønnet som et stopp-punkt). Egnethet er derfor ikke «ja/nei» per lov, men per bestemmelse.

**Prioritering** følger byrden, ikke volumet. Tyskland har valgt ut de ~20 % av reglene som står for ~80 % av byrden for sluttbrukerne — en Pareto-tilnærming der man digitaliserer der det monner først. Det forutsetter at man *måler* byrde, og her mangler Norge et instrument.

**To indekser man ikke må forveksle.** Tysklands *byråkratiindeks* (Wagner/ESMT Berlin/buzer.de) måler **volum** av føderal lovgivning: fra 1 082 lover / ~24 775 sider i 2010 til 1 306 lover / ~39 536 sider tidlig i 2025 — rundt 60 % vekst på 15 år, drevet særlig av finans- (+88 %) og næringsregulering (+110 %). Det er noe annet enn en *byrde-/etterlevelseskostnadsindeks* (timer og kroner for å etterleve), som måles med standardkostnadsmodellen. Volum er en grov proxy; byrde er det vi egentlig vil ned på — og forfatterne understreker selv at føderal lovtekst bare er en del, siden forskrifter, delstatslov og EU-rett gjør den reelle byrden større.

**Hvorfor dette er et argument for rammeverket, ikke mot det.** Anta samme vekst i Norge. Vokser regelverket (det som skal forvaltes) raskere enn forvaltningens egen ressursbruk (ansatte/kostnader), kan forvaltningen *se* mer effektiv ut per regelenhet — samtidig som **byrden er flyttet ut** på innbygger og næringsliv, som må forstå og etterleve stadig mer. To poeng følger:

1. **Riktig suksessmål er total byrde, ikke forvaltningens kostnad.** Maskinlesbare regler (auto-sjekk, forhåndsutfylling, færre tolkningsfeil) reduserer etterlevelsesbyrden — det er gevinsten rammeverket skal hente, og den blir usynlig hvis man bare måler forvaltningens egne tall.
2. **Voksende volum gjør struktur nødvendig, ikke valgfritt.** Mange titalls prosent flere regler kan ikke forvaltes manuelt med samme kvalitet. Et strukturert kildelag og et åpent regellag er svaret på vekst, ikke et tillegg til den.

**Parkert (venter):** en gjennomgang av hver enkelt norsk lov med vurdering av digitaliseringsegnethet. Det er riktig analyse å gjøre, men den bør være byrde-vektet (Pareto) og gjøres bestemmelse for bestemmelse, ikke lov for lov — og den fortjener et eget arbeid. Et naturlig første steg er en norsk byrde-baseline (Regelrådet vurderer i dag næringslivsbyrde ex-ante for nytt regelverk, men det finnes ingen aggregert tidsserie), slik at prioriteringen hviler på tall framfor magefølelse.

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
