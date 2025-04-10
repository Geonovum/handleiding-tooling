# Werkwijze Informatiemodelleren


Intern cursusmateriaal: [op onedrive](https://stichtinggeonovum.sharepoint.com/:f:/s/Basisprogramma/ErIgyU58KvFeoe5cieS22z4BSl-c9UcUoeHVvaXibHPxaA?e=Y2Imgb)

>**Note**
> Een link naar dit document opnemen op intranet voor degenen die liever documentatie aan de hand van een tabel opzoeken.

>**Note** 
> **Todo geonovumwerkwijze voor informatiemodelleurs**

1. Afstemmen met **document dat Arnoud** schrijft als bijlage voor offertes
1. Overzicht onderwerpen/repo's mogelijk betrekking hebben op de **geonovumwerkwijze**
1. Onderscheid tussen **werkwijze** en **werkomgeving** goed controleren bij toevoeging aan tabellen
1. Handleiding voor het maken **begrippenkader** en **ontologie** en de toepassing/noodzaak ervan.
1. Relatie met **BOMOS**
1. Je zou naast **Geometrie in Model en GML** ook **Geometrie in Model en JSON** moeten hebben 

> **Note**
> **Optioneel**

1. Nog kolom `beheer` toevoegen: `["Geonovum", "Armatiek", "W3C", "Logius"]`.
1. Nog Kolom `ReSpec` toevoegen: `["Ja", "Nee"]`. Is het document in ReSpec-formaat beschikbaar?
1. Toelichting bij kolomnamen maken: een document kan bijvoorbeeld in werkversie op GitHub staan en als geconsulteerde (definitieve) versie op docs.geostandaarden. In deze tabel hanteren we locatie van het brondocument; het document op docs.geostandaarden.nl is een snapshot. Op GitHub vind je de actueelste informatie. Bovendien kun vanuit dat document altijd naar de laatst gepubliceerde versie komen.
1. Een andere mogelijk is om een extra kolom toe te voegen met `gepubliceerde versie`, of `formele status`.

| | Onderwerp | Naam document | Korte omschrijving | Laatst bijgewerkt | Locatie | Gebruik | 
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Opstellen van model | HIM - Handreiking Informatie Modelleren | Handleiding voor het opstellen van een informatiemodel of dataproductspecificatie. Beschrijft rol, proces en basismethodiek | 2019 | [Github](https://geonovum.github.io/HIM-Werkomgeving/) | Openbaar |
| 2 | Geometrie in model | GIMEG | Beschrijving van de toepassing van geometrie in informatiemodellering en de implementatie daarvan in GML.| 2021 | [GitHub](https://geonovum.github.io/gimeg/) | Openbaar |
| 3 | Geometrie in uitwisselingsformaten | Geometrie in uitwisselingsformaten | Handreiking over het uitwisselen van geometrie, met o.a. een overzicht van de verschillende bestandsformaten, handvatten voor het kiezen van het juiste formaat en gedetaileerde informatie over het uitwisselen van geometrie in HTML, GML, JSON, GeoPackage en RDF. | 2022 | [GitHub](https://docs.geostandaarden.nl/g4w/vv-hr-geox-20220104/#kieswijzer) | Openbaar |
| 4 | CRS in uitwisselingsformaten | Handreiking gebruik coördinaatreferentiesystemen bij uitwisseling en visualisatie van geo-informatie | Bundeling van bestaande adviezen van het NSGI over geodetisch correcte gebruik van de in Nederland gebruikte CRS-en. | 2022 | [GitHub](https://docs.geostandaarden.nl/crs/crs/) | Openbaar |
| 5 | Lange lijnenadvies | Eenduidige transformatie van grenzen tussen ETRS89 en RD | Advies voor het waarborgen van de nauwkeurigheid van lange lijnstukken van grenzen. | 2018 | [Geoforum](https://geoforum.nl/uploads/default/original/2X/c/c0795baa683bf3845c866ae4c576a880455be02a.pdf) | Openbaar |
| 6 | Keuzehulp standaarden | Raamwerk Geostandaarden 4.0 | Het Raamwerk van geo-standaarden helpt bij de opzet en ontwikkeling van een geo-informatie infrastructuur om de juiste set standaarden te kiezen. | 2023 | [GitHub](https://geonovum.github.io/raamwerk-geostandaarden/) | Openbaar |
| 7 | Beschrijving MIM | MIM - Metamodel Informatie Modellering | Beschrijving van een metamodel waar informatiemodellen mee gemaakt worden. Het informeert over de metaklassen, metastructuur en metagegevens als grondslag voor een informatiemodel.  | 2022 | [GitHub](https://docs.geostandaarden.nl/mim/mim/) | Openbaar |
| 8 | Toepassing NEN3610 | Basismodel geo-informatie - toelichting | Handreiking voor het toepassen van het Basismodel geo-informatie (NEN 3610:2022), bedoeld als service-informatie om te ondersteunen bij het toepassen van het model in sectorale informatiemodellen. | 2023 | [GitHub](https://geonovum.github.io/nen3610-werkomgeving/) | Openbaar |
| 9 | Toepassing NEN3610 in LD | NEN 3610 - Linked Data | Combinatie van een _technisch rapport_, een _handboek_ en een _standaard_ voor NEN3610 in Linked Data. | 2021 | [GitHub](https://geonovum.github.io/NEN3610-Linkeddata/) | Openbaar |
| 10 | Doel en Toepassing Model Basisgeometrie | Basisgeometrie | Specificatie van het model basisgeometrie voor geo-informatiemodellen die een externe geometriereferentie nodig hebben. | 2020 |[GitHub](https://geonovum.github.io/Basisgeometrie-Werkomgeving/) | Openbaar |
| 11 | Toepassing ReSpec | ReSpec Wiki | Engelstalige wiki voor de configuratie en het gebruik van ReSpec | 2021 | [GitHub](https://github.com/w3c/respec/wiki) | Openbaar |
| 12 | Wijzigingen in model | Wijzigingsprotocol geo-standaarden | Sturende principes achter het generieke wijzigingsproces van de basisset geo-standaarden. | 2021 | [GitHub](https://geonovum.github.io/Geo-standaarden-wijzigingsprotocol/) | Openbaar |
| 13 | Beheer standaarden | Beheer basis geo-standaarden | Beschrijving van verschillende beheeraspecten, zoals o.a. _implementatieondersteuning_, _wijzigingsproces_, _governance_, etc. | 2021 | [GitHub](https://geonovum.github.io/Geo-standaarden-beheerplan/) | Openbaar |
| 14 | Object-identificatie | UOI Ontwerp | Ontwerp voor een Unieke Objectidentificator (UOI) om gegevens op verantwoorde en betrouwbare wijze domein-overstijgend te kunnen registreren, uitwisselen (delen) en koppelen aan andere gegevens. | 2022 | [GitHub](https://geonovum.github.io/UOI-Ontwerp/) | Openbaar |
| 15 | Wijzigingen in model| Wijzigingsprotocol Informatiemodel Geluid | Dit document beschrijft de sturende principes achter het wijzigingsproces voor IMG. | 2023 | [GitHub](https://geonovum.github.io/IMG-wijzigingsprotocol/) | Intern |
| 16| Geostandaarden ISO | ISO `19xxx` | Bestandsmap met bij Geonovum aanwezige documentatie van standaarden. Dit zijn niet altijd de meest actuele of formele versies. | 2022 | [Teams](https://stichtinggeonovum.sharepoint.com/sites/Basisprogramma/Gedeelde%20documenten/Forms/AllItems.aspx?csf=1&web=1&e=51pjTB&cid=8e49bf07%2D9c61%2D4222%2D8d16%2Dd7e33e4ae315&FolderCTID=0x01200083248CF916421045A630BAD1CFC3A243&id=%2Fsites%2FBasisprogramma%2FGedeelde%20documenten%2FGeneral%2FStandaardisatie%20GII%2F4%20Bibliotheek%2FISO%2019xxx&sortField=Modified&isAscending=false&viewid=94f965cf%2D2c44%2D46c9%2Dbbd2%2D1aff169b4901) | Intern |
| 17 | Bestaande modellen | n.v.t. | Verschillende bestandsmappen (en archief?) met (documentatie van) verschillende door Geonovum ontwikkelde (sectorale) standaarden | n.v.t. | Teams | Intern |

<!-- ```diff
Niet meegenomen van github.com/geonovum
- eu_regelingen_datastrategie
- praktijkrichtlijn vector tiling
- DashboardGit
- INSPIRE-handreiking
- uml2json
- word2publicatie_template
- nen3610
- mim
- toegankelijke-locatiedata
- vector-tiling-best-practices
- webrichtlijnen-geo
``` -->
