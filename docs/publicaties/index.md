# Publicatieservers bij Geonovum

## register.geostandaarden.nl


Invulinstructies: <https://github.com/Geonovum/technisch-register-2019/blob/master/documentatie/HandleidingVoorBeheerdersInformatiemodellen.md>

Technische onderdelen van de standaard worden op:
[register.geostandaarden.nl](https://register.geostandaarden.nl) gezet. Hoe je
dit met een webhook kan doen staat beschreven in:
[technisch-register-2019](https://github.com/Geonovum/technisch-register-2019/blob/master/documentatie/Handleiding%20voor%20beheerders%20informatiemodellen.md)

### Het publiceren van UML modellen

In de map `informatiemodel` wordt een informatiemodel gepubliceerd. Publicatieinstructies:

#### EAP

Dit is het natieve formaat van Enterprise Architect.

- Zorg ervoor dat alle links naar svn uit het bestand verwijderd zijn: selecteer een beheerde folder. Kies 'Configure->Package-VC'. Haal het vinkje weg bij 'Control Package'.
- Zet de versienummer van het model in de bestandsnaam.


### xmi

xmi is het uitwisselformaat voor UML modellen. Er zijn veel smaken. Voorstel voor manier van publiceren:

- Niet alleen het model, maar ook alle packages waarnaar verwezen wordt.
- Selecteer het te exporteren root package. Kies 'Publish-->Export XML'.
- Kies Export Type: 'XML 1.1'.

## tools.geostandaarden.nl


