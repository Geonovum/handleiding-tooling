# Werkwijze informatiemodelleren

## De basis

**Wat is een informatiemodel?**

Wanneer we informatie over bepaalde onderwerpen willen inwinnen, registreren of uitwisselen, dan is het van belang om deze informatie eerst goed te beschrijven. We doen dit door een model te maken van de informatie, ofwel: een informatiemodel. Dit beschrijft de structuur, semantiek en de eigenschappen van informatie over dingen in de werkelijkheid ([lees meer](https://docs.geostandaarden.nl/mim/mim/#wat-is-een-informatiemodel)).

**Wat is UML?**

UML (Unified Modelling Language) is de modelleertaal die voorgeschreven wordt voor het maken van een informatiemodel. UML bepaalt voor een deel de structuur en informatie-elementen van het informatiemodel, maar het laat nog teveel vrijheden om richtinggevend te zijn. Binnen UML kunnen én moeten nog extra regels vastgelegd worden om de betekenis van de informatie-elementen eenduidig vast te leggen. Voor dat doeleinde is het Metamodel voor Informatiemodellering (MIM) ontwikkeld ([lees meer](https://docs.geostandaarden.nl/mim/mim/)).

**Wat is het Metamodel voor Informatiemodellering (MIM)?**

Een metamodel beschrijft de informatie-elementen die kunnen voorkomen in een informatiemodel. Het is in feite het informatiemodel van onze informatiemodellen. Het Metamodel voor Informatiemodellering definieert een verzameling van modelleerconstructies in de vorm van bouwstenen, oftewel: **modelelementen** zoals ***Objecttype***, ***Relatiesoort*** en ***Attribuutsoort*** met bijbehorende betekenis en afspraken over hoe je dit kunt toepassen in een informatiemodel. Het MIM is een soort "sjabloon" voor de ontwikkeling van conceptuele en logische informatiemodellen bij Geonovum ([lees meer](https://docs.geostandaarden.nl/mim/mim/#wat-is-het-metamodel-voor-informatiemodellering)).

**Welke soorten (informatie)modellen zijn er?**

De modellering van een bepaald domein start in principe met het beschrijven van kennis, te weten de begrippen die een rol spelen in een domein, uitgedrukt in een (meestal) domein specifieke terminologie: **niveau 1**. Op dit niveau is er nog geen of slechts een beperkte notie van welke informatie er geregistreerd en uitgewisseld moet worden; er dus geen nog sprake van een informatiemodel. MIM verstaat onder een informatiemodel een *conceptueel*: **niveau 2**, of *logisch informatiemodel*: **niveau 3**. Het metamodel (MIM) richt zich dan ook primair op niveau 2 en 3. Tot slot kan een het informatiemodel uitgewerkt worden in verschillende soorten technische datamodellen en schema's, zoals XML of JSON. In MIM wordt dit **niveau 4** genoemd. Meer informatie over de verschillende niveau's, vind je hier:  

- Niveau 1: [Model van begrippen](https://docs.geostandaarden.nl/mim/mim/#beschouwingsniveau-1-model-van-begrippen)
- Niveau 2: [Conceptueel informatiemodel](https://docs.geostandaarden.nl/mim/mim/#beschouwingsniveau-2-conceptueel-informatiemodel)
- Niveau 3: [Logisch informatiemodel](https://docs.geostandaarden.nl/mim/mim/#beschouwingsniveau-3-logisch-informatie-of-gegevensmodel)
- Niveau 4: [Fysiek of Technisch gegevensmodel](https://docs.geostandaarden.nl/mim/mim/#beschouwingsniveau-4-fysiek-of-technisch-gegevens-of-datamodel)

Een informatiemodel is altijd **techniek-onafhankelijk**. Niveau 4 valt daarom buiten de scope van het MIM. Wel streeft het MIM naar *Model Driven Development*, waarbij technische modellen (niveau 4) gegenereerd kunnen worden vanuit logische modellen (niveau 3). Hiervoor gebruiken we bij Geonovum Imvertor ([lees meer](https://docs.geostandaarden.nl/mim/mim/#typering-van-modellen-en-wat-wel-en-niet-in-scope-is-van-deze-standaard)).


## ​​​​​​​​​​​​​locatie-informatie

**Basismodel Geo-informatie (NEN3610)**

Geonovum richt zich in het bijzonder op het modelleren van geografische informatie. Hiervoor is het Basismodel Geo-informatie (NEN3610) leidend. Aanvullend op het MIM dat de methode van het informatiemodelleren standaardiseert, geeft het [Basismodel geo-informatie](https://stichtinggeonovum.sharepoint.com/sites/msteams_bf388d/Gedeelde%20documenten/Forms/AllItems.aspx?id=/sites/msteams_bf388d/Gedeelde%20documenten/General/A%20Informatiemodellen/NEN3610/NEN%203610_2022%20nl.pdf&amp;viewid=3a693696-6e40-41fb-a369-1de62b54d550&amp;parent=/sites/msteams_bf388d/Gedeelde%20documenten/General/A%20Informatiemodellen/NEN3610) regels voor het *eenduidig beschrijven van conceptuele en logische informatiemodellen met locatiegebonden informatie* (geo-informatie). Hoe je deze regels hanteert, beschrijft de [handreiking voor het toepassen van het Basismodel geo-informatie](https://geonovum.github.io/nen3610-werkomgeving/). Tevens bestaat er een Linked Data-toepassing van het Basismodel geo-informatie. Meer informatie hierover vind je terug in het document [NEN 3610 - Linked Data](https://geonovum.github.io/NEN3610-Linkeddata/).

**Geometrie in informatiemodellen**

Het basismodel geo-informatie (NEN3610) verwijst voor de toepassing van geometrie in informatiemodellen naar de relevante ISO-normen. Voor toepassing in het werkveld zijn deze normen niet toegankelijk genoeg. De handleiding [toepassing van geometrie in informatiemodellering](https://geonovum.github.io/gimeg/) slaat een brug tussen NEN3610 en het werkveld.

**Coördinaatreferentiesystemen**

In de [handreiking gebruik coördinaatreferentiesystemen bij uitwisseling en visualisatie van geo-informatie](https://docs.geostandaarden.nl/crs/crs/), vind je een bundeling van bestaande adviezen van het [Nederlandse Samenwerking Geodetische Infrastructuur](https://www.nsgi.nl/) (NSGI) over geodetisch correct gebruik van de in Nederland gebruikte coördinaatreferentiesystemen (CRS-en).

**Langelijnenadvies**

Voor het waarborgen van de nauwkeurigheid van lange lijnstukken van grenzen, passen we het advies [Eenduidige transformatie van grenzen tussen ETRS89 en RD](https://geoforum.nl/uploads/default/original/2X/c/c0795baa683bf3845c866ae4c576a880455be02a.pdf) toe.

**Geometrie in Uitwisselingsformaten**

Geography Markup Language (GML) is een hele volledige, maar ook vrij complexe standaard, en daardoor niet geschikt voor alle toepassingen. De handreiking [geometrie in uitwisselingsformaten](https://docs.geostandaarden.nl/g4w/vv-hr-geox-20220104/#kieswijzer) geeft daarom een overzicht van de meest populaire alternatieven voor het uitwisselen en publiceren van vectordata - volgens open standaarden. Het gaat hierbij om 'lichtere bestandsformaten', in tegenstelling tot het allesomvattende (maar daardoor ook complexere) GML-formaat.

**Basisgeometrie**

In sommige situaties beschrijven verschillende informatiemodellen hetzelfde object in de werkelijkheid. Als elk model een unieke set van kenmerken bevat van hetzelfde object en daarvoor dezelfde geometrie hanteert, is het niet nodig dat elk model de geometrie apart vastlegt. Je kunt die modellen naar één geometrie laten verwijzen. Het [model Basisgeometrie](https://geonovum.github.io/Basisgeometrie-Werkomgeving/) biedt hiervoor een gestandaardiseerde oplossing.

## relevante standaarden​

**​​​​​​​​​​​​​Bij de ontwikkeling van een geo-informatiestandaard, krijg je te maken met een grote verscheidenheid aan verschillende soorten standaarden. Niet alle standaarden zijn voor elke toepassing relevant.**

**Raamwerk van Geo-standaarden**

Het [raamwerk van geo-standaarden](https://geonovum.github.io/raamwerk-geostandaarden/) helpt bij de opzet en ontwikkeling van een geo-informatie infrastructuur om de juiste set standaarden te kiezen. Het benoemt de internationale en nationale standaarden die voor Nederland binnen het geo-domein van toepassing zijn voor aansluiting met andere domeinen. Onderwerpen die aan bod komen zijn standaarden voor: [geo-informatie](https://geonovum.github.io/raamwerk-geostandaarden/#geo-standaarden-in-samenhang), [informatiemodellering](https://geonovum.github.io/raamwerk-geostandaarden/#informatiemodellen), [visualisatie](https://geonovum.github.io/raamwerk-geostandaarden/#visualisatie), [API's](https://geonovum.github.io/raamwerk-geostandaarden/#application-programming-interfaces), [uitwisselformaten](https://geonovum.github.io/raamwerk-geostandaarden/#uitwisselformaten), [metadata](https://geonovum.github.io/raamwerk-geostandaarden/#metadata) en [coördinaatreferentiesystemen](https://geonovum.github.io/raamwerk-geostandaarden/#coordinaatreferentiesystemen).

**Standaarden Op Teams**

Hoofdmap waar documentatie van de [ISO-standaarden op Teams](https://stichtinggeonovum.sharepoint.com/sites/Basisprogramma/Gedeelde%20documenten/Forms/AllItems.aspx?csf=1&amp;web=1&amp;e=51pjTB&amp;cid=8e49bf07-9c61-4222-8d16-d7e33e4ae315&amp;FolderCTID=0x01200083248CF916421045A630BAD1CFC3A243&amp;id=/sites/Basisprogramma/Gedeelde%20documenten/General/Standaardisatie%20GII/4%20Bibliotheek/ISO%2019xxx&amp;sortField=Modified&amp;isAscending=false&amp;viewid=94f965cf-2c44-46c9-bbd2-1aff169b4901) beschikbaar zijn. We beschikken niet over de complete set relevante geo-standaarden. Bovendien zijn de documenten in deze map niet altijd de formeel definitieve versie van de standaard.

## Software installeren en configureren

​​​​​​​**UML modelleersoftware: Enterprise Architect (EA)**

Informatiemodellen ontwikkelen we bij Geonovum met de software Enterprise Architect van Sparx Systems. Download en installeer EA ([installatie-instructie](https://sparxsystems.com/enterprise_architect_user_guide/15.2/product_information/installea.html)). Bewaar het installatiebestand. De licentie voor support van Sparx verloopt na een jaar en daarmee tevens de *credentials* voor het downloaden van de laatste versie. Je kunt EA dan nog wel gebruiken. Mocht je EA opnieuw willen installeren, dan heb je dit bestand en je oorspronkelijke *credentials *nodig. Bewaar die dus goed!

**Versiebeheersoftware: Subversion (SVN)**

Informatiemodellen staan altijd onder versiebeheer. Hiervoor gebruiken we het programma **TurtoiseSVN**. Vraag **toegang **tot de SVN-server (via **Rob Kaesehagen**). Installeer SVN en zet een project in versiebeheer ([installatie-instructie](https://geonovum.github.io/handleiding-tooling/SVN-installeren-voor-EAP/)). Ga je met een bestaand project aan de slag, lees dan in de handleiding [importeren bestaand SVN-project in EA](https://github.com/Geonovum/handleiding-tooling/blob/main/docs/SVN-importeren-bestaand-project.md)hoe je dat doet. Onder het kopje [versiebeheer](https://github.com/Geonovum/geonovum-werkwijze/blob/main/howto.md#72---versiebeheer), vind je meer informatie.

**MIM-toolbox voor Enterprise Architect**

Voor een eenvoudige toepassing van Metamodel voor Informatiemodellering (MIM) is de MIM-toolbox beschikbaar. Het gebruik van de toolbox is niet verplicht, maar we raden het wel aan. Het bespaart je als modelleur veel handwerk. De handleiding [importeren en toepassen MIM-toolbox voor Enterprise Architect](https://github.com/Geonovum/MIM-Werkomgeving/blob/master/UML%20profieltooling/werkversie1.1.1/README.md) legt uit hoe je hiermee aan de slag kunt.

**GitHub**

Werkversies van informatiemodellen maken we publiek toegankelijk via GitHub. De **handleiding** [GitHub-introductie](https://geonovum.github.io/handleiding-tooling/GitHub-Inleiding/) legt uit waarom GitHub handig is en hoe je ermee aan de slag kunt. Een **beschrijving** van de manier waarop we GitHub gebruiken, is opgenomen in de handleiding GitHub, onder [werkwijze Geonovum](https://geonovum.github.io/handleiding-tooling/GitHub/#werkwijze-geonovum). Om met GitHub te werken heb je een **account** nodig. Als je dat nog niet hebt, maak er dan één aan ([account maken](https://geonovum.github.io/handleiding-tooling/GitHub/#installatie-en-inrichting)). Vraag vervolgens aan één van de GitHub-*administrators* om je toe te voegen aan de [Geonovum-GitHub-pagina](https://github.com/Geonovum), dit kan onder andere via het Slack-kanaal **#github-admins**. Zorg hierna dat je de juiste **rechten** ontvangt voor de *repository *waaraan je gaat werken. Ga je aan een nieuw project werken, vraag dan of één van de Github *administrators* een **nieuw repository** voor je opzet. 

**Publicatie- en schemageneratiesoftware: Imvertor**

Geonovum ontwikkelt standaarden *Model Driven*. Deze manier van softwareontwikkeling integreert het hele proces van bedenken tot uitvoeren en testen. Hiervoor gebruiken we de software Imvertor. Dit is een *add-in* voor Enterprise Architect. Vraag een **Imvertoraccount **aan. Installeer Imvertor aan de hand van de [installatie-instructie](https://imvertor.armatiek.nl/imvertor-executor/dashboard/wiki?key=info-IMVERTORHTSWWI) op de website van Armatiek. Naast de standaardinstallatie biedt Imvertor veel configuratie-opties. Vanuit gebruikservaring bij Geonovum is er een document met enkele [handige tips voor Imvertorgebruik beschikbaar](https://geonovum.atlassian.net/l/cp/2iwpfavy).

## Informatiemodelleren

**Begrippenkader maken**

Er zijn op dit moment twee manieren om een *model van begrippen* te maken. Beiden leveren hetzelfde resultaat op in de vorm van een Turtle-bestand op (extensie: &lt;modelnaam&gt;.ttl). Je kunt ervoor kiezen om te werken met het programma **Vocbench** ([handleiding](https://stichtinggeonovum.sharepoint.com/:p:/r/sites/msteams_bf388d/_layouts/15/Doc.aspx?sourcedoc=%7bA6142988-50A2-4803-B8EB-658AA51FF4EE%7d&amp;file=20210125%20Werken%20met%20VocBench.pptx&amp;action=edit&amp;mobileredirect=true)). Of je kunt rechtstreeks aan de slag in een **teksteditor**. Hier vind je een [voorbeeld van een gepubliceerd begrippenkader](https://definities.geostandaarden.nl/hitte/nl/) en het onderliggende [Turtle-bestand op GitHub](https://github.com/Geonovum/imka-begrippen/blob/main/ttl/imka-begrippen.ttl). Een **werkversie** van een begrippenkader kun je publiceren op: [https://begrippen.geostandaarden.nl](https://begrippen.geostandaarden.nl/). De **formele publicatie** vindt plaats op: [https://definities.geostandaarden.nl](https://definities.geostandaarden.nl/).

**Informatiemodel maken**

Voor hulp bij het maken van een informatiemodel is de [Handreiking Informatiemodelleren](https://docs.geostandaarden.nl/mim/him10/) (HIM) beschikbaar. Hierin vind je onder andere informatie over [algemene aspecten](https://docs.geostandaarden.nl/mim/him10/#H02) van informatiemodelleren, een [stappenplan](https://docs.geostandaarden.nl/mim/him10/#H03) om te komen tot een informatiemodel én uitleg over de [toepassing van het MIM](https://docs.geostandaarden.nl/mim/him10/#H04) voor het opstellen van een informatiemodel. Het [MIM](https://docs.geostandaarden.nl/mim/mim/), beschrijft de *metaklassen*, *metastructuur* en *metagegevens* van een informatiemodel. Door standaardisatie van de methode van informatiemodelleren, faciliteert het metamodel een stelsel van samenhangende informatiemodellen, zowel binnen als buiten het geodomein.

**EAP-bestanden van bestaande modellen**

Ben je op zoek naar voorbeelden van door Geonovum ontwikkelde modellen? Kijk dan ook eens naar de EAP-bestanden in de Teams folder [A Informatiemodellen](https://stichtinggeonovum.sharepoint.com/:f:/r/sites/msteams_bf388d/Gedeelde%20documenten/General/A%20Informatiemodellen?csf=1&amp;web=1&amp;e=Qc6obQ) in het team 'Geonovum'. Mogelijk is dit niet compleet en actueel. Ook verouderde modellen zijn hierin opgenomen. Ook modellen die niet door ons ontwikkelde zijn, maar wel relevant zijn, kun je hier vinden zoals bijvoorbeeld (een oude versie van) IMWOZ.

**WaU**

Het programma Werk aan Uitvoering (WAU) levert o.a. een aantal [deliverables](https://github.com/geonovum/WaU/#deliverables) op, zoals een *cross-domein model*, *generieke modelleerpatronen* en *vertaalspecificaties*. Dit is nog in ontwikkeling, maar biedt belangrijke uitgangspunten en aanknopingspunten voor het modelleren van domeinoverstijgende vraagstukken.


## Informatiemodel publiceren​​​​​​​

**Hoe en waar je een informatiemodel publiceert, hangt af van de *****status***** en het *****type***** model. Van een model van begrippen komt de werkversie op begrippen.geostandaarden.nl; de vastgestelde versie op definities.geostandaarden.nl (zie: **[Begrippenkader maken](https://github.com/Geonovum/geonovum-werkwijze/blob/main/linkOpnemen)**. De werkversie van een conceptueel model komt als ReSpec-document op GitHub; de vastgestelde versie als ReSpec-document op **[docs.geostandaarden.nl](https://github.com/Geonovum/geonovum-werkwijze/blob/main/linkOpnemen)**. Technische documentie van vastgestelde conceptuele, logische of technische modellen, brengen we onder op **[register.geostandaarden.nl](https://github.com/Geonovum/geonovum-werkwijze/blob/main/linkOpnemen)**. Denk bij technische documenten bijvoorbeeld aan een beschrijving van het informatiemodel in UML (\*.EAP of \*.XMI), maar ook aan een GML-applicatieschema, XML-schema, regels of een waardelijst (zie: **[kolom ingang: soort bestand](https://register.geostandaarden.nl/)**).**

**ReSpec**

ReSpec geneert automatisch vanuit één of meerdere [Markdown](https://www.markdownguide.org/cheat-sheet/)-bestanden een gestandaardiseerd HTML-document. Er is een standaardconfiguratie op Geonovum-standaarden van toepassing, dus in principe is kennis van Markdown voldoende. Wil je meer weten over hoe je ReSpec kunt gebruiken, kijk dan op deze [Engelstalige wiki](https://github.com/w3c/respec/wiki), of in de [officiële documentatie](https://respec.org/docs/). Het is ook mogelijk om vanuit een Word-document ReSpec te genereren. Meer daarover lees je in het document [Word2ReSpec](https://geonovum.github.io/word2werkversie_handleiding/). Het hoofdstuk gegevensdefinitie publiceer je vanuit Enterprise Architect automatisch met behulp van [Imvertor](https://github.com/Geonovum/handleiding-tooling/blob/main/docs/Imvertor.md). Een voorbeeld van een procesbeschrijving lees je terug in het document [publiceren van IMGeluid EAP-bestand](https://geonovum.atlassian.net/l/cp/Fi0U9bCk).

**Docs.geostandaarden**

Het ReSpec-document van een vastgestelde versie van een standaard publiceren we op docs.geostandaarden. Het document [publiceren van het IMGeluid EAP-bestand](https://geonovum.atlassian.net/l/cp/Fi0U9bCk) bevat een [beschrijving](https://geonovum.atlassian.net/wiki/spaces/IMGeluid/pages/2243657743/Het+wijzigen+en+publiceren+van+een+nieuwe+versie+van+IMGeluid#Het-publiceren-van-de-IMGeluid-standaard) hoe je dit doet.

**Register.geostandaarden**

Het technisch register biedt praktische informatie aan met name ontwikkelaars die op basis van deze informatiemodellen software bouwen. Het is daarmee de authentieke bron waar je alle relevante versies van technische bestanden, inclusief validatieregels, direct online kunt vinden. Het register is de centrale plek waar je alle technische bestanden van informatiemodellen uit de NEN3610-familie vindt. Op de [Github-pagina technisch register 2019](https://github.com/Geonovum/technisch-register-2019) vind je meer informatie. Hoe je de technische bestanden van een informatiemodel in het technisch register publiceert, lees je in de [handleiding voor beheerders informatiemodellen](https://github.com/Geonovum/technisch-register-2019/blob/master/documentatie/HandleidingVoorBeheerdersInformatiemodellen.md). Wil je een systeem opzetten voor het volgen van versies van een nieuw informatiemodel, raadpleeg dan de [handleiding voor beheerders technisch register](https://github.com/Geonovum/technisch-register-2019/blob/master/documentatie/HandleidingVoorBeheerdersTechnischRegister.md) en kijk voor meer informatie bij [versiebeheer](https://github.com/Geonovum/geonovum-werkwijze/blob/main/howto.md#versiebeheer).


## Standaardenbeheer

**Beheer basis-geostandaarden**

Het document [beheer basis-geostandaarden](https://geonovum.github.io/Geo-standaarden-beheerplan/) beschrijft verschillende beheeraspecten, zoals implementatieondersteuning, wijzigingsproces en governance. zodat iedere organisatie die de basis geo-standaarden gebruikt haar weg daarin weet te vinden. Met behulp van het [beheer- en ontwikkelmodel voor open standaarden](https://www.logius.nl/domeinen/infrastructuur/bomos) (BOMOS) geeft Geonovum het beheer en de verdere ontwikkeling van de basis geo-standaarden structureel vorm. Wil je meer weten over de **Geonovum werkwijze op basis van BOMOS** dan kun je [in deze map](https://stichtinggeonovum.sharepoint.com/:f:/r/sites/msteams_bf388d/Gedeelde%20documenten/General/A%20Beheer%20Geostandaarden/BOMOS?csf=1&amp;web=1&amp;e=AOLWOO) meer informatie vinden. Of bekijk de presentatie [Geonovum en BOMOS](https://stichtinggeonovum.sharepoint.com/:p:/r/sites/msteams_bf388d/Gedeelde%20documenten/General/A%20Beheer%20Geostandaarden/BOMOS/2022%20Geonovum%20en%20BOMOS.pptx?d=w9baa0e5136b54635bab2a84c620893d0&amp;csf=1&amp;web=1&amp;e=uShrig). 

**Versiebeheer**

Bij een geostandaard in beheer horen ook afspraken over het [versiebeheer](https://geonovum.github.io/Geo-standaarden-beheerplan/#versiebeheer). Versies van een standaard zijn er in verschillende gradaties: X, Y of Z. Elk type wijziging heeft een relatie met een voorgaande versie. Wijzigingen worden vastgelegd in een apart document bij de uitgebrachte versie van de standaard. De gebruiker kan zo nagaan op welke plaatsen de een standaard gewijzigd is. Het verdient de voorkeur deze aanpak ook in de ontwikkelomgeving van informatiemodellen toe te passen. Het document [strategie semantic versioning DiSGeo](https://github.com/Geonovum/disgeo-im/blob/main/docs/algemeen/versionering_strategie.md) toont een praktische toepassing van versiebeheer in Subversion.

**Wijzigingen**

Over de manier waarop de wijzigingen van een basis-geostandaard plaatsvinden lees je in het [wijzigingsprotocol geo-standaarden](https://geonovum.github.io/Geo-standaarden-wijzigingsprotocol/). Hierin staan de sturende principes achter het generieke wijzigingsproces van de basisset van geostandaarden.Het wijzigingsprotocol is alleen van toepassing op de basisset van geostandaarden, voor zover die bij Geonovum in beheer zijn. Een concrete toepassing hiervan vind je in het [wijzigingsprotocol IMGeluid](https://geonovum.github.io/IMG-wijzigingsprotocol/).

**Handboek intern beheer**

Geonovum werkt aan vele projecten en aan flink aantal beheeropdrachten. Beheer is een proces en geen project en daarom des te meer van belang onze ervaring en kennis te delen, te borgen en de nieuwe collega’s te coachen in het standaardenwerk bij Geonovum. Daarbij hoort ook het vastleggen van de afspraken: *zo doen we dat bij Geonovum!* Het [handboek beheer](https://stichtinggeonovum.sharepoint.com/:b:/r/sites/msteams_bf388d/Gedeelde%20documenten/General/A%20Beheer%20Geostandaarden/Handboek%20Beheerder/Handboek%20beheer%20standaarden%20bij%20Geonovum.pdf?csf=1&amp;web=1&amp;e=ltQh3L) is de invulling van de beheeropdracht, het [handboek opdrachtnemer](https://stichtinggeonovum.sharepoint.com/sites/msteams_bf388d/Gedeelde%20documenten/Forms/AllItems.aspx?id=/sites/msteams_bf388d/Gedeelde%20documenten/General/Handboek%20Opdrachtnemer/componenten/pdf/Handboekopdrachtnemer.pdf&amp;viewid=3a693696-6e40-41fb-a369-1de62b54d550&amp;parent=/sites/msteams_bf388d/Gedeelde%20documenten/General/Handboek%20Opdrachtnemer/componenten/pdf) gaat over onder andere het organiseren van de beheeropdracht in samenwerking met de opdrachtgever.

