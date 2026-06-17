# 06 — Regellaget

*Her blir rettskilde til kjørbar regel. Dette er leddet der den nasjonale digitaliseringen faktisk treffer den enkelte avgjørelsen — og derfor der rettssikkerheten avgjøres i praksis. Dokumentet utdyper Lag 2 i [rammeverket](01-rammeverk.md), bygger på kildelaget i [`05`](05-kildelaget-og-lovprosessen.md), og forutsetter at kildelaget er autoritativt og sporbart. Er det ikke det, arver regellaget alle gjettingene ovenfra.*

## 1. Hva regellaget er — og ikke er

Regellaget er formalisert regellogikk utledet fra kildelaget, der **hver regel eksplisitt refererer til hjemmelen** den bygger på (en ELI-peker ned i Lag 1, helt til versjonert bestemmelse). Det er **ikke** en lukket motor i hver etat. Poenget med å skille laget ut er at regelen skal være et *eget, åpent, etterprøvbart artefakt* — noe en jurist, en klageinstans og en innbygger kan inspisere — ikke noe som er smeltet inn i en applikasjons kildekode og bare synlig for utviklerne.

Skillet er praktisk, ikke akademisk. Når regelen er et selvstendig artefakt med kjent hjemmel, kan den testes, versjoneres, gjenbrukes og revideres når kilden endrer seg. Når den er gjemt i kode, må den tolkes på nytt hver gang — og feil blir usynlige til de utløser en skandale.

## 2. Fra rettskilde til kjørbar regel

Dette er oversettelsessteget — det internasjonale fagfeltet kaller det *the translation gap* (se [`03`](03-kunnskapsgrunnlag.md)). En jurist skriver tekst; måneder senere koder en utvikler den; tolkningsvalg treffes underveis, langt nede i organisasjonen, og blir verken dokumentert eller etterprøvd. OsloMet-funnet i [`05`](05-kildelaget-og-lovprosessen.md) beskriver nettopp dette, og trygdeskandalen er det stående eksempelet på hva det koster.

Det som gjør regellaget særlig følsomt, er at en regel ikke avgjør én sak, men **alle framtidige saker av samme type**. Når regelverk kodes, defineres på forhånd hvordan hver enkelt sak skal behandles; man går fra enkeltsaksbehandling til massesaksbehandling. En tolkningsfeil i én regel er derfor ikke en enkeltfeil — den er en systematisk feil som forplanter seg til hver sak regelen rører ved, til noen oppdager den. Det hever kravet til at oversettelsen er eksplisitt, hjemmelssporet og testet, fra «god praksis» til en rettssikkerhetsbetingelse.

Konsekvensen for utformingen: oversettelsen fra tekst til regel må være et **dokumentert, gjennomgåbart trinn** med tydelig hjemmelssporing — ikke en bieffekt av at noen skriver kode.

### «Regel» betyr tre ulike ting

Mye av oversettelsesgapet skyldes at ett ord bærer tre betydninger gjennom kjeden, og at de tre som bruker det ikke vet at de mener forskjellige ting:

- For **juristen** er en regel en *rettsregel* — en normativ slutning fra rettskildene, som bærer hjemmel, tolkningsrom og skjønn. Den kan være vag med vilje.
- For **fageksperten/forretningssiden** er en regel en *beslutnings-/forretningsregel* — en operasjonell betingelse («hvis vilkår A og B, så utfall C»), gjerne som beslutningstabell. Den abstraherer bort den juridiske begrunnelsen og ser på utfallet.
- For **utvikleren** er en regel *kjørbar logikk* — det maskinen faktisk gjør, med datastrukturer, feilhåndtering og grensetilfeller.

Samme ord, tre artefakter, tre eiere, tre feilmodi. Når de tre antar at «regelen» er én ting, forsvinner tolkningsvalgene i sprekkene mellom dem — det er nettopp der trygdeskandalen oppstod. Kjeden adresserer dette på fire måter:

