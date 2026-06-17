# 05 — Kildelaget og lovprosessen

*Her begynner kjeden — lenge før noen skriver kode. Er kildelaget brutt, arver alt nedstrøms feilen. Dette dokumentet utdyper Lag 1 i [rammeverket](01-rammeverk.md) og hull 1 i [problemanalysen](00-problemanalyse.md).*

## Hva som står på spill

Et forskningsprosjekt ved OsloMet («Pålitelig digital velferdsforvaltning») har studert hvordan NAV digitaliserer lovverk. Funnet er ubehagelig konkret: når lovtekst skal «kodes», må utviklerne ofte ta valg om *hvordan loven skal forstås* — og disse valgene treffes gjerne langt nede i organisasjonen, i utviklingsteamene. Valgene avgjør om en sak behandles automatisk eller manuelt, hvor lang tid den tar, og i noen tilfeller selve utfallet. Professor Julia Köhler-Olsen kaller det en rettssikkerhetsutfordring og minner om at en forvaltning som automatiserer rettsanvendelse «først og fremst må være rettssikker». Trygdeskandalen er det stående eksempelet på hva som skjer når en feil lovforståelse får virke over tid.

Poenget for oss: dette er ikke et kodeproblem nederst i stabelen. Det er et **kildeproblem** øverst. Hvis rettskilden ikke finnes som autoritativ, strukturert og sporbar data, *må* noen gjette lenger ned — og gjettingen blir usynlig.

## 1. Slik blir en lov til — og hvor den slutter å være digital

En lov starter med en intensjon eller et innspill, og går så gjennom en lang kjede:

1. **Initiativ/utredning** — et behov, ofte et offentlig utvalg og en NOU.
2. **Høring** — forslaget sendes på høring gjennom høringsinstituttet, en bærebjelke i norsk lovgivning. Høringene publiseres digitalt (regjeringen.no / høring.no), men selve forslagene og innspillene utveksles som *tekstdokumenter* — ikke som strukturerte, maskinlesbare endringer.
3. **Proposisjon** (Prop. L) fra departementet til Stortinget.
4. **Stortingsbehandling** — komitébehandling, innstilling, første og andre gangs votering, lovvedtak.
5. **Sanksjon** i statsråd.
6. **Kunngjøring** i Norsk Lovtidend.
7. **Konsolidering** — innarbeiding av endringer i «gjeldende» tekst (gjøres i praksis av Lovdata).

Gjennom hele dette løpet er produktet og utvekslingsformatet dokumenter (Word/PDF), ikke strukturert data. Til sammenligning representerer f.eks. Storbritannia endringer som strukturerte `<effect>`-objekter (se del 3). Hos oss er en lovendring fortsatt en prosatekst som beskriver hva som skal endres.

**Lovspeil (Schartum).** I dag betyr et «lovspeil» hos Lovdata en tabell som viser hvor en gammel bestemmelse «speiles» i en ny lov (f.eks. straffeloven 1902 → 2005). Dag Wiese Schartum — som etablerte forvaltningsinformatikk ved UiO i 1994 — løfter ideen videre: det må være mulig å vise **samsvar mellom lovbestemmelser/rettskilder og reglene som faktisk er programmert inn i systemene** som treffer automatiserte vedtak. Et slikt vedlikeholdt «speil» er en forutsetning for åpen digital forvaltning og for rettssikkerhet, og henger tett sammen med hans arbeid om automatiseringsvennlig lovgivning. Tankegangen er **offentlig tilgjengelig**: *Lovgivning i et digitalt samfunn* (2025) er utgitt som CompLex 1/2025 og er fritt tilgjengelig i fulltekst, og Schartum oppsummerer hovedlinjene i en åpen Lov&Data-artikkel («Lovgivning og digitalisering», 2025). Boken behandler bl.a. *systemutvikling som lovutvikling* — under begrepet «regelvask» — der systemutvikling brukes til å avdekke uklarheter og inkonsekvenser i lovtekst. Det er translation-gap-en sett fra lovgiversiden, og lovspeilet er mekanismen som binder kildelaget til [regellaget](06-regellaget.md).

## 2. Den autoritative kilden er en PDF

Dette er kjernemissforståelsen vi må rydde i: **Lovdata oppfattes ofte som den autoritative kilden til norsk lov, men er det ikke.**

- Den rettslig autoritative versjonen av en ny lov eller forskrift er teksten slik den **kunngjøres i Norsk Lovtidend**. Norsk Lovtidend utgis av Lovdata på vegne av Justis- og beredskapsdepartementet, og selve kunngjøringen publiseres som **PDF**. (Se Lovdatas egen veiledning om lovtidend og kunngjøring.)
- Lovdata gjør deretter en **strukturering og konsolidering** i sitt eget proprietære format — en verdifull tjeneste, men en *sekundær gjengivelse* uten formell garanti for at struktureringen er korrekt, og ikke åpne strukturerte data. Lovdata er dessuten en **privat stiftelse**.
- **Gyldendal Rettsdata** gjør i praksis noe av det samme på kommersiell basis.

