# UML Vraagstukken

Hier vind je antwoord op sommige modelleervraagstukken.

## Externe koppelingen

**Vraag:** hoe leg je een koppeling naar een ander informatiemodel

**Note:** Het antwoord op deze vraag is nog in ontwikkeling.

**Antwoord:**

Bij deze vraag is het onderscheid tussen conceptuele en logische modellen van belang. In een logisch model wil je verwijzen naar een object dat is vastgelegd in een andere registratie. Bij conceptuele modellen wil je een semantische relatie beschrijven naar een klasse die onderdeel uitmaakt van een ander conceptueel model.

### Verwijzen naar externe conceptuele modellen

Bij verwijzing in conceptuele modellen gaat het om het leggen van een semantische relatie tussen klassen in je eigen model en klassen die in een ander model zijn gedefinieerd.

In semantische modellen is een verwijzing, of relatie, tussen twee klassen.

- Je wilt in een model beschrijven dat een Kadastraal Perceel een Registratief Object is volgens NEN 3610. Dit doe je met een subklasse relatie
- Je wilt semantisch vastleggen dat de geometrie van een windturbine altijd vastgelegd is in de BAG.


### Verwijzen naar een object in andere registratie

Bij logische modellen gaat het om implementatie en is het in de uitwisseling de bedoeling te verwijzen naar een specifiek object dat elders geregistreerd in. Hiervoor moet in de eigen registratie een eenduidige verwijzing naar het object in de andere registratie worden opgenomen bijvoorbeeld door de identificatie op te nemen.

Bij verwijzing komt het vaak voor dat het object waarnaar je verwijst verandert of zelfs verwijderd wordt wat dan?

- Veel registratie bevatten een tijdreismechanisme. In de modellering moet je duidelijk maken of je wilt dat de verwijzing meebeweegt of niet.
- Zorg dat duidelijk is of je naar een versie van een object verwijst 
- Verder is een verwijzing ook vaak bedoeld als trigger om wijzigingen te detecteren. Je neemt een pand identificatie over zodat je in de BAG registratie kunt zien of er iets verandert aan dat pand.


Verschillende use-cases waarin we verwijzen naar een BAG Pand.

#### eenvoudige verwijzing

De eenvoudigste manier van verwijzen is het enkelvoudig opnemen van de identificatie van het object in de BAG. 

### Kopie met bronvermeldig

Wat veel voorkomt is dat je in een model bepaalde kenmerken hergebruikt uit een andere (basis)registratie. In veel gevallen sla je dan een kopie op in je eigen model.

#### verwijzing met kopie

Een veel voorkomend geval is dat je in een model verwijst maar in de uitwisseling ook een kopie van het object en een selectie van de attributen meelevert. In dat geval heb je in je model een 


 



 



