____
## Waarom dit handboek? {#waarom-dit-handboek}


Dit handboek dient om alle verschillende integratiemethodes te beschrijven.

## Overzicht {#overzicht}

1. [API](#api)
2. [Syndication](#syndication)
3. [LDES](#ldes)
4. [Kafka](#kafka)
5. [Database tables](#database-tabellen)


## 1. API {#api}
Onze API's zijn [volledig gedocumenteerd](//docs.basisregisters.vlaanderen.be/docs/api-documentation.html) en zijn beschikbaar voor integraties.

## 2. Syndication {#syndication}
Via een **syndication** endpoint kunnen per register de gegevens worden opgevraagd. Dit werkt vlot voor kleinere registers, maar kan minder vlot werken voor grotere registers zoals addressen-register en gebouwen-register. Het **syndication endpoint** is gedocumenteerd op `https://docs.basisregisters.vlaanderen.be/docs/api-documentation.html#tag/Feeds`

## 3. LDES {#ldes}
**Linked Data Event Streams (LDES)** is een manier om gerelateerde gegevens met elkaar te verbinden. Meer informatie vind je op https://semiceu.github.io/LinkedDataEventStreams/

## 4. Kafka {#kafka}
De gegevens van de **basisregisters** worden **gepubliceerd op Kafka topics**. In uitzonderlijke gevallen kan je rechtstreeks integreren met onze Kafka topics. Stuur hiervoor een bericht naar **digitaal.vlaanderen@vlaanderen.be**

## 5. Database tables {#database-tabellen}
In **uitzonderlijke gevallen** kunnen we onze gegevens publiceren naar een aantal database tables. Stuur hiervoor een bericht naar **digitaal.vlaanderen@vlaanderen.be**
