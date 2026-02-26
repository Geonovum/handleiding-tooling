# JSON schema's maken.

## Imvertor

Met behulp van Imvertor kan een eerste versie van het JSON-schema gemaakt worden uit een UML in Enterprise Architect.
Voor Geonovum is deze aangepast aan [de best practise UML2json](https://docs.ogc.org/bp/24-017r1.html).
Om bij het draaien van Imvertor ook een JSON-schem te maken, moeten 2 regels opgenomen worden in de [Imvertor-propertiesfile](https://armatiek.nl/doc/imvertor/imvertor-properties/1.0/) :

- createjsonschema = yes
- createjsonschemavariant = plainjson

Er zijn daarbij 3 varianten:
- plainjson
- geojson
- jsonfg

Geojson is de beste keuze wanneer het schema bedoeld is voor GIS-bestanden in GEO-json-formaat. Het nadeel is wel dat de structuur gecompliceerder is dan voor plainjson.
Jsonfg is vergelijkbaar met geojson, maar heeft meer mogelijkheden voor 3D en tijd. Ook staat deze bijzonderde datatypes zoals een cirkel toe.

Er zijn organisatie specifieke instellingen die in een organisatiespecifieke configuratiefile verwerkt zijn. 
Als deze ook aangepast moeten worden, moet dat in overleg met de Geonovum coordinator voor Imvertor.

Imvertor geeft een foutmelding in de conversie naar het json-schema wanneer er meer dan 1 stereotypen zijn ingesteld op 1 objectklasse. De extra moeten dan verwijderd worden. 
Dat kan eventueel toegepast worden door de extra stereotypen alleen in het conceptuele model op te nemen, maar in het logische model slechts 1.

## Andere tools

JSON-schemas kunnen ook met [Modeldesk](https://modeldesk.io/) gemaakt worden.
Dit is in het [IBRO](https://github.com/Geonovum/ibro-lm) project gebruikt. Zie: https://raw.githubusercontent.com/Geonovum/ibro-lm/refs/heads/main/schemas/IMIBRO-LM.schema.json

## Handmatig aanpassen

De kans is groot dat het schema uit Imvertor of een andere applicatie niet helemaal zo is als gewenst.
Geonovum heeft ook nog enkele wensen uitstaan bij Armatiek voor aanpassing van Imvertor. Zie: [#585](https://github.com/Imvertor/Imvertor-Maven/issues/585) t/m [#590](https://github.com/Imvertor/Imvertor-Maven/issues/590).
Oxygen is een prettig programma voor het handmatig bewerken van JSON-schema. Het kan de structuur van het schema mooi visualiseren.

Bij dit aanpassen zijn er de volgende overwegingen die gemaakt moeten worden:

- title, comment en description en "$schema": "https://json-schema.org/draft/2020-12/schema" toevoegen in header
- Relaties die twee kanten opgaan, kunnen leiden tot eeuwige loop bij het valideren of bij het aanmaken van voorbeeldbestanden. Een optie is het weglaten van één of beide richtingen.
- Het attribuut entityType toevoegen als constante. Het entityType geeft aan welk type het object betreft. Dit maakt het leesbaarder en het valideren eenduidiger.
- Ga na of er een extra id-attribuut nodig is naast het Nen3610-Id. Het is voor implementaties lastig verwijzen naar een genest id, zoals bij het NEN3610-localid
- Hoe wordt er omgegaan met subtypes en supertypes? Via een oneOf constructie kunnen mogelijke subtypes aangegeven worden, maar dit hoeft niet. Via allof worden de attributen van de supertypes overgenomen. Dit kan ook door al deze attributen afzonderlijk opnieuw op te nemen, maar dat maakt het schema onnodig lang.
- Bij subtypes die een allOf aanroepen, moet een unevaluatedProperties key = false opgenomen worden
- Relaties leggen naar alle mogelijke subtypes van een supertype via oneOf i.p.v. alleen naar het supertype verwijzen. Dat laatste klinkt makkelijker, maar is moeilijker te valideren.
- Hoe ga je om met voidable objecten? Hierover is een discussie gaande op [#590](https://github.com/Imvertor/Imvertor-Maven/issues/590)
- Hoe ga je om met keuze objecten? Het kan door de twee kwuzes als opstionele properties op te nemen en 2 regels toe toe te voegen '"minProperties": 1' en '"maxProperties": 1'. Dit doet Imvertor. Het kan ook via een oneOf-constructie
- Realiseer je dat het schema bedoeld is voor implementatie en daarom kan die afwijken van het model. Een voorbeeld van deze afwijking is het attribuut "entityType". Dit attribuut komt niet voor in het UML.
- Voor hetzelfde UML-model kunnen verschillende schema's bestaan met ieder verschillende doelen. bv voor input of output. Het atribuut "tijdstipRegistratie" komt bv. niet in de input voor, maar wel in de output.
- Kijk goed of alle tagged values uit het UML overgenomen zijn het schema. Let vooral op de formele patronen, min en max values en kardinaliteiten.
- Hoe ga je om met regels/constraints? Sommige kunnen via een constante opgelost worden in een json-schema: vb. "entityType": {"const": "Bewaarplaats"}

## Voorbeeldbestanden maken

Het loont om voorbeeldbestanden te maken. Dat geeft inzicht in de bruikbaarheid van het schema.
Soms zijn deze er al vanuit de praktijk, zoals bij IMEV het geval was vanuit vorige versies van het IMEV. Met slechts enkele aanpassingen konden deze aangepast worden aan de nieuwste versie van het IMEV en het daarbij behorende schema.
Als ze er nog niet zijn, dan biedt Oxygen de mogelijkheid om voorbeeldbestanden met dummy waarden aan te maken. 
Wanneer het UML complex is, loont het om alleen voor enkele representatieve objectklassen voorbeeldbestanden te maken. 
Richt je daarbij ook op de vraag hoe de datauitwisseling voor de bijbehorende registratie verloopt. Maak onderscheid tussen input en output.


## Valideren

Gebleken is dat verschillende tools verschillend valideren. Wanneer er subtypes en supertypes voorkomen, kunnen validaties daar vaak niet goed mee omgaan.
Het beste tot nu toe ging het valideren met Visusal Studio.
Visual Studio gebruikt daarvoor een klein bestandje dat "settings.code" heet en dat in een submap moet staan met de naam .vscode. Hier staat bv. het volgende in:

```
{   
    "json.schemas": [
        {
          "fileMatch": ["voorbeeld.json"],
          "url": "./voorbeeld_schema.json"
        }
      ]
} 
```

Hierna zal hij on the fly het bestand "voorbeeld.json" valideren op "voorbeeld_schema.json". Dus tijdens het editen van voorbeeld.json wordt direct zichbaar of de inhoud voldoet aan het schema.
Door de filenaam te veranderen en te saven, kan er op een ander json-bestand gevalideerd worden.

## Publiceren

Json-schemas worden gepubliceerd in https://register.geostandaarden.nl/jsonschema/.  

Dit gebeurt met sftp.

