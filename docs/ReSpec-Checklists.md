# Checklists

In dit hoofdstuk staat een aantal checklists die je kan gebruiken als je vanuit GitHub en ReSpec “Versies” gaat aanmaken. Bijvoorbeeld hoe maak je een nieuwe GitHub repository aan, of hoe maak je vanuit een werkversie een consultatieversie aan,

## Een nieuwe ReSpec repository maken 

| Stap | Omschrijving                                                                                                                                   |
| ---- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| 1    | Maak een nieuw repository op basis van de ReSpec template. Open: https://github.com/Geonovum/NL-ReSpec-GN-template en kies 'Use this template' |
| 2    | Check met behulp van GitHub Desktop het nieuwe repository uit 'File/Clone Repository...'.                                                      |
| 3    | Pas in index.html de betreffende velden aan                                                                                                    |
| 4    | Pas in config.js de betreffende velden aan                                                                                                     |
| 5    | Maak content in Markdown |


## Consultatie versie (CV) maken

<table style='width: 100%;'><caption></caption>
<colgroup><col id='col1' style='width: 7.9519186315302814%;'
<col id='col2' style='width: 77.18446601941747%;'
<col id='col3' style='width: 14.863615349052242%;'
</colgroup>
<tbody valign='top'><tr><td align='left' ><b>Stap</b>

</td>
<td align='left' ><b>Omschrijving</b>

</td>
<td align='left' ><b>Check</b>

</td>
</tr>
<tr><td align='left' >1

</td>
<td align='left' >Edit en controleer config.js - configureer alles goed voor een consultatieversie

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' ></td>
<td align='left' ><ul><li>specStatus: "GN-CV",</li>
</ul>

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' ></td>
<td align='left' ><ul><li>specType: het doc type.</li>
</ul>

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' ></td>
<td align='left' ><ul><li>pubDomain: de documentgroep waar het doc toe behoort. Moet ingevuld zijn. Er is een lijst met afkortingen. Je mag ook een nieuwe groep bedneken maar geen wildgroei graag</li>
</ul>

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' ></td>
<td align='left' ><ul><li>publishDate: moet ingevuld zijn met de datum van publicatie van de consultatieversie. "jjjj-mm-dd",</li>
</ul>

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' ></td>
<td align='left' ><ul><li>Shortname: moet ingevuld zijn met korte naam voor het document. Dit wordt onderdeel van de URL. Moet uniek zijn binnen pubdomain (afgezien van versies).</li>
</ul>

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' ></td>
<td align='left' ><ul><li>Als er al eerder een versie gepubliceerd is (stabiele versie, dus afgezien van de werkversie in github), kan Respec bovenin een document de navigatie naar vorige versie goed genereren. Daarvoor moet je ook invullen:</li>
<li>Previousmaturity: wat de status toen was.</li>
<li>previousPublishDate: vorige publicatiedatum (jjjj-mm-dd)</li>
</ul>

</td>
<td align='left'></td>
</tr>
<tr><td align='left'>2

</td>
<td align='left' >Maak een snapshot (met de knop “Bewaar Snapshot” vanuit Respec)

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' >3

</td>
<td align='left'>Kies “HTML” en noem dit bestand “snapshot.html”

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' >4

</td>
<td align='left' >Commit het en push het naar dezelfde folder als waar index.html staat in je Github repository

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' >5

</td>
<td align='left' >Valideer HTML en links:

1.    Neem de link naar de werkversie van je document, bv https://geonovum.github.io/Metadata-ISO19115/, en zet daar ‘snapshot.html’ achter. Dus 

https://geonovum.github.io/Metadata-ISO19115/snapshot.html

2.    Ga om HTML te valideren naar https://validator.w3.org. Plak de github.io link uit stap 1 in het Address veld en klik Check. De validator gaat nu valideren en geeft het foutrapport terug. 

3.    Ga om links te checken naar https://validator.w3.org/checklink. Plak de github.io link uit stap 1 in het input veld en klik weer op Check. De links worden nu gecontroleerd. Dit duurt even omdat op de achtergrond alle links in het document nu bezocht worden. Als het klaar is krijg je het rapport terug. NB als er links naar docs.geostandaarden.nl, naar het document dat je aan het checken bent, worden gerapporteerd als gebroken, kun je dit negeren. Dit komt doordat het document daar nu nog niet gepubliceerd staat. <br/>4. Los eventuele HTML fouten en gebroken links op en maak een nieuw snapshot, en commit dit naar dezelfde plek als de vorige keer. 

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' >6

</td>
<td align='left'>Maak een release tag conform de naamgevingsconventie: <br/>\{specStatus\}-\{specType\}-\{shortName\}-\{publishDate\}<br/> \[Todo: een paar voorbeelden geven\]

</td>
<td align='left'></td>
</tr>
<tr><td align='left' >7

</td>
<td align='left' >Het script kopieert nu automatisch (NB: dit moet wel eenmalig geconfigureerd zijn als ‘webhook’ in de github repository!) het snapshot.html en de bijbehorende afbeeldingen naar <a href='http://docs.geonovum.nl' target='_blank'>http://docs.geonovum.nl</a>

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' >8

