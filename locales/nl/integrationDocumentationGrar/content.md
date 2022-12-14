____
## Waarom dit handboek? {#waarom-dit-handboek}

Er komen regelmatig vragen over hoe men kan integreren met Basisregisters. Met Basisregisters bedoelen we hier:

 - Postinfo-register
 - Gemeente-register
 - Straatnamen-register
 - Adressen-register
 - Gebouwen-register
 - Percelen-register
 - Wegen-register

Dit handboek dient om alle verschillende integratiemethodes te beschrijven.

## Overzicht {#overzicht}

1. [API](#api)
2. [Syndication](#syndication)
3. [WMS/WFS](#wms-wfs)
4. [Testbestand](#testbestand)
5. [LDES](#ldes)
6. [Kafka](#kafka)
7. [Database tables](#database-tabellen)


## 1. API {#api}
Onze API's zijn [volledig gedocumenteerd](//docs.basisregisters.vlaanderen.be/docs/api-documentation.html) en zijn beschikbaar voor integraties.

## 2. Syndication {#syndication}
Via een **syndication** endpoint kunnen per register de gegevens worden opgevraagd. Dit werkt vlot voor kleinere registers, maar kan minder vlot werken voor grotere registers zoals addressen-register en gebouwen-register. Het **syndication endpoint** is gedocumenteerd op `https://docs.basisregisters.vlaanderen.be/docs/api-documentation.html#tag/Feeds`

## 3. WMS/WFS {#wms-wfs}
TBC

## 4. Testbestand {#testbestand}
Dagelijks wordt een bestand geproduceerd met de gegevens van alle Basisregisters. Dit noemen we het [Testbestand](//api.basisregisters.vlaanderen.be/v1/extract). Dit bestand is beschikbaar op `https://api.basisregisters.vlaanderen.be/v1/extract`
Het testbestand bestaat uit volgende files:
 
| Filename<br> | DBF<br>*(.dbf)* | PRJ<br>*(.prj)* | SHP<br>*(.shp)* | SHX<br>*(.shx)* |
|----------|-----|-----|-----|-----|
| `Adres` | ✅ | ✅ | ✅ | ✅ |
| `Adres_metadata` | ✅ | - | - | - |
| `Adreskoppelingen` | ✅ | - | - | - |
| `Adreskoppelingen_1` | ✅ | - | - | - |
| `CrabHuisnummer` | ✅ | - | - | - |
| `CrabSubadres` | ✅ | - | - | - |
| `Gebouw` | ✅ | ✅ | ✅ | ✅ |
| `Gebouw_metadata` | ✅ | - | - | - |
| `Gebouweenheid` | ✅ | ✅ | ✅ | ✅ |
| `Gebouweeneheid_metadata` | ✅ | - | - | - |
| `Gemeente` | ✅ | - | - | - |
| `Gemeente_metadata` | ✅ | - | - | - |
| `Perceel` | ✅ | - | - | - |
| `Perceel_metadata` | ✅ | - | - | - |
| `Postinfo` | ✅ | - | - | - |
| `Postinfo_metadata` | ✅ | - | - | - |
| `Straatnaam` | ✅ | - | - | - |
| `Straatnaam_metadata` | ✅ | - | - | - |

*Meer info*
- [*Dbf files*](//en.wikipedia.org/wiki/.dbf) <br>
- [*Shape files*](//en.wikipedia.org/wiki/Shapefile)

## 5. LDES {#ldes}
**Linked Data Event Streams (LDES)** is een manier om gerelateerde gegevens met elkaar te verbinden. Meer informatie vind je op https://semiceu.github.io/LinkedDataEventStreams/

## 6. Kafka {#kafka}
De gegevens van de **basisregisters** worden **gepubliceerd op Kafka topics**. In uitzonderlijke gevallen kan je rechtstreeks integreren met onze Kafka topics. Stuur hiervoor een bericht naar **digitaal.vlaanderen@vlaanderen.be**

## 7. Database tables {#database-tabellen}
In **uitzonderlijke gevallen** kunnen we onze gegevens publiceren naar een aantal database tables. Stuur hiervoor een bericht naar **digitaal.vlaanderen@vlaanderen.be**
