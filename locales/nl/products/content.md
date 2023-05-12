
## Gebouwen- en Adressenregister

Dit register verzamelt alle basisinformatie over gebouwen en adressen op het Vlaamse grondgebied in één register. Het is hét basisregister voor gebouw- en adresinformatie in Vlaanderen en vormt de centrale koppelstandaard in het netwerk van gebouw- en adresgerelateerde gegevensbronnen. 

Het bestaat uit verschillende registers:
* Gemeenteregister
* Postinforegister
* Straatnamenregister
* Adressenregister
* Gebouwen- en gebouweenhedenregister
* Percelenregister

Voor straatnamen, adressen, gebouwen & gebouweneheden is het gebouwen- en adressenregister de authentieke bron. 

Deze informatie kan op verschillende manieren geraadpleegd worden:
* Via de read endpoints
* Via de feed endpoints
* Via het downloadbestand
* Via de WMS, WFS & OGC API features

### Downloadbestand

Het downloadbestand is een momentopname van alle data die het gebouwen- en adressenregister bevat op die moment. Dit bestand kan dagelijks gedownload worden via deze link: https://api.basisregisters.vlaanderen.be/v2/extract. Wanneer de generatie die dag niet gelukt is dan zal er een downloadbestand gedownload worden van de laatste datum waarop de generatie gelukt is. Het downloadbestand is een zip file met daarin een aantal bestanden van verschillende formaten. De formaten die hierin kunnen teruggevonden worden zijn: .dbf, .shp, .prj & .shx. 

#### Inhoud downloadbestand

| Bestandnaam |  Formaat .dbf | Formaat .prj | Formaat .shp | Formaat .shx |
|:---:|:---:|:---:|:---:|:---:|
| Adres | x | x | x | x |
| Adres_metadata | x | \ | \ | \ |
| AdresGebouweenheidKoppelingen | x | \ | \ | \ |
| AdresPerceelKoppelingen | x | \ | \ | \ |
| CrabHuisnummer | x | \ | \ | \ |
| CrabSubadres | x | \ | \ | \ |
| Gebouw | x | x | x | x |
| Gebouw_metadata | x | \ | \ | \ |
| Gebouweenheid | x | x | x | x |
| Gebouweeneheid_metadata | x | \ | \ | \ |
| Gemeente | x | \ | \ | \ |
| Gemeente_metadata | x | \ | \ | \ |
| Perceel | x | \ | \ | \ |
| Perceel_metadata | x | \ | \ | \ |
| Postinfo | x | \ | \ | \ |
| Postinfo_metadata | x | \ | \ | \ |
| Straatnaam | x | \ | \ | \ |
| Straatnaam_metadata | x | \ | \ | \ |

#### Handleiding
Om meer te weten te komen over hoe het downloadbestand te gebruiken, kan deze handleiding gedownload worden: [Handleiding opsplitsen donwloadbestand gebouwen- en adressenregister](https://github.com/Informatievlaanderen/base-registries-content/files/11381530/CookBook_opsplitsen_downloadbestand_gebouwen-_en_adressenregister.docx).

#### Feed endpoints
Om aan de slag te gaan met de feed endpoints van het gebouwen- en adressenregister kan er ook vertrokken worden vanaf het downloadbestand. Zo moeten de feed endpoints niet volledig van het eerste eventid tot het laatste eventid uitgelezen worden. In het downloadbestand zijn er namelijk bestanden met in hun naamgeving ‘_metadata.dbf’. In deze bestanden staat het ‘Latest_event_id’. Dit id wordt in de overeenkomstige feed endpoint meegegeven bij de parameter ‘from’ & dat is het startpunt vanaf waar de feed endpoints kan worden ingelezen op basis van het downloadbestand.  
* vb. In het bestand Adres_metadata.dbf staat er dat het Latest_event_id = 100 dan wordt er in de feed endpoint adressen het volgende meegegeven: `https://api.basisregisters.vlaanderen.be/v1/feeds/adressen?embed=object,event&from=100`.

#### Bestanden crabHuisnummer & crabSubadres
In het downloadbestand zijn er ook 2 bestanden te vinden die de mapping maken tussen CRAB & het gebouwen- en adressenregister, namelijk crabHuisnummer.dbf & crabSubadres.dbf. De adres objectid's die in het gebouwen- en adressenregister gebruikt worden zijn andere objectId's dan in het CRAB. Omdat er moet worden overgeschakeld van CRAB naar het gebouwen- en adressenregister, werden deze bestanden voorzien zodat er vlot kan overgeschakeld worden. De laatste versie van deze CRAB objectId's zal nog worden bijwerkt tot en met 1 november 2023. Deze bestanden zullen nog bijgehouden worden na 1 november 2022, maar zullen geen updates meer kennen. Vanaf 1 maart 2024 worden deze bestanden uit het downloadbestand gehaald. 

### WMS, WFS & OGC API features

Het gebouwen- en adressenregister wordt ook als WMS & WFS ontsloten:
* De WMS maakt het mogelijk om adressen, gebouwen & gebouweenheden van het gebouwen- en adressenregister te visualiseren op een kaart. Per status is er een laag voorzien. Meer informatie over wat een WMS is, kan [hier][5] gevonden worden. 
* De WFS maakt het mogelijk om geografische bevragingen te doen op adressen, gebouwen en gebouweenheden van het gebouwen- en adressenregister. Meer informatie over wat een WFS is, kan [hier][6] gevonden worden.
* De standaard [OGC API Features][9], ontwikkeld door het Open Geospatial Consortium (OGC), specificeert de vereisten en aanbevelingen voor API’s met betrekking tot ruimtelijke gegevens. Het laat toe de adressen, gebouwen en gebouweenheden geometrisch te bevragen. 

Alle URL's van de WMS'en, WFS'en en OGC API features van het gebouwen- en adressenregister kunnen gevonden worden in de catalogus van datavindplaats. 

#### WMS
* [WMS gebouwenregister][1]
* [WMS adressenregister][2]

#### WFS
* [WFS gebouwenregister][3]
* [WFS adressenregister][4]

#### OGC API features
* [OGC API features gebouwenregister][7]
* [OGC API features adressenregister][8]

[1]:https://www.vlaanderen.be/datavindplaats/catalogus/wms-gebouwenregister
[2]:https://www.vlaanderen.be/datavindplaats/catalogus/wms-adressenregister
[3]:https://www.vlaanderen.be/datavindplaats/catalogus/wfs-gebouwenregister
[4]:https://www.vlaanderen.be/datavindplaats/catalogus/wfs-adressenregister
[5]:https://vlaanderen.be/digitaal-vlaanderen/onze-oplossingen/geografische-webdiensten/ons-gis-aanbod/raadpleegdiensten
[6]:https://www.vlaanderen.be/digitaal-vlaanderen/onze-oplossingen/geografische-webdiensten/ons-gis-aanbod/overdrachtdiensten
[7]:https://www.vlaanderen.be/datavindplaats/catalogus/ogc-api-features-gebouwenregister
[8]:https://www.vlaanderen.be/datavindplaats/catalogus/ogc-api-features-adressenregister
[9]:https://ogcapi.ogc.org/features/
