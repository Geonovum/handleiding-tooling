# Publicatie Infrastructuur van Geonovum

Dit is de publicatie infrstructuur van Geonovum. Onder het architectuurplaatje staan:

- Een korte [beschrijving](#kort-overzicht).
- Verwijzing naar [documentatie](#documentatie).
- Verbeterpunten [verbeterpunten](#verbeterpunten).


![Publicatie Infrastructuur Geonvoum](media/PublicatieInfrastructuurGeonovum.drawio.svg)

## Kort Overzicht

### [1] UML

- UML klasse diagrammen maken we met Enterprise Architect.
- Binnen UML gebruiken we MIM als metataal.
- Ook gebruiken we NEN 3610 als raamwerk.

### [2] Subversion

- De UML diagram worden met subversion (svn) beheerd.
- Deze server draait op `svn.geostandaarden.nl`

### [3] Imvertor

- Imvertor vertaalt het UML naar catalog, xsd etc.

### [4] ReSpec document

- Onze standaarden maken we in ReSpec.
- Dit is een tool die uit een aantal bestanden (Markdown, HTML) een mooi document publiceert.
- De bestanden beheren we in GitHub

### [5] GitHub

- Onze standaarden beheren en versioneren we in GitHub.

### [6] docs.geostandaarden.nl

- Onze standaarden publiceren we op docs.geostandaarden.nl
- Dit doen we door het ftp de bestanden daarnaartoe te kopieren.

### [7] tools.geostandaarden.nl

- Op deze server staan css bestanden en hulpbestanden voor ReSpec

## Documentatie

### [1] UML

- [Overzicht](EA.md)
- [Primitieve datatypes](EA-toepassing-standaarddatatypen.md): Handleiding
    en toelichting op het toepassen van standaarddatatypes in
    modelleeromgeving Geonovum.

### [2] Subversion

- [Subversion installeren voor EA](SVN-importeren-bestaand-project.md):
    Installatie SVN en informatiemodel in versiebeheer zetten.
- [Subversion importeren bestaand project](SVN-installeren-voor-EAP.md):
    Packages importeren vanuit SVN in EA.

### [3] Imvertor

- [Imvertor](Imvertor.md): Verwijzingen naar verschillende onderwerpen met
    betrekking tot Imvertor.

### [4] ReSpec
- [Respec handleiding](ReSpec.md): Algemene handleiding.
- [Respec code toepassen](ReSpec-code-toepassen.md): Richtlijnen voor het
    toepassen van code in documentatie.
- [Respec definitielijst maken](ReSpec-definitielijst-maken.md):
    Handleiding voor het maken van een definitielijst in
    ReSpec-documentatie.

### [5] GitHub*
- [GitHub werkwijze](GitHub-Inleiding.md): algemene inleiding over GitHub.
- [GitHub handleiding](GitHub.md): Hoe maak je een account aan en hoe doe
    je beheertaken.

### [6] docs.geostandaarden.nl
- Zie [pubDomainList.json](https://github.com/Geonovum/respec-utils/blob/master/src/autodeploy/config/pubDomainList.json)

### Markdown
 - [Markdown handleiding](Markdown.md): Handleiding werken met Markdown
     voor ReSpec-documentatie.

### MIM
- [Toolbox importeren](MIM-toolbox-importeren.md): Handleiding voor het
    importeren van de MIM-toolbox in EA.
- [Toolbox genereren](MIM-toolbox-genereren.md): Handleiding voor het
    maken van een EA-toolbox.
- [Toolbox genereren extensie](MIM-toolbox-genereren-extensie.md):
    Handleiding voor het maken van een extensie op de MIM-toolbox.

### GML

- [GML](GML.md): Toelichting GML, XSD en Namespaces.
### Ontologie

- [Ontologie](Handleiding-ontologie-maken-en-publiceren.md): Handleiding
    voor het maken en publiceren van een ontologie.
### Word2XXX

- [Word2werkversie](WordConversies.md)

Voor licenties of de interne beheerder van de tooling kun je terecht op
[intranet](https://stichtinggeonovum.sharepoint.com/:b:/r/sites/FBICT/Gedeelde%20documenten/General/wat%20staat%20waar/Tooling_en_Beheerders.pdf?csf=1&web=1&e=aEcKjl)


### Het Technisch Register (register.geostandaarden.nl)

Technische onderdelen van de standaard worden op:
[register.geostandaarden.nl](https://register.geostandaarden.nl) gezet. Hoe je
dit met een webhook kan doen staat beschreven in:
[technisch-register-2019](https://github.com/Geonovum/technisch-register-2019/blob/master/documentatie/Handleiding%20voor%20beheerders%20informatiemodellen.md)

### Ontologieën (modellen.geostandaarden.nl)

Er is één ontologie gepubliceerd: die van NEN 3610. 

Dit is uitgelegd in de [handleiding ontologie maken](Handleiding-ontologie-maken-en-publiceren.md)

### Conceptenbibliotheek (definities.geostandaarden.nl)


## Verbeterpunten

### [1] UML

- Er is een alternatieve tool voor UML: 

### [3] Imvertor

- De beheerders van Imvertor willen binnenkort met pensioen.
- Imvertor is niet echt modulair

### [6] Imvertor

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
