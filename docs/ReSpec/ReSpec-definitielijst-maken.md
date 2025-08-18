# Definities in ReSpec


## Intro

Een  onderdeel van een dataspecificatie is de definitie van begrippen. Steeds vaker leggen we bij Geonovum begrippen vast in een [begrippenkader](https://definities.geostandaarden.nl/nl/). Idealiter verwijs je voor de definitie van een begrip altijd daarnaar. Op deze plek leggen we uit hoe we nu een definitie opnemen.

## Definitie van een begrip opnemen in specificatie

In een informatiemodel worden veel begrippen gedefinieerd in de met Imvertor gemaakte catalogus. In andere hoofdstukken worden ook begrippen gedefinieer. Deze handleiding gaat hierover

De [beschrijving in de handleiding van ReSpec](https://respec.org/docs/#definitions-and-linking) is heel summier. Hierdoor pas je het snel en eenvoudig toe, maar het leidt niet vanzelfsprekend tot éénduidig gebruik. 

Een definitie wordt als volgt gemaakt:

```markdown
<dfn>boek</dfn>een samengebonden of genaaid aantal bedrukte bladen.
```

Het resultaat ziet er zo uit:

![Voorbeeld van definitie in ReSpec](media/ReSpec-definitie.png)

## Gebruik van definitie

Wil je naar een gedefinineerd begrip verwijzen gaat dat zo: `<a>boek</a>`` of `[=boek-]`

Houd als richtlijn dat je alleen de eerste keer dat een term in een alinea voorkomt een verwijzing maakt. Dit voorkomt een overdaad aan verwijzingen in de tekst.

## Aanvullende styling

wrap een definitie in een aside met attribute class="definition"

```html
<aside class="definition">
    <dfn>papier</dfn>stof om te beschrijven of bedrukken, uit vezelachtige
    stoffen, hout, lompen, stro enz. vervaardigd
</aside>
```

## Resultaat

[`afbeelding opnemen`]

> **TODO**
> Het zou wel heel leuk zijn om een link met [NL-SBB](https://docs.geostandaarden.nl/nl-sbb/nl-sbb/) te leggen.
