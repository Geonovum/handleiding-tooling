# Publicatie Infrastructuur van Geonovum

Dit is de publicatie infrastructuur van Geonovum. Onder het architectuurplaatje staan:

- Een korte [beschrijving](#kort-overzicht).
- Verwijzing naar [documentatie](#documentatie).
- Aandachtspunten [verbeterpunten](#aandachtspunten).
- Hoe we de boel beheren staat in [wie beheert wat](#beheer).
- Wat vertellen wij onze opdrachtgevers in de [bijsluiter](https://stichtinggeonovum.sharepoint.com/:b:/s/Basisprogramma/EVGORVYMb0FFkjC0L14Ud5AB3cuyP27Ux2lz6ZfxGqqMDw?e=EYVtfs)


![publicatie infrastructuur](media/PublicatieInfrastructuurGeonovum.drawio.svg)



## Kort Overzicht

Zie het document [werkwijze informatiemodelleren](https://stichtinggeonovum.sharepoint.com/sites/StarterspakketGeonovum/SitePages/Werkwijze-informatiemodelleren.aspx) voor een iets langer overzicht.


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

### [7] beheertools

- Interne server die beheertaken automatiseert.

### [9] register.geostandaarden.nl

- Technisch register met xsds, json-schema etc.

### [13] Nationaal Georegister

- Staat los van de rest van de publicatie infrastructuur.

### [14] Web server van Geonovum

- Staat los van rest van publicatie infrastructuur.




## Documentatie

### [1] UML

- [Overzicht](EA/index.md)
- [Primitieve datatypes](EA/EA-toepassing-standaarddatatypen.md): Handleiding
    en toelichting op het toepassen van standaarddatatypes in
    modelleeromgeving Geonovum.
- [Toolbox importeren](EA/MIM-toolbox-importeren.md): Handleiding voor het
    importeren van de MIM-toolbox in EA.

### [2] Subversion

- [Subversion installeren voor EA](SVN-importeren-bestaand-project.md):
    Installatie SVN en informatiemodel in versiebeheer zetten.
- [Subversion importeren bestaand project](SVN-installeren-voor-EAP.md):
    Packages importeren vanuit SVN in EA.

### [3] Imvertor

- [Imvertor](Imvertor.md): Verwijzingen naar verschillende onderwerpen met
    betrekking tot Imvertor.

### [4] ReSpec
- [Respec handleiding](ReSpec/): Algemene handleiding.
- [Respec code toepassen](ReSpec/ReSpec-code-toepassen.md): Richtlijnen voor het
    toepassen van code in documentatie.
- [Respec definitielijst maken](ReSpec/ReSpec-definitielijst-maken.md):
    Handleiding voor het maken van een definitielijst in
    ReSpec-documentatie.

### [5] GitHub
- [GitHub werkwijze](GitHub/GitHub-Inleiding.md): algemene inleiding over GitHub.
- [GitHub handleiding](GitHub/index.md): Hoe maak je een account aan en hoe doe
    je beheertaken.

### [6] docs.geostandaarden.nl
- Zie [pubDomainList.json](https://github.com/Geonovum/respec-utils/blob/master/src/autodeploy/config/pubDomainList.json)


### [9] register.geostandaarden.nl

Zie [publiceren op register.geostandaarden.nl](publicaties/#register.geostandaarden.nl)

### [10] Markdown
 - [Markdown handleiding](Markdown.md): Handleiding werken met Markdown
     voor ReSpec-documentatie.

### MIM
- [Toolbox genereren](EA/MIM-toolbox-genereren.md): Handleiding voor het
    maken van een EA-toolbox.
- [Toolbox genereren extensie](EA/MIM-toolbox-genereren-extensie.md):
    Handleiding voor het maken van een extensie op de MIM-toolbox.

### GML

- [GML](GML.md): Toelichting GML, XSD en Namespaces.

### Ontologie

- [Ontologie](Handleiding-ontologie-maken-en-publiceren.md): Handleiding
    voor het maken en publiceren van een ontologie.

### Word2XXX

- [Word2werkversie](WordConversies.md)

### Ontologieën (modellen.geostandaarden.nl)

Er is één ontologie gepubliceerd: die van NEN 3610. 

Dit is uitgelegd in de [handleiding ontologie maken](Handleiding-ontologie-maken-en-publiceren.md)

## beheer

Voor licenties of de interne beheerder van de tooling kun je terecht op
[intranet](https://stichtinggeonovum.sharepoint.com/:b:/r/sites/FBICT/Gedeelde%20documenten/General/wat%20staat%20waar/Tooling_en_Beheerders.pdf?csf=1&web=1&e=aEcKjl)

## Aandachtspunten

- **Algemeen**
    - Het is niet één gezicht naar buiten maar meerdere. De samenhang kan beter.
- **UML**
    - Er is een alternatieve tool voor UML. Wat gaan we daar mee doen? [Modeldesk](https://modeldesk.io/).
- **Imvertor**
    - De beheerders van Imvertor willen binnenkort met pensioen.
    - Imvertor is niet echt modulair
- **modellen.geostandaarden.nl**
    - Hoe kan het dat hier maar 1 standaard op staat?
- **docs.geostandaarden.nl**
    - De gegevens op deze server worden slecht beheerd. We hebben ideeën voor een mooie beheeromgeving maar die is er nog niet.
    - Documenten op de site zouden self contained moeten zijn maar sommige verwijzen naar css bestanden op register.geostandaarden.nl waardoor gepubliceerde standaarden opeens onleesbaar kunnen worden.
- **definities.geostandaarden.nl**
    - Er zijn hiervoor twee verschillende werkwijzes die een verschillend resultaat leveren. Goede beschrijving werkwijze is hier nodig.
- **register.geostandaarden.nl**
    - De documenten die hierop staan zijn niet in beheer.
- **beheertools**
    - Deze server moet zelf in beheer genomen worden.
- **GitHub**
    - Deze server is publiek waardoor alles wat hierop staat publiek is.
- **ReSpec**
    - Heel veel documenten zijn van minder dan gewenste kwaliteit omdat er geen goede kwaliteitscriteria en controle mechanismes zijn.
- **Website Geonovum**
    - Beheer links met technische servers is vooral handmatig.
    - Scheiding met technische servers kan leiden tot lagere ranking documenten bij zoeken.
- **Microsoft teams**
    - Dit is vooral een intern systeem waardoor samenwerking met externe partijen soms lastig is.
    - Alle teams zouden voor iedereeen binnen Geonovum zichbaar moeten zijn maar zijn dat niet.
    - Onderscheid tussen dingen die per jaar gaan en dingen die per project gaan is niet goed geregeld.
    - Heel veel spookmappen en document die bij niemand bekend zijn.

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