</td>
<td align='left' >Na succesvolle publicatie: 

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' ></td>
<td ><ul><li>zet de specStatus in config.js terug op GN-WV</li>
</ul>

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' ></td>
<td align='left' ><ul><li>Vul previousMaturity in met GN-CV</li>
</ul>

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' ></td>
<td align='left' ><ul><li>Vul previousPublishDate in met de datum van de zojuist gepubliceerde consultatieversie</li>
</ul>

</td>
<td align='left'></td>
</tr>
</tbody>
</table>

## Vaststellingsversie (VV) maken

Moet nog worden ingevuld.


## Definitieve versie (DEF) maken

<table style='width: 100%;'><caption></caption>
<colgroup><col id='col1' style='width: 8.079056865464633%;'
<col id='col2' style='width: 77.05732778548312%;'
<col id='col3' style='width: 14.863615349052242%;'
</colgroup>
<tbody valign='top'><tr><td align='left' ><b>Stap</b>

</td>
<td align='left' ><b>Omschrijving</b>

</td>
<td align='left' ><b>Check</b>

</td>
</tr>
<tr><td align='left' >1

</td>
<td align='left' >Edit en controleer config.js - configureer alles goed voor een definitieve versie

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' ></td>
<td align='left' >specStatus: "GN-DEF",

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' ></td>
<td align='left' >specType: het doc type.

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' ></td>
<td align='left' >pubDomain: de documentgroep waar het doc toe behoort. Moet ingevuld zijn. Er is een lijst met afkortingen. Je mag ook een nieuwe groep bedneken maar geen wildgroei graag

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' ></td>
<td align='left' >publishDate: moet ingevuld zijn met de datum van publicatie van de definitieve versie. "jjjj-mm-dd",

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' ></td>
<td align='left' >Shortname: moet ingevuld zijn met korte naam voor het document. Dit wordt onderdeel van de URL. Moet uniek zijn binnen pubdomain (afgezien van versies).

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' ></td>
<td align='left' ><ul><li>Als er al eerder een versie gepubliceerd is (stabiele versie, dus afgezien van de werkversie in github), kan Respec bovenin een document de navigatie naar vorige versie goed genereren. Daarvoor moet je ook invullen:</li>
<li>Previousmaturity: wat de status toen was.</li>
</ul>

previousPublishDate: vorige publicatiedatum (jjjj-mm-dd)

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' >2

</td>
<td align='left' >Maak een snapshot (met de knop “Bewaar Snapshot” vanuit Respec)

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' >3

</td>
<td align='left' >Kies “HTML” en noem dit bestand “snapshot.html”

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' >4

</td>
<td align='left' >Commit het en push het naar dezelfde folder als waar index.html staat in je Github repository

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' >5

</td>
<td align='left' >Valideer HTML en links:

1.    Neem de link naar de werkversie van je document, bv https://geonovum.github.io/Metadata-ISO19115/, en zet daar ‘snapshot.html’ achter. Dus 

https://geonovum.github.io/Metadata-ISO19115/snapshot.html

2.    Ga om HTML te valideren naar https://validator.w3.org. Plak de github.io link uit stap 1 in het Address veld en klik Check. De validator gaat nu valideren en geeft het foutrapport terug. 

3.    Ga om links te checken naar https://validator.w3.org/checklink. Plak de github.io link uit stap 1 in het input veld en klik weer op Check. De links worden nu gecontroleerd. Dit duurt even omdat op de achtergrond alle links in het document nu bezocht worden. Als het klaar is krijg je het rapport terug. NB als er links naar docs.geostandaarden.nl, naar het document dat je aan het checken bent, worden gerapporteerd als gebroken, kun je dit negeren. Dit komt doordat het document daar nu nog niet gepubliceerd staat. <br/>4. Los eventuele HTML fouten en gebroken links op en maak een nieuw snapshot, en commit dit naar dezelfde plek als de vorige keer. 

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' >6

</td>
<td align='left' ><img src='media/image33.png' alt='media/image33.png' style='width: 28.798560071996402%;'></img>
</td>
<td align='left' ></td>
</tr>
<tr><td align='left' >7

</td>
<td align='left' >Het script kopieert nu automatisch (NB: dit moet wel eenmalig geconfigureerd zijn als ‘webhook’ in de github repository!) het snapshot.html en de bijbehorende afbeeldingen naar <a href='http://docs.geonovum.nl' target='_blank'>http://docs.geostandaarden.nl</a> Hoe dit werkt is beschreven in: <a href='https://github.com/Geonovum/technisch-register-2019' target='_blank'>https://github.com/Geonovum/technisch-register-2019</a>  

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' >8

</td>
<td align='left' >Na succesvolle publicatie: 

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' ></td>
<td align='left' >zet de specStatus in config.js terug op GN-WV

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' ></td>
<td align='left' >Vul previousMaturity in met GN-DEF

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' ></td>
<td align='left' >Vul previousPublishDate in met de datum van de zojuist gepubliceerde definitieve versie

</td>
<td align='left' ></td>
</tr>
<tr><td align='left' ></td>
<td align='left' ></td>
<td align='left' ></td>
</tr>
</tbody>
</table>

