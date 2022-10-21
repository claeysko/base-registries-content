**Decentraal beheer**

De edit endpoints maken decentraal beheer mogelijk in het gebouwen- en adressenregister. Deze endpoints worden door de dienstenleveranciers geïmplementeerd in hun software. Zo kunnen vb. straatnamen, adressen, gebouwen en gebouweenheden toegevoegd, verwijderd of aangepast worden. Hieronder kan u per register een lijst vinden van welke beheeracties er allemaal mogelijk zijn.

Straatnamen
* Stel een straatnaam voor.
* Keur een straatnaam goed.
* Keur een straatnaam af.
* Hef een straatnaam op.
* Corrigeer de straatnaam van een straatnaam.
* Corrigeer de goedkeuring van een straatnaam.
* Corrigeer de afkeuring van een straatnaam.
* Corrigeer de opheffing van een straatnaam.

Adressen
* Stel een adres voor.
* Keur een adres goed.
* Keur een adres af.
* Hef een adres op.
* Regulariseer een adres.
* Deregulariseer een adres.
* Corrigeer de adrespositie van een adres.
* Corrigeer de postcode van een adres.
* Corrigeer het huisnummer van een adres.
* Corrigeer het busnummer van een adres.
* Corrigeer de goedkeuring van een adres.
* Corrigeer de afkeuring van een adres.
* Corrigeer de opheffing van een adres.
* Wijzig de postcode van een adres.

Gebouwen
* Plan een gebouw in.
* Plaats een gebouw in aanbouw.
* Realiseer een gebouw.
* Realiseer een gebouw niet.
* Corrigeer de inAanbouw plaatsing van een gebouw.
* Corrigeer de realisering van een gebouw.
* Corrigeer de nietRealisering van een gebouw.

Gebouweenheid
* Plan een gebouweenheid in.
* Realiseer een gebouweenheid
* Realiseer een gebouweenheid niet.
* Corrigeer de realisering van een gebouweenheid.
* Corrigeer de niet realisering van een gebouweenheid.

**Betekenis van de edit events en velden in de feed**

Een overzicht van alle mogelijke edit events en de betekenis van de attributen onder het blokje <event> vindt u op deze pagina: https://api.basisregisters.staging-vlaanderen.be/v1/info/events?tags=edit.

**Welke huisnummers & busnummers worden aanvaard voor een nieuw adres?**

Als er een nieuw voorgesteld adres wordt ingevoerd dan moet het huisnummer en eventueel het busnummer aan bepaalde voorwaarden voldoen.

De regex die van toepassing is op het huisnummer is ^[1-9]([0-9]{0,8}([A-H]|[K-N]|[P]|[R-T]|[V-Z]){0,1}|[0-9]{0,9})$. Dit wilt zeggen dat huisnummers 45, 2C of 7563M zullen aanvaard worden, maar huisnummers 045, 2I, 5BIS of 4a niet aanvaard zullen worden.

De regex die van toepassing is op het busnummer is ^[a-zA-Z0-9]{1,10}$. Bovenop deze regex wordt het woord bus, Bus of BUS ook niet aanvaard. Dit wilt zeggen dat busnummers 1, 001 of 5C aanvaard zullen worden, maar busnummers 0, Bus 1 of 1-A niet aanvaard zullen worden.

**Welke combinaties zijn mogelijk bij adrespositie?**

Wanneer de positieGeometrieMethode aangeduidDoorBeheerder wordt meegegeven dan moet de positieSpecificatie 1 van de volgende zaken zijn:
* Lot
* Perceel
* Ingang
* Standplaats
* Ligplaats

In dit geval is het ook verplicht om een geldige positie mee te geven bij het adres.

Wanneer de positieGeometrieMethode afgeleidVanObject wordt meegegeven dan moet de positieSpecificatie gemeente zijn of kan deze leeg worden gelaten. Wanneer positieSpecificatie leeg wordt geladen, wordt er achterliggend voor positieSpecificatie gemeente gekozen. Een positie kan worden meegegeven, maar deze gaat altijd overschreden worden met de centroïde van de gemeente waarbinnen het adres ligt.

Bij de edit api ‘Stel een adres voor’ is het mogelijk om geen positieGeometrieMethode mee te geven. In dit geval gaat er automatisch gekozen worden voor positieGeometrieMethode afgeleidVanObject.

**Functie van een gebouweenheid: nietGekend of gemeenschappelijkDeel**

Een gebouweenheid kan 2 functies hebben: nietGekend of gemeenschappelijkDeel. In de toekomst zal deze lijst met mogelijke waarden uitgebreid worden.

Wanneer er een gebouweenheid wordt ingepland, is het enkel mogelijk om een ‘nietGekend’ als functie mee te geven. De functie ‘gemeenschappelijkDeel’ wordt automatisch toegekend van zodra er 2 ‘nietGekend’ ‘gepland/gerealiseerde’ gebouweenheden gekoppeld zijn aan het gebouw.

**Wat is het verschil tussen een correctie en een wijziging?**

Er wordt een onderscheid gemaakt tussen correcties en wijzigingen. In het eerste geval gaat het om een rechtzetting van een fout (vb. ‘Van Eikstraat’ moet zijn ‘Van Eyckstraat’), in het tweede geval gaat het om een verandering in administratieve toestand (vb. gebouw veranderd van status ‘inAanbouw’ naar ‘inGebruik’).
