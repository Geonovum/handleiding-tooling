.# Handleiding voor het Gebruik van EA2RDF en RDF2RDF Tools

Deze handleiding legt uit hoe je een RDF-bestand kunt genereren vanuit een Enterprise Architect (EA) EAPX-bestand, met behulp van de [**ea2rdf**](https://github.com/architolk/ea2rdf/releases/tag/v1.2.3) en [**rdf2rdf**](https://github.com/architolk/rdf2rdf/releases/tag/v1.4.0)tools ontwikkeld door Marco Bratingo. We zullen ook enkele tips geven voor het aanpassen van de output om het geschikt te maken voor verdere verwerking in RDF- en Linked Data-toepassingen.

## Vereisten

- **EA2RDF en RDF2RDF JAR-bestanden**: De benodigde tools zijn de `ea2rdf.jar` en `rdf2rdf.jar`, die gedownload moeten worden.
- **YAML-configuratie**: Voor de RDF2RDF stap heb je een configuratiebestand nodig, bijvoorbeeld `ea2skosIMG.yaml`.

## Stap 1: Converteer EA-bestand naar TTL (Turtle formaat)

De eerste stap is het omzetten van het Enterprise Architect-bestand (EAP of EAPX) naar een tussentijds TTL-bestand. Dit wordt gedaan met de **ea2rdf** tool.

#### Voorbereidingen:

1. Maak een nieuwe map.
`mkdir {NAAm van je map}`

In deze map maak je 4 submappen aan:

- lib
- input
- pipeline
- output
2. Zet je EAP(X)-bestand in de map input.

3. Sla de JAR-bestanden op in de map lib.

4. Maak een YAML-bestand aan in de hoofdmap.Het structuur van de yaml bestand zie in het deel [structuur](#structuur).

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
Het structuur van YAML bestaand:

De YAML-file heeft de volgende structuur en inhoud, die een handleiding beschrijft voor het uitvoeren van SPARQL-query's in de context van een MIM-conversie (MIM staat voor Metamodel Informatie Modellering). Hieronder is de opbouw beschreven:

### Structuur
#### Metadata

- title: De titel van de handleiding of tool (bijvoorbeeld "MIM conversie").
version: Versienummer van het bestand (bijvoorbeeld "0.3").
prefixes: Lijst met namespaces en hun bijbehorende URI's om de SPARQL-query's eenvoudiger te maken.
Queries

- Een lijst van query's, elk met de volgende onderdelen:
title: Een korte beschrijving van de query, bijvoorbeeld "get skos:ConceptAttribuutSoort".
query: De daadwerkelijke SPARQL-query, inclusief PREFIX-definities en INSERT-instructies voor het vullen van een grafiek.
Voorbeeldinhoud
Metadata
yaml
```
title: MIM conversie
version: 0.3
prefixes:
  imevbegrip: http://definities.geostandaarden.nl/imev/id/begrip/
  begrippenkader: http://definities.geostandaarden.nl/id/begrippenkader/
  skos: http://www.w3.org/2004/02/skos/core#
  owl: http://www.w3.org/2002/07/owl#
```
- Queries
Elke query bevat de logica voor het extraheren en transformeren van gegevens. Hier is een voorbeeld van één query:

```YAML
- title: get skos:ConceptAttribuutSoort
  query: >
    PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
    PREFIX imevbegrip: <http://definities.geostandaarden.nl/imev/id/begrip/>
    PREFIX ea: <http://www.sparxsystems.eu/def/ea#>
    INSERT {
      GRAPH <urn:output> {
        ?begrip a skos:Concept;
          rdfs:label ?label;
          skos:prefLabel ?label;
          skos:definition ?comment;
          skos:inScheme begrippenkader:IMEV;
          skos:notation ?label.
        begrippenkader:IMEV a skos:ConceptScheme;
          rdfs:label "Begrippenkader IMEV"@nl;
          skos:prefLabel "Begrippenkader IMEV"@nl.
      }
    }
    WHERE {
      GRAPH <urn:input> {
        SELECT (iri(concat('http://definities.geostandaarden.nl/imev/id/begrip/',?label)) as ?begrip) ?label ?comment
        WHERE {
          ?element a ea:Attribute;
          ea:stereotype "Attribuutsoort";
          rdfs:label ?label;
          rdfs:comment ?comment.
        }
      }
    }
```
Deze structuur is bedoeld om gegevens uit een bron te halen en om te zetten naar SKOS-concepten in een RDF-graaf.


### Structuur van de SPARQL-query
- Prefixes
Deze sectie definieert namespaces die in de query worden gebruikt. Prefixes maken de query compacter door URI's af te korten.
Voorbeeld:

```sparql
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX imevbegrip: <http://definities.geostandaarden.nl/imev/id/begrip/>
```

- INSERT-sectie
In deze sectie wordt gedefinieerd welke triples moeten worden toegevoegd aan een doelgraaf (GRAPH <urn:output>). De structuur van de RDF-triples (subject, predicate, object) is hier beschreven.
Voorbeeld:

```sparql
INSERT {
  GRAPH <urn:output> {
    ?begrip a skos:Concept;
      rdfs:label ?label;
      skos:prefLabel ?label;
      skos:definition ?comment;
      skos:inScheme begrippenkader:IMEV;
      skos:notation ?label.
    begrippenkader:IMEV a skos:ConceptScheme;
      rdfs:label "Begrippenkader IMEV"@nl;
      skos:prefLabel "Begrippenkader IMEV"@nl.
  }
}
```

- WHERE-sectie
Hier wordt beschreven welke data uit de bron moet worden opgehaald en welke voorwaarden gelden voor de selectie.
Voorbeeld:

```sparql
WHERE {
  GRAPH <urn:input> {
    SELECT (iri(concat('http://definities.geostandaarden.nl/imev/id/begrip/', ?label)) AS ?begrip) ?label ?comment
    WHERE {
      ?element a ea:Attribute;
      ea:stereotype "Attribuutsoort";
      rdfs:label ?label;
      rdfs:comment ?comment.
    }
  }
}
```

Deze SPARQL-query is ontworpen om begrippen te creëren en te transformeren in overeenstemming met het SKOS (Simple Knowledge Organization System)-model. De resulterende RDF-data kunnen direct worden geüpload naar de omgeving https://staging-definities.geostandaarden.nl/nl/.




## Stap 5: Controleer en Pas de Output Aan

Na de transformatie is het belangrijk om het resultaat te controleren. Vaak moeten taal-tags en datatypes worden toegevoegd of geoptimaliseerd. Bijvoorbeeld, bij SKOS kan het nodig zijn om de taal voor labels of beschrijvingen te specificeren, of om de juiste datatypes voor numerieke waarden toe te voegen.

## Tips voor Werken met EA2RDF en RDF2RDF

* **SPARQL-queries zijn krachtig** : Door SPARQL-constructs in je YAML-bestand te gebruiken, kun je gegevens uit je model extraheren en het RDF-formaat aanpassen aan je wensen.
SPARQL voor begrippen van "Class"
```sparql
      PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
      PREFIX imklbegrip: <http://definities.geostandaarden.nl/imkl/id/begrip/>
      prefix begrippenkader: <http://definities.geostandaarden.nl/id/begrippenkader/>
      PREFIX ea: <http://www.sparxsystems.eu/def/ea#>
      PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
      PREFIX owl: <http://www.w3.org/2002/07/owl#>
      INSERT {
        GRAPH <urn:output> {
          ?begrip a skos:Concept.
          ?begrip skos:notation ?label.
        }
      }
      WHERE {
        GRAPH <urn:input> {
          SELECT (iri(concat('http://definities.geostandaarden.nl/imkl/id/begrip/',?label) as ?begrip)) ?label
          WHERE {
            {
              ?s a ea:Object.
              ?s ea:type "Class".
              ?s ea:stereotype "Objecttype".
              ?s rdfs:label ?label.
              ?s ea:alias ?alias.
            }
          }
        }
      }
```

* **SHACL en andere Linked Data** : Je kunt SHACL-shapes genereren en de output in andere Linked Data-formaten omzetten door de YAML-configuratie te wijzigen.
Voorbeelden van creeren een SHACL shapes

```sparql
      PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
      PREFIX imgbegrip: <http://definities.geostandaarden.nl/img/id/begrip/>
      PREFIX ea: <http://www.sparxsystems.eu/def/ea#>
      PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
      PREFIX owl: <http://www.w3.org/2002/07/owl#>
      PREFIX img: <http://definities.geostandaarden.nl/img/>
      PREFIX sh: <http://www.w3.org/ns/shacl#>
      INSERT {
        GRAPH <urn:output> {
      ?shape
        a sh:PropertyShape;
        sh:minCount ?lower;
        sh:maxCount ?upper;
        sh:dataType ?type;
        rdfs:comment ?comment.
        }
      }
      WHERE {
        GRAPH <urn:input> {
          SELECT ?lower ?type ?comment (iri(concat("http://definities.geostandaarden.nl/def/",if(?label = "lokaalID" || ?label = "namespace", "nen3610/", ""), ?label)) as ?shape) ?upper
          WHERE {
            {
              ?sh ea:lowerBound ?lower;
                ea:stereotype "Data element";
                rdfs:label ?label;
                ea:upperBound ?upper;
                ea:type ?type;
                rdfs:comment ?comment.
            }
          }
        }
      }
```

* **Schoonmaken van bestanden** : Sommige tijdelijke transformatie heeft "trailing newlines" die wij kunnen vind en replace met deze regex
