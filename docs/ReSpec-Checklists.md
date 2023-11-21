# Checklist voor publicatie

In dit hoofdstuk staan checklists die je kan gebruiken als je vanuit GitHub en ReSpec “Versies” gaat aanmaken. Bijvoorbeeld hoe maak je een nieuwe GitHub repository aan, of hoe maak je vanuit een werkversie een consultatieversie aan,

## Een nieuwe ReSpec repository maken

1. Maak een nieuw repository op basis van [de ReSpec template](https://github.com/Geonovum/NL-ReSpec-GN-template) en kies 'Use this template'
2. Check met behulp van GitHub Desktop het nieuwe repository uit 'File/Clone Repository...'.
3. Pas in `index.html` de betreffende velden aan
4. Pas in `config.js` de betreffende velden aan
    - Pas het `specType` aan. (TODO: welke zijn er?)
    - `pubDomain`: de documentgroep waar het doc toe behoort. Moet ingevuld zijn. Er is een lijst met afkortingen. Je mag ook een nieuwe groep bedneken maar geen wildgroei graag
5. Maak content in Markdown

## Controles voor publicatie

Controleer de volgende onderwerpen voor iedere publicatie:

- Controleer op WCAG regels. Bij het pushen van een ReSpec document naar GitHub wordt automatisch een WCAG rapport geschreven. Dit is te vinden onder 'Actions'. Kies hier de commit die je gedaan hebt en je ziet daar 'Check/WCAG').
- Controleer op Broken links. Bij het pushen van een ReSpec document naar GitHub wordt automatisch op broken links gechecked. Dit is te vinden onder 'Actions'. Kies hier de commit die je gedaan hebt en je ziet daar 'Check/Links').
- Je kunt oook het HTML controleren: maak een snapshot aan en biedt het aan aan de [W3C validator](https://validator.w3.org)

## Consultatie versie (CV) maken

1. Edit en controleer config.js - configureer alles goed voor een consultatieversie
    - `specStatus`:`"GN-CV"`
    - `publishDate`: moet ingevuld zijn met de datum van publicatie van de consultatieversie. `"jjjj-mm-dd"`,
    - `Shortname`: moet ingevuld zijn met korte naam voor het document. Dit wordt onderdeel van de URL. Moet uniek zijn binnen pubdomain (afgezien van versies).
        -  Als er al eerder een versie gepubliceerd is (stabiele versie, dus afgezien van de werkversie in github), kan Respec bovenin een document de navigatie naar vorige versie goed genereren. Daarvoor moet je ook invullen:
        - `Previousmaturity`: wat de status toen was.
        - `Previousmaturity`: wat de status toen was.
1. Maak een snapshot (met de knop “Bewaar Snapshot” vanuit Respec)
1. Kies “HTML” en noem dit bestand “snapshot.html”
1. Commit het en push het naar dezelfde folder als waar `index.html` staat in je Github-repository

### Consultatieversie maken met behulp van webhook

[Klik hier](/Publiceren/) voor een beschrijving over hoe je een webhook eenmalig configureert voor een repository. over het toepassen van de webhook.

1.  Maak een release tag conform de naamgevingsconventie: `\{specStatus\}-\{specType\}-\{shortName\}-\{publishDate\}`
1. Het script kopieert nu automatisch (NB: dit moet wel eenmalig geconfigureerd zijn als ‘webhook’ in de github repository!) het `snapshot.html` en de bijbehorende afbeeldingen naar [docs.geostandaarden.nl]http://docs.geostandaarden.nl).
1. Na succesvolle publicatie: 	
    - zet de `specStatus` in `config.js` terug op `"GN-WV"`
    - Vul `previousMaturity` in met `"GN-CV"`
    - Vul `previousPublishDate` in met de datum van de zojuist gepubliceerde consultatieversie


### Consultatieverise met behulp van webhook.

> **Note**: uitwerken

## Vaststellingsversie (VV) maken

1. Edit en controleer config.js - configureer alles goed voor een vaststellingsversie
    - specStatus: "GN-VV"
    - publishDate: moet ingevuld zijn met de datum van publicatie van de consultatieversie. "jjjj-mm-dd",
    - Shortname: moet ingevuld zijn met korte naam voor het document. Dit wordt onderdeel van de URL. Moet uniek zijn binnen pubdomain (afgezien van versies).
        -  Als er al eerder een versie gepubliceerd is (stabiele versie, dus afgezien van de werkversie in github), kan Respec bovenin een document de navigatie naar vorige versie goed genereren. Daarvoor moet je ook invullen:
        - Previousmaturity: wat de status toen was.
        - Previousmaturity: wat de status toen was.
2. Maak een snapshot (met de knop “Bewaar Snapshot” vanuit Respec)
3. Kies “HTML” en noem dit bestand “snapshot.html”
4. Commit het en push het naar dezelfde folder als waar index.html staat in je Github repository
5.  Maak een release tag conform de naamgevingsconventie: \{specStatus\}-\{specType\}-\{shortName\}-\{publishDate\}
6. Het script kopieert nu automatisch (NB: dit moet wel eenmalig geconfigureerd zijn als ‘webhook’ in de github repository!) het snapshot.html en de bijbehorende afbeeldingen naar http://docs.geonovum.nl
7. Na succesvolle publicatie: 	
    - zet de specStatus in config.js terug op GN-WV
    - Vul previousMaturity in met GN-CV
    - Vul previousPublishDate in met de datum van de zojuist gepubliceerde consultatieversie


## Definitieve versie (DEF) maken

1. Edit en controleer config.js - configureer alles goed voor een definitieve versie
    - specStatus: "GN-DEF",
    - publishDate: moet ingevuld zijn met de datum van publicatie van de definitieve versie. "jjjj-mm-dd",
    - Shortname: moet ingevuld zijn met korte naam voor het document. Dit wordt onderdeel van de URL. Moet uniek zijn binnen pubdomain (afgezien van versies).
    - Als er al eerder een versie gepubliceerd is (stabiele versie, dus afgezien van de werkversie in github), kan Respec bovenin een document de navigatie naar vorige versie goed genereren. Daarvoor moet je ook invullen:
        - Previousmaturity: wat de status toen was.
        - previousPublishDate: vorige publicatiedatum (jjjj-mm-dd)
2. Maak een snapshot (met de knop “Bewaar Snapshot” vanuit Respec)
3. Kies “HTML” en noem dit bestand “snapshot.html”
4. Commit het en push het naar dezelfde folder als waar index.html staat in je Github repository
6. Maak een release tag conform de naamgevingsconventie: {specStatus}-{specType}-{shortName}-{publishDate}
7. Het script kopieert nu automatisch (NB: dit moet wel eenmalig geconfigureerd zijn als ‘webhook’ in de github repository!) het snapshot.html en de bijbehorende afbeeldingen naar http://docs.geostandaarden.nl Hoe dit werkt is beschreven in: https://github.com/Geonovum/technisch-register-2019
8. Na succesvolle publicatie:
    - zet de specStatus in config.js terug op GN-WV
    - Vul previousMaturity in met GN-DEF
    - Vul previousPublishDate in met de datum van de zojuist gepubliceerde definitieve versie