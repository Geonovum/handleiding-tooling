# Welkom

Welkom bij de beschrijving van de Geonovum Werkwijze. Deze helpfiles beschrijven
welke tools we gebruiken voor het maken en beheren van de standaarden van
Geonovum. Deze tools staan in onderstaand overzicht. Daaronder staat de
publicatieomgeving van Geonovum beschreven.

## Geonovum tooling

- **UML Modelleertool:** Enterprise Architect
    - [Overzicht](EA.md)
    - [Primitieve datatypes](EA-toepassing-standaarddatatypen.md): Handleiding
        en toelichting op het toepassen van standaarddatatypes in
        modelleeromgeving Geonovum.
- **GitHub**:
    - [GitHub werkwijze](GitHub-Inleiding.md): algemene inleiding over GitHub.
    - [GitHub handleiding](GitHub.md): Hoe maak je een account aan en hoe doe
        je beheertaken.
- **Imvertor**
    - [Imvertor](Imvertor.md): Verwijzingen naar verschillende onderwerpen met
        betrekking tot Imvertor.
- **Markdown**
    - [Markdown handleiding](Markdown.md): Handleiding werken met Markdown
        voor ReSpec-documentatie.
- **ReSpec**
    - [Respec handleiding](ReSpec.md): Algemene handleiding.
    - [Respec code toepassen](ReSpec-code-toepassen.md): Richtlijnen voor het
        toepassen van code in documentatie.
    - [Respec definitielijst maken](ReSpec-definitielijst-maken.md):
        Handleiding voor het maken van een definitielijst in
        ReSpec-documentatie.
- **MIM**
    - [Toolbox importeren](MIM-toolbox-importeren.md): Handleiding voor het
        importeren van de MIM-toolbox in EA.
    - [Toolbox genereren](MIM-toolbox-genereren.md): Handleiding voor het
        maken van een EA-toolbox.
    - [Toolbox genereren extensie](MIM-toolbox-genereren-extensie.md):
        Handleiding voor het maken van een extensie op de MIM-toolbox.
- **Subversion (SVN)**
    - [Subversion installeren voor EA](SVN-importeren-bestaand-project.md):
        Installatie SVN en informatiemodel in versiebeheer zetten.
    - [Subversion importeren bestaand project](SVN-installeren-voor-EAP.md):
        Packages importeren vanuit SVN in EA.
- **GML**
    - [GML](GML.md): Toelichting GML, XSD en Namespaces.
- **Ontologie**
    - [Ontologie](Handleiding-ontologie-maken-en-publiceren.md): Handleiding
        voor het maken en publiceren van een ontologie.
- **Word2XXX**
    - [Word2werkversie](WordConversies.md)

Voor licenties of de interne beheerder van de tooling kun je terecht op
[intranet](https://stichtinggeonovum.sharepoint.com/:b:/r/sites/FBICT/Gedeelde%20documenten/General/wat%20staat%20waar/Tooling_en_Beheerders.pdf?csf=1&web=1&e=aEcKjl)

### Documentatie elders

De documentatie van de werkwijze is niet alleen hier vastgelegd. Links naar
andere documenten:

- [werkomgeving modelleren](werkomgeving-modelleren.md).
- [werkwijze modelleren](werkwijze-modelleren.md).
- [geonovum werkwijze modelleren](geonovum-werkwijze-modelleren.md)

## Geonovum publicatieomgeving

Verschillende onderdelen van standaarden worden op verschillende plaatsen
gepubliceerd. De publicatieomgeving ziet er als volgt uit

![Architectuurplaatje](https://raw.githubusercontent.com/Geonovum/DrawIO/master/GeonovumInterneArchitectuur.drawio.png)
### Documenten (docs.geostandaarden.nl)

Standaarden en technische documentatie. Voor een nette lijst van pubdomains op
docs.geostandaarden.nl moet de de volgende lijst up-to-date zijn:
[pubDomainList.json](https://github.com/Geonovum/respec-utils/blob/master/src/autodeploy/config/pubDomainList.json)

### Het Technisch Register (register.geostandaarden.nl)

Technische onderdelen van de standaard worden op:
[register.geostandaarden.nl](https://register.geostandaarden.nl) gezet. Hoe je
dit met een webhook kan doen staat beschreven in:
[technisch-register-2019](https://github.com/Geonovum/technisch-register-2019/blob/master/documentatie/Handleiding%20voor%20beheerders%20informatiemodellen.md)

### Ontologieën (modellen.geostandaarden.nl)

Er is één ontologie gepubliceerd: die van NEN 3610. 

Dit is uitgelegd in de [handleiding ontologie maken](Handleiding-ontologie-maken-en-publiceren.md)

### Conceptenbibliotheek (definities.geostandaarden.nl)

## MkDocs voor deze handleiding

De handleiding wordt beheerd in [MkDocs](https://www.mkdocs.org/). Dit is een
lichtgewicht tool die een doorzoekbare en navigeerbare site maakt van een
verzameling Markdown documenten. De handleiding staat op
[github pages](https://github.com/Geonovum/handleiding-tooling). De
bronbestanden staan in:
[handleiding-tooling](https://github.com/Geonovum/handleiding-tooling).

Je kunt mkdocs ook lokaal installeren. Dan kun je live je edits volgen in je
browser: [http://127.0.0.1:8000/](http://127.0.0.1:8000/) met het commando:

```shell
mkdocs serve
```
