# Markdown

Voor het extern publiceren van documenten en standaarden gebruiken we
[ReSpec](../ReSpec). Deze tool ondersteunt naast HTML en Javascript ook Markdown

[Markdown](https://nl.wikipedia.org/wiki/Markdown) is een lichtgewicht
opmaaktaal op basis van platte tekst die zodanig ontworpen is dat het
gemakkelijk valt te converteren naar HTML en andere. Markdown wordt vaak
gebruikt voor de opmaak van project documentatie (README-bestanden), eenvoudige
CMS-systemen en berichten in online fora. Je kunt Markdown in iedere simpele
teksteditor bewerken.

Het ontwerpdoel van de taal is leesbaarheid. Teksten geschreven met behulp van
Markdown worden geacht al leesbaar te zijn voordat opmaak is toegepast op de
tekst. Opmaakinstructies en tags zijn dan ook niet te vinden in pure Markdown.

## Lokale markdown in je browser

Sommige browsers weigeren het openen van lokale bestanden, of negeren links naar
locale bestanden. Dit kun je in de configuratie aanpassen:

### Chrome

Je moet twee dingen instellen:

- Local access: Toestaan dat je local files toont in Chrome, dat is een opstart
  argument. Kan je doen vanuit een cmd-prompt
  `%localappdata%\google\chrome\application\chrome
  --allow-file-access-from-files
- CORS Toestaan : zelfde soort oplossing: `--disable-web-security`

Dit kan je ook in een snelkoppeling zetten als icoon op de desktop.

### Firefox

In Firefox kan je dat instellen via de parameters.

- Ga naar het configuratiescherm van Firefox door `about:config` in de zoekbalk te zetten.
- Firefox vraag nu of je het zeker weet. Niet twijfelen.
- zet de instelling `security.fileuri.strict_origin_policy = false` op false.

## Tools voor Markdown

| tool                                                                                        | omschrijving                                                                                    |
| ------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [Markdown Tutorial](https://www.markdownguide.org/getting-started/)                         | Handleiding Markdown                                                                            |
| [Markdown Reference](https://www.markdownguide.org/basic-syntax)                            | Naslag Markdown                                                                                 |
| [Visual Studio Code](https://code.visualstudio.com/)                                        | Fijne teksteditor die ook goed integreert met Github Desktop                                    |
| [PowerToys](https://learn.microsoft.com/en-us/windows/powertoys/)                           | Geeft preview van Markdown rechtstreeks in Windows Explorer (en nog heeel veel andere tooltjes) |
| [Tables Generator](https://www.tablesgenerator.com/markdown_tables)                         | Helpt met het maken van tabellen in MarkDown                                                    |
| [Markdown Table](https://marketplace.visualstudio.com/items?itemName=TakumiI.markdowntable) | VSCode plugin voor het editen van Markdown tabellen.                                            |
| [Prettier](https://prettier.io/)                                                            | Een code formatter die automatisch zorgt dat je markdown aan de regels voldoet.                 |
| [markdownlint](https://github.com/Laboratoria/mdlint)                                       | Een style checker form markdown bestanden. Geeft meldingen voor verkeerde markdown               |
| [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)    | VSCode plugin. Klik rechtsonder op "Go Live" en je ReSpec doc wordt in live browser geopend.    |

## Regels voor Markdown

Styling regels vastleggen voor Markdown zorgt ervoor dat wijzigingen in de markdown ook
altijd inhoudelijke wijzigingen zijn. Suggesties hiervoor

- Regellengte vastleggen.
- Hoeveel springen we in?
- Gebruiken unix end-of-line of windows

Deze afspraken kunnen we ook vastleggen. Zie hieronder twee voorbeelden. Het lijkt
erop dat de veschillende tools op verschillende manier formatteren. Niet alles
gaat goed samen.

Voorbeeld van '.prettierrc' gebruikt in dit project:

```json
{
  "printWidth": 80,
  "tabWidth": 2,
  "useTabs": false,
  "singleQuote": true,
  "endOfLine": "lf",
  "proseWrap": "always"
}
```

Voorbeeld van `.markdownlinkt.json`:

```json
{
    "default": true,
    "MD003": { "style": "atx" },
    "MD007": { "indent": 4 },
    "MD013": { "line_length": 80, "code_blocks": false, "heading_line_length": 200, "tables": false},
    "no-hard-tabs": false
}
```