1. **Navngi de tre, aldri bare «regel».** Vokabularet skiller rettsregel, beslutningsregel og kjørbar regel som distinkte, navngitte artefakter (jf. regeltypene i [`03`](03-kunnskapsgrunnlag.md)). «Regelen sier X» er ufullstendig til man vet hvilken.
2. **Felles hjemmelsanker.** Hver representasjon bærer samme stabile peker (ELI ned i [Lag 1](05-kildelaget-og-lovprosessen.md)), slik at man kan spore fra kjørbar regel tilbake til rettsregel og rettskilde. [Lovspeilet](05-kildelaget-og-lovprosessen.md) er denne bindingen.
3. **Mellomspråk som er lesbare for to sider samtidig.** DMN er lesbart for både fagekspert og utvikler; FLINT/NRML ligger mellom jurist og resten. De fungerer som grenseobjekter der to fag deler én modell i stedet for å oversette i blinde.
4. **Tverrfaglig fra dag én (prinsipp 7).** Innsiktsfasen (jf. Politiets juridiske innsiktsarbeid i [`03`](03-kunnskapsgrunnlag.md)) tvinger jurist, fagekspert og utvikler til å bygge én delt modell *før* koden — og verifiseringsregler holder den kjørbare regelen i samsvar med rettsregelen etterpå.

Poenget er ikke å tvinge alle til å bruke ordet likt, men å gjøre oversettelsen mellom de tre til et synlig, sporbart trinn i stedet for en stilltiende antakelse.

## 3. Grensen regel/skjønn

Dette er kjernen i hele laget, og det vanskeligste. Prinsipp 4 i charteret er ufravikelig: **skjønn forblir hos mennesker der loven krever en vurdering.** Automatisering avlaster, men erstatter ikke rettsanvendelse som krever skjønn. Spørsmålet regellaget må svare på er hvor den grensen går — og hvordan den gjøres synlig i selve regelen.

**To slags grenser.** Juridisk skiller man grovt mellom *bundet* rettsanvendelse (loven gir ett riktig svar når faktum er klarlagt — egner seg for regel) og rom for *skjønn*. Skjønnet kan igjen være rettsanvendelsesskjønn (tolkning av et vagt rettslig begrep, f.eks. «særlig stor belastning») eller forvaltningsskjønn (et «kan»-rom der forvaltningen velger mellom lovlige utfall). Ingen av skjønnsformene skal automatiseres bort; de skal **synliggjøres og rutes til et menneske**.

**Besøksbidrag som arbeidseksempel** (jf. [Case A](04-norske-case.md)). I samme lov ligger begge sider: den prosentvise satsen og innkrevingsplikten er bundet regel — egner seg fullt ut for regellaget. Terskelen «særlig stor belastning fra reiselivet» og departementets godkjenning av kommunens plan er skjønn — må forbli menneskelig. En god regellags-representasjon koder det første og **markerer det andre som et stopp-punkt**, i stedet for å skjule en gjetning bak en grenseverdi.

**Stopp-punktet som arkitektur.** NAVs egen referansemodell gjør nettopp dette: et «behandlingssteg» har en inngang (henter grunnlag), et innhold (den logiske vurderingen/beregningen) og en **utgang med eksplisitt avklaringsbehov** — steget *stopper* ved behov for menneskelig skjønn, manuell vurdering eller ekstern frist. Det offentlige uttrykket for dette finnes på nav.no: regelmotoren avgjør der vilkårene er klare, og sender ellers saken til en saksbehandler, i tråd med forvaltningslovens saksbehandlingsregler. At «avklaringsbehov» er en *navngitt steg-type* og ikke en unntakshåndtering, er det vi vil løfte fram som mønster: grensen regel/skjønn blir en førsteklasses del av modellen, ikke noe som faller mellom stolene.

**Én nyanse å være presis på.** Effektiviseringsargumenter omtaler gjerne «mindre behov for skjønn» som en gevinst (f.eks. i [Alkoholfloken](04-norske-case.md), Case D). Det er riktig — men bare for *tilfeldig, ustrukturert* skjønn: variasjonen som oppstår når 300 kommuner tolker samme regel hver for seg, er ikke rettssikkerhet, den er sprik. Klare, delte regler som fjerner *den* variasjonen er likebehandling (jf. prinsipp 9). Prinsipp 4 verner noe annet: skjønnet loven *krever*. Regellaget skal redusere det første og verne det andre — og aldri forveksle dem. Alkoholfloken treffer instinktet riktig når simuleringen flagger at en kommunal dispensasjonsvei er skjønnsbasert og «kan utfordre rettssikkerheten»: den *synliggjør* hvor skjønnet bor i stedet for å regne det bort.

## 4. Regeltaksonomi i praksis

