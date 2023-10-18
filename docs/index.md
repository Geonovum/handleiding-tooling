# Welkom

Welkom bij de Geonovum Werkwijze. Dit is
geen formele beschrijving maar  een hulpmiddel om
stap voor stap de tooling uit te leggen.

Om de [standaarden van Geonovum](https://docs.geostandaarden.nl) te beheren, gebruiken we verschillende tools. We publiceren standaarden als HTML met een tool van W3C: ReSpec.

ReSpec maakt gebruik van input bestanden om de HTML te genereren. Deze
inputbestanden (de content) wordt gemaakt in een formaat: Markdown. Deze
Markdown bestanden kunnen worden aangemaakt met text editor zoals Visual Studio
van Microsoft of Notepad++. Visual Studio heeft het voordeel dat de editor mooi
integreert met de Github Desktop Client. GitHub tenslotte wordt gebruikt als de
'repository', waarin alle bestanden die bij een standaard horen, komen te
staan.

Deze handleiding beschrijft hoe je een GitHub Account maakt, hoe je GitHub
Desktop Client installeert en gebruikt, hoe je een Respec mappenstructuur
opbouwt, welke bestanden er nodig zijn voor een standaard, en hoe je de
verschillende versies van een standaard genereert. Ook wordt uitgelegd hoe je
de Markdown plugin in Microsoft Word installeert en gebruikt.

## De tools van Geonovum


- **GitHub**
    -   [GitHub handleiding](GitHub.md): Beschrijft hoe je een account aanmaakt en
        je beheertaken uitvoert.
    -   [GitHub werkwijze](GitHub-Inleiding.md): Meer algemene inleiding over GitHub.
- **Imvertor**
    -   [Imvertor](Imvertor.md): Verwijzingen naar verschillende onderwerpen met betrekking tot Imvertor.
- **Markdown**
    -   [Markdown handleiding](Markdown.md): Handleiding werken met Markdown voor ReSpec-documentatie.
- **ReSpec**
    -   [Respec handleiding](ReSpec.md): Algemene handleiding.
    -   [Respec checklist](ReSpec-Checklists.md): Checklist van handeling bij het
        publiceren van een standaard middels ReSpec.
    -   [Respec code toepassen](ReSpec-code-toepassen.md): Richtlijnen voor het toepassen van code in documentatie.
    -   [Respec definitielijst maken](ReSpec-definitielijst-maken.md): Handleiding voor het maken van een definitielijst in ReSpec-documentatie.
- **MIM**
    -   [Toolbox importeren](MIM-toolbox-importeren.md): Handleiding voor het importeren van de MIM-toolbox in EA.
    -   [Toolbox genereren](MIM-toolbox-genereren.md): Handleiding voor het maken van een EA-toolbox.
    -   [Toolbox genereren extensie](MIM-toolbox-genereren-extensie.md): Handleiding voor het maken van een extensie op de MIM-toolbox.
- **Subversion (SVN)**
    -   [Subversion instructies](SVN.md): Algemene handleiding
    -   [Subversion installeren voor EA](SVN-importeren-bestaand-project): Installatie SVN en informatiemodel in versiebeheer zetten. 
    -   [Subversion importeren bestaand project](SVN-installeren-voor-EAP): Packages importeren vanuit SVN in EA.
- **EA**
    -   [Primitieve datatypes](EA-toepassing-standaarddatatypen.md): Handleiding en toelichting op het toepassen van standaarddatatypes in modelleeromgeving Geonovum.
- **GML**
    -   [GML](GML.md): Toelichting GML, XSD en Namespaces.
- **Ontologie**
    -   [Ontologie](Handleiding-ontologie-maken-en-publiceren.md):Handleiding voor het maken en publiceren van een ontologie.
- **Publiceren**
    -   [Documentatie publiceren](Publiceren.md): Handleiding voor de publicatie van ReSpec-documenten via GitHub met behulp van een webhook.

## Uitleg MkDocs

[MkDocs](https://www.mkdocs.org/) is een lichtgewicht tool die een collectie
Markdown handleidingen omzet in een navigeerbare handleiding. De markdown bestanden staan in de github repository [handleiding-tooling](https://github.com/Geonovum/handleiding-tooling). Deze wordt automatisch ontsloten op [github pages](https://github.com/Geonovum/handleiding-tooling)

Je kunt mkdocs ook lokaal installeren. Dan kun je live je edits volgen in je [browser](http://127.0.0.1:8000/) met het commando:

```
mkdocs serve
```
