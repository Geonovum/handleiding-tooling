# Werkwijzen voor het maken van een begrippenkader

Stappen in het maken van een begrippenkader

1. Schrijf in een paragraaf de scope op van het begrippenkader.
2. Zorg voor een goede set met bronnen


```mermaid
---
config:
  flowchart:
    htmlLabels: true
---
flowchart LR
    Start([Start])
    Start --> q1
    q1{is het begrip in scope?}
    q1-- ja --> q2
    q1-- nee --> q4
    q2{hebben we de definitie zelf bedacht?}
    q2-- ja -->a1
    q2-- nee -->q3
    a1[neem begrip op in begrippenkader.]
    a1 --> Klaar
    q3{staat de definitie in een ander begrippenkader?}
    q3-- ja -->a2
    q3-- nee -->a3
    a2[kopieer het begrip en verwijs «is exact overeenkomstig met» naar andere begrippenkader.]
    a2 --> Klaar
    a3[kopieer de definitie en verwijs in de toelichting naar andere begrip.]
    a3 --> Klaar
    q4{Willen we naar het begrip verwijzen?}
    q4-- ja --> q5
    q4-- nee --> Klaar
    q5{komt het begrip uit een ander kader?}
    q5-- ja --> a5
    q5-- nee --> a6
    a5[verwijs naar de identificatie van het begrip.]
    a5 --> Klaar
    a6[verwijs in de toelichting naar het begrip.]
    a6 --> Klaar
    Klaar([klaar])
```

**Regel:** ALS een begrip elders gedefinieerd is en machine leesbaar
beschikbaar en dit begrip is van belang voor ons kader  DAN nemen we een begrip met deze voorkeursnaam, en zonder
definitie op en verwijzen (SKOS-relatie) we naar het begrip in het andere begrippenkader.

**Regel:** ALS  een begrip gedefinieerd is in een bestaand document (bijv. begrippenkader rijksinspecties als PDF) maar niet machineleesbaar gepubliceerd is DAN publiceren we dit begrip zelf en verwijzen naar de bron.