Den lagdelte modellen sier hvor en regel hører hjemme; [`01`](01-rammeverk.md) la til en akse for hvor *bredt* den gjelder (etterlevelsesmodellens tre ringer: tverrgående/felles, virksomhetsgenerelle og fagspesifikke regler). For regellaget gir det prinsipp 9: **delte regler modelleres autoritativt én gang og gjenbrukes** — forvaltningsloven, GDPR, arkivloven og eForvaltningsforskriften tolkes i dag på nytt i hver etat, hver i sin kode. Det er duplisert-tolkning løftet helt opp til fundamentet, der det koster mest for likebehandling.

NAVs «prosessregelverk» — en universell mal som gjenbrukes på tvers av ytelser i porteføljen — er en konkret instans av prinsipp 9: standardiserte, gjenbrukbare regelkomponenter framfor én tolkning per tjeneste. Det er mønsteret vi vil generalisere fra etat til forvaltning.

Innenfor laget er det dessuten nyttig å skille mellom **regeltyper** (jf. [`03`](03-kunnskapsgrunnlag.md)): interaksjonsregler, konverterings-/transformasjonsregler, juridiske regler (det egentlige rettskildegrunnlaget), forretningsregler (f.eks. uttrykt i DMN), verifiseringsregler og regelstyringsobjekter (krav, tiltak, konklusjon). Skillet betyr at «regler som kode» ikke er én ting: det avgjørende skillet for sporbarhet er mellom de *juridiske* reglene (som må peke på hjemmel) og de øvrige (som tjener utførelsen).

## 5. Standarder og verktøy

Vi trenger ikke finne opp formatene selv; flere finnes allerede (utdypet i [`03`](03-kunnskapsgrunnlag.md)):

- **DMN** (Decision Model and Notation) — OMG-standard for å modellere beslutningslogikk; bro mellom forretningsregler og utførelse.
- **OpenFisca** — åpen motor for å representere lovgivning som kjørbar kode; brukt til mikrosimulering og ex-ante differensialanalyse (LexImpact, Frankrike).
- **FLINT** — formelt språk (TNO/Nederland) for å tolke rettskilder til maskinlesbare normative rammeverk.
- **NRML** (Normalized Rule Model Language) — JSON-basert utvekslingsformat for maskinlesbare regler *(venter på primærkilde — bør verifiseres mot spesifikasjon)*.

**Rulemapping og verktøystøtte.** «Fra regelverk til behandlingssteg» kan gjøres for hånd — et regelverk dekomponert til en ordnet graf av beslutningssteg, hvert merket med hjemmel — eller med verktøy. Den tyske Rulemapping Group (SPRIND-finansiert) tilbyr en gratis «Rulemap Builder» (rulemapping.org) som representerer lov som visuelle beslutningsmodeller som er både maskinlesbare og forståelige for mennesker, med en deterministisk regelkjerne, et bibliotek for deling/gjenbruk, og LLM-er bare til å håndtere ustrukturerte data under menneske-i-løkka. Et håndtegnet flytdiagram er manuell-baseline; poenget er at *gapet det blottlegger* er nettopp det verktøystøtte fyller.

**To editorlag.** Det er lærerikt å skille editoren for *teksten* fra editoren for *regelen*. [LEOS](05-kildelaget-og-lovprosessen.md) (EUs åpne lovskrivingsverktøy) er Lag 1-editoren: strukturert lovtekst i Akoma Ntoso (AKN4EU), med versjonering, sporing av endringer, og interne referanser som oppdateres automatisk når strukturen endres. En *policy-as-code*-editor er Lag 2-analogen: der rettskilde blir kjørbar regel med hjemmelssporing. De to henger sammen — regelen i Lag 2 peker på bestemmelsen i Lag 1 — men de er ulike artefakter med ulike eiere.

**Deterministisk kjerne, KI som simulator.** Prinsipp 4 og [`03`](03-kunnskapsgrunnlag.md) trekker en hard linje: KI kan *assistere* utforming og forklaring, men den autoritative avgjørelsen må være deterministisk og sporbar — en LLM kan hallusinere. [Alkoholfloken](04-norske-case.md) (Case D) er en levende norsk demonstrasjon: en «digital tvilling» av regelverkssystemet, bygget på LLM-agenter, brukt til å *simulere* hvordan endringer slår ut — og som eksplisitt «ikke gir fasitsvar». Det er den riktige rollen. Prosjektets eget risikobilde navngir motsatsen (hallusinering, for høy tillit, at tvillingen forvitrer) — som er nøyaktig hvorfor *avgjørelsesmotoren* ikke kan være modellen. Forskning på hybride tilnærminger (XHAILe, LEXplain) hører hjemme her *(venter på primærkilde)*. Linja for regellaget er kort: KI som simulator/utforsker — ja; KI som autoritativ avgjørelsesmotor — nei.

