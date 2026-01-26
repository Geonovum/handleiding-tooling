# Tooling

Dit is de publicatie infrastructuur van Geonovum. Onder het architectuurplaatje staan:

- Een korte [beschrijving](#kort-overzicht).
- Verwijzing naar [documentatie](#documentatie).
- Aandachtspunten [verbeterpunten](#aandachtspunten).
- Hoe we de boel beheren staat in [wie beheert wat](#beheer).

![publicatie infrastructuur](media/PublicatieInfrastructuurGeonovum.drawio.svg)

## Kort Overzicht

### [1] UML

- UML klasse diagrammen maken we met Enterprise Architect. (zie [UML](UML/index.md))
- Binnen UML gebruiken we MIM als meta-taal. (zie [MIM](MIM/index.md))
- We gebruiken NEN 3610 als raamwerk.
- [Overzicht](EA/index.md)
- [Primitieve datatypes](EA/EA-toepassing-standaarddatatypen.md): Handleiding
    en toelichting op het toepassen van standaarddatatypes in
    modelleeromgeving Geonovum.
- [Toolbox importeren](EA/MIM-toolbox-importeren.md): Handleiding voor het
    importeren van de MIM-toolbox in EA.

### [2] Subversion

- De UML diagram worden met subversion (svn) beheerd. (zie [svn](svn/index.md))
- De repositories staan op `svn.geostandaarden.nl`
- [Subversion installeren voor EA](svn/SVN-importeren-bestaand-project.md):
    Installatie SVN en informatiemodel in versiebeheer zetten.
- [Subversion importeren bestaand project](svn/SVN-installeren-voor-EAP.md):
    Packages importeren vanuit SVN in EA.


### [3] Imvertor

- Imvertor vertaalt het UML naar catalog, xsd etc. (zie [Imvertor](Imvertor/index.md))

### [4] ReSpec document

- Onze standaarden maken we in ReSpec. (zie [ReSpec](ReSpec/index.md))
- Dit is een tool die uit een aantal bestanden (Markdown, HTML) een mooi document publiceert.
- De bestanden beheren we in GitHub

### [5] GitHub

- Onze standaarden beheren en versioneren we in GitHub.
- [GitHub werkwijze](GitHub/GitHub-Inleiding.md): algemene inleiding over GitHub.
- [GitHub handleiding](GitHub/index.md): Hoe maak je een account aan en hoe doe
    je beheertaken.

### [6] docs.geostandaarden.nl

- Onze standaarden publiceren we op docs.geostandaarden.nl
- Dit gebeurt via een geautomatiseerde workflow die in onze github repositories werkt. 

### [7] tools.geostandaarden.nl

Op deze server staan css bestanden en hulpbestanden voor ReSpec. Ook staan
hier de logo's die in docs.geostandaarden.nl gebruikt worden.

### [7] beheertools

Interne server die beheertaken automatiseert.

### [8] Word2ResSpec

- [Word2werkversie](Word2xxx/index.md)

### [9] register.geostandaarden.nl

Technisch register met xml-schemas, json-schemas etc.
Invulinstructies: [https://github.com/Geonovum/technisch-register-2019/blob/master/documentatie/HandleidingVoorBeheerdersInformatiemodellen.md](https://github.com/Geonovum/technisch-register-2019/blob/master/documentatie/HandleidingVoorBeheerdersInformatiemodellen.md)
 
Technische onderdelen van de standaard worden op: [register.geostandaarden.nl](https://register.geostandaarden.nl) gezet. Hoe je dit met een webhook kan doen staat beschreven in: [technisch-register-2019](https://github.com/Geonovum/technisch-register-2019/blob/master/documentatie/Handleiding%20voor%20beheerders%20informatiemodellen.md)

Invulinstructies: <https://github.com/Geonovum/technisch-register-2019/blob/master/documentatie/HandleidingVoorBeheerdersInformatiemodellen.md>

Technische onderdelen van de standaard worden op:
[register.geostandaarden.nl](https://register.geostandaarden.nl) gezet. Hoe je
dit met een webhook kan doen staat beschreven in:
[technisch-register-2019](https://github.com/Geonovum/technisch-register-2019/blob/master/documentatie/Handleiding%20voor%20beheerders%20informatiemodellen.md)

**UML**

In de map `informatiemodel` wordt een informatiemodel gepubliceerd. Publicatieinstructies:

**EAP**

Dit is het natieve formaat van Enterprise Architect.

- Zorg ervoor dat alle links naar svn uit het bestand verwijderd zijn: selecteer een beheerde folder. Kies 'Configure->Package-VC'. Haal het vinkje weg bij 'Control Package'.
- Zet de versienummer van het model in de bestandsnaam.

**xmi**

xmi is het uitwisselformaat voor UML modellen. Er zijn veel smaken. Voorstel voor manier van publiceren:

- Niet alleen het model, maar ook alle packages waarnaar verwezen wordt.
- Selecteer het te exporteren root package. Kies 'Publish-->Export XML'.
- Kies Export Type: 'XML 1.1'.

### [10] Markdown
 - [Markdown handleiding](Markdown/index.md): Handleiding werken met Markdown
     voor ReSpec-documentatie.

### [11] Ontologie (modellen.geostandaarden.nl)

- [Ontologie](Ontologie/index.md): Handleiding
    voor het maken en publiceren van een ontologie.

### [13] Nationaal Georegister

Staat los van de rest van de publicatie infrastructuur.

### [14] Web server van Geonovum

Staat los van rest van publicatie infrastructuur.


## beheer

Voor licenties of de interne beheerder van de tooling kun je terecht op
[intranet](https://stichtinggeonovum.sharepoint.com/:b:/s/FBICT/IQC8YxUUkR6tRr6RnMcPSmOgAQxZOKTlWu6-wg4oWK6oiwI?e=5SyNFk)

## Aandachtspunten

- **Algemeen**
    - Het is niet één gezicht naar buiten maar meerdere. De samenhang kan beter.
- **UML**
    - We gebruiken ook [Modeldesk](https://modeldesk.io/).
- **modellen.geostandaarden.nl**
    - Hoe kan het dat hier maar 1 standaard op staat?
- **docs.geostandaarden.nl**
    - Documenten op de site zouden self contained moeten zijn maar sommige verwijzen naar css bestanden op register.geostandaarden.nl waardoor gepubliceerde standaarden opeens onleesbaar kunnen worden.
- **definities.geostandaarden.nl**
    - Er zijn hiervoor twee verschillende werkwijzes die een verschillend resultaat leveren. Goede beschrijving werkwijze is hier nodig.
- **beheertools**
    - Deze server moet zelf in beheer genomen worden.
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
