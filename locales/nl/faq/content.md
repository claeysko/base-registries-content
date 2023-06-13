## Hoe kan in de WMS gebruiken?

De WMS laat toe gebouwen en gebouweenheden (per status) **op kaart te visualiseren** en objecten aan te klikken voor meer informatie. Deze kaartlagen kunnen ingeladen worden in GIS- of andere software. Een lijst van GIS-software vindt u [hier](https://en.wikipedia.org/wiki/Comparison_of_geographic_information_systems_software). We kunnen zelf QGIS (open source, gratis) aanbevelen.

Hieronder vindt u een overzicht van de meest voorkomende vragen met hun antwoorden die onze gebruikers hebben over de basisregisters.
Als u een vraag heeft die hieronder niet beantwoord wordt, mail naar digitaal.vlaanderen@vlaanderen.be.

## Hoe kan in de WMS gebruiken?

De WMS laat toe gebouwen en gebouweenheden (per status) **op kaart te visualiseren** en objecten aan te klikken voor meer informatie. Deze kaartlagen kunnen ingeladen worden in GIS- of andere software. Een lijst van GIS-software vindt u [hier](https://en.wikipedia.org/wiki/Comparison_of_geographic_information_systems_software). We kunnen zelf QGIS (open source, gratis) aanbevelen.

Het is belangrijk in de GIS-software als coördinatensysteem voor het project ‘EPSG:31370’ (Belgian Lambert 72) te kiezen en ‘PNG’ als beeldformaat vooraleer lagen toe te voegen. De gebouwen en gebouweenheden worden zichtbaar vanaf schaal 1:8000 of hoger.

Via de ‘identify’-functie kunt u de details van een object op de kaart met een muisklik opvragen.

## Hoe kan ik de REST-API uitproberen? 
Een eenvoudige test van de REST-services kan door een URL samen te stellen in de adresbalk van uw browser.

[Documentatie van hoe de URL’s er moeten uitzien en hoe u uw browser moet configureren.](https://docs.basisregisters.vlaanderen.be/docs/api-documentation.html#tag/api-documentation.html)

Het antwoord van de service zal in uw browser getoond worden.

Voor het visualiseren van objecten op kaart maakt u gebruik van de WMS of het testbestand.

## Hoe kan ik het testbestand gebruiken?

Het testbestand kan ingeladen en gevisualiseerd worden met GIS-software. Een lijst van GIS-software vindt u [hier](https://en.wikipedia.org/wiki/Comparison_of_geographic_information_systems_software). We kunnen zelf QGIS (open source, gratis) aanbevelen.

Het kan handig werken om bepaalde velden uit het testbestand als categorie of label bij de objecten te gebruiken (bv. ‘posspec’ bij Adres of ‘gebouwid’ bij Gebouw):

## Zal het testbestand later als dataproduct bestendigd worden? 
Er zal een dataproduct voorzien worden indien hier voldoende interesse voor bestaat. Laat het ons weten indien een dataproduct voor u essentieel is. Geef ook aan of de vorm van het testbestand OK is dan wel hoe dit verbeterd kan worden.

## Hoe worden gebouweenheden en hun adreskoppeling(en) momenteel aangemaakt? 
In deze projectfase worden **gebouweenheden** aangemaakt daar waar CRAB-huisnummers aan een gebouw (of meerdere gebouwen) in CRAB gekoppeld zijn. Ook voor de CRAB-subadressen ‘onder’ deze huisnummers wordt een gebouweenheid gecreëerd. Waar van toepassing wordt een gebouweenheid met functie ‘gemeenschappelijk deel’ toegevoegd. De gebouweenheden in het Gebouwenregister worden gekoppeld aan het geïnstantieerde Adressenregister-adres (voorbeelden: zie vraag 7).

**Adreskoppelingen met een perceel** worden aangemaakt voor CRAB-huisnummers en -subadressen die (bijkomend) aan een perceel gekoppeld zijn.

Heeft een CRAB-huisnummer of -subadres geen enkele gebouw- of perceelkoppeling, maar wel een adrespositie met herkomst ‘manuele aanduiding van lig- resp. standplaats’, dan zal het adres (in een volgende release) aan een **lig- resp. standplaats** gekoppeld worden.

Tot slot kan een CRAB-huisnummer of -subadres ook **ongekoppeld** voorkomen. Het verwijst daarbij bijvoorbeeld naar een ‘lot’ of kreeg een afgeleide, laagkwalitatieve positie (bv. geïnterpoleerd o.b.v. nevenliggende gebouwen, in het centrum van de straat of gemeente). Ook deze adressen worden in het Adressenregister overgenomen met hun positie en worden idealiter alsnog aan een adresseerbaar object gekoppeld.

## Is de puntgeometrie van een gebouweenheid dezelfde als deze van het adres?

Het attribuut ‘GeometriePunt’ van een gebouweenheid is de positie van de gebouweenheid binnen de gebouwcontour.

Staat de ‘PositieGeometrieMethode’ op ‘AfgeleidVanObject’ dan werd deze positie afgeleid van het gebouw waarbinnen de gebouweenheid ligt en betreft het de centroïde van het gebouw.

Staat de ‘PositieGeometrieMethode’ op ‘AangeduidDoorBeheerder’ dan werd de positie manueel geplaatst door een decentraal beheerder (in concreto: aangezien gebouweenheden momenteel automatisch aangemaakt worden o.b.v. CRAB-adressen betekent dit dat van het corresponderende adres in CRAB de meest kwalitatieve, manuele positie gebruikt werd).

Echter, ligt de positie van het CRAB-adres buiten de gebouwcontour, dan zal de daarop gebaseerde gebouweenheid automatisch op de centroïde van het gebouw geplaatst worden. Gebouweenheden dienen namelijk steeds binnen een gebouw te liggen.

Dit betekent dat de gebouweenheid een andere positie kán hebben dan het adres in CRAB waarop het gebaseerd werd.

## Graag enkele voorbeelden van de aanmaak van gebouweenheden en adressen o.b.h. CRAB?

Hieronder geven we enkele frequent voorkomende situaties in CRAB en de wijze waarop deze doorvertaald werden (tekstueel en grafisch). Merk op dat er andere en complexere uitgangssituaties in CRAB bestaan; het zou ons te ver leiden deze allemaal te beschrijven. De doorvertaling volgt echter telkens hetzelfde patroon.

| **Situatie in CRAB**  | **Vertaald naar Gebouwenregister als … (zie bijhorende figuren)** | 
|:-:|:-:|
| Eengezinswoning (Aan een gebouw werd het huisnummer ‘8’ gekoppeld)  |Gebouw met één gebouweenheid, waarbij de gebouweenheid een adres met huisnummer ‘8’ draagt. | 
| Meergezinswoning (Aan een gebouw werd het huisnummer ‘10’ gekoppeld met daaronder twee subadressen ’bus 1’ en ‘bus 2’) | Gebouw met twee gebouweenheden, die respectievelijk de adressen ’10 bus 1’ en ’10 bus 2’ dragen. Daarnaast werd een derde gebouweenheid gecreëerd, het gemeenschappelijk deel, dat het adres met huisnummer ‘10’ draagt. | 
| Meergezinswoning met minder optimale nummering (Aan een gebouw werd het huisnummer ‘11’ gekoppeld met daaronder één subadres ’bus 1’) | Gebouw met twee gebouweenheden, die respectievelijk de adressen ’11’ en ’11 bus 1’ dragen. Daarnaast werd een derde gebouweenheid gecreëerd, het gemeenschappelijk deel, dat hier geen adres draagt. | 
| Flatgebouw (Aan een gebouw werd het huisnummer ‘12’ gekoppeld met daaronder vijf subadressen) | Gebouw met vijf gebouweenheden, die respectievelijk de adressen ’12 bus 1’ t/m ’12 bus 5’ dragen. Daarnaast werd een zesde gebouweenheid gecreëerd, het gemeenschappelijk deel, dat het adres met huisnummer ‘12’ draagt.| 
| Woonblok met meerdere ingangen (Binnen een woonblok werd ervoor gekozen om de flats achter elke ingang met een apart huisnummer aan te duiden (14/16/18). Er zijn dus drie huisnummers met daaronder telkens vier subadressen. De adresbeheerder gaf deze huisnummers in CRAB een manuele positie met aanduiding ‘ingang’.) | Gebouw met 12 gebouweenheden, die elk een adres met huis- en busnummer dragen. De adressen zonder busnummer, zijnde de huisnummers 14/16/18, werden aan de 13de gebouweenheid, het gemeenschappelijk deel, gekoppeld. De adresposities van de huisnummers, die de gebouw­ingangen aanduiden, werden overgenomen bij de adressen.|

## Heeft ieder gebouw één gebouweenheid? Hoe gebeurt de afbakening? 
Nee, dit is niet het geval.

Zoals te zien is in het informatiemodel op de productpagina, kan een gebouw nul, één of meerdere gebouweenheden hebben.

Zoals aangegeven in het antwoord bij vraag 1.1 worden gebouweenheden vandaag aangemaakt waar in CRAB een adres aan een gebouw gekoppeld werd. Dit is echter een tijdelijke situatie tot het moment waarop de navelstreng met CRAB doorgeknipt wordt.

Daarna zullen gebouweenheden rechtstreeks aangemaakt worden door decentrale beheerders in het Gebouwenregister. Zij zullen enkel gebouweenheden mogen creëren wanneer aan de criteria voor de afbakening van een gebouweenheid voldaan is. Deze criteria werden opgenomen in een beslisboom.

Ruimten in gebouwen (bv. tuinhuis), die dienstbaar zijn aan een nabijgelegen gebouweenheid (bv. de gebouweenheid in de bijhorende woning), voldoen niet aan criterium 7: ‘functionele zelfstandigheid’. In een tuinhuis zal dus typisch géén gebouweenheid mogen aangemaakt worden (tenzij er bijvoorbeeld, volledig zelfstandig, een winkel zou in uitgebaat worden). Gebouwen zoals deze, zonder gebouweenheden, beschouwen we als bijgebouwen. Gebouwen mét gebouweenheden zijn hoofdgebouwen. Een gebouw kan ook meerdere gebouweenheden hebben. Een typevoorbeeld daarvan zijn woonblokken waarin elke flat potentieel een gebouweenheid vormt.

Het zal uiterst belangrijk zijn dat de beslisboom in de toekomst strikt gerespecteerd wordt bij het beheer van gebouweenheden, dit om te vermijden dat voor eender welke ruimte in een gebouw een gebouweenheid wordt aangemaakt. Zonder beslisboom zou in extremis voor elke kamer in een gebouw een gebouweenheid aangemaakt kunnen worden, met als gevolg dat iedereen over andere gebouweenheden spreekt en informatie-uitwisseling op basis van gebouweenheden niet meer mogelijk is. Deze richting willen we uiteraard niet uitgaan, vandaar het belang van deze beslisboom en het respecteren daarvan door beheerders.

## Wat is de betekenis van gebouweenheden met functie 'gemeenschappelijk deel'?

In gebouwen waarin minstens twee functioneel zelfstandige gebouweenheden voorkomen (bv. gebouw met winkel op gelijkvloers en wooneenheid op eerste verdieping) worden de ruimten en structuren die door de eenheden in kwestie gedeeld worden voorgesteld door een extra gebouweenheid met functie ‘gemeenschappelijk deel’.

Aldus kan men bij het koppelen van de eigen, thematische informatie (bv. rond energie, eigendom, veiligheid …) aan het Gebouwenregister in bovenstaand voorbeeld de identificator van een
- gebouweenheid met functie ‘wonen’ gebruiken om naar de wooneenheid te verwijzen;
- gebouweenheid met functie ‘detailhandel’ gebruiken om naar de winkel te verwijzen;
- gebouweenheid met functie ‘gemeenschappelijk deel’ gebruiken om naar de hal te verwijzen die toegang geeft tot de wooneenheid resp. winkel.
Merk op dat slechts één gemeenschappelijk deel per gebouw wordt aangemaakt. Een flatgebouw met meerdere trappenhallen, liftkokers en een gedeelde ondergrondse garage krijgt dus één gemeenschappelijk deel (niet één per trappenhal/liftkoker/garage).

Het gemeenschappelijk deel is tevens de drager van het huisnummeradres daar waar dit huisnummer uitsluitend naar (de gemeenschappelijke ruimten en structuren van) het gebouw verwijst. Er kan ook een gemeenschappelijk deel zijn zonder bijhorend adres (voorbeelden: zie vraag 7).

## Waarom zie ik vakantieparken, begijnhoven e.a. een groter aantal gebouweenheden dan ik - volgens de definitie van een gebouweenheid - zou verwachten? 
In een eerste fase worden gebouweenheden automatisch aangemaakt o.b.v. CRAB-adressen die een gebouwkoppeling hebben (zie vraag 5). In vakantieparken en begijnhoven koppelt de CRAB-beheerder het huisnummer (bv. Begijnhofstraat 1) van het hoofdgebouw vaak aan alle gebouwen binnen dat vakantiepark of begijnhof, om aan te geven dat de onderliggende subadressen (bv. Begijnhofstraat 1 bus 1) elk afzonderlijk naar één van deze gebouwen verwijzen (in CRAB kan ‘Begijnhofstraat 1 bus 1’ nl. niet rechtstreeks aan het juiste gebouw gekoppeld worden).

Bij de doorvertaling naar het Gebouwenregister wordt per huisnummer-gebouwkoppeling, en voor alle onderliggende subadressen, een gebouweenheid in dat gebouw aangemaakt. Er is dus sprake van een **vermenigvuldigingseffect**. Dit kan vermeden worden door het huisnummer in kwestie slechts aan één gebouw te koppelen in CRAB.

In de toekomst zal de CRAB-beheerder in staat zijn de gebouweenheden direct met het juiste adres in het juiste gebouw te plaatsen.

## Hoe wordt de status (levensloop) voor de verschillende objecten ingevuld? 
De beoogde levensloop van de kernobjecten werd eerst uitgetekend i.s.m. de werkgroep-Gebouwenregister. In deze projectfase worden de data in het Gebouwenregister uitsluitend uit het CRAB gehaald (dat op zijn beurt ook gebouwgeometrieën uit het [GRB](https://www.vlaanderen.be/digitaal-vlaanderen/onze-oplossingen/basiskaart-vlaanderen-grb) betrekt).

Daarbij worden de CRAB-statussen als volgt omgezet naar het nieuwe statusverloop (de statussen worden toegelicht in de objectcataloog Gebouwenregister):

## Gebouw
| Informatie in CRAB | Status | 
|:-:|:-:|
| Gebouw met status ‘vergunning aangevraagd’ | gepland | 
| Gebouw met status ‘bouwvergunning verleend’ | gepland | 
| Gebouw met status ‘in aanbouw’ | in aanbouw | 
| Gebouw met status ‘in gebruik’| gerealiseerd | 
| Gebouw met status ‘buiten gebruik’| gerealiseerd | 
| Gebouw waarvoor einddatum ingevuld werd toen gebouw status ‘in gebruik’ of ‘buiten gebruik’ had| gehistoreerd | 
| Gebouw waarvoor einddatum ingevuld werd toen gebouw status ‘vergunning verleend/aangevraagd’ of ‘in aanbouw’ had| niet gerealiseerd | 

Merk op: de levensloop wordt beschreven vanuit het resultaat, niet vanuit de vergunningsprocedure (deze informatie hoort thuis in het Vergunningenregister) dan wel het gebruik (we spreken ons niet uit over het al dan niet in gebruik zijn van een gebouw: dit is thematische informatie). In het Gebouwenregister worden ook niet-vergunningsplichtige gebouwen opgenomen.

## Gebouweenheid
| **Informatie in CRAB** | **Status** | 
|:-:|:-:|
| Gebouweenheid gebaseerd op huisnummer/subadres met status ‘voorgesteld’ | gepland | 
| Gebouweenheid gebaseerd op huisnummer/subadres met status ‘gereserveerd’ | gepland | 
| Gebouweenheid gebaseerd op huisnummer/subadres met status ‘inGebruik’ | gerealiseerd | 
| Gebouweenheid gebaseerd op huisnummer/subadres met status ‘buitenGebruik’ | gerealiseerd | 
| Gebouweenheid gebaseerd op huisnummer/subadres met status ‘nietOfficieel’ | gerealiseerd | 
| Gebouweenheid gebaseerd op huisnummer/subadres waarvan einddatum ingevuld werd toen adres status ‘inGebruik’ , ‘buitenGebruik’ of ‘nietOfficieel’ had| gehistoreerd | 
| Gebouweenheid gebaseerd op huisnummer/subadres waarvan einddatum ingevuld werd toen adres status ‘voorgesteld’ of ‘gereserveerd’ had| niet gerealiseerd | 

### Adres
| **Informatie in CRAB** | **Status** | **OfficieelToegekend** |
|:-:|:-:|
| Huisnummer/subadres met status ‘voorgesteld’ | voorgesteld | ja |
| Huisnummer/subadres met status ‘gereserveerd’ | voorgesteld | ja |
| Huisnummer/subadres met status ‘in gebruik’ | in gebruik | ja |
| Huisnummer/subadres met status ‘buiten gebruik’ | in gebruik | ja| 
| Huisnummer/subadres met status ‘niet officieel’| in gebruik | nee| 
| Huisnummer/subadres waarvoor einddatum ingevuld werd| gehistoreerd | (afhankelijk van adresstatus)| 

### Straatnaam
| **Informatie in CRAB** | **Status** | 
|:-:|:-:|
| Straatnaam met status ‘voorgesteld’ | voorgesteld | 
| Straatnaam met status ‘gereserveerd’ | voorgesteld | 
| Straatnaam met status ‘in gebruik’ | in gebruik | 
| Straatnaam met status ‘buiten gebruik’ | in gebruik | 
| Straatnaam waarvoor einddatum ingevuld werd| gehistoreerd | 

### Gemeente
| **Informatie in CRAB** | **Status** | 
|:-:|:-:|
| Actuele gemeente | in gebruik | 
| Gemeente waarvoor einddatum ingevuld werd | gehistoreerd | 

### Postinfo en Perceel
| **Informatie in CRAB** | **Status** | 
|:-:|:-:|
| Actueel object | gerealiseerd | 
| Object waarvoor einddatum ingevuld werd | gehistoreerd | 

In een latere projectfase zal de status rechtstreeks op het Gebouwenregister kunnen aangepast worden door decentrale beheerders. Daarbij wordt gestreefd naar een zo volledig mogelijk levensloop, waarbij het object in een zo vroeg mogelijk stadium in het register opgenomen wordt zodat het beschikbaar is voor thematische koppelingen.

## Wanneer krijgt een gebouweenheid status 'gehistoreerd'?
- Zolang het Gebouwenregister gevoed wordt vanuit CRAB (situatie vandaag): samen met de historering (= invullen van einddatum) van het adres waarop de eenheid gebaseerd werd.
- Van zodra er beheer is rechtstreeks op het Gebouwenregister (later) zal de beheerder kunnen oordelen dat een gebouweenheid **niet meer actueel is of niet meer in die afbakening bestaat** en dus gehistoreerd moet worden.
Worden bv. twee appartementen samengevoegd, dan zal de decentrale beheerder de twee corresponderende gebouweenheden op ‘gehistoreerd’ zetten en een nieuwe gebouweenheid met status ‘gerealiseerd’ aanmaken.

## Wanneer krijgt een gebouw status 'gehistoreerd'?
Een gebouw krijgt status ‘gehistoreerd’ wanneer het **gesloopt/samengevoegd/gesplitst werd of afgebrand is.** De levensloop van het gebouw wordt dan beëindigd.

Een ander gebouw dat in de plaats komt krijgt een andere objectidentificator en dus aparte levensloop.

**Een object dat gehistoreerd werd, wordt niet meer ‘tot leven gewekt’** met dezelfde objectidentificator. Dit geldt dus ook voor een gebouw.

## Welke objecten kunnen een adres dragen?
Er worden vier adresseerbare objecten onderscheiden:
- gebouweenheid
- perceel
- standplaats
- ligplaats
Stand- en ligplaatsen zullen later als object (‘resource’) worden toegevoegd. Gebouwen dragen enkel adressen via de daarbinnen gelegen gebouweenheden (fijnmazigere adressering).

## Hoe kan ik gebouwen terugvinden o.b.h. hun adres?
**Adressen worden in het Gebouwenregister niet meer rechtstreeks aan het gebouw gekoppeld, maar aan gebouweenheden binnen dat gebouw.**

De te volgend aanpak - met de services die vandaag beschikbaar zijn- is daarom:

1. Bepaal de objectidentificator van het adres in kwestie.

http://beta.basisregisters.vlaanderen.be/api/v1/adressen?gemeentenaam=Denderleeuw&straatnaam=Nieuwstraat&huisnummer=2

2. Filter de gebouweenheden o.b.v. dit adres

http://beta.basisregisters.vlaanderen.be/api/v1/gebouweenheden?adresobjectid=1859449

3. Bepaal in welk gebouw(en) de teruggegeven gebouweenheden liggen

## Ik heb een CRAB-adres resp. kadastraal/rijksregisteradres. Hoe kan ik dit in verband brengen met een authentiek adres in het adressenregister?
Er werden **migratieservices** voorzien om o.b.v. een CRAB-huisnummerId of -subadresId het corresponderende adres (met adresId) in het Adressenregister terug te vinden (opgelet: de bètaversie van deze service zal een AdresId teruggeven die verschilt van de AdresId in de productieomgeving; gebruik voor operationele processen steeds de service uit de productieomgeving!).

Voor kadastrale adressen en rijksregisteradressen kan gebruik gemaakt worden van de **adresmatchservice**. Op basis van adrescomponenten, straatcodes of indices kan de corresponderende straatnaam en/of het adres (met adresId) uit het Adressenregister teruggevonden worden.

Voor toelichting bij het gebruik van deze services, raadpleeg de documentatie:

[https://basisregisters.vlaanderen.be/Help/](https://basisregisters.vlaanderen.be/Help/) (productie)

## Waar vind ik de adresposities met herkomst 'brievenbus', 'nutsaansluiting' en 'toegang tot de weg' uit het CRAB terug?
Door de werkgroep-Gebouwenregister werd besloten dit soort ‘toepassingsgerichte’ adresposities niet langer in het Adressenregister op te nemen. De motivatie daarvoor is tweeledig:
- Deze zijn **teveel gericht op één gebruikersgroep, horen niet thuis in een basisregister.** Andere partijen kunnen deze informatie kwalitatiever bijhouden. Het heeft geen zin de gemeenten met de kartering ervan te belasten.
- In het CRAB werd deze informatie niet uniform door alle gemeenten beheerd. Het aandeel van de toepassingsgerichte posities bedroeg slechts 0.73% (ca. 24000 posities).
Waar de toepassingsgerichte positie de enige of meest kwalitatieve positie voor een adres vormde in CRAB, zal enkel de positie overgenomen worden in het Adressenregister (de positiespecificatie zal echter ‘gebouweenheid’ of ‘perceel’ zijn).

## Hoe kan ik adressuggesties (autocomplete) in mijn toepassing implementeren? 
Maak gebruik van de **geolocation-API** (documentatie: https://loc.geopunt.be/) om suggesties te verkrijgen voor vrije tekstinvoer:
bv: https://loc.geopunt.be/v4/suggestion?q=Koningin Mar

Teruggegeven straatnamen volgen het patroon:
**<straatnaam>, <gemeentenaam>**

bv: https://loc.geopunt.be/v4/suggestion?q=Graaf van Hoornestraat 5

Teruggegeven adressen volgen het patroon:
**<straatnaam> <huisnummer>, <postcode> <gemeentenaam>**
(merk op: er worden geen adressen met busnummer gesuggereerd)

Indien u de unieke adresidentificator van de gesuggereerde adressen wil kennen, ‘parst’ u de adrescomponenten uit bovenstaand antwoord en plakt u deze in volgende request:
bv: https://basisregisters.vlaanderen.be/api/v1/adressen?gemeentenaam=Nevele&straatnaam=Graaf van Hoornestraat&huisnummer=5

Vervolgens leest u het <id>-veld uit:
  
## Hoe kan ik keuzelijsten voor adresformulieren creëren?
  
  Bekijk [hier](https://assets.vlaanderen.be/image/upload/w_600,c_fill/v1678267926/Basisregisters_-_Flow_keuzelijsten_adresformulieren_qtpbks.jpg) het te volgen stappenplan.
  
## Wat is de betekenis van het veld 'homoniemtoevoeging'?
- In CRAB dragen sommige straatnamen een suffix, bv. ‘Krijgsbaan_HO, Antwerpen’, waarbij ‘HO’ staat voor het district ‘Hoboken’.
- Aangezien elke straatnaam uniek moet zijn binnen de gemeente, en districten in geen enkel adresmodel (CRAB, Adressenregister, OSLO², BeSt-Add) worden voorzien, heeft men deze suffix nodig om het onderscheid te maken met bv. ‘Krijgsbaan_DE, Antwerpen’ (gelijknamige straatnaam in district Deurne). Ook in andere gemeenten worden zeer sporadisch suffices gebruikt om homoniemen te onderscheiden.
- Daarom wordt in het Adressenregister naast het veld ‘straatnaam’ ook een ‘homoniemtoevoeging’ voorzien waarin deze suffix kan worden opgenomen, daar waar deze suffix in CRAB integraal deel uitmaakt van het veld ‘straatnaam’:
  -  CRAB: straatnaam=Krijgsbaan_HO
  - Adressenregister: straatnaam=Krijgsbaan, homoniemtoevoeging=HO
- **Nieuwe homoniemtoevoegingen zijn niet toegestaan.** Bij gemeentelijke fusies bijvoorbeeld moeten de homoniemen opgelost zijn op de datum dat de fusie ingaat.
  
## Elk object heeft een identificator (attribuut 'id') in de vorm van webadres. Wat is dit?

De **Vlaamse URI-standaard** schrijft voor dat naar Vlaamse ‘resources’ (zoals een object in het Gebouwenregister) kan verwezen worden met een [Uniform Resource Identifier](https://www.vlaanderen.be/digitaal-vlaanderen/onze-oplossingen/gebouwen-en-adressenregister/verklarende-woordenlijst-adressen-en-gebouwenregister) (URI). Deze data-URI is door zijn opbouw uniek binnen het World Wide Web en kan dus als stabiele identificator in eender welk systeem of databank gebruikt worden om ondubbelzinnig naar dat ene object te verwijzen. Daarnaast laten data-URI’s toe de resources als ‘linked data’ aan te bieden (cfr. CRAB-LOD).

Op dit moment zijn enkel de data-URI’s voor adressen resolvable, dit wil zeggen, linken enkel deze URI’s door naar een webdocument (voorstelling van het adres op het web).
  
## Waar vind ik de 'begin- en einddatum' uit het CRAB terug?

De begin- en einddatum in het CRAB definiëren een administratieve geldigheidsperiode bij de status van een object (de zogenaamde ‘objecthistoriek’). Zo kan bij de ingebruikname van een officiële straatnaam de datum van het gemeenteraadsbesluit meegegeven worden (begindatum) of bij het slopen van een gebouw de datum waarop de sloop voltooid werd (einddatum).

In de praktijk is het voor decentrale beheerders niet altijd even evident om deze administratieve data te kennen. Zo wordt het ‘einde der werken’ (het moment waarop de status van een gebouw in het Gebouwenregister op ‘gerealiseerd’ dient te komen) vandaag maar zelden door de bouwheer aan de gemeente meegedeeld. Bijgevolg kan de begin- en einddatum niet voldoende kwalitatief ingevuld worden.

Daarnaast kan geargumenteerd worden dat deze administratieve informatie al in andere bronnen beschikbaar is (cfr. [lokale besluiten als gelinkte open data](https://lokaalbestuur.vlaanderen.be/gelinkt-publiceren-en-melden)  en Vergunningenregister).

Door de werkgroep-Gebouwenregister werd daarom beslist **geen administratieve geldigheidsperiode** bij objecten in het Gebouwenregister te voorzien. Wel zullen datum en tijdstip alsook bijkomende herkomstinformatie (beschikbaar vanaf een volgende release) geregistreerd worden op het moment dat objecten worden opgevoerd, aangepast of verwijderd (de zogenaamde ‘recordhistoriek’).
  
## Hoe wordt het onderliggend perceel bij een gebouw bepaald?

Via de REST-API kunnen de [details van een gebouw](https://docs.basisregisters.staging-vlaanderen.be/docs/api-documentation.html#tag/api-documentation.html) opgevraagd worden. Daarbij wordt het eventuele onderliggende perceel getoond.

Een perceel wordt als onderliggend aan een gebouw beschouwd indien het voldoet aan volgende voorwaarde (formule voor de berekening van de ‘verbeterde topologische relatie’):

oppervlak overlap gebouw - perceel / oppervlak gebouw > 0.8 / # percelen waarmee het gebouw overlapt
  
## Waar vind ik het onderscheid en de relatie tussen hoofd- en bijgebouwen?

Een hoofdgebouw is een gebouw mét gebouweenheden, een bijgebouw een gebouw zonder gebouweenheden. Of een gebouw gebouweenheden mag bevatten, zie je in het antwoord op vraag 8. Aangezien een gebouw enkel geadresseerd kan worden via zijn gebouweenheden, kan een bijgebouw dus per definitie geen adressen dragen.

Het informatiemodel (zie productpagina) beschrijft geen relatie tussen hoofd- en bijgebouwen (bijvoorbeeld tussen een woning en het tuinhuis dat daarbij staat). Hoewel dit nuttig zou zijn, is het in de praktijk niet evident om deze relatie te bepalen. Bijgebouwen bij een hoofdgebouw bevinden zich bijvoorbeeld niet noodzakelijk op hetzelfde perceel (denk aan stallen bij een boerderij). Ook kunnen verschillende partijen andere interpretaties hebben van welke bijgebouwen bij een hoofdgebouw horen; deze koppeling kan toepassingsafhankelijk zijn, terwijl het register beoogt zo toepassingsonafhankelijk mogelijk te zijn. Als de relatie al in het Gebouwenregister beheerd zou worden, moeten beheerders gevonden worden die deze relatie actualiseren. Om deze redenen werd besloten de relatie vooralsnog niet in het register op te nemen.
  
## Wat is het verschil tussen de gebouwen in het GRB en deze in het Gebouwenregister?

Zie antwoord bij vraag 26.
  
## Op het terrein zie ik één gebouw, in het Gebouwenregister is het gebouw in kwestie echter opgesplitst in meerdere gebouwen. Hoe komt dit?

We ambiëren gebouwen, die op het terrein één geheel vormen, ook als één gebouw met één geometrie in het Gebouwenregister op te nemen. Vandaag is dit nog niet altijd het geval, om deze redenen:

Vandaag neemt het Gebouwenregister gebouwen over uit het CRAB (dat op zijn beurt ingemeten gebouwen ontvangt vanuit het GRB). Zo stromen gebouwen, die in het CRAB samen met hun adressen beheerd worden, netjes door naar het Gebouwenregister. Dit is een tijdelijke situatie die ervoor moet zorgen dat gebouwen beheerd worden in afwachting van het aanbieden van beheerprocessen rechtstreeks op het Gebouwenregister, en de daaropvolgende uitfasering van het beheer op CRAB.
Bijgevolg is de geometrie van een gebouw in het Gebouwenregister dezelfde als deze van het corresponderende gebouw in het CRAB. Er is vandaag nog geen methode beschikbaar om een onterecht gesplitst gebouw uit CRAB in het Gebouwenregister samen te voegen tot één. **Wanneer de beheerders van CRAB (= gemeenten) of GRB (= dienstenleveranciers Informatie Vlaanderen) verkeerdelijk oordeelden dat een gebouw gesplitst moest worden, dan moet die fout dus eerst in het CRAB of GRB rechtgezet worden (melding mogelijk via de CRAB- resp. GRB-meldingssystemen).**

Later zal de navelstreng met CRAB doorgeknipt worden en zal de gebouwgeometrie rechtstreeks in het Gebouwenregister kunnen aangepast worden (of zal een melding van een onterechte splitsing daar kunnen gemaakt worden).

1% van de gebouwen beschikt vandaag nog niet over een correcte geometrie in het Gebouwenregister. De geometrie voor deze gebouwen zal immers samengesteld moeten worden uit meerdere geometrieën die in het GRB beschikbaar zijn. Het GRB zal altijd de situatie op maaiveldhoogte karteren, het Gebouwenregister zal waar nodig de GRB-entiteiten samenvoegen tot een ‘bovenaanzicht’-weergave van het gebouw.
**Het opnemen van deze samengestelde gebouwgeometrieën is voor een latere fase gepland.**
  
## Hoe kan ik adressen aan gebouweenheden of percelen koppelen in het testbestand?

Zowel gebouweenheden als percelen kunnen adressen dragen. In het testbestand zitten gebouweenheden, percelen en adressen in drie afzonderlijke .dbf-bestanden. Om ze aan elkaar te koppelen heeft u ook het bestand ‘Adreskoppelingen.dbf’ nodig. Via software als MS Access, QGIS e.a. kunt u een ‘inner join’ uitvoeren tussen adreskoppelingen-gebouweenheid enerzijds, en adreskoppelingen-adres anderzijds. In onderstaande figuur staat aangegeven tussen welke velden u de koppeling moet leggen (zie zwarte pijlen). Dezelfde werkwijze is ook toepasbaar met ‘Perceel.dbf’ in de plaats van ‘Gebouweenheid.dbf’.


Merk op: vanwege de grootte wordt ‘Adreskoppelingen.dbf’ opgesplitst in afzonderlijke bestanden. Deze kunt u best eerst terug samenvoegen vooraleer de ‘join’ met de andere tabellen uit te voeren.
  
## Hoe worden gebouwen afgebakend?

Voor afbakening gebouwen worden deze uiterlijke kenmerken in acht genomen:
- Zijn er meerdere huisnummers toegekend?
- Loopt er een perceelsgrens door het gebouw?
- Zijn er meerdere ingangen?
- Is er een verticale as door het gebouw?
Als 3 van deze 4 criteria positief zijn, dan wordt een gebouw meestal gesplitst.

Indien men beschikt over bouwplannen, dan kunnen deze meer inzicht verschaffen over de opdeling.

Een gedetailleerde toelichting hierover vind je [hier](https://assets.vlaanderen.be/image/upload/v1678268047/Basiskaart_-_Procedure_afbakening_gebouw_bjocy0.pdf)).