## 6. Styring: eierskap, versjonering og lovspeilet

En regel uten eier råtner. Regellaget krever et styringsregime som svarer på: hvem eier og vedlikeholder regelen, hvordan en endring i kilden (Lag 1) forplanter seg til regelen, og hvordan endringen logges.

**Lovspeilet binder Lag 1 til Lag 2.** Schartums idé om et vedlikeholdt samsvar mellom lovbestemmelser og reglene som faktisk er programmert inn (se [`05`](05-kildelaget-og-lovprosessen.md)) er styringsmekanismen som gjør sporbarhet (prinsipp 2) operativ: når kilden endres, peker speilet på hvilke regler som må gjennomgås. Uten speilet er versjonering en intensjon; med det blir det en rutine.

**Sporbarhet som arkitektur.** NAVs oversettelse av juridiske rammer til arkitektoniske føringer viser hvordan: regelmotor med deklarativ logikk framfor hardkoding, logging av kildekodeversjon og inndata-snapshots, og uavviselige revisjonsspor (event sourcing). Den offentlige instansen er NAVs «Behandlingskatalog» (Polly), som versjonerer hver endring med tidspunkt, hvem som endret, og et snapshot av hele dataobjektet. Det er prinsipp 2 gjort til mekanisme, og det er åpent dokumentert.

**Testing er ikke valgfritt.** [Case C](04-norske-case.md) — barnehagetilskuddet som regneark med en latent formelfeil kopiert ut til ~300 kommuner — er argumentet i renform: et autoritativt, versjonert og **testet** regel-artefakt retter feilen ett sted, og gjør hver beregning sporbar til gjeldende regel. Verifiseringsregler (jf. §4) hører hjemme i selve laget, ikke i en manuell etterkontroll.

**Åpenhet som standardvalg.** At NAV forvalter over tusen prosjekter som åpen kildekode (MIT), etter retningslinjer modellert på GOV.UK, viser at åpen regellogikk er praktisk gjennomførbart i norsk forvaltning i dag — det er prinsipp 3 i praksis, ikke en utopi.

## 7. Hvorfor rettssikkerheten avgjøres her

Kildelaget gjør sporbarhet *mulig*; regellaget gjør den *virkelig*. Det er her en automatisert avgjørelse enten kan spores tilbake til en versjonert bestemmelse (prinsipp 2) — eller forsvinner inn i en udokumentert motor. Det er her grensen regel/skjønn enten er en navngitt del av modellen — eller en gjetning bak en grenseverdi. Og det er her en lovendring enten trigger en gjennomgang via lovspeilet — eller blir hengende som en stille inkonsekvens.

Dette er svaret på hull 3 i [problemanalysen](00-problemanalyse.md): den nye forvaltningsloven åpner for automatisering, men setter ingen standard for sporbarhet, etterprøvbarhet eller skillet regel/skjønn. Regellaget — åpent, hjemmelssporet, testet og versjonert, med et menneske der loven krever det — *er* den standarden.

---

*Kilder brukt i dette dokumentet: NAVs offentlige beskrivelse av automatisk saksbehandling (nav.no), Behandlingskatalogen/Polly og NAVs retningslinjer for åpen kildekode (github.com/navikt); Rulemapping Group / Rulemap Builder (rulemapping.org, SPRIND); LEOS-brukermanual v5.0.3 (Europakommisjonen, CC BY 4.0); Helsedirektoratets utredning på alkoholområdet (2025) for Alkoholfloken. Schartums lovspeil-/samsvarstankegang, jf. `05`. NAV-/Politiet-presentasjonsmateriale er brukt som bakgrunn; normative påstander er forankret i de offentlige kildene over. Punkter merket «venter på primærkilde» (NRML, XHAILe, LEXplain) skal verifiseres før de brukes normativt, jf. `CONTRIBUTING.md`.*
