
## Gebouwen- en Adressenregister

Dit register verzamelt alle basisinformatie over gebouwen en adressen op het Vlaamse grondgebied in één register. Dit register is hét basisregister voor gebouw- en adresinformatie in Vlaanderen en vormt de centrale koppelstandaard in het netwerk van gebouw- en adresgerelateerde gegevensbronnen. 

Het bestaat uit verschillende registers:
* Gemeenteregister
* Postinforegister
* Straatnamenregister
* Adressenregister
* Gebouwen- en gebouweenhedenregister
* Percelenregister

Voor straatnamen, adressen, gebouwen & gebouweneheden is het gebouwen- en adressenregister de authentieke bron. 

Deze informatie kan op verschillende manieren geraadpleegd worden:
- Via de read endpoints
- Via de feed endpoints
- Downloadbestand
- WMS & WFS

### Downloadbestand

Het downloadbestand gebouwen- en adressenregister kan dagelijks gedownload worden via deze link: https://api.basisregisters.vlaanderen.be/v2/extract. Wanneer de generatie die dag niet gelukt is dan zal er een downloadbestand gedownload worden van de laatste datum waarop de generatie gelukt is.

Dit is een zip file met daarin een aantal bestanden van verschillende formaten. De formaten die hierin kunnen teruggevonden worden zijn: .dbf, .shp, .prj & . shx.

| Bestandnaam |  Formaat .dbf | Formaat .prj | Formaat .shp | Formaat .shx |
|:----------:|:-----:|:-----:|:-----:|:-----:|
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
* [Handleiding opsplitsen donwloadbestand gebouwen- en adressenregister](https://github.com/Informatievlaanderen/base-registries-content/files/11381530/CookBook_opsplitsen_downloadbestand_gebouwen-_en_adressenregister.docx)

### WMS & WFS

#### WMS
* WMS gebouwenregister
  * [Datavindplaats][1]
* WMS adressenregister
  * [Datavindplaats][2]

#### WFS
* WFS gebouwenregister
  * [Datavindplaats][3]
* WFS adressenregister
  * [Datavindplaats][4]

[1]:https://www.vlaanderen.be/datavindplaats/catalogus/wms-gebouwenregister
[2]:https://www.vlaanderen.be/datavindplaats/catalogus/wms-adressenregister
[3]:https://www.vlaanderen.be/datavindplaats/catalogus/wfs-gebouwenregister
[4]:https://www.vlaanderen.be/datavindplaats/catalogus/wfs-adressenregister
