# Publiceren van een ReSpec document

Het publiceren van een ReSpec document bestaat uit het omzetten van de werkversie
van dat document op GitHub naar een vaststellingsversie, consultatieversie of definitieve versie en het neerzetten van die versie op <https://docs.geostandaarden.nl>. Dit gaat in een aantal stappen:

1. Zet de werkversie klaar voor publicatie door in config.js de velden `pubDomain`, `shortName`, `publishDate`, `specStatus` en evt. `specType`, `previousMaturity` en `previousPublishDate` in te vullen. 
2. Zorg ook dat de automatische controle (bij push naar github) geen fouten meer geeft. 
3. Door in het GitHub repository op 'Draft a new Release' te drukken wordt het publicatieproces automatisch in werking gezet wat resulteert in publicatie op <https://docs.geostandaarden.nl>, of als je het vinkje 'set as a pre-release` zet op <https://test.docs.geostandaarden.nl>. Dit zorgt voor een pull request op <https://github.com/Geonovum/docs.geostandaarden.nl>. Een pre-release wordt automatisch goedgekeurd. Een officiële release moet goedgekeurd worden door een reviewer.
4.  Als de release gelukt is begint het proces weer van voor af aan en zet je in de werkversie de specStatus weer op `wv`. Ook laat je `previousMaturity`en `previousPublishDate` verwijzen naar de zojuist gepubliceerde versie.

## Stap 1: zet de werkversie klaar voor publicatie

Zorg dat je werkversie op GitHub helemaal klaarstaat voor publicatie door in config.js `pubDomain`, `shortName`, `publishDate`, `specStatus` en evt. `specType`, `previousMaturity` en `previousPublishDate` in te vullen. Zorg ook dat de automatische controle (bij push naar github) geen fouten meer geeft.

De status van een document staat in het veld `specStatus`. Documenten met de status 'wv' (werkversie) staat altijd op github. Te publiceren documenten hebben één van de volgende statussen:

- 'cv': voor een consultatieversie.
- 'vv': voor een vaststellingsversie.
- 'def': voor een definitieve versie.
- 'ld': voor een levend document.

- 'basis': ***nog beschrijven***

De velden `previousmaturity` en `previousPublishDate` moeten ingevuld zijn. Deze velden zorgen ervoor dat het nieuw gepubliceerde document verwijst naar de vorige gepubliceerde versie waardoor door steeds op 'vorige' te klikken alle versies van een document te vinden blijven.

**Noot:** Automatisch publiceren werkt alleen wanneer er, conform de [werkwijze](./index.md#respec-via-markdown), één ReSpec document in een repository staat. Als er meerdere Respec documenten in een repository staan kun je [handmatig publiceren](#handmatig-publiceren-van-respec-document).

## Stap 2: Fouten bij push oplossen

**Tip**: Probeer de fouten steeds na een push op te lossen zodat wellicht duidelijker is wat de oorzaak is.

Details om problemen op te lossen staan op een [aparte pagina](ReSpec-problemen.md/#fouten-bij-push-oplossen) en zijn alleen van toepassing als er problemen (❌) in het document aanwezig zijn.  

  
## Stap 3: Maak een (Test)Release

Via het knopje 'Draft a new Release' start je het publicatieproces. Er verschijnt het volgende scherm:

![Release a Document](media/ReleaseADocument.png)

Vul de velden als volgt in:

- Tag: kies hier een tag voor de release. Conventie: `[specStatus]-[spectype]-[shortName]-[publishDate]/`
- Release title: mens leesbare naam.
- Set as a pre-release: gaat het om een testversie of een officiële publicatie?

Door de knop 'Publish release' in te drukken wordt het publicatieproces gestart. Dit kan enige tijd duren. Afhankelijk van of het een test release is of gebeurt het volgende:

- Bij een test-release wordt de publicatie automatisch goedgekeurd en gepubliceerd op <https://test.docs.geostandaarden.nl>. 
- Bij een officële release resulteert de publicatie in een pull request op <https://github.com/Geonovum/docs.geostandaarden.nl>. Eén van de reviewers checkt de publicatie en na goedkeuring verschijnt deze automatisch.

Voor deze automatische publicatie gelden de volgende eisen, naast uitgangspunten en controles zoals beschreven bij **stap 2**: GEEN?

Meer documentatie staat in de readme van [NL-ReSpec-template](https://github.com/Geonovum/NL-ReSpec-template?tab=readme-ov-file#automatische-checks-en-build).

### Stap 4: Zet de 'specStatus' weer op werkversie

Als de publicatie gelukt is begin het werk aan de volgende versie. Deze
start weer als werkversie. Zet in je beheerdocument de specStatus weer op 'wv'.


### Configureren van de automatische workflow

Bij het maken van een nieuw ReSpec document via de [template](https://github.com/Geonovum/NL-ReSpec-template) krijg je de workflow automatisch. De repository bevat dan alleen twee kleine workflows in `.github/workflows/`: `main.yml` en `visual-regression.yml`. Die roepen de centrale build-, controle- en publicatiestappen aan uit [NL-ReSpec-workflows](https://github.com/Geonovum/NL-ReSpec-workflows). Pas deze twee bestanden niet zelf aan; ze worden centraal bijgehouden.

Alle actieve repositories waarin een `js/config.js` staat, worden vanuit NL-ReSpec-workflows automatisch bijgewerkt. Je kan controleren of de workflow is geïnstalleerd door `.github/workflows/main.yml` in je repository te openen: daarin moet `Geonovum/NL-ReSpec-workflows` staan.

Staat de workflow er niet in, vraag dan Linda, Wilko, Inge of Matthijs om je repository mee te nemen in de centrale update. Je kan de twee bestanden ook zelf toevoegen:

1. Open in NL-ReSpec-workflows de map [`document-repo/.github/workflows`](https://github.com/Geonovum/NL-ReSpec-workflows/tree/main/document-repo/.github/workflows).
1. Maak in je eigen repository via **Add file** → **Create new file** het bestand `.github/workflows/main.yml` aan en plak de inhoud van `main.yml` erin. Doe hetzelfde voor `visual-regression.yml`.
1. Staan er in `.github/workflows/` nog oude bestanden zoals `build.yml`, `publish.yml` of `pdf.js`, verwijder die dan.

## 'Handmatig' publiceren van respec document.

Het is ook mogelijk om documenten handmatig te publiceren op docs.geostandaarden.nl:

- docs.geostandaarden.nl is een mirror van: <https://github.com/Geonovum/docs.geostandaarden.nl/>
- Bij handmatige publicatie wijzig je rechtstreeks de repository. Maak in dit geval een pull request voor het repository met de publish-versie van je respec-document' (~ snapshot.html als index.html +media) en laat het goedkeuren zoals hierboven beschreven.
- In noodgevallen kunnen beheerders ook zonder pull request wijzigingen doorvoeren. In dat geval moet <docs.geostandaarden.nl> handmatig gesynchroniseerd worden. Dat kan via <https://github.com/Geonovum/docs.geostandaarden.nl/actions/workflows/deploy.yml> . Hier zie je een knopje: ‘Run workflow’.
