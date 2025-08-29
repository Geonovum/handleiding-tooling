# Imvertor

>
> TODO: invullen vanuit de volgende documenten
>

Imvertor wordt veel gebruikt binnen Geonovum voor het transformeren van UML modellen naar bijvoorbeeld xml-schema’s of feature catalogues. De instructies van hoe er mee om te gaan zijn overal verspreid.  Op deze pagina probeer ik alles te verzamelen….

| onderwerp             | verwijzing                                                                                                                    |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Imvertor-properties   | [Uitleg verschillende properties](https://imvertor.armatiek.nl/imvertor-executor/dashboard/wiki?key=info-IMVERTORCONFIG-PROP) |
| Algemeen              | [Verzamelde handleiding van organisaties](https://vng-realisatie.github.io/Model-Driven-Design-Documentatie/)                 |
| Werkinstructie        | [IMGeluid werkinstructie](https://geonovum.atlassian.net/l/cp/Fi0U9bCk)                                                       |
| Uitleg schema mapping | [Hier](https://imvertor.armatiek.nl/imvertor-executor/dashboard/wiki?key=info-IMVERTORCONCEPTUALSCHEMAS)                      |
| Nieuwsbrieven         | <https://armatiek.nl/nieuwsbrieven.html> |

## Veel te veel plaatjes in de data folder


- Een Imvertor run levert een flink aantal UML diagrammen op in de `data` folder. Niet meer gebruikt diagrammen worden nooit verwijderd uit deze folder waardoor er vaak veel niet gebruikt diagrammen in staan. **Tip:** gooi voor het draaien van Imvertor de data map een keer leeg.

# Schema generatie

Imvertor in in staat om verschillende soorten schema's (i.e. verschillende
uitwisselformaten) te genereren. Via het properties file kun je aangeven of en
welke schema's je wilt genereren. Er zijn ook (gelimiteerde) mogelijkheden om
datgene wat er gegenereerd wordt aan je wensen aan te passen. 

Zie de [imvertor documentatie van het properties
file](https://imvertor.armatiek.nl/imvertor-executor/dashboard/wiki?key=info-IMVERTORCONFIG-PROP). 

## JSON genereren

Geef in de properties file die je kunt kiezen bij het runnen van imvertor, de volgende parameter mee: 

`createjsonschema = yes`

Imvertor genereert dan een `.json` en een `.yaml` bestand. Dit zijn, in 2
formaten, API beschrijvingen conform OpenAPI 3.0.0 die zijn gegenereerd uit je
informatiemodel. 

TODO uitzoeken wat er mogelijk is met de property `createjsonschemavariant`. De
mogelijke waarden zijn niet gedocumenteerd.


# Mapping van geo-klassen en -typen

Imvertor werkt met een configuratiebestand `conceptual-schemas.xml` waarin een
mapping is opgenomen tussen gestandaardiseerde **ISO-, OGC- en INSPIRE-klassen**
en typen die wij in informatiemodellen gebruiken, naar bijvoorbeeld in **GML**
voorkomende typen. **Imvertor** gebruikt dit om bijvoorbeeld **GML Application
schema's** te genereren uit een informatiemodel. 

Bij deze klassen en typen is het ook mogelijk om links op te nemen naar een
online gepubliceerde definitie en/of uitleg ervan, die Imvertor dan kan
gebruiken om links in de documentatie te genereren. 

Een voorbeeldje. In onze UML modellen gebruiken we vaak `GM_Surface`. 

Imvertor “weet” al (omdat dit in een configuratiebestand staat) hoe dit vertaald
moet worden naar een **GML-type** zodat er een correct **GML application
schema** uit komt rollen. 

We genereren met Imvertor niet alleen **XML/GML schema’s**, maar ook
dataspecificaties, bv. dit hoofdstuk uit de **IMGeluid** **catalogus** is met
Imvertor uit **UML** gegenereerd: https://docs.geostandaarden.nl/cvgg/img/#cat

Je ziet daarin dat het **ISO-concept** `GM_Surface` niet gedocumenteerd is. Een
lezer die het niet kent, kan niet direct opzoeken wat het betekent. Zie bv. het
geometrie attribuut in de klasse `VlakbronIndustrie`
https://docs.geostandaarden.nl/cvgg/img/#detail_attribute_IMGeluidAlgemeen_VlakbronIndustrie_geometrie

Terwijl andere typen klikbaar zijn omdat ze elders in de data specificatie
worden gedefinieerd. 

Nu willen we Imvertor in gevallen zoals `GM_Surface links` laten genereren naar
definities in de **ISO Geolexica**, het **INSPIRE register** en ons eigen
definities.geostandaarden.nl voor **NEN 3610**. Daarvoor hebben we een eerste
(onvolledige)
[mapping](mapping-ISOlexicon.xlsx)
gemaakt. 

De ambitie is om niet alleen deze mapping te verbeteren, maar om ook de lijst
van in informatiemodellen te gebruiken geo-klassen en -typen te standaardiseren. 
