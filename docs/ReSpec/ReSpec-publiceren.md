# Publiceren van een ReSpec document

## Handmatig publiceren
Handmatig publiceren van een ReSpec document met FTP is niet meer mogelijk. 

## Automatisch publiceren
We gebruiken een automatische publicatieworkflow voor het publiceren van ReSpec documenten op [docs.geostandaarden.nl](https://docs.geostandaarden.nl). 

**Noot**
Automatisch publiceren werkt alleen in Github repositories waar, conform de [werkwijze](./index.md#respec-via-markdown), maar één ReSpec document in staat. 

### Aan de praat krijgen van de automatische workflow
De workflow wordt automatisch geïnstalleerd in de meeste github repositories waarin ReSpec documenten ontwikkeld worden binnen https://github.com/geonovum. Bij het maken van een nieuw ReSpec document via de [template](https://github.com/Geonovum/NL-ReSpec-template) wordt de workflow automatisch geïnstalleerd. In github repositories die al een ReSpec document hadden voordat de nieuwe publicatieworkflow werd geïntroduceerd, is de workflow meestal ook al geinstalleerd. Alle actieve repositories waar een 'js/config.js' in gevonden is, hebben de nieuwe workflow gekregen.

Je kan controleren of de workflow is geïnstalleerd door bovenin de README.md in je repository te kijken. Hier moet in staan: 

> Deze repository is automatisch bijgewerkt naar de nieuwste workflow. Voor vragen, neem contact op met Linda van den Brink of Wilko Quak.
> Als je een nieuwe publicatie wilt starten, lees dan eerst de instructies in de README van de NL-ReSpec-template: https://github.com/Geonovum/NL-ReSpec-template.

Als de workflow niet automatisch is geïnstalleerd, kun je dit zelf doen. Dit is een eenmalige stap. Mocht dit niet lukken, dan kan Linda, Wilko of Matthijs erbij helpen:

**Zorg dat Git is geïnstalleerd en beschikbaar is in je terminal**

1. Open de **Opdrachtprompt**:
    - ➜ Druk op de **Windows-knop**, typ `cmd`, druk op **Enter**
1. Typ vervolgens in de cmd terminal:
    - `git --version`
    - Zie je een versie zoals `git version 2.x.x`, dan is alles goed.
1. Krijg je een foutmelding zoals `'git' is not recognized as an internal or external command`, dan moet je Git nog installeren via: https://git-scm.com/downloads/win
 
**Vervolg, na installatie van git**

1. **Navigeer naar de repository in Verkenner**
1. Open de map waarin de repository staat
    - **Shift** + **rechter muisklik** in een lege ruimte in de map
    - Kies **"PowerShell-venster hier openen"** of **"Open in terminal"**
1. **Download en voer het script uit**
1. Kopieer en plak de volgende regels in PowerShell, voer ze om beuren uit:
    1. `curl -o replace_workflow-local.ps1 https://raw.githubusercontent.com/Geonovum/NL-ReSpec-template/main/replace_workflow-local.ps1`
    1. `Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass`
    1. `.\replace_workflow-local.ps1`
1. Als er geen errors verschijnen is dit gelukt. Je kunt dit checken door README.md te openen: als het goed is staat hier nu bovenin een tekst die begint met "Deze repository is automatisch bijgewerkt..."

**Tenslotte**

1. Verwijder het bestand "replace_workflow-local.ps1"

### Automatisch publiceren via de workflow

De automatische workflow gaat aan het werk bij elke keer dat je iets commit in de github repository, en bij elke keer dat je een Release aanmaakt in github. De stappen om een ReSpec document te publiceren naar docs.geostandaarden.nl via de workflow zijn als volgt:

1. configureer je document op de juiste manier (zie [Publiceren in ReSpec](./index.md#publiceren-in-respec) voor meer informatie) en commit je wijzigingen.
    1. Er wordt een HTML snapshot aangemaakt via ReSpec
    1. (optioneel) PDF wordt gegenereerd indien je dit geconfigureerd hebt
    1. WCAG (web toegankelijkheidseisen) en HTML worden gevalideerd
    1. Links worden gecontroleerd
1. Bekijk de resultaten van de controles via het tabblad **Actions** van de repository. Als er fouten gevonden zijn, los deze dan op en herhaal stap 1, of vraag om hulp.
1. (optioneel) maak een Pre-release aan in de github repository. 
    - Het ReSpec document wordt automatisch gepubliceerd op [test.docs.geostandaarden.nl](https://test.docs.geostandaarden.nl/). Je kunt het hier bekijken om te zien of alles goed is gegaan.
1. Maak een Release aan in de github repository (zie [Publiceren in ReSpec](./index.md#publiceren-in-respec) voor meer informatie). 
    - Er wordt automatisch een Pull Request (PR) aangemaakt naar: Geonovum/docs.geostandaarden.nl
    - Na goedkeuring van de PR (door Wilko, Frank of Linda) wordt het document gepubliceerd op: https://docs.geostandaarden.nl/

Meer documentatie staat in de readme van [NL-ReSpec-template](https://github.com/Geonovum/NL-ReSpec-template?tab=readme-ov-file#automatische-checks-en-build).