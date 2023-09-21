# Welkom

Welkom bij de helppagina's waarin de Geonovum Werkwijze beschreven is. Dit is
niet een formele beschrijving van de werkwijze maar maar meer een hulpmiddel om
stap voor stap de tooling uit te leggen.

Om de standaarden die in beheer zijn bij Geonovum te kunnen beheren, wordt
gebruik gemaakt van verschillende tooling. Documenten die behoren bij de
standaarden worden gepubliceerd op
[docs.geostandaarden.nl](https://docs.geostandaarden.nl) als HTML bestanden,
deze HTML bestanden worden aangemaakt met een tool van W3C: ReSpec.

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

## Overzicht tooling

Binnen Geonovum maken we gebruik van de volgende tools:

- **GitHub**
  - [GitHub handleiding](GitHub.md): Beschrijft hoe je een account aanmaakt en
    je beheertaken uitvoert.
  - [GitHub werkwijze](GitHub-Inleiding.md): Meer algemene inleiding over GitHub.
- **Imvertor**
  - [Imvertor](Imvertor.md)
- **Markdown**
  - [Markdown handleiding](Markdown.md)
- **ReSpec**
  - [Respec handleiding](ReSpec.md): Algemene handleiding.
  - [Respec checklist](ReSpec-Checklists.md): Checklist van handeling bij het
    publiceren van een standaard middels ReSpec.
  - [Respec code toepassen](ReSpec-code-toepassen.md)
  - [Respec definitielijst maken](ReSpec-definitielijst-maken.md)
- **Subversion**
  - [Subversion instructies](SVN.md)
- **EA**
  - [Primitieve datatypes](EA-toepassing-standaarddatatypen.md)
- **GML**
  - [GML](GML.md)

## Uitleg MkDocs

[MkDocs](https://www.mkdocs.org/) is een lichtgewicht tool die een collectie
Markdown handleidingen omzet in een navigeerbare handleiding. De markdown bestanden staan in de github repository [handleiding-tooling](https://github.com/Geonovum/handleiding-tooling). De wordt automatisch ontsloten op [github pages](https://github.com/Geonovum/handleiding-tooling)

Je kunt mkdocs ook lokaal installeren. Dan kun je live je edits volgen in je [browser](http://127.0.0.1:8000/) met het commando:

```
mkdocs serve
```
