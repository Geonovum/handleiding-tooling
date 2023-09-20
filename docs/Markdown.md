# Markdown

Voor het extern publiceren van documenten en standaarden gebruiken we “ReSpec”. ReSpec werkt met HTML en Javascript. Dat is niet voor iedereen de meest voor de hand liggende documentatie tooling. Gelukkig ondersteunt ReSpec ook het gebruik van Markdown

[Markdown](https://nl.wikipedia.org/wiki/Markdown) is een lichtgewicht opmaaktaal op basis van platte tekst die zodanig ontworpen is dat het gemakkelijk valt te converteren naar HTML en andere formaten middels een applicatie met dezelfde naam. Markdown wordt vaak gebruikt voor de opmaak van project documentatie (README-bestanden), eenvoudige CMS-systemen en berichten in online fora. Tekst in deze opmaaktaal is gemakkelijk te maken met een simpele teksteditor.

Het ontwerpdoel van de taal is leesbaarheid. Teksten geschreven met behulp van Markdown worden geacht al leesbaar te zijn voordat opmaak is toegepast op de tekst. Opmaakinstructies en tags zijn dan ook niet te vinden in pure Markdown.

## Het viewen van Markdown in je broswer

Het openen van lokale bestanden in de browser is soms lastig omdat browsers vaak verwijzingen naar lokale bestanden niet toestaan. Voor iedere browser zijn de instellingen hiervoor verschillend:

### Chrome

Je moet twee dingen instellen:

- Local access: Toestaan dat je local files toont in Chrome, dat is een opstart argument. Kan je doen vanuit een cmd-prompt `%localappdata%\google\chrome\application\chrome --allow-file-access-from-files
- CORS Toestaan : zelfde soort oplossing: `--disable-web-security`

Het opstartcommando kan je ook in een snelkoppeling zetten als icoon op de desktop

### Firefox

In Firefox kan je dat makkelijker instellen via de parameters.

In de adresbalk: about:config, dan het risico aanvaarden, en deze parameter veranderen: `security.fileuri.strict_origin_policy = false` (dus op false zetten)

## Tools voor Markdown

| tool                                                                                        | omschrijving                                                                                    |
| ------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [Markdown Tutorial](https://www.markdownguide.org/getting-started/)                         | Handleiding Mardown                                                                             |
| [Markdown Reference](https://www.markdownguide.org/basic-syntax)                            | Naslag Markdown |
| [Visual Studio Code](https://code.visualstudio.com/)                                        | Fijne teksteditor die ook goed integreert met Github Desktop                                    |
| [Notepad++](https://notepad-plus-plus.org/)                                                 | Nog een goede editor                                                                            |
| [PowerToys](https://learn.microsoft.com/en-us/windows/powertoys/)                           | Geeft preview van Markdown rechtstreeks in Windows Explorer (en nog heeel veel andere tooltjes) |
| [Tables Generator](https://www.tablesgenerator.com/markdown_tables)                         | Helpt met het maken van tabellen in MarkDown                                                    |
| [Markdown Table](https://marketplace.visualstudio.com/items?itemName=TakumiI.markdowntable) | Plugin voor Visual Studion Code die het editen van Markdown tabellen ondersteunt.               |
| [Prettier](https://prettier.io/)                                                            | Een code formatter die automatisch zorgt dat je markdown aan de regels voldoet.                 |
| [mdlint](https://github.com/Laboratoria/mdlint)                                             | Een style checker form markdown bestanden. Geef meldingen voor verkeerde markdown               |


> **Note**
> `@Wilko`: we zouden nog een stel regels kunnen maken voor de formattering van markdown. Maximale regellengte = 80 bijvoorbeeld. Dit zou in `.mdlintrc` of de configuratie van Prettier kunnen gebruiken.