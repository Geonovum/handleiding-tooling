# Checklists

In dit hoofdstuk staat een aantal checklists die je kan gebruiken als je vanuit GitHub en ReSpec “Versies” gaat aanmaken. Bijvoorbeeld hoe maak je een nieuwe GitHub repository aan, of hoe maak je vanuit een werkversie een consultatieversie aan,

## Een nieuwe ReSpec repository maken

1. Maak een nieuw repository op basis van [de ReSpec template](https://github.com/Geonovum/NL-ReSpec-GN-template) en kies 'Use this template'
2. Check met behulp van GitHub Desktop het nieuwe repository uit 'File/Clone Repository...'.
3. Pas in `index.html` de betreffende velden aan
4. Pas in `config.js` de betreffende velden aan
    - Pas het `specType` aan. (TODO: welke zijn er?)
    - `pubDomain`: de documentgroep waar het doc toe behoort. Moet ingevuld zijn. Er is een lijst met afkortingen. Je mag ook een nieuwe groep bedneken maar geen wildgroei graag
5. Maak content in Markdown

## Controles voor publicatie

1. Valideer HTML en links:
    -  Neem de link naar de werkversie van je document, bijvoorbeeld `https://geonovum.github.io/Metadata-ISO19115/`, en zet daar `snapshot.html` achter. Dus: `https://geonovum.github.io/Metadata-ISO19115/snapshot.html`
    -  De volgende stap is: [HTML valideren](https://validator.w3.org). Plak de github.io- link uit stap 1 in het Address veld en klik Check. De validator gaat nu valideren en geeft het foutrapport terug.
    -  Hierna kun je de [links checken](https://validator.w3.org/checklink). Plak de github.io-link uit stap 1 in het input veld en klik weer op Check. De links worden nu gecontroleerd. Dit duurt even omdat op de achtergrond alle links in het document nu bezocht worden. Als het klaar is krijg je het rapport terug. NB als er links naar docs.geostandaarden.nl, naar het document dat je aan het checken bent, worden gerapporteerd als gebroken, kun je dit negeren. Dit komt doordat het document daar nu nog niet gepubliceerd staat.
    - Los eventuele HTML fouten en gebroken links op en maak een nieuw snapshot, en commit dit naar dezelfde plek als de vorige keer.


## Consultatie versie (CV) maken

1. Edit en controleer config.js - configureer alles goed voor een consultatieversie
    - `specStatus`:`"GN-CV"`
    - `publishDate`: moet ingevuld zijn met de datum van publicatie van de consultatieversie. `"jjjj-mm-dd"`,
    - `Shortname`: moet ingevuld zijn met korte naam voor het document. Dit wordt onderdeel van de URL. Moet uniek zijn binnen pubdomain (afgezien van versies).
        -  Als er al eerder een versie gepubliceerd is (stabiele versie, dus afgezien van de werkversie in github), kan Respec bovenin een document de navigatie naar vorige versie goed genereren. Daarvoor moet je ook invullen:
        - `Previousmaturity`: wat de status toen was.
        - `Previousmaturity`: wat de status toen was.
2. Maak een snapshot (met de knop “Bewaar Snapshot” vanuit Respec)
3. Kies “HTML” en noem dit bestand “snapshot.html”
4. Commit het en push het naar dezelfde folder als waar `index.html` staat in je Github-repository
6.  Maak een release tag conform de naamgevingsconventie: `\{specStatus\}-\{specType\}-\{shortName\}-\{publishDate\}`
7. Het script kopieert nu automatisch (NB: dit moet wel eenmalig geconfigureerd zijn als ‘webhook’ in de github repository!) het `snapshot.html` en de bijbehorende afbeeldingen naar [docs.geostandaarden.nl]http://docs.geostandaarden.nl).
8. Na succesvolle publicatie: 	
    - zet de `specStatus` in `config.js` terug op `"GN-WV"`
    - Vul `previousMaturity` in met `"GN-CV"`
    - Vul `previousPublishDate` in met de datum van de zojuist gepubliceerde consultatieversie

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


\