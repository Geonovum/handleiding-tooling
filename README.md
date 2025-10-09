# Handleiding tooling

In dit repository zit de [handleinding van de Geonovum tooling](https://geonovum.github.io/handleiding-tooling/).
Deze handleiding heeft twee doelen:

- Handleiding van de tools binnen die binnen Geonovum gebruikt worden.
- De gezamenlijke werkwijze van Geonovum vast

De handleiding is in MarkDown geschreven en gebruikt [mkdocs](https://www.mkdocs.org/).

## Werwijze voor bijwerken handleiding

- Dit document is van iedereen. Als je geen schrijfrechten hebt vraag die dan aan bij een [GitHub beheerder](https://github.com/orgs/Geonovum/people?query=role%3Aowner).
- De menustructuur zit in het bestandje `mkdocs.yml`. Hierin is een aantal hoofdonderwerpen gedefinieerd.
- Voor ieder hoofdonderwerp is een mapje gemaakt in de `docs` folder.
- In iedere folder is een subfolder `media` voor de plaatjes.
- Als je je wijzingen commit en pusht naar github wordt de [handleiding](https://geonovum.github.io/handleiding-tooling/) automatisch bijgewerkt


### Lokale preview

Mkdocs biedt ondersteuning om de gemaakte handleiding lokaal te previewen. Zie hiervoor de [user guide](https://www.mkdocs.org/user-guide/). Twee opties zijn:

- Gebruik [mkdocs buid](https://www.mkdocs.org/user-guide/cli/#mkdocs-build) om lokaal een statische versie van de handleiding te maken.
- Gebruik [mkdocs serve](https://www.mkdocs.org/user-guide/cli/#mkdocs-serve) om je eigen repository lokaal uit te serveren. Je zie dat de pages live mee veranderen.
