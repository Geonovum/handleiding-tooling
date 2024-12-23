# Handleiding voor het Gebruik van EA2RDF en RDF2RDF Tools

Deze handleiding legt uit hoe je een RDF-bestand kunt genereren vanuit een Enterprise Architect (EA) EAPX-bestand, met behulp van de [**ea2rdf](https://github.com/architolk/ea2rdf/releases/tag/v1.2.3)** en [**rdf2rdf](https://github.com/architolk/rdf2rdf/releases/tag/v1.4.0)**tools ontwikkeld door Marco Bratingo. We zullen ook enkele tips geven voor het aanpassen van de output om het geschikt te maken voor verdere verwerking in RDF- en Linked Data-toepassingen.

## Vereisten

- **EA2RDF en RDF2RDF JAR-bestanden**: De benodigde tools zijn de `ea2rdf.jar` en `rdf2rdf.jar`, die gedownload moeten worden.
- **YAML-configuratie**: Voor de RDF2RDF stap heb je een configuratiebestand nodig, bijvoorbeeld `ea2skosIMG.yaml`.

## Stap 1: Converteer EA-bestand naar TTL (Turtle formaat)

De eerste stap is het omzetten van het Enterprise Architect-bestand (EAP of EAPX) naar een tussentijds TTL-bestand. Dit wordt gedaan met de **ea2rdf** tool.

#### Voor EAPX-bestanden:

Gebruik het volgende commando in de terminal:

```bash
java -jar lib/ea2rdf.jar -ea -0 -e input/{NAAM VAN DE BESTAND}.eapx > pipeline/{NAAM VAN DE OUTPUT BESTAND}.ttl
```

#### Voor EAP-bestanden:

Gebruik het volgende commando in de terminal:

```bash
java -jar lib/ea2rdf.jar -ea -e input/{NAAM VAN DE BESTAND}.eap > pipeline/{NAAM VAN DE OUTPUT BESTAND}.ttl
```

## Stap 2: Verfijn het Tussentijdse TTL-bestand

Het bestand dat je ontvangt (`img.ttl`) is een tussenbestand in TTL-formaat, maar het kan enige schoonmaak vereisen omdat het niet altijd volledig TTL-compatibel is. Het is aanbevolen om de uitvoer te controleren en waar nodig aan te passen, zoals het toevoegen van de juiste taal-tags en datatypes. Je kunt dit bestand handmatig aanpassen of een script gebruiken om de inconsistenties te verhelpen.

## Stap 3: Gebruik RDF2RDF voor Verdere Transformatie

Na het genereren van het TTL-bestand, gebruik je de **rdf2rdf** tool om het bestand om te zetten naar een specifiek RDF-formaat (bijvoorbeeld SKOS) of SHACL-shapes.

Gebruik het volgende commando om de transformatie uit te voeren:

```
java -jar lib/rdf2rdf.jar -i pipeline/{Naam van de bestand}.ttl -o output/{Naam van de bestaand}.ttl -c ea2skos.yaml
```

Het `ea2skos.yaml` bestand bevat de configuratie voor de transformatie, en je kunt dit bestand aanpassen om verschillende uitvoerformaten te verkrijgen, zoals SKOS of andere Linked Data-vormen.

## Stap 4: Aanpassen van de YAML-configuratie

De YAML-configuratie (`ea2skos.yaml`) bepaalt hoe de transformatie plaatsvindt. Het kan nodig zijn om de SPARQL-constructies in de YAML aan te passen om specifieke gegevens zoals definities of scope-notities te extraheren.

Bijvoorbeeld, als je definities en beschrijvingen uit een commentaarveld wilt halen, kun je de volgende SPARQL-aanpassing gebruiken:

```
SPARQL
?subject rdfs:comment ?comment.
bind(replace(?comment, "^.*-- Definition --(.*?)-- Description --.*$", "$1") as ?newDescription)
bind(replace(?comment, "^.*-- Description --(.*?)-- Source.*$", "$1") as ?newNote).

```

## Stap 5: Controleer en Pas de Output Aan

Na de transformatie is het belangrijk om het resultaat te controleren. Vaak moeten taal-tags en datatypes worden toegevoegd of geoptimaliseerd. Bijvoorbeeld, bij SKOS kan het nodig zijn om de taal voor labels of beschrijvingen te specificeren, of om de juiste datatypes voor numerieke waarden toe te voegen.

## Tips voor Werken met EA2RDF en RDF2RDF - TODO (meerdere SPARQL voorbeelden toevoegen)

* **SPARQL-queries zijn krachtig** : Door SPARQL-constructs in je YAML-bestand te gebruiken, kun je gegevens uit je model extraheren en het RDF-formaat aanpassen aan je wensen.
* **SHACL en andere Linked Data** : Je kunt SHACL-shapes genereren en de output in andere Linked Data-formaten omzetten door de YAML-configuratie te wijzigen.
* **Tijdschatting** : Het kan 2-3 uur duren om een goed werkend TTL-bestand te genereren, en tot een dag voor het schoonmaken van de data.
