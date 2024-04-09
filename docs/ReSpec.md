# Inleiding ReSpec

Binnen Geonovum gebruiken we ReSpec voor het maken van standaarden. ReSpec maakt
gebruik van input bestanden om HTML te genereren. Deze inputbestanden (de
content) wordt gemaakt in het Markdown formaat. Deze Markdown bestanden kunnen
worden aangemaakt met text editor. GitHub wordt gebruikt als de 'repository'
waarin alle bestanden die bij een standaard horen, beheerd worden.

Deze handleiding beschrijft hoe je een GitHub Account maakt, hoe je GitHub
Desktop Client installeert en gebruikt, hoe je een Respec mappenstructuur
opbouwt, welke bestanden er nodig zijn voor een standaard, en hoe je de
verschillende versies van een standaard genereert. Ook wordt uitgelegd hoe je de
Markdown plugin in Microsoft Word installeert en gebruikt.

ReSpec is een tool van W3C die het schrijven van specifications makkelijker
maakt. ReSpec zorgt voor een uniforme styling in het document, onderhoudt
referenties en verwijzingen naar andere documentatie, verzorgt de inhoudsopgave,
zorgt voor links naar vorige en meest recente versies, en heeft een integratie
met Github issues.

Geonovum gebruikt een fork van ReSpec die door Logius beheerd wordt. Dit
document bevat een globale instructie over hoe snel aan de start te gaan. Meer
documentatie is op andere plaatsen te vinden:

