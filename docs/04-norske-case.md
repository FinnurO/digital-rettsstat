# 04 — Norske case

To norske case forankrer rammeverket empirisk: ett **framoverlent** (besøksbidrag — gjør det riktig nå) og ett **advarende** (fritidsbolig-verdsettelsen — kostnaden ved å la være). Sammen utgjør de argumentet for ex-ante regelmodellering som standard.

---

## Case A — Lov om besøksbidrag: kandidat for Fase 1-pilot

**Verifiserte fakta** (LOV-2025-06-20-104, besøksbidragsloven):

- Prop. 96 L (2024–2025), Innst. 452 L, Lovvedtak 110; behandlet i Stortinget 5. og 10. juni 2025, sanksjonert 20. juni 2025. Fremmet av Nærings- og fiskeridepartementet (NFD).
- **Trer i kraft 1. juli 2026**; kommunene ventes å kunne kreve inn besøksbidrag i første halvår 2027.
- Avgiften er et prosentvist påslag på tre prosent av overnattingsvederlaget (eks. mva.). Gjelder for Svalbard med enkelte unntak; egen hjemmel for forskrift om cruise og om Longyearbyen.
- **Forskrift om overnattingsavgift er fortsatt under arbeid** og skal tre i kraft samtidig med loven.

**Hvorfor den egner seg som pilot:**

1. **Regel + skjønn i samme lov.** Klar sats og innkrevingsplikt (regel) side om side med terskelen «særlig stor belastning fra reiselivet» og departementets godkjenning av kommunens plan (skjønn) — ideelt for å teste grensen i regellaget.
2. **«Leaky borders» er innebygd.** Avgiften følger kommunegrensen, mens fellesgodene og finansieringsbehovet ikke gjør det. Det er duplisert-tolkning-problemet i miniatyr: uten felles regelinfrastruktur må hver kommune og hvert bookingsystem tolke loven hver for seg.
3. **Mange aktører implementerer samme regel.** Kommuner, NFD, kommersielle overnattingssteder og plattformer (Airbnb, FINN.no m.fl.) pålegges roller — det roper etter én delt, autoritativ regel framfor N private tolkninger.
4. **Tidsvinduet.** Loven er vedtatt, men ikke i kraft, og forskriften skrives nå. Det er den beste muligheten til å demonstrere digital-ready/RaC på ekte norsk regelverk *mens* det utformes.

> Din «Strategisk Blåkopi» for besøksbidrag (#493) er det mest verdifulle dokumentet å laste opp her — den kobler pilotforslaget til din egen strategiske tenkning.

---

## Case B — Ny verdsettelsesmodell for fritidsboliger: kostnaden ved status quo

**Verifiserte fakta:**

- Forslag til nytt verdsettelsessystem for fritidsboliger i formuesskatten ble sendt på høring i 2021 (Finansdepartementet, saksnr. 21/3144). Modellen skulle anslå verdi ut fra faktorer som areal, byggeår og beliggenhet — etter mønster fra boligmodellen.
- Innføring ble gjentatte ganger utsatt: opprinnelig 2024, så 2026, deretter «mulig innføring fra 2027».
- Selve takseringsmodellen ble utviklet av konsulentselskapet **PwC**, med tilrettelegging i **Skatteetaten, Kartverket og SSB** (regelverk, forvaltningsprosesser og IT-system). Arbeidet gikk over flere år og flere etater.
- Kritikken var omfattende: mangelfull konsekvensutredning, fare for kraftige og ujevne utslag (særlig for eldre fritidsboliger med lav likningsverdi og eiere med lav inntekt), og risiko for dobbel skjerping gjennom både formues- og eiendomsskatt.
- **Utfall:** I april 2026 besluttet Finansdepartementet å ikke gå videre med modellen, og ba Skatteetaten avslutte arbeidet og ikke pådra kostnader utover avviklingen.

**RaC-lærdommen.** Dette er nettopp bruksområdet RaC-litteraturen kaller *ex-ante-simulering* og *differensialanalyse (ny vs. gammel lovgivning)* — kjernen i verktøy som OpenFisca/LexImpact. Hadde verdsettelsesmodellen vært uttrykt som kjørbare regler tidlig, kunne de fordelingsmessige konsekvensene vært simulert raskt, billig og transparent *før* man bandt opp flere års arbeid hos fire aktører og et konsulenthus. Da ville beslutningen blitt bedre uansett retning: enten ved å justere modellen, eller ved å forkaste den langt tidligere og billigere.

**Forbehold.** Forkastelsen var også politisk, ikke bare analytisk. RaC ville ikke avgjort utfallet — men det ville gjort konsekvensene synlige tidlig og til en brøkdel av kostnaden. Det er poenget.

Knytter til: hull 1 og 3 ([problemanalysen](00-problemanalyse.md)), prinsippene om sporbarhet og transparens ([rammeverket](01-rammeverk.md)), og ex-ante-pilaren i [kunnskapsgrunnlaget](03-kunnskapsgrunnlag.md).

---

## Case C — Tilskudd til private barnehager: regelen som regneark

**Verifiserte fakta:** KS og PBL (Private Barnehagers Landsforbund) tilbyr en veileder med tilhørende **regnearkmodell** for kommunenes beregning av tilskudd til private barnehager, ment for å gjøre beregningen etterprøvbar og i tråd med regelverket. Modellen oppdateres i versjoner — og en tidligere utgave hadde en **formelfeil** i selvkostberegningen (arbeidsgiveravgift av pensjon havnet feil i beregningsgrunnlaget).

**RaC-lærdommen.** Her er regelen i praksis et Excel-ark som distribueres til ~300 kommuner, som hver kjører sin egen kopi. Det er duplisert-tolkning-problemet i renform: én latent formelfeil forplanter seg til alle som bruker arket, beregningene blir vanskelige å etterprøve på tvers, og tilskuddstvister mellom kommuner og private barnehager er en gjenganger. Som ett autoritativt, versjonert og testet regel-artefakt (regellaget) ville feilen vært rettet ett sted, og hver beregning vært sporbar til gjeldende regel. (UDI-presentasjonen trekker selv frem nettopp denne veilederen som et Excel-eksempel.)

Knytter til: hull 1 og 5, og prinsippene om sporbarhet og likebehandling.

---

## Hva de tre sammen viser

Besøksbidrag er **muligheten** — et levende lovarbeid der vi kan vise digital-ready regelverk i praksis. Fritidsbolig-modellen er **kostnaden ved å la være** — dyr, sen og ugjennomsiktig manuell konsekvensvurdering som likevel kollapser. Barnehagetilskuddet er **dagens nødløsning** — regler som regneark, kopiert og feilbeheftet. Til sammen er de et konkret, norsk argument for å gjøre strukturerte, autoritative regler og ex-ante regelmodellering til en standard del av regelverksarbeidet, slik [veikartet](02-veikart.md) foreslår.