Resultatet er paradoksalt: det autoritative artefaktet er **ustrukturert** (en PDF), mens det strukturerte artefaktet er **uoffisielt og proprietært**. For en digital rettsstat er dette bokstavelig talt baklengs. At tilgangen til rettskilder som åpne data også har vært rettslig omstridt (Lovdata mot rettspraksis.no, 2018–2019) understreker hvor sårbart fundamentet er.

## 3. Forslag: snu avhengigheten

To grep, som forsterker hverandre:

### 3.1 Digitalt og strukturert fra starten
Rettskilder bør produseres som strukturert, maskinlesbar data *gjennom selve lovprosessen* — ikke struktureres i etterkant av en tredjepart. Det betyr tverrfaglige team (jurist, utvikler, tjenestedesigner) og forfatterverktøy for lovtekst (jf. EUs åpne LEOS), med Schartums samsvars-/lovspeil-tankegang innebygd. Den strukturerte representasjonen blir **primær**; den lesbare PDF-en blir et *avledet* format. Da blir konsolidering deterministisk og etterprøvbar i stedet for et privat tolkningsarbeid.

### 3.2 Felles åpen standard, eid og publisert av hver kilde-eier
Hver eier av rettskilder (Stortinget, departementer, direktorater, kommuner) bør være forpliktet til å publisere i et **standardisert, åpent, maskinlesbart format med stabile identifikatorer** (ELI). Vi trenger ikke finne opp dette selv — flere har gått foran:

- **Storbritannia:** legislation.gov.uk publiserer lovverk som XML (CLML, på vei mot **Akoma Ntoso**), eid og vedlikeholdt av The National Archives. Alt eksponeres via et åpent API (`/data.akn`, `/data.xml`, `/data.html`, `/data.pdf`), med massenedlasting, **endringer som strukturerte `<effect>`-data**, og historiske «point-in-time»-versjoner. PDF er bare ett av mange avledede formater.
- **EU:** Akoma Ntoso / LegalDocML, Formex (Publications Office) og **ELI** for stabil identifikasjon.
- **USA:** USLM (United States Legislative Markup) for U.S. Code og kunngjøringer.

Modellen er den samme overalt: **strukturert data er grunnformatet, eid av det offentlige; PDF er avledet.** Det er den inverteringen Norge mangler.

### 3.3 Strukturert høring — gjør innspill og endringer maskinlesbare
Høringsinstituttet (steg 2 over) er en bærebjelke i norsk lovgivning, men i dag utveksles forslag og innspill som tekstdokumenter, ikke som strukturerte endringer knyttet til den bestemmelsen de gjelder. Det er ikke en ny erkjennelse: Schartum prototypet et **digitalt høringssystem** allerede rundt 2007, der høringsinstanser kunne kommentere et lovforslag ned på paragrafnivå, se gjeldende bestemmelse mot forslaget side om side (prototypen hadde til og med en egen «Lovspeil»-fane), og der departementet kunne sortere uttalelsene strukturert. Ideen er altså verken urealistisk eller udokumentert — den er ~18 år gammel.

Internasjonalt er dette satt i drift: i EUs åpne lovskrivingsverktøy [LEOS](06-regellaget.md) håndterer Kommisjonens instans (EdiT) nettopp kommentarer og endringsforslag i interservice-høringen som *strukturerte* artefakter ved siden av selve lovteksten, ikke som vedlegg i prosa.

Likevel er kjeden hos oss fortsatt ikke digital ende-til-ende. [Alkoholfloken](04-norske-case.md) (Case D) gir det konkrete bildet: en saksbehandler beskriver å sende høring digitalt til en annen etat, som svarer i vanlig postgang. Avstanden fra Schartums prototype til denne hverdagen er målet på hvor mye som gjenstår — og et strukturert kildelag med strukturert høring er det som lukker den.

## 4. Hvorfor dette er fundamentet

Uten et autoritativt, strukturert kildelag har regellaget ([Lag 2](01-rammeverk.md)) ingen pålitelig grunn å stå på. Da skjer nettopp det NAV-rapporten beskriver: tolkningsvalg skyves ned til utviklerne og blir usynlige. Og det skjer det [barnehage-eksempelet](04-norske-case.md) viser — at samme regel kopieres ut i regneark med en latent formelfeil. Et åpent, eid og versjonert kildelag, med et vedlikeholdt lovspeil mot reglene, er det som gjør sporbarhet (prinsipp 2) mulig i det hele tatt.

---

*Kilder brukt i dette dokumentet: OsloMet-rapporten via digi.no (2026); Lovdatas veiledning om Lovtidend/kunngjøring; legislation.gov.uk «Technology Choices» og The National Archives' «Legislation Data Access, Formats & Completeness»; Schartum, *Lovgivning i et digitalt samfunn* (CompLex 1/2025, fritt tilgjengelig) og Lov&Data-artikkelen «Lovgivning og digitalisering» (2025); Schartums e-høringsprototype (folk.uio.no/oddrk/eHoering), dokumentert bl.a. i en DRI3001-bacheloroppgave (UiO, 2008); LEOS-brukermanual v5.0.3 (Europakommisjonen, CC BY 4.0); Helsedirektoratets utredning på alkoholområdet (2025) for høringseksempelet. Detaljer merket «venter på primærkilde» skal verifiseres før de brukes normativt.*
