
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
* Via de WMS & WFS

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


### WMS & WFS

Het gebouwen- en adressenregister wordt ook als WMS & WFS ontsloten:
* De WMS maakt het mogelijk om adressen, gebouwen & gebouweenheden van het gebouwen- en adressenregister te visualiseren op een kaart. Per status is er een laag voorzien. Meer informatie over wat een WMS is, kan [hier][5] gevonden worden. 
* De WFS maakt het mogelijk om geografische bevragingen te doen op adressen, gebouwen en gebouweenheden van het gebouwen- en adressenregister. Meer informatie over wat een WFS is, kan [hier][6] gevonden worden.

Alle URL's van de WMS'en en WFS'en van het gebouwen- en adressenregister kunnen gevonden worden in de catalogus van datavindplaats. 

#### WMS
* [WMS gebouwenregister][1]
* [WMS adressenregister][2]

#### WFS
* [WFS gebouwenregister][3]
* [WFS adressenregister][4]

[1]:https://www.vlaanderen.be/datavindplaats/catalogus/wms-gebouwenregister
[2]:https://www.vlaanderen.be/datavindplaats/catalogus/wms-adressenregister
[3]:https://www.vlaanderen.be/datavindplaats/catalogus/wfs-gebouwenregister
[4]:https://www.vlaanderen.be/datavindplaats/catalogus/wfs-adressenregister
[5]:https://vlaanderen.be/digitaal-vlaanderen/onze-oplossingen/geografische-webdiensten/ons-gis-aanbod/raadpleegdiensten
[6]:https://www.vlaanderen.be/digitaal-vlaanderen/onze-oplossingen/geografische-webdiensten/ons-gis-aanbod/overdrachtdiensten
