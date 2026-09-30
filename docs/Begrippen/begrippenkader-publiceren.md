# BegrippenXL-portaal


## Inhoud

- [Huidige stand van zaken](#huidige-stand-van-zaken)
- [Beheer via het uploadportaal](#beheer-via-het-uploadportaal)
- [Uploaden via een bestand](#uploaden-via-een-bestand)
- [Uploaden via een URL](#uploaden-via-een-url)
- [Importeren vanuit een wiki](#importeren-vanuit-een-wiki)
- [Logging en terugkoppeling](#logging-en-terugkoppeling)
- [URL wijzigen voor rechtstreeks inlezen via Git](#url-wijzigen-voor-rechtstreeks-inlezen-via-git)
- [Governance en autorisatie](#governance-en-autorisatie)

## Huidige stand van zaken

Er zijn twee BegrippenXL-portalen:

| Omgeving | URL | Inhoud |
|---|---|---|
| Productie | [definities.geostandaarden.nl](https://definities.geostandaarden.nl/) | 9 thema's en 22 modellen |
| Staging | [staging-definities.geostandaarden.nl](https://staging-definities.geostandaarden.nl/) | 1 thema en 11 modellen |

## Beheer via het uploadportaal

Het beheer vindt plaats via het [BegrippenXL-uploadportaal](https://upload.begrippenxl.nl/).

Het portaal ondersteunt drie manieren om gegevens te importeren:

1. via een bestand;
2. via een URL;
3. vanuit een wiki.

## Uploaden via een bestand

Gebruik deze methode om een lokaal RDF-bestand te uploaden.

1. Open **Upload RDF**.
2. Selecteer **Bestand**.
3. Kies een bestand in een van de volgende formaten:
   - Turtle (`.ttl`);
   - RDF/XML (`.rdf` of `.xml`).
4. Kies het woordenboek waarin het bestand moet worden geladen.
5. Klik op **Uploaden**.

## Uploaden via een URL

Gebruik deze methode om RDF vanaf een vooraf geconfigureerde URL in te lezen.

1. Open **Upload RDF**.
2. Selecteer **URL**.
3. Kies het woordenboek waarin de gegevens moeten worden geladen.
4. Kies de vooraf geconfigureerde URL.
5. Klik op **Uploaden**.

## Importeren vanuit een wiki

Gebruik deze methode om gegevens vanuit een vooraf geconfigureerde wiki te importeren.

1. Open **Wiki importeren**.
2. Kies het woordenboek waarin de gegevens moeten worden geladen.
3. Kies de vooraf geconfigureerde wiki.
4. Stel indien nodig de volgende opties in:
   - **Samenvoegen:** plaats de import over de bestaande inhoud heen.
   - **Debug:** schakel deze optie in wanneer problemen optreden bij het uploaden, zodat meer debuginformatie beschikbaar komt.
5. Klik op **Uploaden**.

## Logging en terugkoppeling

Na een upload geeft het portaal informatie over het resultaat:

- De status **done** betekent dat het Turtle-bestand succesvol is geüpload.
- De gebruiker ontvangt na iedere upload een e-mail.
- De bijlage bij deze e-mail bevat de logging van de Skosify-datacontrole.
- Foutmeldingen worden eveneens meegestuurd. Een mislukte upload krijgt de status **failure**.

## URL wijzigen voor rechtstreeks inlezen via Git

De ingestelde URL kan worden gewijzigd om gegevens rechtstreeks vanuit Git in te lezen. Gebruik hiervoor de wijzigingsfunctie bij de betreffende URL in het uploadportaal.

> **Let op:** De oorspronkelijke presentatie bevat geen verdere stappen of voorwaarden voor het wijzigen van deze URL.

## Governance en autorisatie

Autorisatie kan per woordenboek worden ingesteld.

---
