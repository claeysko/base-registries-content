Het  Wegenregister verzamelt alle basisinformatie over wegen op het Vlaamse grondgebied in één register. Het is hét basisregister voor wegeninformatie in Vlaanderen en vormt de centrale koppelstandaard in het netwerk van wegengerelateerde gegevensbronnen. Hieronder geven we aan op welke manieren je het Wegenregister kan raadplegen, en hoe het Wegenregister bijgewerkt wordt.


# Het Wegenregister raadplegen {#raadplegen}

Het Wegenregister kan op verschillende manieren geraadpleegd worden:
* [Via de WMS, WFS & OGC API features](#wmswfsogcwr)
* [Als download in shapefile formaat](#download)
* [Als kaartlaag op Geopunt](#geopunt)

## WMS, WFS & OGC API features {#wmswfsogcwr}

Het Wegenregister wordt als WMS, WFS & OGC API features ontsloten:
* De WMS maakt het mogelijk om wegen van het wegenregister te visualiseren op een kaart. Meer informatie over wat een WMS is, kan [hier][4] gevonden worden. 
* De WFS maakt het mogelijk om ruimtelijke bevragingen te doen op wegsegmenten en wegknopen van het Wegenregister. Meer informatie over wat een WFS is, kan [hier][5] gevonden worden.
* De standaard [OGC API Features][6], ontwikkeld door het Open Geospatial Consortium (OGC), specificeert de vereisten en aanbevelingen voor API’s met betrekking tot ruimtelijke gegevens. Het laat toe de wegen ruimtelijk te bevragen. 

Alle URL's van de WMS'en, WFS'en en OGC API features van het wegenregister kunnen gevonden worden in de catalogus van de [Datavindplaats][9]: 
* [WMS wegenregister][1]
* [WFS wegenregister][2]
* [OGC API features wegenregister][3]

## Download in shapefile formaat {#download}
Het Wegenregister wordt driemaandelijks aangeboden als download. De download bestaat uit een zip-archief met shapefile bestanden voor wegsegmenten en wegknopen, en met database (dbf) bestanden voor de andere data-objecten in het Wegenregister. De meest recente download vind je door te zoeken naar "Wegenregister" in de catalogus van de [Datavindplaats][9].

## Kaartlaag op Geopunt {#geopunt}

Om het Wegenregister te raadplegen op [Geopunt][8] voeg je de kaartlaag "Wegennet" toe. Klik hiervoor op de knop "Lagen" en vervolgens op "Lagen toevoegen". Je vindt het wegennet onder Mobiliteit > Transport over land > Wegen. 


# Bijhouding van het Wegenregister {#bijhouding}

## Wie actualiseert het Wegenregister?

Het Wegenregister wordt meegenomen in de bijwerking van het **GRB**. Dienstverleners van het GRB werken het Wegenregister bij op basis van o.a. meldingen en as-builtplannen. Ze volgen hierbij contractueel afgesproken actualiteitsvereisten. Voor nieuwe wegen geldt bijvoorbeeld dat deze opgenomen moeten zijn binnen de 3 maanden nadat Digitaal Vlaanderen op de hoogte werd gebracht van de realisatie van de weg.

Verder wordt het Wegenregister op regelmatige basis bijgewerkt door het **AWV**, en loopt er momenteel een piloottraject met een aantal **steden en gemeenten** om aanpassingen door te voeren. Tenslotte worden de trage wegen in het Wegenregister jaarlijks bijgewerkt o.b.v. updates in het **Tragewegenregister**. 

## Hoe wordt het Wegenregister geactualiseerd?

Bijwerkingen gebeuren doorgaans in een **GIS-omgeving** zoals ArcGIS of QGIS. Bijwerkers downloaden een stukje van het Wegenregister, voeren lokaal hun aanpassingen door en laden deze vervolgens op. Dit is een arbeidsintensief proces dat goede coördinatie en de nodige GIS-expertise vereist. 

Verder zijn er ook **API's** beschikbaar die aangesproken kunnen worden
* om nieuwe wegen in te schetsen,
* om geometrieën van schetsen te corrigeren / verwijderen, en
* om attribuutinformatie van wegen aan te passen. 

Deze API's zullen o.a. geïmplementeerd worden in het vernieuwde **LARA**, zodat lokale besturen deze bijwerkingen op een gebruiksvriendelijke manier kunnen doorvoeren in het Wegenregister.

## Hoe kan ik als lokaal bestuur het Wegenregister bijwerken?

* Vanaf december 2023 zullen een aantal beheersacties mogelijk worden in het vernieuwde LARA, zoals het inschetsen van een nieuwe weg en het aanpassen van attribuutinformatie van wegsegmenten uit het Wegenregister. Bijwerkers kunnen ook rechtstreeks de API's van het Wegenregister aanspreken om deze beheersacties te implementeren in hun eigen toepassingen. 
* Met een beperkt aantal steden en gemeenten wordt er in een piloottraject onderzocht of het haalbaar is voor deze partijen om het Wegenregister bij te werken in een GIS-omgeving. Indien u interesse heeft hierin, dan graag een seintje via digitaal.vlaanderen@vlaanderen.be.
* Verder kan u ook steeds fouten of onvolledigheden melden op één van de twee manieren die hieronder beschreven staan.

## Hoe kan ik een fout of onvolledigheid in het Wegenregister melden? 

* Professionele gebruikers kunnen fouten of onvolledigheden melden via een GRB terugmelding met thema "Weg, as". Meer info over GRB terugmeldingen vindt u [hier][7]. 
* Burgers kunnen fouten of onvolledigheden melden via [Geopunt][8]. Voeg de laag "Wegennet" toe onder Mobiliteit > Transport over land > Wegen en klik rechtsboven op "Hulp nodig?" en vervolgens "Meld een probleem met de kaart". Selecteer de datalaag "Wegennet" in uw melding om te garanderen dat uw melding bij de juiste behandelaar terechtkomt.


[1]:https://www.vlaanderen.be/datavindplaats/catalogus/wegenregister-0
[2]:https://www.vlaanderen.be/datavindplaats/catalogus/wfs-wegenregister
[3]:https://www.vlaanderen.be/datavindplaats/catalogus/ogc-api-features-wegenregister
[4]:https://vlaanderen.be/digitaal-vlaanderen/onze-oplossingen/geografische-webdiensten/ons-gis-aanbod/raadpleegdiensten
[5]:https://www.vlaanderen.be/digitaal-vlaanderen/onze-oplossingen/geografische-webdiensten/ons-gis-aanbod/overdrachtdiensten
[6]:https://ogcapi.ogc.org/features/
[7]:https://overheid.vlaanderen.be/help/grb/terugmelding
[8]:https://www.geopunt.be
[9]:https://www.vlaanderen.be/datavindplaats

