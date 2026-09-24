# begrippenkader

Informatiemodellen op [MIM beschouwingsniveau 1](https://docs.geostandaarden.nl/mim/mim/#beschouwingsniveau-1-model-van-begrippen) maken we volgens de [NL-SBB](https://docs.geostandaarden.nl/nl-sbb/nl-sbb/) standaard.

Onderwerpen:
- [werkwijze](werkwijze-begrippenkader.md)

## Hoe maak ik een begrippenkader (technisch)

Een begrippenkader is een SKOS bestand in .ttl formaat. Deze kun je op verschillende manieren maken:

1. Je kunt de begrippen met Imvertor uit een UML model halen door de optie `createskos = yes` in de configuratie op te nemen. Dit levert een SKOS bestand op.
1. [Modeldesk](https://app.modeldesk.io) heeft een ingebouwde begrippeneditor.
1.  Je kunt de [begrippeneditor van de stelselcatalogus](https://editor.stelselcatalogus.nl/) gebruiken.
1. Je kunt de [begrippenXL](BegrippenXL.md) editor gebruiken.
1.  Met een spreadsheet kom je al een heel eind. Dan kun je later naar SKOS converteren.

## Hoe publiceerd ik een begrippenkader

Een begrippenkader wordt gepubliceerd op <https://definities.geostandaarden.nl>, of op de staging omgeving <https://staging-definities.geostandaarden.nl/> door de volgende stappen uit te voeren:

1. Controleer of het begrippenkader voldoet aan de interne kwaliteitseisen in [regels](begrippen-regels.md)
2. Sla het te publiceren bestand op in een git repository. Voorstel maak in het mapje bij een informatiemodel een submap begrippenkaders
3. Stuur een link naar Tanja met een verzoek tot publicatie. op de publicatie omgeving <https://definities.geostandaarden.nl> of de staging omgeving <https://staging-definities.geostandaarden.nl/>.
4. Tanja geeft invulling aan het vier-ogen principe door het bestand te controleren of dit uit te besteden aan Frank, Linda of Wilko.
5. Als resultaat wordt het begrippenkader gepubliceerd of je krijgt een melding terug.

**Regel:** Bij het publiceren van een definitieve versie moet de staging versie verwijderd worden.