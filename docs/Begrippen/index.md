# Begrippenmodel

Bij informatiemodelleren is het maken van een Begrippenmodel [MIM beschouwingsniveau 1](https://docs.geostandaarden.nl/mim/mim/#beschouwingsniveau-1-model-van-begrippen) een belangrijk onderdeel. Hiervoor gebruiken we de [NL-SBB](https://docs.geostandaarden.nl/nl-sbb/nl-sbb/) standaard.

Het begrippenmodel wordt gepubliceerd op: <https://definities.geostandaarden.nl>. 

## Hoe maak ik een begrippenmodel (inhoudelijk)

Een begrippenmodel wordt opgesteld door mensen bij voorkeur voordat er een informatiemodel wordt gemaakt.

**TODO:** best practise zoeken en opnemen.

Hoewel niet wenselijk komt het ook voor dat er achteraf een begrippenmodel wordt gemaakt op basis van een informatiemodel.


## Hoe maak ik een begrippenmodel (technisch)

Voor het maken en editen van begrippenmodellen zijn twee routes:

1. Je kunt de [begrippenXL](begrippenXL.md) editor gebruiken.
2. Je kunt de begrippen met Imvertor uit een UML digrap halen door de optie `createskos = yes` in de configuratie op te nemen.

Dit SKOS bestand (in .ttl formaat) kan je daarna met de hand editen.

## Regels voor een begrippenmodel binnen Geonovum

**Regel:** Een begrippenmodel is conform [NL-SBB](https://docs.geostandaarden.nl/nl-sbb/nl-sbb/)

**Regel:** Een definitief begrippenmodel wordt gepubliceerd op: <https://definities.geostandaarden.nl>

**Regel:** We voldoen minimaal aan [Best Practice 1](https://docs.geostandaarden.nl/nl-sbb/nl-sbb/#bp-gangbare-conventies-voor-het-beschrijven-van-termen-voorkeurstermen-alternatieve-termen-zijn) uit NL-SBB.

**TODO:** Invulling van NL-SBB [best practices](https://docs.geostandaarden.nl/nl-sbb/nl-sbb/#H5) maken voor Geonovum.

### Het publiceren van een SKOS bestand

Begrippenmodellen die nog niet definitief zijn kun je publiceren op: <https://staging-definities.geostandaarden.nl/>.
Definitief publiceren gebeurt op <https://definities.geostandaarden.nl>

Instructies voor het publiceren van het SKOS bestand staan in de laatste paragraaf van [begrippenXL](begrippenXL.md) editor.

**Regel:** Bij het publiceren van een definitieve versie moet de staging versie verwijderd worden.