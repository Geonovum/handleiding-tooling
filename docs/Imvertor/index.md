# Imvertor

Imvertor wordt veel gebruikt binnen Geonovum voor het transformeren van UML 
modellen naar bijvoorbeeld xml-schema’s of feature catalogues. Imvertor is
een add-in in [Enterprise Architect](../EA/index.md)

## Installatie

De [installatieinstructie](https://armatiek.nl/doc/imvertor/imvertor-startup/1.0/#installeren-van-de-software). Houd er rekening mee dat je ondersteuning nodig kunt hebben van systeembeheer voor deze installatie.
Wanneer de knop "Toch uitvoeren" niet verschijnt, moet je de cmd-promp openen als administrator en dan het gedownloade installatiescript runnen door de filenaam van de executable met pad en extensie in te tikken en enter te geven.

## Gebruik

| onderwerp             | verwijzing                                                                                                    |
| --------------------- | ------------------------------------------------------------------------------------------------------------- |
| Algemeen              | [Verzamelde handleiding van organisaties](https://vng-realisatie.github.io/Model-Driven-Design-Documentatie/) |
| Werkinstructie        | [IMGeluid werkinstructie](https://geonovum.atlassian.net/l/cp/Fi0U9bCk)                                       |
| Uitleg schema mapping | [Hier](https://imvertor.armatiek.nl/imvertor-executor/dashboard/wiki?key=info-IMVERTORCONCEPTUALSCHEMAS)      |
| Nieuwsbrieven         | <https://armatiek.nl/nieuwsbrieven.html>                                                                      |
| Imvertor-properties   | [Uitleg verschillende properties](https://armatiek.nl/doc/imvertor/imvertor-properties/1.0/)                  |

## Losse onderwerpen

### Schema generatie

Imvertor in in staat om verschillende soorten schema's (i.e. verschillende
uitwisselformaten) te genereren. Via het properties file kun je aangeven of en
welke schema's je wilt genereren. Er zijn ook  mogelijkheden om
datgene wat er gegenereerd wordt aan je wensen aan te passen via het Imvertor-properties bestand zie: [properties](https://armatiek.nl/doc/imvertor/imvertor-properties/1.0/)

### In welk git repo komt de catalogus terecht

Bij het runnen van Imvertor wordt een catalogus bestand gepushed naar de data folder van een Git repository. Dit wordt als volgt bepaald:

- Als in het UML package de Alias is ingevuld wordt één van de volgend gebruikt: `https://github.com/[Alias]` of `https://github.com/Geonovum/[Alias]`.
- Ook kan je in de  imvertor.properties file een variable `gitpath = /Geonovum/XXX` opnemen dan wordt het git repo 'https://github.com/Geonovum/XXX/` gebruikt.
.

De eerste methode heeft de voorkeur omdat het vaak voorkomt dat je invertor draait met het verkeerde `imvertor.properties` bestand waardoor de catalogus op de verkeerde plek terechtkomt.


### JSON genereren

Geef in de properties file die je kunt kiezen bij de aanroep Imvertor de parameter 
`createjsonschema = yes` mee.

Imvertor maakt dan een `.json` en een `.yaml` bestand. Dit zijn, in 2
formaten, API beschrijvingen conform OpenAPI 3.0.0 die zijn gegenereerd uit je
informatiemodel. 

Met de property `createjsonschemavariant` kun je varianten configureren. Zie [handleiding](https://armatiek.nl/doc/imvertor/imvertor-properties/1.0/#cli-createjsonschemavariant).  
Voor meer informatie: zie [hier](https://geonovum.github.io/handleiding-tooling/schemas/JSON/).

### Veel te veel plaatjes in de data folder

Een Imvertor run levert een flink aantal UML diagrammen op in de `data` folder. Niet meer gebruikt diagrammen worden nooit verwijderd uit deze folder waardoor er vaak veel niet gebruikt diagrammen in staan.

**Tip:** gooi voor het draaien van Imvertor de data map een keer leeg.
