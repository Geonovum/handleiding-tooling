# Begrippenmodel

Bij informatiemodelleren is het maken van een Begrippenmodel (Mim beschouwingsniveau 1) een belangrijk onderdeel. Hiervoor gebruiken we de [NL-SBB](https://docs.geostandaarden.nl/nl-sbb/nl-sbb/) standaard.

Met begrippenmodel wordt gepubliceerd op: <https://definities.geostandaarden.nl>. 

## Hoe maak ik een begrippenmodel (inhoudelijk)

Je kunt samen met het werkveld een begrippenmodel maken voor je echt gaat modelleren. Wat ook vaak gebeurt is dat er al een (conceptueel) model is waar je met een druk op de knop (Imvertor) de start van een begrippenmodel uit filtert. Dit kun na wat nabewerkingen publiceren.

Ook kun je met een begrippeneditor of spreadsheet vanuit het niets een begrippenmodel maken.

## Hoe maak ik een begrippenmodel (technisch)

Voor het maken en editen van begrippenmodellen zijn twee routes:

1. Je kunt de [begrippenXL](begrippenXL.md) editor gebruiken.
2. Je kunt de begrippen met Imvertor uit een UML digrap halen door de optie `createskos = yes` in de configuratie op te nemen.

Dit SKOS bestand (in .ttl formaat) kan je daarna met de hand editen.

## Regels voor een begrippenmodel binnen Geonovum

**Regel:** Een begrippenmodel is conform [NL-SBB](https://docs.geostandaarden.nl/nl-sbb/nl-sbb/)

**Regel:** Een definitief begrippenmodel wordt gepubliceerd op: <https://definities.geostandaarden.nl>

**TODO:** Invulling van NL-SBB [best practices](https://docs.geostandaarden.nl/nl-sbb/nl-sbb/#H5) maken voor Geonovum.

### Het publiceren van een SKOS bestand.

Begrippenmodellen die nog niet definitief zijn kun je publiceren op: <https://staging-definities.geostandaarden.nl/>.
Definitief publiceren gebeurt op <https://definities.geostandaarden.nl>

Instructies voor het publiceren van het SKOS bestand staan in de laatste paragraaf van [begrippenXL](begrippenXL.md) editor.

**Regel:** Bij het publiceren van een definitieve versie moet de staging versie verwijderd worden.