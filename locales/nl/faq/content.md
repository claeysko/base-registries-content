Hieronder vindt u een overzicht van de meest voorkomende vragen met hun antwoorden die onze gebruikers hebben over de basisregisters.
Als u een vraag heeft die hieronder niet beantwoord wordt, mail dan naar digitaal.vlaanderen@vlaanderen.be.

* [Algemene vragen](#algemenevragen)
* [Vragen gebouwen- en adressenregister](#vragengebouwenenadressenregister)

  
## Algemene vragen {#algemenevragen}
 
<details>

<summary>Hoe kan ik de WMS gebruiken?</summary>

De WMS laat toe adressen, gebouwen en gebouweenheden per status en wegsegmenten per soort **op kaart te visualiseren** en objecten aan te klikken voor meer informatie. Deze kaartlagen kunnen ingeladen worden in GIS- of andere software. Een lijst van GIS-software vindt u [hier](https://en.wikipedia.org/wiki/Comparison_of_geographic_information_systems_software). We kunnen zelf QGIS (open source, gratis) aanbevelen.

Het is belangrijk in de GIS-software als coördinatensysteem voor het project **EPSG:31370** (Belgian Lambert 72) te kiezen en **PNG** als beeldformaat vooraleer lagen toe te voegen. De adressen worden zichtbaar vanaf schaal 1:2000 en hoger, gebouwen en gebouweenheden worden zichtbaar vanaf schaal 1:8000 of hoger en wegen worden zichtbaar afhankelijk van soort weg. De maximumschaal is 1:28000. 

Via de ‘identify’-functie kunt u de details van een object op de kaart met een muisklik opvragen.

</details>


<details>

<summary>Hoe kan ik de endpoints van de basisregisters uitproberen? </summary>

Een eenvoudige test van de REST-services kan door een URL samen te stellen in de adresbalk van uw browser. In uw browser krijgt u dan ook het resultaat van de aangeroepen service. 
- Algemene uitleg over de endpoints kan [hier](https://basisregisters.vlaanderen.be/producten/grar#readendpointsgrar) gevonden worden.
- Documentatie over de URL's en bijhorende parmameters kan [hier](https://docs.basisregisters.vlaanderen.be/docs/api-documentation.html#tag/api-documentation.html) gevonden worden.

</details>


<details>

<summary>Elk object heeft een identificator (attribuut 'id') in de vorm van webadres. Wat is dit?</summary>

De **Vlaamse URI-standaard** schrijft voor dat naar Vlaamse ‘resources’ (zoals een object in het Gebouwenregister) kan verwezen worden met een [Uniform Resource Identifier](https://www.vlaanderen.be/digitaal-vlaanderen/onze-oplossingen/gebouwen-en-adressenregister/verklarende-woordenlijst-adressen-en-gebouwenregister) (URI). Deze data-URI is door zijn opbouw uniek binnen het World Wide Web en kan dus als stabiele identificator in eender welk systeem of databank gebruikt worden om ondubbelzinnig naar dat ene object te verwijzen. Daarnaast laten data-URI’s toe de resources als ‘linked data’ aan te bieden (cfr. CRAB-LOD).

Op dit moment zijn enkel de data-URI’s voor adressen resolvable, dit wil zeggen, linken enkel deze URI’s door naar een webdocument (voorstelling van het adres op het web).

</details>


## Vragen gebouwen- en adressenregister {#vragengebouwenenadressenregister}

<details>

<summary>Ik heb een CRAB huisnummer- of CRAB subadresId, wat is het gebouwen- en adressenregister objectId?</summary>

U kan op 2 manieren achterhalen wat het adressen objectId is van een CRAB huisnummer of een CRAB subadres.
- Via de read endpoints
  -   Voor CRAB huisnummers gebruikt u volgende readAPI: https://docs.basisregisters.vlaanderen.be/docs/api-documentation.html#operation/ListCrabHouseNumbers.
  -   Voor CRAB subadressen gebruikt u volgende readAPI: https://docs.basisregisters.vlaanderen.be/docs/api-documentation.html#operation/ListCrabSubaddresses.
- Via het downloadbestand
  - In het downloadbestand van het gebouwen- en adressenregister zitten er 2 dbf's files met daarin een overzicht van het CRAB huisnummer- en CRAB subadresId met hun overeenkomstige gebouwen- en adressenregister objectId.

</details>


<details>

<summary>Ik heb een terreinObjectId of identificatorTerreinObject, hoe weet ik welke gebouwen- en adressenregister objectId dit is?</summary>

Via het read endpoint van CRAB gebouwen kan u achterhalen wat het gebouwen- en adressenregister objectId is. U geeft in de URL het terreinObjectId of identificatorTerreinObject mee en u krijgt een overzicht 
Zie https://docs.basisregisters.vlaanderen.be/docs/api-documentation.html#operation/ListCrabBuildings.

</details>


<details>

<summary>Hoe kan ik het downloadbestand gebruiken?</summary>

Het downloadbestand kan ingeladen en gevisualiseerd worden met GIS-software. Een lijst van GIS-software vindt u [hier](https://en.wikipedia.org/wiki/Comparison_of_geographic_information_systems_software). We kunnen zelf QGIS (open source, gratis) aanbevelen.
Meer informatie over dit downloadbestand kan u [hier](https://basisregisters.vlaanderen.be/producten/grar#downloadbestandgrar) vinden. 

</details>


<details>

<summary>Zal het downloadbestand later als dataproduct bestendigd worden? </summary>

Het is de bedoeling dat het downloadbestand een dataproduct gaat worden.  

</details>


<details>

<summary> Moet ik nu al overschakelen naar de v2 endpoints van het gebouwen- en adressenregister? </summary>

Dit wordt sterk aangeraden. Vanaf ten laatste 1 november 2023 zullen de v1 endpoints niet meer up-to-date zijn als gevolg van de migratie van CRAB naar het Gebouwen- en Adressenregister. Om ervoor te zorgen dat u de meest recente gegevens blijft ontvangen, is het dus belangrijk om vóór deze datum over te stappen naar de nieuwe v2 endpoints. We begrijpen dat het migratieproces enige tijd kan vergen. Daarom hebben we besloten om de v1 endpoints **tot 1 maart 2024** beschikbaar te houden, zodat u voldoende tijd heeft om over te stappen naar de nieuwe v2 endpoints.
</details>


<details>

<summary> Wat is het verschil tussen adresmatch endpoint v1 en adresmatch endpoint v2? </summary>

#### Wat is hetzelfde gebleven tov adresmatch v1?
- De logica achter de fuzzy matching.
- De responses die als resultaat worden teruggestuurd.

#### Wat is er uit adresmatch v2 verwijderd dat in adresmatch v1 zat?
- De query parameter ‘kadStraatcode’.
- De query parameter ‘rrStraatcode’.
- De query parameter ‘index’.
- Het response veld ‘adresseerbareObjecten’. Er werd hiervoor een alternatief voorzien. Dit kan u vinden onder toevoegingen. 

#### Wat is het verschil tussen adresmatch v2 en adresmatch v1?
- Het content-type van v2 is ‘application/ld+json’. Van v1 was dit default ‘application+json’, maar ‘application/xml’ was ook mogelijk.
- De geometrievelden zijn gewijzigd. De coördinaten van het object staan vanaf nu in het gml-formaat en alle velden die met geometrie te maken hebben zijn samengevoegd onder 1 veld.

#### Wat is er in adresmatch v2 toegevoegd dat niet in adresmatch v1 zit?
- Het veld ‘links’. In dit veld zit een lijst van gerelateerde resources om te achterhalen wat de gelinkte objecten zijn aan het adres. Momenteel worden er 2 URL’s getoond. 
  - URL 1: URL die alle gebouweenheden gaat tonen die gekoppeld zijn aan dit adres objectId.
  - URL 2: URL die alle percelen gaat tonen die gekoppeld zijn aan dit adres obejctId.
  - Op termijn zal er een nieuwe API zijn waarin de adreskoppelingen per adres zullen getoond worden.
- Het veld @context. Dit veld bevat de linked-data context van het endpoint. Dit is een URI naar de JSON-LD file.
- Het veld @type. Dit veld bevat het linked-data type van het endpoint. 
</details>


<details>

<summary>Wat is de update frequentie van de WMS'en van het gebouwen- en adressenregister?  </summary>
De update frequentie van de WMS'en bij wijzigingen in het gebouwen- en adressenregister zijn near real time. Wat houdt dit in? Dit wit zeggen dat als bijvoorbeeld een adres wordt aangepast, de aanpassing van het adres zo goed als direct erna ook in de WMS van het gebouwen- en adressenregister zichtbaar zal zijn. 

</details>


<details>

<summary>Wat is de relatie tussen een gebouweenheid en adres?  </summary>
In gebouwen met exact één gebouweenheid krijgt de gebouweenheid een huisnummer. Als er voor één gebouw meerdere gebouweenheden bestaan, dan moeten de gemeenten aan elk van deze gebouweenheden een busnummer toekennen terwijl aan de gemeenschappelijke delen geen busnummer mag worden toegekend. Het is niet verplicht om aan een gemeenschappelijk deel een huisnummer toe te kennen. 

</details>


<details>

<summary>Is de puntgeometrie van een gebouweenheid dezelfde als deze van het adres?</summary>
Het attribuut ‘geometrie’ van een gebouweenheid is de positie van de gebouweenheid binnen de gebouwcontour.
- Staat de ‘positieGeometrieMethode’ op ‘afgeleidVanObject’ dan werd deze positie afgeleid van het gebouw waarbinnen de gebouweenheid ligt en betreft het de centroïde van het gebouw.
- Staat de ‘positieGeometrieMethode’ op ‘aangeduidDoorBeheerder’ dan werd de positie manueel geplaatst door een decentraal beheerder (in concreto: aangezien gebouweenheden momenteel automatisch aangemaakt worden o.b.v. CRAB-adressen betekent dit dat van het corresponderende adres in CRAB de meest kwalitatieve, manuele positie gebruikt werd).
- Echter, ligt de positie van het CRAB-adres buiten de gebouwcontour, dan zal de daarop gebaseerde gebouweenheid automatisch op de centroïde van het gebouw geplaatst worden. Gebouweenheden dienen namelijk steeds binnen een gebouw te liggen.
Dit betekent dat de gebouweenheid een andere positie kán hebben dan het adres in CRAB waarop het gebaseerd werd.

</details>


<details>

<summary>Heeft ieder gebouw één gebouweenheid? Hoe gebeurt de afbakening?  </summary>

Nee, dit is niet het geval. Het gebouw kan 0, 1 of meerdere gebouweenheden hebben. Momenteel worden gebouweenheden vandaag aangemaakt waar in CRAB een adres aan een gebouw gekoppeld werd. Dit is echter een tijdelijke situatie tot december 2023 wanneer CRAB is uitgeschakeld. Daarna zullen gebouweenheden rechtstreeks aangemaakt worden door decentrale beheerders in het gebouwen- en adressenregister.  

</details>


<details>

<summary>Wat is de betekenis van gebouweenheden met de functie 'gemeenschappelijk deel'? </summary>

In gebouwen waarin minstens twee functioneel zelfstandige gebouweenheden voorkomen (bv. gebouw met winkel op gelijkvloers en wooneenheid op eerste verdieping) worden de ruimten en structuren die door de eenheden in kwestie gedeeld worden voorgesteld door een extra gebouweenheid met functie ‘gemeenschappelijk deel’. Merk op dat slechts één gemeenschappelijk deel per gebouw wordt aangemaakt. Een flatgebouw met meerdere trappenhallen, liftkokers en een gedeelde ondergrondse garage krijgt dus één gemeenschappelijk deel (niet één per trappenhal/liftkoker/garage). Het gemeenschappelijk deel is tevens de drager van het huisnummeradres daar waar dit huisnummer uitsluitend naar (de gemeenschappelijke ruimten en structuren van) het gebouw verwijst. Er kan ook een gemeenschappelijk deel zijn zonder bijhorend adres.

</details>


<details>

<summary>Wat is de flow van de statussen van de verschillende objecten van het gebouwen- en adressenregister?  </summary>

Zie https://basisregisters.vlaanderen.be/documentatie/statusflowgrar voor een volledig overzicht per object per status. 

</details>


<details>

<summary>Welke objecten kunnen een adres dragen? </summary>

Er worden vier adresseerbare objecten onderscheiden:
- gebouweenheid
- perceel
- standplaats
- ligplaats
Stand- en ligplaatsen zullen later als object (‘resource’) worden toegevoegd. Gebouwen dragen enkel adressen via de daarbinnen gelegen gebouweenheden (fijnmazigere adressering).
</details>


<details>

<summary>Hoe kan ik gebouwen terugvinden o.b.h. hun adres? </summary>

**Adressen worden in het gebouwen- en adressenregister niet meer rechtstreeks aan het gebouw gekoppeld, maar aan gebouweenheden binnen dat gebouw.**

De te volgend aanpak - met de services die vandaag beschikbaar zijn- is daarom:
- Stap 1: Bepaal de objectidentificator van het adres in kwestie (vb. URL: http://basisregisters.vlaanderen.be/api/v2/adressen?gemeentenaam=Denderleeuw&straatnaam=Nieuwstraat&huisnummer=2).
- Stap 2: Filter de gebouweenheden o.b.v. dit adres (vb. URL: http://basisregisters.vlaanderen.be/api/v2/gebouweenheden?adresobjectid=278669).
- Stap 3: Bepaal in welk gebouw(en) de teruggegeven gebouweenheden liggen.
</details>


<details>

<summary>Waar vind ik de adresposities met herkomst 'brievenbus', 'nutsaansluiting' en 'toegang tot de weg' uit het CRAB terug? </summary>

Door de werkgroep werd besloten dit soort ‘toepassingsgerichte’ adresposities niet langer in het gebouwen- en addressenregister op te nemen. De motivatie daarvoor is tweeledig:
- Deze zijn **teveel gericht op één gebruikersgroep, horen niet thuis in een basisregister.** Andere partijen kunnen deze informatie kwalitatiever bijhouden. Het heeft geen zin de gemeenten met de kartering ervan te belasten.
- In het CRAB werd deze informatie niet uniform door alle gemeenten beheerd. Het aandeel van de toepassingsgerichte posities bedroeg slechts 0.73% (ca. 24000 posities).
Waar de toepassingsgerichte positie de enige of meest kwalitatieve positie voor een adres vormde in CRAB, zal enkel de positie overgenomen worden in het gebouwen-en adressenregister (de positiespecificatie zal echter ‘gebouweenheid’ of ‘perceel’ zijn). 
</details>


<details>

<summary>Hoe kan ik adressuggesties (autocomplete) in mijn toepassing implementeren?  </summary>

- Stap 1: Maak gebruik van de **geolocation-API** (documentatie: https://loc.geopunt.be/) om suggesties te verkrijgen voor vrije tekstinvoer: vb: https://loc.geopunt.be/v4/suggestion?q=Koningin Mar.
- Stap 2: Teruggegeven straatnamen volgen het patroon: **<straatnaam>, <gemeentenaam>** vb: https://loc.geopunt.be/v4/suggestion?q=Graaf van Hoornestraat 5.
- Stap 3: Teruggegeven adressen volgen het patroon: **<straatnaam> <huisnummer>, <postcode> <gemeentenaam>** (merk op: er worden geen adressen met busnummer gesuggereerd).
- Stap 4: Indien u de unieke adresidentificator van de gesuggereerde adressen wil kennen, ‘parst’ u de adrescomponenten uit bovenstaand antwoord en plakt u deze in volgende request: vb: https://basisregisters.vlaanderen.be/api/v2/adressen?gemeentenaam=Nevele&straatnaam=Graaf van Hoornestraat&huisnummer=5
- Stap 5: Vervolgens leest u het id-veld uit.
</details>


<details>

<summary>Hoe kan ik keuzelijsten voor adresformulieren creëren?</summary>

![image](https://github.com/Informatievlaanderen/base-registries-content/assets/49196256/88364e4e-fcae-4a90-9d1a-ca711ea75174)

U kan op basis van de verschillende read endpoints (https://basisregisters.vlaanderen.be/producten/grar#readendpointsgrar) een lijst tonen met gegevens in.
- Stap 1: Vraag een lijst met gemeenten op​.
- Stap 2: Vraag een lijst met postinfo over postcodes op binnen de gekozen gemeente.​
- Stap 3: Vraag een lijst met straatnamen op binnen de gekozen gemeente​.
- Stap 4: Vraag een lijst met adressen op binnen de gekozen gemeente & straatnaam.​
- Stap 5: Vraag een adres op.

</details>


<details>

<summary>Wat is de betekenis van het veld 'homoniemtoevoeging'?</summary>

- In CRAB dragen sommige straatnamen een suffix, bv. ‘Krijgsbaan_HO, Antwerpen’, waarbij ‘HO’ staat voor het district ‘Hoboken’.
- Aangezien elke straatnaam uniek moet zijn binnen de gemeente, en districten in geen enkel adresmodel (CRAB, Adressenregister, OSLO², BeSt-Add) worden voorzien, heeft men deze suffix nodig om het onderscheid te maken met bv. ‘Krijgsbaan_DE, Antwerpen’ (gelijknamige straatnaam in district Deurne). Ook in andere gemeenten worden zeer sporadisch suffices gebruikt om homoniemen te onderscheiden.
- Daarom wordt in het Adressenregister naast het veld ‘straatnaam’ ook een ‘homoniemtoevoeging’ voorzien waarin deze suffix kan worden opgenomen, daar waar deze suffix in CRAB integraal deel uitmaakt van het veld ‘straatnaam’:
  -  CRAB: straatnaam=Krijgsbaan_HO
  - Adressenregister: straatnaam=Krijgsbaan, homoniemtoevoeging=HO
- **Nieuwe homoniemtoevoegingen zijn niet toegestaan.** Bij gemeentelijke fusies bijvoorbeeld moeten de homoniemen opgelost zijn op de datum dat de fusie ingaat.
</details>


<details>

<summary>Waar vind ik de 'begin- en einddatum' uit het CRAB terug?</summary>

De begin- en einddatum in het CRAB definiëren een administratieve geldigheidsperiode bij de status van een object (de zogenaamde ‘objecthistoriek’). Zo kan bij de ingebruikname van een officiële straatnaam de datum van het gemeenteraadsbesluit meegegeven worden (begindatum) of bij het slopen van een gebouw de datum waarop de sloop voltooid werd (einddatum).

In de praktijk is het voor decentrale beheerders niet altijd even evident om deze administratieve data te kennen. Zo wordt het ‘einde der werken’ (het moment waarop de status van een gebouw in het Gebouwenregister op ‘gerealiseerd’ dient te komen) vandaag maar zelden door de bouwheer aan de gemeente meegedeeld. Bijgevolg kan de begin- en einddatum niet voldoende kwalitatief ingevuld worden.

Daarnaast kan geargumenteerd worden dat deze administratieve informatie al in andere bronnen beschikbaar is (cfr. [lokale besluiten als gelinkte open data](https://lokaalbestuur.vlaanderen.be/gelinkt-publiceren-en-melden)  en vergunningenregister).

Door de werkgroep werd daarom beslist **geen administratieve geldigheidsperiode** bij objecten in het gebouwen- en adressenregister te voorzien. Wel zullen datum en tijdstip alsook bijkomende herkomstinformatie (beschikbaar vanaf een volgende release) geregistreerd worden op het moment dat objecten worden opgevoerd, aangepast of verwijderd (de zogenaamde ‘recordhistoriek’).
</details>


<details>

<summary>Hoe weet ik welk perceel aan het gebouw gekoppeld is?</summary>

Via het read endpoint detail gebouw v2 ([Documentatie](https://docs.basisregisters.vlaanderen.be/docs/api-documentation.html#operation/GetBuildingV2)) kunnen de eventuele gekoppelde percelen opgevraagd worden.
Een perceel wordt als onderliggend aan een gebouw beschouwd indien het voldoet aan volgende voorwaarde (formule voor de berekening van de ‘verbeterde topologische relatie’): oppervlak overlap gebouw - perceel / oppervlak gebouw > 0.8 / # percelen waarmee het gebouw overlapt.
</details>


<details>

<summary>Waar vind ik het onderscheid en de relatie tussen hoofd- en bijgebouwen?</summary>

Een hoofdgebouw is een gebouw mét gebouweenheden, een bijgebouw een gebouw zonder gebouweenheden. Aangezien een gebouw enkel geadresseerd kan worden via zijn gebouweenheden, kan een bijgebouw dus per definitie geen adressen dragen. Het informatiemodel beschrijft geen relatie tussen hoofd- en bijgebouwen (bijvoorbeeld tussen een woning en het tuinhuis dat daarbij staat). Hoewel dit nuttig zou zijn, is het in de praktijk niet evident om deze relatie te bepalen. Bijgebouwen bij een hoofdgebouw bevinden zich bijvoorbeeld niet noodzakelijk op hetzelfde perceel (denk aan stallen bij een boerderij). Ook kunnen verschillende partijen andere interpretaties hebben van welke bijgebouwen bij een hoofdgebouw horen; deze koppeling kan toepassingsafhankelijk zijn, terwijl het register beoogt zo toepassingsonafhankelijk mogelijk te zijn. Als de relatie al in het gebouwen- en adressenregister beheerd zou worden, moeten beheerders gevonden worden die deze relatie actualiseren. Om deze redenen werd besloten de relatie vooralsnog niet in het register op te nemen.
</details>


<details>

<summary>Hoe worden gebouwen afgebakend?</summary>

Voor afbakening gebouwen worden deze uiterlijke kenmerken in acht genomen:
- Zijn er meerdere huisnummers toegekend?
- Loopt er een perceelsgrens door het gebouw?
- Zijn er meerdere ingangen?
- Is er een verticale as door het gebouw?
Als 3 van deze 4 criteria positief zijn, dan wordt een gebouw meestal gesplitst.

Indien men beschikt over bouwplannen, dan kunnen deze meer inzicht verschaffen over de opdeling.

Een gedetailleerde toelichting hierover vind je [hier](https://assets.vlaanderen.be/image/upload/v1678268047/Basiskaart_-_Procedure_afbakening_gebouw_bjocy0.pdf)).
</details>
