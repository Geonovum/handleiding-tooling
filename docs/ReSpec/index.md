# ReSpec

We maken standaarden met ReSpec. De inhoud van ReSpec documenten zit in Markdown bestanden die je met een text editor kunt bewerken. De bestanden worden in een GitHub repository beheerd.

ReSpec is een tool van voor het schrijven van specifications.
ReSpec zorgt voor een uniforme styling in het document, onderhoudt
referenties en verwijzingen naar andere documentatie, verzorgt de inhoudsopgave,
zorgt voor links naar vorige en meest recente versies, en heeft een integratie
met Github issues.

Dit diagram beschrijft het proces voor het maken van een
ReSpec publicatie:

![publicatie infrastructuur](../media/WorkflowPublicatieProces.drawio.svg)

De workflow bevat de volgende stappen

- ReSpec document uitchecken en bewerken en weer [inchecken](#respec-document-uitchecken-wijzigen-en-weer-inchecken).
- Check je document voor publicatie via de [checklist](#controles-voor-publicatie).
- ReSpec document [publiceren](#respec-document-publiceren).
- ReSpec document [aanmaken](#een-nieuw-respec-document-aanmaken).

Geonovum gebruikt een fork van ReSpec die door Logius beheerd wordt. Meer
documentatie is op andere plaatsen te vinden:

- Er is een gedetailleerde
  [gebruikershandleiding](https://github.com/w3c/respec/wiki/ReSpec-Editor's-Guide)
  beschikbaar.
- Er is ook een
  [ontwikkelaarshandleiding](https://github.com/w3c/respec/wiki/Developers-Guide)
  te vinden.
- De Geonovum [wiki over ReSpec](https://github.com/Geonovum/respec/wiki) is
  een fork van de w3c ReSpec met aanpassingen voor Geonovum. Deze is
  achterhaald omdat we nu van de Logius Respec gebruik maken. (TODO aanpassen)

## ReSpec document uitchecken wijzigen en weer inchecken

- ReSpec documenten worden beheerd in een GitHub repository. Meestal zit er één ReSpec document in een repository.
- Maakt met `git clone` een lokaal kopie van repository waarin het ReSpec document zodat je het lokaal kunt bewerken. Een overzicht van alle GitHub repositories van Geonovum staat [hier](https://github.com/Geonovum/repositories).
- Het lokale kopie bestaat uit een collectie bestanden. De tekstuele inhoud zit meestal in markdown (*md) bestanden. Deze kan je nu lokaal wijzingen
- Met `git commit` en `git push` kun je de lokale wijzingen naar de centrale werkversie overzetten.

Meer informatie over [GitHub](../GitHub/index.md).
Meer informatie over [Markdown](../Markdown/index.md)

## Publiceren in ReSpec

In dit hoofdstuk staan checklists die je kan gebruiken als je een nieuwe
versie van een ReSpec document wilt publiceren op docs.geostandaarden.nl

### Controles voor publicatie

Controleer de volgende onderwerpen voor iedere publicatie:

- Controleer op **WCAG** (web toegankelijkheids-) regels. Bij het pushen van een ReSpec document naar
    GitHub wordt automatisch een WCAG rapport geschreven. Dit is te vinden onder
    'Actions'. Kies hier de commit die je gedaan hebt en je ziet daar
    'build/WCAG Accessibility Check'). Deze controle checkt ook de HTML.
- Controleer op **Broken links**. Bij het pushen van een ReSpec document naar
    GitHub wordt automatisch op broken links gechecked. Dit is te vinden onder
    'Actions'. Kies hier de commit die je gedaan hebt en je ziet daar
    'Build/Link validation').

Los eventuele fouten op voordat je verder gaat met publiceren. 

### Controles voor publicatie

[Klik hier](ReSpec-publiceren.md) voor een beschrijving van de automatische publicatieworkflow.

Voorwaarden voor de werking van de publicatieworkflow: 

- de folderstructuur van de repository waarin het ReSpec document staat, moet conform de [Geonovum ReSpec template](https://github.com/Geonovum/NL-ReSpec-template) zijn
    - dat wil zeggen, `index.html` in de root folder, `config.js` in `/js` folder, afbeeldingen in `/media` en/of `/data/Images` folder;
- de github repository mag maar één ReSpec document bevatten.

### Publiceren van een Consultatie versie (CV)

1. In 'js/config.js':
    - `specStatus`:`"CV"`
    - `publishDate`: moet ingevuld zijn met de datum van publicatie van de. `"jjjj-mm-dd"`,
    - `Shortname`: moet ingevuld zijn met korte naam voor het document. Dit
      wordt onderdeel van de URL. Moet uniek zijn binnen pubdomain (afgezien van
      versies).
        - Als er al eerder een versie gepubliceerd is (stabiele versie, dus
          afgezien van de werkversie in github), kan Respec bovenin een document
          de navigatie naar vorige versie goed genereren. Daarvoor moet je ook
          invullen:
        - `Previousmaturity`: wat de status toen was.
        - `previousPublishDate`: wat de status toen was.
1. Commit je wijzigingen en push de commit. Dit triggert de [publicatieworkflow](ReSpec-publiceren.md).

### Consultatieversie maken en automatisch publiceren

1. Maak een release tag conform de naamgevingsconventie:
   `\{specStatus\}-\{specType\}-\{shortName\}-\{publishDate\}`
1. Het script kopieert nu automatisch (NB: dit moet wel eenmalig geconfigureerd
   zijn als [workflow](ReSpec-publiceren.md) in de github repository!) het `snapshot.html` en de
   bijbehorende afbeeldingen naar de [publicatierepository](https://github.com/Geonovum/docs.geostandaarden.nl). 
1. Eén van de reviewers Frank Terpstra, Linda van den Brink of Wilko Quak checkt de publicatie. Als alles goed is bevonden  wordt het document vervolgens automatisch gepubliceerd op 
   [docs.geostandaarden.nl](http://docs.geostandaarden.nl).
1. Na succesvolle publicatie:
    - zet de `specStatus` in `config.js` terug op `"WV"`
    - Vul `previousMaturity` in met `"CV"`
    - Vul `previousPublishDate` in met de datum van de zojuist gepubliceerde
      consultatieversie

### Vaststellingsversie (VV) maken

1. Edit en controleer config.js - configureer alles goed voor een
   vaststellingsversie
    - specStatus: "VV"
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
2. Commit je wijzigingen en push de commit. 
5. Maak een release tag conform de naamgevingsconventie:
   \{specStatus\}-\{specType\}-\{shortName\}-\{publishDate\}
6. Het script kopieert nu automatisch (NB: dit moet wel eenmalig geconfigureerd
   zijn als [workflow](ReSpec-publiceren.md) in de github repository!) het`snapshot.html` en de
   bijbehorende afbeeldingen naar de [publicatierepository](https://github.com/Geonovum/docs.geostandaarden.nl). 
1. Eén van de reviewers Frank Terpstra, Linda van den Brink of Wilko Quak checkt de publicatie. Als alles goed is bevonden  wordt het document vervolgens automatisch gepubliceerd op 
   [docs.geostandaarden.nl](http://docs.geostandaarden.nl).
7. Na succesvolle publicatie:
    - zet de specStatus in config.js terug op WV
    - Vul previousMaturity in met CV
    - Vul previousPublishDate in met de datum van de zojuist gepubliceerde
      consultatieversie

### Definitieve versie (DEF) maken

1. Zet in config.js alles goed voor een definitieve versie
    - specStatus: "DEF",
    - publishDate: de publicatiedatum van de definitieve versie. "jjjj-mm-dd",
    - Shortname: korte naam voor het document. Dit wordt
      onderdeel van de URL. Moet uniek zijn binnen pubdomain (afgezien van
      versies).
    - Als er al eerder een versie gepubliceerd is (stabiele versie, dus afgezien
      van de werkversie in github), kan Respec bovenin een document de navigatie
      naar vorige versie goed genereren. Daarvoor moet je ook invullen:
        - Previousmaturity: wat de status toen was.
        - previousPublishDate: vorige publicatiedatum (jjjj-mm-dd)
2. Commit je wijzigingen en push de commit. Dit triggert de publicatieworkflow.
5. Maak een release tag conform de naamgevingsconventie:
   {specStatus}-{specType}-{shortName}-{publishDate}
6. Het script kopieert nu automatisch (NB: dit moet wel eenmalig geconfigureerd
   zijn als [workflow](ReSpec-publiceren.md) in de github repository!) het`snapshot.html` en de
   bijbehorende afbeeldingen naar de [publicatierepository](https://github.com/Geonovum/docs.geostandaarden.nl). 
1. Eén van de reviewers Frank Terpstra, Linda van den Brink of Wilko Quak checkt de publicatie. Als alles goed is bevonden  wordt het document vervolgens automatisch gepubliceerd op 
   [docs.geostandaarden.nl](http://docs.geostandaarden.nl).
7. Na succesvolle publicatie:
    - zet de specStatus in config.js terug op WV
    - Vul previousMaturity in met DEF
    - Vul previousPublishDate in met de datum van de zojuist gepubliceerde
      definitieve versie


## Een nieuw ReSpec document aanmaken

ReSpec documenten worden beheerd in een [GitHub](../GitHub/index.md) repository.

Gebruik de [Geonovum ReSpec template](https://github.com/Geonovum/NL-ReSpec-template) om een nieuw document te maken; druk op 'Use this template'. Dit maakt een GitHub repository met een template document. Dit kun je meteen gaan wijzigen. Pas op alle plekken waar TODO staat het document aan.

**Regel:** kies een logische naam voor het repository.

**Regel:** Een github repository mag maar één ReSpec document bevatten.