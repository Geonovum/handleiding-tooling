
# Workflow Modelleur Tips&Tricks
Hieronder volgt een ruwe opsomming van suggesties voor het maken van nieuwe, dan wel uitbreiden van bestaande handleidingen.

> **Note**: Hoe omgaan met onderdelen die regelmatig wijzigen?

> **Note**: Op Confluence staan ook al verschillende documenten.

## ENTERPRISE ARCHITECT (EA)
### Meest gebruikte windows
 - Project browser
 - Properties
 - Notes
 - Zoom/pan
 - Resources
 - Features
 - Tagged values
 - Relationships
 - Imvertor

> **Note**: Waar kun je deze windows vinden?

> **Note**: Creëer workspaces
### Creëer workspace(s)
 - Hoe maak je een workspace?
### Handige tips
 - Find *-in project browser* of *-in all diagrams*
 - View as feature matrix
 - View as relation matrix
 - View as specification view...
 - Relationship matrix
### Verwijderen relaties
 - Gebruik (rel. matr./relationships)
 - Verwijderen uit diagram is niet model
### Package as Namespace
 - Set package as namespace root: https://sparxsystems.com/enterprise_architect_user_guide/15.2/model_domains/namespaces.html
 - Is dit nodig? En waarom? Voor je XML/GML-schema generatie o.i.d.?
### Installatie MIM-toolbox
 - Voor *project* vs. *user*
 - Hoe kun je toolbox *project*/*user* verwijderen?
### Tagged values invullen packages/MIM
 - Beschrijving toevoegen
### EA-bestand voor oplevering
 - Uit VC (SVN) halen
 - SVN Checkout folder niet leegmaken
 - Dat doe je bijvoorbeeld wel als je een package opnieuw of definitief uit Version Control wilt halen.
 - Dus aan je checkout folder verander je niks
 - Je maakt alleen een EA-bestand dat VC-vrij is.

## SUBVERSION (SVN) - VERSION CONTROL (VC) 
- Verwijderen packages
- Suggestie structuur
- Werkwijze put/get latest
- Inchecken forceren: voor- en nadelen
- Gebruik repo browser (kijken, geen bewerkingen)
- URL repo browser
- Credentials
- Delete --> commit (als je lokaal wijzigingen aanbrengt)
- Verander niet zomaar iets in of aan checkout folder
### Herstel package control
   - Check out
   - Package VC
   - Untick 'Control package'
   - Verwijder `.xml` van het package dat je uit VC hebt gehaald uit checkout repo.
   - Rechtermuis op repo
   - Kies 'SVN Commit...'
   - Selecter de `.xml`-bestanden van de verwijderde package(s)
   - Klik op 'ok'.
   - Nu kun je opnieuw het package onder VC brengen
### Versiestructuur
 - Handleiding voor SVN versioning maken
 - De mogelijkheid om hoofd- subpackages apart in- en uit te kunnen checken
 - Eerst de domeinen erin hijsen
 - Dan pas hogere packages,
 - Met andere woorden: van onder naar boven of van laag naar hoog
 - Versienr tags in het versieveld
 - Mappenstructuur
 - (plaatje pano overnemen of linken/samenvoegen)
 - Propertiesfile weer terugzetten in cm vanuit imsor notitiemap
 - XML's prefix van package stereotype meegeven dus `view_<naam>` of `domein_<naam>`
 - Version packages is van tags
 - Maar moet overeenkomen met versiemapnaam\
 - Dus versie in EA moet overeenkomen met versiemapnaam SVN
 - Waarschijnlijk leidt dit ertoe dat je voor elke versie op nieuw alle domeinen in en uit SVN moet halen
 - ...

## IMVERTOR
- Handleiding Armatiek
- Zoekfunctie Armatiek
- Propertiesfile (standaard settings?)
- GitHub publicatie
- Batch Tagged Values?
- XML-/GML-schema's
- Diagrammen vinkje in settings + `-overzicht` in diagramnaam EA, properties?

> **Note**: op properties staan 2x beschreven. De lijst met CLI-properties is compleet/uitgebreider