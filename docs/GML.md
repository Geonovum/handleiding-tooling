# GML en XSD

Zie hiervoor: [Geometrie in model en GML](https://geonovum.github.io/gimeg/)

## XSD en Namespaces

Bij een XML applicatie schema (dus ook voor GML schema's) wordt vaak een namespace gebruikt. Deze namespace hoort vaak bij een domein en het is de bedoel dat de combinatie van de namespace  en het element uniek is. Dit kan alleen als de namespace, die de vorm van een URI heeft uniek is. Door een URI te kiezen die bij jou onder beheer is weet je zeker dat de combinatie uniek is. In de volgende paragraaf zie je een lijste gebruikte namespaces. Hieronder wat richtlijnen.

 - Voor de basis wordt: http://www.geostandaarden.nl gebruikt.  Het is nog even de vraag of we niet op https moeten overstappen. Dat doen we niet want niemand anders doet deze overstap.
 - Daarna volgt een identificatie van de standaard. 
 - Een versienummer volgens semver X.Y. Een Z-versie is niet nodig omdat alle Z-versies backwards compatible zijn en je dus nooit meer dan 1 versie gebruikt.

De volgende model onderdelen wordt gebruikt bij het maken construeren van schemas:
 - Een schema heeft een X.Y.Z versienummer
 - Een schema hoort bij een standaard met een [standaard]
 - Een schema heeft een onderdeel [onderdeel]

namespace van schema: http://www.geostandaarden.nl/[standaard]/[onderdeel]/x.y
locatie van schema: https://register.geostanadaarden.nl/xmlschema/[standaard]/[x.y.z]/[onderdeel].xsd
vesion in het schema: x.y.z

Bij een standaard zonder onderdelen wordt de bestandsnaam als onderdeelnaam gebruikt bij locatie.


## Namespaces in door Geonovum beheerde schema's


GML applicatieschema's zijn te vinden op: https://register.geostandaarden.nl/gmlapplicatieschema/

Een korte inventarisatie levert:

| standaard         | versie    | namespace                                                                |
| ----------------- | --------- | ------------------------------------------------------------------------ |
| basisgeometrie    | 1.0.0     | http://www.geostandaarden.nl/basisgeometrie/1.0                          |
| basisgeometrie    | v20190901 | http://www.geostandaarden.nl/basisgeometrie/v20190901                    |
| brt-algemeen      | 1.2.0     | http://register.geostandaarden.nl/gmlapplicatieschema/brt-algemeen/1.2.0 |
| imaer             | 5.1.1     | http://imaer.aerius.nl/5.1                                               |
| img               | 3.0.0     | http://www.geluidgegevens.nl/IMGeluid/3.0                                |
| imgeo (simple)    | 2.1.1     | http://www.geostandaarden.nl/imgeo/2.1/simple/gml31                      |
| imgeo             | 2.1.1     | http://www.geostandaarden.nl/imgeo/2.1                                   |
| imkl (wibon)      | 2.0.0     | http://www.geostandaarden.nl/imkl/wibon                                  |
| imkl (wibonbr)    | 2.0.0     | http://www.geostandaarden.nl/imkl/wibonbr                                |
| imkl2015 (wionbr) | 1.2       | http://www.geostandaarden.nl/imkl/2015/wionbr/1.2                        |
| imkl2015 (wionbr) | 1.2.1     | http://www.geostandaarden.nl/imkl/2015/wionbr/1.2                        |
| top10nl           | 1.1.1     | http://www.kadaster.nl/schemas/top10nl/v20120116                         |
| top10nl            | 1.2.0     | http://register.geostandaarden.nl/gmlapplicatieschema/top10nl/1.2.0      |
|                   |           |                                                                          |

