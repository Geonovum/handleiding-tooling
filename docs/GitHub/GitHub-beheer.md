# Beheer GitHub

Geldt voor organisaties Geonovum en Geonovum-labs (**Geonovum-labs nog zonder teams!**).


## GitHub beheer

GitHub beheerders zijn te vinden in het github [gebuikersoverzicht](https://github.com/orgs/Geonovum/people?query=role%3Aowner).

**Regel:** Alle teamleden hebben 2FA aanstaan. (Vanuit Github required voor contributors) [Configure 2FA](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication)


**Regel:** Om lid te worden van de Geonovum organisatie op GitHub moet je een actief email adres hebben bij Geonovum of op de pas-toe-of-leg-uit lijst staan.

**Regel:** De GitHub beheerders beheren de pas-toe-of-leg-uit lijst.

**Regel:** Iedereen binnen de organisatie heeft (automatisch) leesrechten tot alle repos.

**Regel:** Iedereen (binnen en buiten de Geonovum organisatie) heeft (automatisch) leesrechten tot alle *publieke* repos.

**Regel:** Wie behoort tot de Geonovum organisatie heeft toegang tot GitHub repositories via GitHub teams. Beheerde repositories moeten daarom onder een GitHub-team vallen.

**Regel:** Omdat externen niet lid kunnen worden van een team worden lees- en schrijfrechten
voor externen op repository niveau geregeld.

**Regel:** Mensen buiten de Geonovum organisatie kunnen individueel toegang krijgen tot repositories.

 Hierdoor worden ze [outside collaborator](https://docs.github.com/en/organizations/managing-user-access-to-your-organizations-repositories/managing-outside-collaborators/adding-outside-collaborators-to-repositories-in-your-organization#about-outside-collaborators). Per outside collaborator is te zien tot welke repositories ze toegang hebben via [deze link](https://github.com/orgs/Geonovum/outside-collaborators) (als admin).

**Regel:** Er is geen bezwaar tegen het gebruik van een privé github account binnen het Geonovum team. 

Achterliggende gedachte is dat er flink wat mensen al een github account hebben 
en het geen toegevoegde waarde heeft om een tweede github account te hebben.

## GitHub teams

Er is een aantal teams gemaakt binnen Geonovum. Deze zijn te vinden op: <https://github.com/orgs/Geonovum/teams>.

**Regel:** Ieder team is gekoppeld aan een actief project binnen Geonovum.

**Regel:** GitHub-team hebben een maintainer (soms meerdere) als eerstverantwoordelijke voor de groep repositories. De `maintainer` van het GitHub-team waar de repository onder valt bepaalt *wie wat mag*. De GitHub beheerders voeren admin werkzaamheden uit.

**Regel:** Niet meer actieve teams (alle repos zijn archived) krijgen toevoeging `(archived)` en de zichtbaarheid wordt op `Secret` gezet.

**Regel:** Repositories met content die in beheer zijn horen bij een team dat aanspreekpunt is voor die repository.   
(*Andere* repositories geven in de README.md aan wie aanspreekpunt is voor die repository. *Willen we dit nog of alleen voor legacy/archived? Spreekt regel toegang repos via teams tegen.*)

**Regel:** Publieke Geonovum repositories welke toegevoegd worden aan een team krijgen in beginsel de role `Write`.

**Conventie:** Team namen eindigen op ' team'. Bijvoorbeeld 'DSO team'.

## GitHub repository roles

role | description
--- | ---
Read | Read and clone repositories. Open and comment on issues and pull requests.
Triage | Read permissions plus manage issues and pull requests.
**Write** | Triage permissions plus read, clone and push to repositories.
Maintain | Write permissions plus manage issues, pull requests and some repository settings (e.g. *github pages*).
Admin | Full access to repositories including **sensitive and destructive** actions.

**Regel:** Repositories vallen onder een Github-team waarvan de `maintainer` de roles bepaalt. De GitHub beheerders voeren het uit.

**Regel:** Outside_collaborators welke aanpassingen op een Geonovum repository doen, krijgen in beginsel de role `Write`.

**Regel:** Indien de role `Write` niet toereikend is kan de role aangepast worden naar `Maintain`. Dit geldt voor outside-collaborators en team-members. **NB** role `Admin` is niet nodig.

**Regel:** GitHub beheerders (admin) zijn verantwoordelijk voor en behulpzaam bij archiveren en andere **sensitieve en destructieve** acties.