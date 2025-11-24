# ReSpec

We maken standaarden met ReSpec. De inhoud van ReSpec documenten zit in Markdown bestanden die je met een text editor kunt bewerken. De bestanden worden in een GitHub repository beheerd. ReSpec

- zorgt voor een uniforme styling.
- onderhoudt referenties en verwijzingen naar andere documentatie, 
- verzorgt de inhoudsopgave,
- zorgt voor links naar vorige en meest recente versies, 
- heeft een integratie met Github issues.

Met volgende diagram beschrijft het proces voor het maken van een
ReSpec publicatie:

![publicatie infrastructuur](media/WorkflowReSpecGit.drawio.svg)

Het proces bestaat uit een [voortbrengingsproces](#het-voorbrengingsproces) waarin met het werkveld het
document wordt gemaakt. Als uit dit proces een publiceerbare versie ontstaat wordt deze via het [publicatieproces](./ReSpec-publiceren.md) gepubliceerd.

Geonovum gebruikt een fork van ReSpec die door Logius beheerd wordt. Meer
documentatie is op andere plaatsen te vinden:

- Er is een gedetailleerde
  [gebruikershandleiding](https://github.com/w3c/respec/wiki/ReSpec-Editor's-Guide)
  beschikbaar.
- Er is ook een
  [ontwikkelaarshandleiding](https://github.com/w3c/respec/wiki/Developers-Guide)
  te vinden.
- De Geonovum [wiki over ReSpec](https://github.com/Geonovum/respec/wiki) is
  een fork van de w3c ReSpec met aanpassingen voor Geonovum. Deze is
  achterhaald omdat we nu van de Logius Respec gebruik maken. (TODO aanpassen)

## Het voorbrengingsproces

- ReSpec documenten worden beheerd in een GitHub repository. Meestal zit er één ReSpec document in een repository.
- Maakt met `git clone` een lokaal kopie van repository waarin het ReSpec document zodat je het lokaal kunt bewerken. Een overzicht van alle GitHub repositories van Geonovum staat [hier](https://github.com/Geonovum/repositories).
- Het lokale kopie bestaat uit een collectie bestanden. De tekstuele inhoud zit meestal in markdown (*md) bestanden. Deze kan je nu lokaal wijzingen
- Met `git commit` en `git push` kun je de lokale wijzingen naar de centrale werkversie overzetten.

Meer informatie over [GitHub](../GitHub/index.md).
Meer informatie over [Markdown](../Markdown/index.md)

## Een ReSpec document publiceren op docs.geostandaarden.nl

Zie [ReSpec publiceren](ReSpec-publiceren.md)

## Een nieuw ReSpec document aanmaken

ReSpec documenten worden beheerd in een [GitHub](../GitHub/index.md) repository.

Gebruik de [Geonovum ReSpec template](https://github.com/Geonovum/NL-ReSpec-template) om een nieuw document te maken; druk op 'Use this template'. Dit maakt een GitHub repository met een template document. Dit kun je meteen gaan wijzigen. Pas op alle plekken waar TODO staat het document aan.

**Regel:** kies een logische naam voor het repository.

**Regel:** Een github repository mag maar één ReSpec document bevatten.