# Welkom

Welkom bij de helppagina's waarin de Geonovum Werkwijze beschreven is. Dit is niet een formele beschrijving van de werkwijze maar maar meer een hulpmiddel om stap voor stap de tooling uit te leggen.

Om de standaarden die in beheer zijn bij Geonovum te kunnen beheren, wordt gebruik gemaakt van verschillende tooling. Documenten die behoren bij de standaarden worden gepubliceerd op https://docs.geostandaarden.nl als HTML bestanden, deze HTML bestanden worden aangemaakt met een tool van W3C: ReSpec. 

ReSpec maakt gebruik van input bestanden om de HTML te genereren. Deze inputbestanden (de content) wordt gemaakt in een formaat: Markdown. Deze Markdown bestanden kunnen worden aangemaakt met text editor zoals Visual Studio van Microsoft of Notepad++. Visual Studio heeft het voordeel dat de editor mooi integreert met de Github Desktop Client. GitHub tenslotte wordt gebruikt als de 'repository', waarin alle bestanden die bij een standaard horen, komen te staan.

Deze handleiding beschrijft hoe je een GitHub Account maakt, hoe je GitHub Desktop Client installeert en gebruikt, hoe je een Respec mappenstructuur opbouwt, welke bestanden er nodig zijn voor een standaard, en hoe je de verschillende versies van een standaard genereert. Ook wordt uitgelegd hoe je de Markdown plugin in Microsoft Word installeert en gebruikt.

## Overzicht tooling

Binnen Geonovum maken we gebruik van de volgende tools:

- **GitHub**
    - [GitHub handleiding](GitHub.md): Beschrijft hoe je een account aanmaakt en je beheertaken uitvoert.
    - [GitHub werkwijze](GitHub-Inleiding.md): Meer algemene inleiding over GitHub.
- **Imvertor**
     - [Imvertor](Imvertor.md)
- **Markdown**
    - [Markdown handleiding](Markdown.md)
-  **ReSpec**  
    - [Respec handleiding](ReSpec.md): Algemene handleiding.
    - [Respec checklist](ReSpec-Checklists.md): Checklist van handeling bij het publiceren van een standaard middels ReSpec.
    - [Respec code toepassen](ReSpec-code-toepassen.md)
    - [Respec definitielijst maken](ReSpec-definitielijst-maken.md)
- **Subversion**
    - [Subversion instructies](SVN.md)
- **EA**
    - [Primitieve datatypes](EA-toepassing-standaarddatatypen.md)
- **GML**
     - [GML](GML.md)

## Uitleg MkDocs

[MkDocs](https://www.mkdocs.org/) is een lichtgewicht tool die een collectie Markdown documenten omzet in een navigeerbare handleiding. Omdat we er bij Geonovum nog niet uit zijn hoe we documentatie gaan behren is MkDocs een eenvoudige manier om de bestaande documentatie te ontsluiten. In de menubalk aan de bovenkant zie je de verschillende onderwerpen die in deze documentatie behandeld worden. Van sommige van die onderwerpen zijn nog subonderwerpen beschreven. Kies een onderwerp en in de linkermenubalk verschijnt een hoofdstukindeling. Ook is er zoekfunctie.

Na installeren van de mkdocs tooling heb je de volgende mogelijkheden:

### Realtime documentatie bekijken

Als je deze folder lokaal hebt staan kan je met het commando

```
mkdocs serve
```

een locale webserver starten en live kijken hoe de document eruitziet in je [browser](http://127.0.0.1:8000/).



### GitHub page up to date brengen

Deze handleiding is als HTML gepubliceerd op: de [GitHub](https://geonovum.github.io/handleiding-tooling/) paginas van Geonovum. Om deze up to date te houden kun je in een linux omgeving in de root folder van het repository het commando

```
mkdocs gh-deploy
```
hiervoor heb je wel een github token

>
> TODO: Het is ook mogelijk om met een github action automatisch bij iedere wijziging de pages up te daten. 
>

