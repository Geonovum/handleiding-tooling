# JSON schema's maken.

## Imvertor

Met behulp van Imvertor kan een eerste versie van het JSON-schema gemaakt worden uit een UML in Enterprise Architect.
Voor Geonovum is deze aangepast aan [de best practise UML2json](https://docs.ogc.org/bp/24-017r1.html).
Om een bij het draaien van Imvertor ook een JSON-schem te maken moeten 2 regels opgenomen worden in de [Imvertor-propertiesfile](https://armatiek.nl/doc/imvertor/imvertor-properties/1.0/) de volgende 3 regels opnemen:

- createjsonschema = yes
- createjsonschemavariant = plainjson

Er zijn daarbij 3 varianten:
- plainjson
- geojson
- jsonfg

Geojson is de beste keuze wanneer het schema bedoeld is voor GIS-bestanden in GEO-json-formaat. Het nadeel is wel dat de structuur gecompliceerder is dan voor plainjson.
Jsonfg is vergelijkbaar met geojson, maar heeft meer mogelijkheden voor 3D en tijd. Ook staat deze bijzonderde datatypes zoals een cirkel toe.

Er zijn ook organisatie specifieke instellingen die in een organisatiespecifike configuratiefile verwerkt zijn. 
Als deze ook aangepast moeten worden, moet dat in overleg met de Geonovum coordinator voor Imvertor.

## Handmatig aanpassen

De kans is groot dat het schema uit Imvertor of een andere applicatie niet helemaal zo is als gewenst.
Geonovum ook nog enkele wensen uitstaan bij Armatiek: [#585](https://github.com/Imvertor/Imvertor-Maven/issues/585) t/m [#590](https://github.com/Imvertor/Imvertor-Maven/issues/590).
Oxygen is een prettig programma voor het handmatig bewerken van JSON-schema. Het kan de structoor ook mooi visualiseren.

Bij dit aanpassen zijn er de volgende overwegingen die gemaakt moeten worden:

- title, comment en description en "$schema": "https://json-schema.org/draft/2020-12/schema" toevoegen in header
- relaties die twee kanten opgaan kunnen leiden tot eeuwige loop bij het valideren of bij het aanmaken van voorbeeldbestanden. Een optie is het weglaten van één of beide reichtingen.
- entityType toevoegen als constante. Het entityType geeft aan welk type het object betreft. Dit maakt het leesbaarden en het valideren eenduidiger.
- Hoe wordt er omgegaan met subtypes en supertypes. Via een oneof constructie kunnen subtypes aangegeven worden, maar dit hoeft niet. Via allof worden de attributen van de supertypes overgenomen. Dit kan ook door al deze attributen afzonder opnieuw op te nemen, maar dat maakt het schema onnodig lang.
- Relaties leggen naar alle mogelijke subtypes via oneOf ipv alleen naar het supertype
- Hoe ga je om met voidable objecten

## Valideren

Gebleken is dat verschillende tool verschilled valideren. Wanneer er subtypes en supertypes voorkomen, kunnen validaties daar vaak niet goed mee omgaan.
Het beste tot nu toe ging het valideren met Visusal Studio.
Visual Studio gebruikt daarvoor een klein bestandje dat "settings.code" heet en dat in een submap moet staan met de naam .vscode.

{   
    "json.schemas": [
        {
          "fileMatch": ["voorbeeld.json"],
          "url": "./voorbeeld_schema.json"
        }
      ]
} 

Hierna zal hij on the fly het bestand "voorbeeld.json" valideren op "voorbeeld_schema.json". Dus tijdens het editen van voorbeeld.json wordt direct zichbaar of de inhoud voldoet aan het schema.
Door de filenaam te veranderen en te saven, kan er op een ander json-bestand gevalideerd worden.


geen 2 stereotypen


JSON-schemas kunnen ook met [Modeldesk](https://modeldesk.io/) gemaakt worden.

