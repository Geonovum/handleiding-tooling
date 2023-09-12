# ReSpec - richtlijn code in tekst

Veel documenten die we bij Geonovum publiceren zijn datatspecificaties. In de tekst gebruik je daarom regelmatig stukken code. Het kan gaan om bepaalde termen of gegevens, waarover je iets in de lopende tekst wilt zeggen (_inline code_), of over langere stukken code (_code block_). 
Deze handleiding is specifiek bedoeld voor de toepassing van code in documentantatie over informatiemodellen. Voor andere type code staat het je vrij hoe je dit toepast.

## Inline code
Wanneer je in een lopende tekst een term of gegeven wilt markeren als code, pas je _inline code_ toe. Door een term of gegeven als `code` te markeren, maak je duidelijk dat het woord een specifieke technische betekenis heeft. _Inline code_ pas je toe door tekst tussen [backticks](https://en.wikipedia.org/wiki/Backtick) (`` ` ``) te plaatsen. De standaardopmaak voor _inline code_ is sober: ReSpec zet het lettertype enkel om in een _monospace font_. Voor een duidelijkere opmaak van _inline code_, is daarom een css-bestand beschikbaar. De schrijfwijze van metaklassenamen, modelelementnamen of gegevens volgt de [naamgevingsconventies van het MIM](https://geonovum.github.io/MIM-Werkomgeving/#afspraken-rondom-naamgeving-en-definities). Wees hierop alert als je _inline code_ toepast in handgeschreven teksten. 

> **Note**
> Waar en onder welke naam het bestand beschikbaar stellen?


### Metaklassenaam

Pas deze notatie toe als je een modelelement (in UML: stereotype) uit een metamodel opneemt in de lopende tekst. Geonovum past het metamodel informatiemodellering (MIM) toe, maar de onderstaande richtlijn kan ook toegepast worden op modelelementen uit een ander metamodel. Enkele voorbeelden van modelelementen uit het MIM zijn:

 - `«Objecttype»`
 - `«Attribuutsoort»`
 - `«Relatiesoort»`

Plaats voor deze notatiewijze naam van de metaklasse tussen twee dubbele _guillemets_ `«`, `»`. Je vindt ze met de volgende toetsencombinaties:

 - `«` = `"alt"` + `"["`
 - `»` = `"alt"` + `"]"`

In het markdown-bestand neem je een metaklassenaam als volgt op:
`` `«metaklassenaam»` ``. 

### Modelelementnaam

Pas deze notatie toe als je de naam van een modelelement van een informatiemodel opneemt in de lopende tekst. Het gaat dan bijvoorbeeld om de naam van een `«Objecttype»` of `«Attribuutsoort»` in een specifiek domeinmodel, zoals bijvoorbeeld:

 - `Pand` (`«Objecttype»`)
 - `Persoon` (`«Objecttype»`)
 - `naam` (`«Attribuutsoort»`)
 - `geboortedatum` (`«Attribuutsoort»`)
 - `geometrie` (`«Attribuutsoort»`)
 - `VlakOfMultivlak` (`«Keuze»`)

In het markdown-bestand neem je een metaklassenaam als volgt op:
`` `modelelementnaam` ``.

### Gegeven

Pas deze notitie toe als je een feitelijk of fictief gegeven opneemt in de lopende tekst. Het gaat om concrete waarden zoals die in een registratie (kunnen) voorkomen, zoals: 

 - `"Jan"`
 - `"01-01-1970"`
 - `"234.5"`
 - `"[125.6, 10.1]"`

Specifiek in de context van het MIM, gaat het om waarden die ingevuld (kunnen) worden bij de volgende modelelementen:

 - `«Attribuutsoort»`
 - `«Gegevensgroeptype»`
 - `«Relatiesoort»`
 - `«Relatieklasse»`
 - `«Data-element»`
 - `«Referentie-element»`
 - `«Enumeratie-waarde»`

In het markdown-bestand neem je een metaklassenaam als volgt op:
`` `"gegeven"` ``.

### Voorbeeld: gecombineerde inlinecodetypen

Stel je wilt in een tekst de volgende zin opnemen:

>Het model bevat een objecttype persoon met een attribuutsoort naam met het gegeven: Jan én een attribuutsoort geboortedatum met het gegeven: "01-01-1970".

Dan ziet die zin er, na toepassing van bovenstaande richtlijnen er als volgt uit:

>Het model bevat een `«Objecttype»` `Persoon` met een `«Attribuutsoort»` `naam` met het gegeven:`"Jan"` én een `«Attribuutsoort»` `geboortedatum` met het gegeven:`"01-01-1970"`.

Uitgeplitst naar inlinecodetype, levert dat het volgende overzicht op:

##### Metaklassenaam
 - `«Objecttype»`
 - `«Attribuutsoort»`

##### Modelelementnaam
 - `Persoon`
 - `naam`
 - `geboortedatum`

##### Gegeven
 - `"Jan"`
 - `"01-01-1970"`

## Code block

Als je een stuk code hebt dat uit meerdere regels bestaat, kun je dit in een _code block_ plaatsen. Hiermee scheidt je de code van de lopende tekst in een apart tekstblok. In het markdown-bestand neem je een stuk code dat uit meerdere regels bestaat als volgt op. Plaats de code tussen drie backticks (```` ``` ````). Geef optioneel direct achter de eerste drie backticks de (programmeer-)taal op voor _syntax highlighting_, zoals in het volgende voorbeeld.

##### input

<pre>```json
{
  "type": "Feature",
  "geometry": {
    "type": "Point",
    "coordinates": [125.6, 10.1]
  },
  "properties": {
    "name": "Dinagat Islands"
  }
}
```</pre>

##### rendered output

```json
{
  "type": "Feature",
  "geometry": {
    "type": "Point",
    "coordinates": [125.6, 10.1]
  },
  "properties": {
    "name": "Dinagat Islands"
  }
}
```