-   Er is een gedetailleerde (Engelstalige)
    [gebruikershandleiding](https://github.com/w3c/respec/wiki/ReSpec-Editor's-Guide)
    beschikbaar.
-   Er is ook een
    [ontwikkelaarshandleiding](https://github.com/w3c/respec/wiki/Developers-Guide)
    te vinden.
-   De Geonovum [wiki over ReSpec](https://github.com/Geonovum/respec/wiki) is
    een fork van de w3c ReSpec met aanpassingen voor Geonovum. Deze is
    achterhaald omdat we nu van de Logius Respec gebruik maken. (TODO aanpassen)

## Een nieuwe document maken

ReSpec documenten worden beheerd in een [GitHub](/GitHub) repository. Als je een
nieuw ReSpec document wilt maken gebruik dan de
[Geonovum ReSpec template](https://github.com/Geonovum/NL-ReSpec-GN-template)
als startpunt en druk op de 'Use this template' knop om een nieuw repository aan
te maken.

Zoek in dit repository op de tekst 'TODO' om de plaatsen te vinden waar
aanpassen van de template vereist is.

## De URL van een publicatie op docs.geonovum.nl

ReSpec documenten worden gepubliceerd op
[docs.geostandaarden.nl](https://docs.geostandaarden.nl). Iedere gepubliceerde
versie van een document heeft een eigen URL. Voor de laatst gepubliceerde versie
is een aparte URL.

De URL van iedere publicatie wordt als volgt bepaald:

```text
https://docs.geostandaarden.nl/[pubdomain]/[specStatus]-[spectype]-[shortName]-[publishDate]/
```

De laatst gepubliceerde versie is OOK te vinden op:

```text
https://docs.geostandaarden.nl/[pubdomain]/[shortName]/
```

De namen van de variabelen staan verderop uitgelegd.

## De mapindeling van een ReSpec repository

Dit levert een nieuw repository op met de onderstaande mappenstructuur.

| hoofdmap | map        | file      | omschrijving                                           |
| -------- | ---------- | --------- | ------------------------------------------------------ |
| Hoofdmap |            |           | naam van de hoofdmap                                   |
|          | media      |           | Map met mediabestanden                                 |
|          |            | Style.css | File met vaste naam, bevat de styling van het document |
|          |            | \*.png    | Afbeeldingsbestanden                                   |
|          | index.html |           | File met de vaste naam `Index.html`                    |
|          | js         |           |                                                        |
|          |            | config.js | File met de vaste naam `config.js`                     |
|          | \*md       |           | Tekstbestanden (Markdown) die de content bevatten      |

Hieronder staat een voorbeeld van zo’n mappenstructuur.

![media/image22.png](media/image22.png)

## Het bestand 'index.html'

Het bestand index.html zorgt ervoor dat het ReSpec document automatisch wordt
geladen in de browser. Bij het laden wordt ook automatisch de
geonovum-ReSpec-code geladen en uitgevoerd. Deze code zorgt ervoor dat het
document zijn standaard layout krijgt.

Het bestand 'index.html' heeft een vaste indeling. Hieronder de structuur uit de
template:

```html
<!DOCTYPE html>
<html lang="nl">
    <head>
        <meta content="text/html; charset=utf-8" http-equiv="content-type" />
        <meta
            name="viewport"
            content="width=device-width, initial-scale=1, shrink-to-fit=no"
        />
        <script
            src="https://cdn.jsdelivr.net/gh/digitalbazaar/respec-mermaid@1.0.1/dist/main.js"
            class="remove"
        ></script>
        <script
            src="https://tools.geostandaarden.nl/respec/config/geonovum-config.js"
            class="remove"
        ></script>
        <script src="js/config.js" class="remove"></script>
        <script class="remove">
            respecConfig = { ...organisationConfig, ...respecConfig };
        </script>
        <script>
            document.title = respecConfig.title;
        </script>
        <title>TODO: Vul hier de titel in</title>
        <link
            rel="shortcut icon"
            type="image/x-icon"
            href="https://tools.geostandaarden.nl/respec/style/logos/Geonovum.ico"
        />
        <script
            src="https://gitdocumentatie.logius.nl/publicatie/respec/builds/respec-nlgov.js"
            class="remove"
            async
        ></script>
    </head>

    <body>
        <section
            id="abstract"
            data-include-format="markdown"
            data-include="abstract.md"
        ></section>
        <section id="sotd"></section>
        <!-- Wordt automatisch gevuld -->

        <!-- TODO: voeg hier je eigen hoofdstukken toe -->
        <section
            data-include-format="markdown"
            data-include="ch01.md"
            class="informative"
        ></section>
        <section
            data-include-format="markdown"
            data-include="ch02.md"
        ></section>
        <section
            data-include-format="markdown"
            data-include="mermaid.md"
        ></section>

        <section id="conformance"></section>
        <section id="tof"></section>
        <section id="index"></section>
    </body>
</html>
```

In de HTML-header wordt de js-ReSpec bibliotheek geladen. Het enige dat in de
header mag worden aangepast is de title (tussen \<title\> en \</title\>. Andere
aanpassingen die nodig zijn in de header mogen alleen worden gedaan in overleg
met de ReSpec beheerders. Een overzicht van de ReSpec beheerders staat in
Hoofdstuk 6

In de HTML-Body geldt _vrijheid in gebondenheid_ De `<div>` en/of `<section>`
regels mogen worden gekopieerd en toegevoegd. Wel belangrijk om de structuur
over te nemen, dus als volgt:

```
<div id='H00' data-format='Markdown' data-include="ToCoVo.md"></div>

<section id='H01' data-format='Markdown' data-include="H1-Inleiding.md"\>\<h2\>Inleiding\</h2\>\</section\>
```

Een `<div>` is een sectie plus bijbehorend document, dat niet in de
inhoudsopgave terechtkomt. Deze gebruik je bijvoorbeeld voor een Toelichting,
een Colofon of een Voorwoord.

Een `<section>` komt wél in de inhoudsopgave terecht. Deze heeft daarom behalve
de data-include van het document, ook (verplicht!) een `<h2>` tag. De tekst
tussen `<h2>` en `</h2>` komt in de inhoudsopgave te staan.

## Het bestand 'config.js'

In config.js wordt een stuurvariabele voor ReSpec gevuld. De waarden in deze
variabele worden door ReSpec gebruikt om de layout te bepalen, en bevatten een
aantal document-eigenschappen.

### SpecStatus

De SpecStatus in de configuratie geeft de keuze uit 4 waarden, deze waarden zijn
vastgesteld, en mogen niet zomaar uitgebreid of aangepast worden. Elke status
hoort bij een formele fase van een ReSpec document. Zie ook de Geonovum ReSpec
[wiki](https://github.com/Geonovum/respec/wiki).

-   _GN-WV, Werkversie_: Dit is de versie van het document waaraan wordt
    gewerkt. Deze versie is continu 'under-construction'.
-   _GN-CV, Consultatieversie_: Dit is een 'snapshot' van de versie die 'in
    consultatie' wordt gezet. Aan deze versie wordt niks meer gedaan totdat de
    consultatie is afgelopen. Daarna worden alle op en aanmerkingen uit de
    consultatieronde verwerkt.
-   _GN-VV, Vaststellingsversie_: Dit is een 'snapshot' van de versie na het
    verwerken van de op en aanmerkingen uit de consultatieronde is ontstaan.
    Deze versie wordt aangeboden aan de programma-raad van Geonovum, om te
    wordern 'vastgesteld'.
-   _GN-DEF, Definitieve versie_: Dit is de definitieve versie van het document,
    zoals vastgesteld door de programma-raad. Van deze versie wordt opnieuw een
    'snapshot' gemaakt in ReSpec. Het resultaat van die snapshot wordt op
    <a href='http://docs.geonovum.nl' target='_blank'>http://docs.geonovum.nl</a>
    neergezet.

### SpecType

Het SpecType in de configuratie is een vaste lijst met waarden, deze waarden
zijn vastgesteld, en mogen niet zonder overleg met de Technische ReSpec
beheerders uitgebreid of aangepast worden.

Onderstaande beschrijvingen komen uit het generiek
beheerplan<span class='noot'>[5]<span class='noottekst'> Zie:
https://www.geonovum.nl/uploads/documents/Geonovum%20GENERIEK%20Beheerplan%20geo-standaarden%20v1.1.pdf
<br/></span></span>.

- **NO** Norm: Een norm is bij een officieel standaardisatie instituut
    ondergebracht en bevat bindende afspraken. Naast het gebruik van normen is
    NEN 3610 de enige norm waar Geonovum een inhoudelijke verantwoordelijkheid
    heeft. Het formele beheer en beslissingen worden genomen in de NEN
    normcommissie 351 240 waar Geonovum de voorzitter van is.

- **ST** Standaard: Een document met (bindende) afspraken.

- **IM** Informatiemodel: Een standaard waarbij door de term informatiemodel
    te hanteren wordt aangegeven dat het een abstractie (het model) vormt van de
    werkelijkheid zoals beschreven binnen een bepaalde sector/domein.
    Informatiemodellen zijn een semantische invulling van normen voor sectoren
    zoals ruimtelijke ordening, kabels en leidingen, water, etc..

- **PR** Praktijkrichtlijn: Praktijkrichtlijnen zijn producten die informatie
    geven, vaak met een technisch karakter, die nodig is voor het toepassen van
    standaarden. Een praktijkrichtlijn hoort altijd bij een standaard/norm.

- **HR** Handreiking: Op zichzelf staande documentatie dat als doel heeft een
    hulpmiddel te zijn, niet verplichtend maar ondersteunend.

- **WA** Werkafspraak: Legt uit hoe wetgeving moet worden toegepast bij
    onduidelijkheden, discrepanties of fouten in de standaarden.

- **BD** Beheerdocumentatie: Documentatie met betrekking tot het beheerproces
    van de standaard. Deze documentatie betreft niet een standaard of onderdeel
    daarvan, zoals een handreiking of werkafspraak.

- **AL** Algemeen: Op zichzelf staande algemene documentatie over standaarden.
    De documentatie betreft niet een specifieke standaard of onderdeel daarvan,
    het is ook geen beheerdocumentatie van een specifieke standaard.

## pubDomain

pubDomain bepaalt bij publicatie een deel van de URL waarop het document wordt
gepubliceerd. Het zorgt voor een groepering van de documenten op
docs.geostandaarden.nl Omdat je de URL van gepubliceerde documenten niet wilt
veranderen is moet je hier goed over nadenken en alleen in overleg nieuwe
toevoegen.

De actuele lijst van pubDomains staat in de tabel hieronder. De herkomst van
deze lijst is als volgt:

1. Lijst op github :
   [respec-utils](https://github.com/Geonovum/respec-utils/blob/master/src/autodeploy/config/pubDomainList.json).
2. docs.geostandaarden.nl.
3. register.geostandaarden.nl.

Naamgevinsregels voor pubDomain:

- Lowercase
- Geen spaties

| Pubdomain      | Omschrijving                                             | Herkomst                   | status                    | GitHub Team                                                   | Beslissing                              |
| -------------- | -------------------------------------------------------- | -------------------------- | ------------------------- | ------------------------------------------------------------- | --------------------------------------- |
| 3dbv           | 3D basisvoorziening                                      | docs.geostandaarden.nl     | inactief (gemigreerd)     |                                                               | mag niet meer gebruikt worden           |
| api            | Kennisplatform APIs                                      | respec utils               |                           | [API team](https://github.com/orgs/Geonovum/teams/api-team)   | OK                                      |
| basisgeometrie | Informatiemodel Basisgeometrie                           | register.geostandaarden.nl | zit op docs bij nen3610   |                                                               | niet gebruiken eigenlijk xsd redirecten |
| bgt            | Basisregistratie grootschalige topografie                | docs.geostandaarden.nl     |                           | [BGT team](https://github.com/orgs/Geonovum/teams/bgt-team)   | Arnoud vragen                           |
| brt            | Informatiemodellen Basisregistratie Topografie           | register.geostandaarden.nl |                           | [BRT team](https://github.com/orgs/Geonovum/teams/brt-team)   | OK                                      |
| crs            | Coördinaatreferentiesystemen                             | docs.geostandaarden.nl     |                           | [CRS team](https://github.com/orgs/Geonovum/teams/crs-team)   | OK                                      |
| cvgg           | Informatiemodel Geluid                                   | docs.geostandaarden.nl     | duplicaat van img         |                                                               | OK                                      |
| disgeo         | DisGeo                                                   | respec utils               |                           |                                                               | OK                                      |
| dsgo           | Digitaal Stelsel Gebouwde Omgeving                       | docs.geostandaarden.nl     |                           |                                                               | OK (rare uri)                           |
| dso            | Digitaal Stelsel Omgevingswet                            | respec utils               | duplicaten: tpod imow ow  | [DSO team](https://github.com/orgs/Geonovum/teams/dso-team)   | OK                                      |
| eu             |                                                          | docs.geostandaarden.nl     |                           | [EU team](https://github.com/orgs/Geonovum/teams/eu-team)     | OK (rare uri en werkversie weg)         |
| g4w            |                                                          | docs.geostandaarden.nl     |                           |                                                               | groeperen?                              |
| gbd            |                                                          | docs.geostandaarden.nl     |                           |                                                               | groeperen?                              |
| geobag         |                                                          | docs.geostandaarden.nl     |                           |                                                               | OK                                      |
| gsw            |                                                          | docs.geostandaarden.nl     |                           |                                                               | groeperen?                              |
| imaer          | Informatiemodel AERIUS                                   | register.geostandaarden.nl |                           |                                                               | OK                                      |
| imev           | Informatiemodel Externe Veiligheid                       | docs.geostandaarden.nl     |                           | [IMEV team](https://github.com/orgs/Geonovum/teams/api-team)  | OK                                      |
| img            | Informatiemodel Geluid                                   | respec utils               | duplicaat: cvgg           | [IMG team](https://github.com/orgs/Geonovum/teams/img-team)   | redirecten naar cvgg                    |
| imgeo          | Informatiemodel Grootschalige Geografie                  | docs.geostandaarden.nl     |                           |                                                               | Arnoud vragen                           |
| imka           | Informatiemodel Klimaatadaptatie                         | docs.geostandaarden.nl     |                           |                                                               | OK                                      |
| imkad          | Informatiemodel Kadaster                                 | register.geostandaarden.nl |                           | [IMKA team](https://github.com/orgs/Geonovum/teams/imka-team) | OK                                      |
| imkl           | Informatiemodel Kabels en Leidingen                      | register.geostandaarden.nl | duplicaat: kl             | [IMKL team](https://github.com/orgs/Geonovum/teams/imkl-team) | Zou kl moeten worden                    |
| imle           |                                                          | docs.geostandaarden.nl     |                           |                                                               | OK (niet netjes gepubliceerd)           |
| imro           | Informatiemodel Ruimtelijke Ordening                     | register.geostandaarden.nl | duplicaat: ro             |                                                               | liefst naar RO                          |
| imow           | Informatiemodel Omgevingswet                             | register.geostandaarden.nl | duplicaten: tpod ow dso   |                                                               | liefst weg                              |
| kl             | IMKL                                                     | respec utils               | duplicaat: imkl           |                                                               | OK                                      |
| md             | Metadata                                                 | respec utils               | duplicaat: metadata       |                                                               | OK                                      |
| mim            | Metamodel Informatie Modellering (MIM                    | respec utils               |                           |                                                               | OK                                      |
| metadata       | Nederlandse metadata profielen voor datasets en services | register.geostandaarden.nl | duplicaat: md             |                                                               | verplaatsen naar md??                   |
| nen3610        | NEN3610-Linkeddata                                       | respec utils               |                           |                                                               | OK                                      |
| ngii           |                                                          | docs.geostandaarden.nl     |                           |                                                               | OK                                      |
| oov            |                                                          | docs.geostandaarden.nl     |                           |                                                               | OK                                      |
| ow             | Standaarden omgevingswet                                 | respec utils               | duplicaten: tpod imow dso |                                                               | OK                                      |
| ro             | RO Standaarden                                           | respec utils               | duplicaat: imro           |                                                               | OK                                      |
| rwgs           | Raamwerk van Geo-standaarden                             | respec utils               |                           |                                                               | groeperen?                              |
| serv           | Services                                                 | respec utils               |                           |                                                               | groeperen?                              |
| tpod           | Toepassingsprofiel omgevingsdocumenten                   | respec utils               | duplicaten: ow imow dso   |                                                               | OK                                      |
| vg             | Informatiemodel Vastgoedgebruik                          | respec utils               |                           |                                                               | OK                                      |
| visu           | Visualisatie                                             | respec utils               |                           |                                                               | groeperen?                              |
| vtm            |                                                          | docs.geostandaarden.nl     | is eigenlijk metadata     |                                                               | verhuizen naar MD                       |
| wp             | Whitepaper Geostandaarden                                | respec utils               | ook een raar pubdomain    |                                                               | verhuizen naar ngii                     |

## LocalBiblio

In de localBiblio variabele worden Referenties naar andere documenten gezet.
Voordat je hier citaten toevoegt, loont het de moeite om eerst in de
[https://www.specref.org/](SpecRef) van ReSpec zelf te kijken. Pas als je een
verwijzing niet vindt in SpecRef voeg je hem hier toe!

Verwijzen naar een bibliografieelement gebeurt als volgt `[[ID]]`. De dubbele
haakjes zorgen ervoor dat er blokhaken om de verwijzing staan in de tekst. Je
kunt ook aangeven dat een verwijzing normatief is door er een uitroepteken voor
te zetten `[[!ID]]`

## Voorbeeld config.js

```
let respecConfig = {
  useLogo: true,
  useLabel: true,
  // title is verplicht! Neem hier de titel van het document op ----------------------
  title: "[Neem titel op in config.js]",
  //-- specStatus is verplicht! (activeer 1 van de volgende) --------------------------
  specStatus: "wv",                   // Werkversie

  //-- specType is verplicht bij alle andere dan BASIS ---------------------------------
  specType: "HR",                     // HandReiking

  //-- pubDomain is verplicht! (komt in de URL) -------------------------------------
  pubDomain: "TODO",
  //-- license: voor de geldende gebruiksvoorwaarden. Default is cc-by.
  //licence: "cc-by-nd",            // bronvermelding, geen afgeleide werken (default)
  //licence: "cc0",                 // Public Domain Dedication
  licence: "cc-by",                 // Attribution, met bronvermelding
  //-- shortName is verplicht! (komt in de URL: kies logische afkorting)--------------
  shortName: "NL-ReSpec-GN-template",
  //-- publishDate is verplicht -------------------------------------------------------
  //-- NB: in de werkversie uitzetten, want dan pakt Respec de pushdate ---------------
  //publishDate: "2023-03-28",
  //eventueel is het mogelijk een versienummer mee te geven, maar bij Geonovum werken we gewoonlijk alleen met datum als onderdeel van de permanente URI.
  //publishVersion: "0.0.2",
  //previousVersion: "0.0.1",
  //-- Voor dit blok geldt: alleen als er eerdere versies zijn en altijd beiden aan/uit!
  //previousPublishDate: "2014-05-01",
  //previousMaturity: "CV",
  //-- de namen van de Editor(s) / Redacteur(en)---------------------------------------
  //-- vul in: per Editor: name:, company:, companyURL: -------------------------------
  editors:
    [
      {
        name: "voornaam achternaam",
        company: "Geonovum",
        companyURL: "https://www.geonovum.nl",
      }
    ],
  //-- de namen van de auteur(s) ------------------------------------------------------
  //-- vul in: per auteur: name:, company:, companyURL: -------------------------------
  authors:
    [
      {
        name: "voornaam achternaam",
        company: "Geonovum",
        companyURL: "https://www.geonovum.nl",
      }
    ],
  //neem hier de URL van de github repository op waar het respec document in staat
  github: "https://github.com/Geonovum/NL-ReSpec-GN-template",
  // Create PDF and link to file in header (optional):
  alternateFormats: [
      {
          label: "pdf",
          uri: "template.pdf",
      },
  ],
};
```

De file config.js is een stukje javascript (JSON) code, het bevat alle mogelijke
waarden voor de verschillende versies die wij hanteren bij Geonovum. In de file
zelf staat aangegeven welke waarden verplicht zijn, en uit welke waarden te
kiezen is. In bovenstaand voorbeeld gaat het om een 'Werkversie van een
standaard'.

### Content: bestanden '\*.md'

De 'echte' content wordt gemaakt in het formaat 'Markdown'. Er is een aantal
editors beschikbaar die dat formaat ondersteunen. Zie hiervoor
<a href='#_Ref17112190'>Hoofdstuk 3<a></a>. Het is handig om voor elk hoofdstuk
een aparte Markdown file te maken, want dan blijven de bestanden beperkt in
grootte, en zijn er gemakkelijker werkafspraken te maken over wie wanneer in
welke file aan het editen is.

### Content: Afbeeldingen '\*.png'

Afbeeldingen worden als '.png' of '.svg' bestand neergezet in de map 'media'. In
je Markdown document neem je gewoon een plaatje op zoals je in Word gewend bent.
Writage en ReSpec zorgen ervoor dat de plaatjes worden getoond.

## ReSpec Frontend

### De knop 'ReSpec'

De knop 'ReSpec' rechtsboven in de frontend van ReSpec, bevat een aantal handige
functies. Als je klikt op de knop, verschijnt het vervolgscherm met een viertal
functies.

Elk van de functies wordt hieronder uitgelegd.

![media/image25.png](media/image25.png)

### Bewaar snapshot

![media/image26.png](media/image26.png)

### <a name='_Ref17110974'></a>Doorzoek SpecRef

![media/image27.png](media/image27.png) ![media/image28.png](media/image28.png)

De gevonden zoekresultaten kunnen worden overgenomen in het ReSpec document.

### Lijst van definities

Zie: [definitielijst maken](ReSpec-definitielijst-maken.md)

## HTML ingebed in ReSpec

Omdat wij ervoor hebben gekozen om documenten te schrijven in Markdown,
gebruiken wij niet alle ReSpec functionaliteit. In dit hoofdstuk worden de
speciale ReSpec functies beschreven die als HTML code in het Markdown document
kunnen wordnen opgenomen, of die in de door respec gegenereerde HTML file kunnen
worden neergezet. Het gebruik van deze functionaliteit vereist dus wel HTML
kennis.

## HTML voor Afbeeldingen

Een lijst van afbeeldingen kan door ReSpec automatisch worden gegenereerd, maar
dan moet er wel aan een aantal ReSpec specifieke voorwaarden worden voldaan:

In Index.html komt ergens te staan:

```html
<figure id="flowchart">
   <img src="flowchart.svg" alt="">
   <figcaption>The water flows from bucket A to bucket B.</figcaption>
</figure>
```

In de documenten worden de afbeeldingen op de volgende manier neergezet:

```html
<figure id="flowchart">
   <img src="flowchart.svg" alt="">
   <figcaption>The water flows from bucket A to bucket B.</figcaption>
</figure>
```

NB: `<figure>` inclusief uniek ID en een ge-embedde `<figcaption>` zijn
verplicht!

Eventuele referenties naar plaatjes doe je op e volgende manier:

```html
<p>The flowchart shown in <a href="#flowchart"></a> is quite impressive.</p>
</section>
```

## Referentie naar GitHub issues

ReSpec ondersteunt ook een koppeling naar issues die zijn gemeld op GitHub. Jek
kan referenties opnemen naar individuele issues. Ook is het mogelijk om een
lijst met alle issues op te nemen in je document.

Om GitHub issues op te nemen moet je in 'config.js' een referentie opnemen naar
de GitHub repository.

```
issueBase: "https://github.com/Geonovum/MIM-Werkomgeving/issues/"
```

Een referentie naar een issue neem je als volgt op:

```
<div class="issue" data-number="363"></div>
```

Waarbij data-number het issuenummer is.

Een lijst met issues kan je toevoegen met de volgende HTML code:

```
<section class="appendix" id="issue-summary">
  <!-- Issues will magically be listed here! -->
</section>

```

## Foutmeldingen en waarschuwingen

![media/image29.png](media/image29.png) ![media/image30.png](media/image30.png)

In dit geval is er een tikfout gemaakt bij de naam van de Markdownfile die
ge-include wordt. Het moet natuurlijk `H2-Testcases.md` zijn.

![media/image31.png](media/image31.png)

Een voorbeeld van een waarschuwing. Klikken hierop geeft je je de waarschuwing.

In het onderstaande voorbeeld meldt ReSpec dat er een `<h2>` header ontbreekt in
het Markdown document.

![media/image32.png](media/image32.png)

# Publiceren in ReSpec

In dit hoofdstuk staan checklists die je kan gebruiken als je vanuit GitHub en
ReSpec “Versies” gaat aanmaken. Bijvoorbeeld hoe maak je een nieuwe GitHub
repository aan, of hoe maak je vanuit een werkversie een consultatieversie aan,

## Controles voor publicatie

Controleer de volgende onderwerpen voor iedere publicatie:

-   Controleer op WCAG regels. Bij het pushen van een ReSpec document naar
    GitHub wordt automatisch een WCAG rapport geschreven. Dit is te vinden onder
    'Actions'. Kies hier de commit die je gedaan hebt en je ziet daar
    'Check/WCAG').
-   Controleer op Broken links. Bij het pushen van een ReSpec document naar
    GitHub wordt automatisch op broken links gechecked. Dit is te vinden onder
    'Actions'. Kies hier de commit die je gedaan hebt en je ziet daar
    'Check/Links').
-   Je kunt oook het HTML controleren: maak een snapshot aan en biedt het aan
    aan de [W3C validator](https://validator.w3.org)

## Consultatie versie (CV) maken

1. Edit en controleer config.js - configureer alles goed voor een
   consultatieversie
    - `specStatus`:`"GN-CV"`
    - `publishDate`: moet ingevuld zijn met de datum van publicatie van de
      consultatieversie. `"jjjj-mm-dd"`,
    - `Shortname`: moet ingevuld zijn met korte naam voor het document. Dit
      wordt onderdeel van de URL. Moet uniek zijn binnen pubdomain (afgezien van
      versies).
        - Als er al eerder een versie gepubliceerd is (stabiele versie, dus
          afgezien van de werkversie in github), kan Respec bovenin een document
          de navigatie naar vorige versie goed genereren. Daarvoor moet je ook
          invullen:
        - `Previousmaturity`: wat de status toen was.
        - `Previousmaturity`: wat de status toen was.
1. Maak een snapshot (met de knop “Bewaar Snapshot” vanuit Respec)
1. Kies “HTML” en noem dit bestand “snapshot.html”
1. Commit het en push het naar dezelfde folder als waar `index.html` staat in je
   Github-repository

### Consultatieverise met ftp

> **Note**: uitwerken

Omdat de webhook nogal eens problemen oplevert is er ook een proces voor het
publiceren met ftp. In het kort is het als volgt:

1. Zet alles klaar in github (zoals bij de webhook).
2. Vraag een beheerder om de boel naar docs.geostandaarden.nl om te zetten.

### Consultatieversie maken met behulp van webhook

[Klik hier](/Publiceren/) voor een beschrijving over hoe je een webhook eenmalig
configureert voor een repository. over het toepassen van de webhook.

1. Maak een release tag conform de naamgevingsconventie:
   `\{specStatus\}-\{specType\}-\{shortName\}-\{publishDate\}`
1. Het script kopieert nu automatisch (NB: dit moet wel eenmalig geconfigureerd
   zijn als ‘webhook’ in de github repository!) het `snapshot.html` en de
   bijbehorende afbeeldingen naar
   [docs.geostandaarden.nl]<http://docs.geostandaarden.nl>).
1. Na succesvolle publicatie:
    - zet de `specStatus` in `config.js` terug op `"GN-WV"`
    - Vul `previousMaturity` in met `"GN-CV"`
    - Vul `previousPublishDate` in met de datum van de zojuist gepubliceerde
      consultatieversie



## Vaststellingsversie (VV) maken

1. Edit en controleer config.js - configureer alles goed voor een
   vaststellingsversie
    - specStatus: "GN-VV"
    - publishDate: moet ingevuld zijn met de datum van publicatie van de
      consultatieversie. "jjjj-mm-dd",
    - Shortname: moet ingevuld zijn met korte naam voor het document. Dit wordt
      onderdeel van de URL. Moet uniek zijn binnen pubdomain (afgezien van
      versies).
        - Als er al eerder een versie gepubliceerd is (stabiele versie, dus
          afgezien van de werkversie in github), kan Respec bovenin een document
          de navigatie naar vorige versie goed genereren. Daarvoor moet je ook
          invullen:
        - Previousmaturity: wat de status toen was.
        - Previousmaturity: wat de status toen was.
2. Maak een snapshot (met de knop “Bewaar Snapshot” vanuit Respec)
3. Kies “HTML” en noem dit bestand “snapshot.html”
4. Commit het en push het naar dezelfde folder als waar index.html staat in je
   Github repository
5. Maak een release tag conform de naamgevingsconventie:
   \{specStatus\}-\{specType\}-\{shortName\}-\{publishDate\}
6. Het script kopieert nu automatisch (NB: dit moet wel eenmalig geconfigureerd
   zijn als ‘webhook’ in de github repository!) het snapshot.html en de
   bijbehorende afbeeldingen naar <http://docs.geonovum.nl>
7. Na succesvolle publicatie:
    - zet de specStatus in config.js terug op GN-WV
    - Vul previousMaturity in met GN-CV
    - Vul previousPublishDate in met de datum van de zojuist gepubliceerde
      consultatieversie

## Definitieve versie (DEF) maken

1. Edit en controleer config.js - configureer alles goed voor een definitieve
   versie
    - specStatus: "GN-DEF",
    - publishDate: moet ingevuld zijn met de datum van publicatie van de
      definitieve versie. "jjjj-mm-dd",
    - Shortname: moet ingevuld zijn met korte naam voor het document. Dit wordt
      onderdeel van de URL. Moet uniek zijn binnen pubdomain (afgezien van
      versies).
    - Als er al eerder een versie gepubliceerd is (stabiele versie, dus afgezien
      van de werkversie in github), kan Respec bovenin een document de navigatie
      naar vorige versie goed genereren. Daarvoor moet je ook invullen:
        - Previousmaturity: wat de status toen was.
        - previousPublishDate: vorige publicatiedatum (jjjj-mm-dd)
2. Maak een snapshot (met de knop “Bewaar Snapshot” vanuit Respec)
3. Kies “HTML” en noem dit bestand “snapshot.html”
4. Commit het en push het naar dezelfde folder als waar index.html staat in je
   Github repository
5. Maak een release tag conform de naamgevingsconventie:
   {specStatus}-{specType}-{shortName}-{publishDate}
6. Het script kopieert nu automatisch (NB: dit moet wel eenmalig geconfigureerd
   zijn als ‘webhook’ in de github repository!) het snapshot.html en de
   bijbehorende afbeeldingen naar <http://docs.geostandaarden.nl> Hoe dit werkt
   is beschreven in: <https://github.com/Geonovum/technisch-register-2019>
7. Na succesvolle publicatie:
    - zet de specStatus in config.js terug op GN-WV
    - Vul previousMaturity in met GN-DEF
    - Vul previousPublishDate in met de datum van de zojuist gepubliceerde
      definitieve versie
