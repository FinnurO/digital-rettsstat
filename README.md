# Digital rettsstat

**Et rammeverk og veikart for de grunnleggende kapabilitetene, systemene og standardene Norge mangler for hvordan vi lager regelverk og leverer offentlige tjenester — med rettssikkerhet, sporbarhet og åpne standarder i kjernen.**

> **Status:** tidlig utkast (v0). Dette er et levende diskusjonsgrunnlag, ikke et ferdig standardforslag. Arbeidstittel — navnet kan endres (alternativer: `rettsinfrastruktur`, `regelverk-som-infrastruktur`, `åpen-rettsstat`).

---

## Problemet i én setning

Norge har verdensledende enkeltdeler — Lovdata, ID-porten, Altinn, Folkeregisteret, dyktige fagmiljøer i rettsinformatikk og forvaltningsinformatikk — men mangler **bindeleddet**: en autoritativ, maskinlesbar og sporbar kjede fra rettskilde → regel → data → tjeneste, styrt av forpliktende standarder og et tydelig eierskap.

Resultatet er at den nasjonale digitaliseringsstrategiens ambisjon (*«verdens mest digitaliserte land» innen 2030*) hviler på virkemidler som i dag i hovedsak er **veiledende, ikke forpliktende**, og at automatisert saksbehandling vokser frem etat for etat uten felles krav til etterprøvbarhet. Det er både et effektivitets- og et rettssikkerhetsproblem.

## Hva dette repoet inneholder

| Dokument | Innhold |
|---|---|
| [`docs/00-problemanalyse.md`](docs/00-problemanalyse.md) | Hva som faktisk mangler, forankret i dagens norske situasjon |
| [`docs/01-rammeverk.md`](docs/01-rammeverk.md) | Den lagdelte modellen + prinsippene (charteret) |
| [`docs/02-veikart.md`](docs/02-veikart.md) | Plan i faser, fra problemforankring til skalering |
| [`docs/03-kunnskapsgrunnlag.md`](docs/03-kunnskapsgrunnlag.md) | Rules as Code / Better Rules-syntese, koblet til norsk praksis |
| [`docs/04-norske-case.md`](docs/04-norske-case.md) | Tre norske case: besøksbidrag, fritidsbolig-skatt, barnehagetilskudd |
| [`docs/05-kildelaget-og-lovprosessen.md`](docs/05-kildelaget-og-lovprosessen.md) | Hvordan en lov blir til, hvorfor den ikke er digital, og forslag til kildelag |
| [`docs/06-regellaget.md`](docs/06-regellaget.md) | Hvordan rettskilde blir kjørbar regel, og hvor grensen regel/skjønn trekkes |
| [`LISENS.md`](LISENS.md) | Anbefaling for lisensiering av tekst og kode |

## Sentrale referansepunkter

Rammeverket bygger videre på — og forsøker å tette hullene i — eksisterende norsk arbeid:

- **Fremtidens digitale Norge** – Nasjonal digitaliseringsstrategi 2024–2030
- **Lov 20. juni 2025 nr. 81 (ny forvaltningslov)** — vedtatt, ikke trådt i kraft; åpner for automatisert saksbehandling, men er teknologinøytral
- **Digdirs veileder for digitaliseringsvennlig regelverk** (2021–) — skiller mellom *digitaliseringsvennlig* og *automatiseringsvennlig* regelverk
- **Sammenhengende tjenester / 7 livshendelser** og medfinansieringsordningen
- Internasjonale standarder: **ELI** (rettsakt-identifikator), **ECLI** (rettsavgjørelser), **Akoma Ntoso / LegalDocML**, **Once-Only-prinsippet**, **Interoperable Europe Act**

## Bidra

Se [`docs/02-veikart.md`](docs/02-veikart.md) for hva som trengs nå. Diskusjoner tas i Issues; endringer via pull requests.

## Lisens

Dokumentasjon foreslås under CC BY 4.0 / NLOD; eventuell kode under EUPL 1.2 eller MIT. Se [`LISENS.md`](LISENS.md).
