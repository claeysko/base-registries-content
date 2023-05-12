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

### Read endpoints

De read endpoints van het gebouwen- en adressenregister kan 
lijsten opvragen of details van data

Welkom bij de REST API van Basisregisters Vlaanderen!

REST is een webserviceprotocol dat zich leent tot snelle ontwikkeling door het gebruik van HTTP- en JSON-technologie.
URL rest: https://en.wikipedia.org/wiki/Representational_state_transfer

URL documentatiepagina (omgevingsvariabel maken?):  
"url": {
          "dev": "https://docs.basisregisters.dev-vlaanderen.be/docs/api-documentation.html#tag/api-documentation.html",
          "stg": "https://docs.basisregisters.staging-vlaanderen.be/docs/api-documentation.html#tag/api-documentation.html",
          "prd": "https://docs.basisregisters.vlaanderen.be/docs/api-documentation.html#tag/api-documentation.html"
          
#### Toegang
De read endpoints zijn anoniem raadpleegbaar echter is er een beperking aanwezig op het aantal verzoeken dat u tegelijkertijd kan versturen naar deze endpoints. Wanneer u een API key meegeeft dan zal u meer requests kunnen versturen.

Om dus optimaal gebruik te maken van de endpoints vraagt u best een API key aan. Dit kan door uw gegevens in volgende link achter te laten: [Vraag hier uw API key aan][10]. U kan deze API key op 2 manieren meegeven:
* Via de header x-api-key.
* In de URL. Bijvoorbeeld: https://api.basisregisters.dev-vlaanderen.be/v2/adressen?apikey={apikey} waarbij {apikey} vervangen wordt door de unieke code van uw API key.

#### V1 vs v2
Voor de read endpoints zijn er zowel v1 als v2 endpoints beschikbaar. De v2 read endpoints zijn een vernieuwde versie van de v1 read endpoints en zijn conform aan het OSLO-model. Om duidelijk aan te geven of het een v1 of een v2 endpoint is, hebben we achteraan de titels gewerkt met (v1) voor versie 1 en (v2) voor versie 2.

##### Wat is het verschil tussen de v1 en de v2 endpoints?
*  Het content-type van v2 is ‘application/ld+json’. Van v1 is dit default ‘application+json’, maar ‘application/xml’ is ook mogelijk.
* Er zijn 2 velden bijgekomen, namelijk @context en @type.
  * Het @context veld bevat de linked-data context van het endpoint. Dit is een URI naar de JSON-LD file.
  * Het @type veld bevat het linked-data type van het endpoint.
* De geometrievelden bij ‘Vraag een adres op (v2)’, ‘Vraag een gebouw op (v2)’ en ‘Vraag een gebouweenheid op (v2)’ zijn gewijzigd. De coördinaten van het object staan vanaf nu in het gml-formaat en alle velden die met geometrie te maken hebben zijn samengevoegd onder 1 veld.

##### Wat betekent 'conform aan het OSLO-model'?
Door informatie conform aan het OSLO-model te ontsluiten, kan deze vlot gecombineerd worden met datasets op het wereldwijde web. Contextuele informatie wordt aan de response van de endpoints gekoppeld waardoor ze geschikt zijn om te gebruiken in Linked Data toepassingen.
Meer informatie over OSLO kan u hier vinden: https://overheid.vlaanderen.be/producten-diensten/oslo.

##### Hoe v2 endpoints visueel in browser tonen?
In de browser moet een accept header meegegeven worden bij de request. In Chrome is dit door middel van een extensie. Een voorbeeld hiervan is ‘NoRefer’. In het witte scherm dat verschijnt na het klikken op het extensie icoon moet het volgende meegegeven worden: 'accept: application/ld+json'. Daarna wordt de pagina best opnieuw geladen.

### Feed endpoints

x

### Downloadbestand

Het downloadbestand is een momentopname van alle data die het gebouwen- en adressenregister bevat op die moment. Dit bestand kan dagelijks gedownload worden via deze link: https://api.basisregisters.vlaanderen.be/v2/extract. Wanneer de generatie die dag niet gelukt is dan zal er een downloadbestand gedownload worden van de laatste datum waarop de generatie gelukt is. Het downloadbestand is een zip file met daarin een aantal bestanden van verschillende formaten. De formaten die hierin kunnen teruggevonden worden zijn: .dbf, .shp, .prj & .shx. 

#### Inhoud downloadbestand

| Bestandnaam |  Formaat .dbf | Formaat .prj | Formaat .shp | Formaat .shx |
|:-:|:-:|:-:|:-:|:-:|
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
[10]:https://dynamicforms.crmiv.vlaanderen.be/DynamicForms/Page/Show/CfDJ8M4Eu9v84l9JmW3p7WGylS-u2ToCLC5KvqQZmZ4G99X5TBULO4n0LCDpm7870eDUOk90hogqVcE7BCVQf2u_4WlsZ7B8friBrkyuAqmXYpIX_BzvQVVo8eUZyNd-njc33Y-Z-B87y03Y2Jgukp2AN5U93jT1Xv2l0afgvenLD9k0fasSMJkt4uNzKmlr_gILGrOy%2FJSqnRom_MLu0h7sALJ8uNvPywCMsZ1zy5Lal4h63?path=APIKey-aanvraag
