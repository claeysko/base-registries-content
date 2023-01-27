**Decentraal beheer**

De edit endpoints maken decentraal beheer mogelijk in het gebouwen- en adressenregister. Deze endpoints worden door de dienstenleveranciers geïmplementeerd in hun software. Zo kunnen vb. straatnamen, adressen, gebouwen en gebouweenheden toegevoegd, verwijderd of aangepast worden. Hieronder kan u per register een lijst vinden van welke beheeracties er allemaal mogelijk zijn en wie welke beheeractie mag uitvoeren. 

Er zijn 2 soorten rollen mogelijk:
* Decentrale bijwerker:  Staan in voor het beheer van adressen, gebouwen en enkele correcties. vb. lokale besturen. 
* Interne bijwerker: Staan in voor de correcties van adressen, gebouwen. vb. GRB of operatoren van Digitaal Vlaanderen. 

Straatnamen
* Stel een straatnaam voor. (Decentrale bijwerker)
* Keur een straatnaam goed. (Decentrale bijwerker)
* Keur een straatnaam af. (Decentrale bijwerker)
* Hef een straatnaam op. (Decentrale bijwerker)
* Corrigeer de straatnaam van een straatnaam. (Decentrale bijwerker)
* Corrigeer de goedkeuring van een straatnaam. (Interne bijwerker)
* Corrigeer de afkeuring van een straatnaam. (Interne bijwerker)
* Corrigeer de opheffing van een straatnaam. (Interne bijwerker)

Adressen
* Stel een adres voor. (Decentrale bijwerker)
* Keur een adres goed. (Decentrale bijwerker)
* Keur een adres af. (Decentrale bijwerker)
* Hef een adres op. (Decentrale bijwerker)
* Verwijder een adres. (Interne bijwerker)
* Regulariseer een adres. (Decentrale bijwerker)
* Deregulariseer een adres. (Decentrale bijwerker)
* Corrigeer de adrespositie van een adres. (Decentrale bijwerker)
* Corrigeer de postcode van een adres. (Decentrale bijwerker)
* Corrigeer het huisnummer van een adres. (Decentrale bijwerker)
* Corrigeer het busnummer van een adres. (Decentrale bijwerker)
* Corrigeer de goedkeuring van een adres. (Decentrale bijwerker)
* Corrigeer de afkeuring van een adres. (Decentrale bijwerker)
* Corrigeer de opheffing van een adres. (Decentrale bijwerker)
* Corrigeer de regularisatie van een adres. (Decentrale bijwerker)
* Corrigeer de deregularisatie van een adres. (Decentrale bijwerker)
* Wijzig de postcode van een adres. (Interne bijwerker)

Gebouwen
* Plan een gebouw in. (Decentrale bijwerker)
* Plaats een gebouw in aanbouw. (Decentrale bijwerker)
* Realiseer een gebouw. (Decentrale bijwerker)
* Realiseer een gebouw niet. (Decentrale bijwerker, Omgeving)
* Verwijder een geschetst gebouw. (Interne bijwerker)
* Corrigeer de inAanbouw plaatsing van een gebouw. (Decentrale bijwerker)
* Corrigeer de realisering van een gebouw. (Decentrale bijwerker)
* Corrigeer de nietRealisering van een gebouw. (Decentrale bijwerker)
* Wijzig de geometrie van een geschetst gebouw. (Decentrale bijkwerker)

Gebouweenheid
* Plan een gebouweenheid in. (Decentrale bijwerker)
* Realiseer een gebouweenheid (Decentrale bijwerker)
* Realiseer een gebouweenheid niet. (Decentrale bijwerker)
* Hef een gebouweenheid op. (Decentrale bijwerker)
* Verwijder een gebouweenheid. (Interne bijwerker)
* Regulariseer een gebouweenheid. (Decentrale bijwerker)
* Deregulariseer een gebouweenheid. (Decentrale bijwerker)
* Corrigeer de realisering van een gebouweenheid. (Decentrale bijwerker)
* Corrigeer de niet realisering van een gebouweenheid. (Decentrale bijwerker)
* Corrigeer de opheffing van een gebouweenheid. (Decentrale bijwerker)
* Corrigeer de positie van een gebouweenheid. (Decentrale bijwerker)
* Corrigeer de regularisatie van een gebouweenheid. (Decentrale bijwerker)
* Corrigeer de deregularisatie van een gebouweenheid. (Decentrale bijwerker)
* Koppel een adres aan een gebouweenheid. (Decentrale bijwerker)
* Ontkoppel een adres van een gebouweenheid. (Decentrale bijwerker)

Percelen
* Koppel een adres aan een perceel. (Decentrale bijwerker)
* Ontkoppel een adres van een perceel. (Decentrale bijwerker)

**Betekenis van de edit events en velden in de feed**

Een overzicht van alle mogelijke edit events en de betekenis van de attributen onder het blokje <event> vindt u op deze pagina: https://api.basisregisters.staging-vlaanderen.be/v1/info/events?tags=edit.

**Welke huisnummers & busnummers worden aanvaard voor een nieuw adres?**

Als er een nieuw voorgesteld adres wordt ingevoerd dan moet het huisnummer en eventueel het busnummer aan bepaalde voorwaarden voldoen.

De regex die van toepassing is op het huisnummer is ^[1-9] ([0-9]{0,8}([A-H]|[K-N]|[P]|[R-T]|[V-Z]){0,1}|[0-9]{0,9})$. Dit wilt zeggen dat huisnummers 45, 2C of 7563M zullen aanvaard worden, maar huisnummers 045, 2I, 5BIS of 4a niet aanvaard zullen worden.

De regex die van toepassing is op het busnummer is ^[a-zA-Z0-9]{1,10}$. Bovenop deze regex wordt het woord bus, Bus of BUS ook niet aanvaard. Dit wilt zeggen dat busnummers 1, 001 of 5C aanvaard zullen worden, maar busnummers 0, Bus 1 of 1-A niet aanvaard zullen worden.

**Welke combinaties zijn mogelijk bij adrespositie?**

In de edit endpoints ‘Stel een adres voor’ en ‘Corrigeer de adrespositie van een adres’ zijn de parameters positieGeometrieMethode, positieSpecificatie en positie verplicht. 

De parameter positieGeometrieMethode kan de waarde aangeduidDoorBeheerder of afgeleidVanObjrect bevatten. Wanneer positieGeometrieMethode aangeduidDoorBeheerder wordt gekozen dan zijn volgende waarden mogelijk bij de parameter positieSpecificatie:
* Lot
* Perceel
* Ingang
* Standplaats
* Ligplaats
* Gebouweenheid

Wanneer positieGeometrieMethode afgeleidVanObject wordt gekozen dan zijn volgende waarden mogelijk bij de parameter positieSpecificatie:
* Perceel
* Gebouweenheid

**Functie van een gebouweenheid: nietGekend of gemeenschappelijkDeel**

Een gebouweenheid kan 2 functies hebben: nietGekend of gemeenschappelijkDeel. In de toekomst zal deze lijst met mogelijke waarden uitgebreid worden.

Wanneer er een gebouweenheid wordt ingepland, is het enkel mogelijk om een ‘nietGekend’ als functie mee te geven. De functie ‘gemeenschappelijkDeel’ wordt automatisch toegekend van zodra er 2 ‘nietGekend’ ‘gepland/gerealiseerde’ gebouweenheden gekoppeld zijn aan het gebouw.

**Wat is het verschil tussen een correctie en een wijziging?**

Er wordt een onderscheid gemaakt tussen correcties en wijzigingen. In het eerste geval gaat het om een rechtzetting van een fout (vb. ‘Van Eikstraat’ moet zijn ‘Van Eyckstraat’), in het tweede geval gaat het om een verandering in administratieve toestand (vb. gebouw veranderd van status ‘inAanbouw’ naar ‘inGebruik’).

vb. Het wijzigen of corrigeren van de postcode van een adres.

Hiervoor zijn 2 aparte API’s gemaakt. De API ‘Corrigeer de postcode van een adres’ mag door elke decentrale beheerder uitgevoerd worden. Dit wordt uitgevoerd als de verkeerde postinfoID van een gemeente aan het adres is gekoppeld. Deze correctie kan alleen maar naar postinfoId’s worden gezet gekoppeld aan deze gemeente. De API ‘Wijzig de postcode van een adres’ is voor interne bijwerkers en wordt bijvooorbeeld op vraag van Bpost uitgevoerd. Bpost wilt dat postbodes een zo optimaal mogelijke route afleggen om deze reden kan het zijn dat adressen van bepaalde gemeenten een andere postinfoId krijgen dan deze die in de gemeente liggen. Deze API laat dit toe, vandaar dat dit niet door iedereen mogelijk is om uit te voeren. 

**Flow statussen**  
 
Straatnamen
  
![image](https://user-images.githubusercontent.com/49196256/197489328-2bfea6b1-4f23-4ab2-ab1e-9f7d7c31ffc6.png)
 
Adressen
 
![image](https://user-images.githubusercontent.com/49196256/197489432-41f09dff-4dda-4ca3-86ab-348245b64169.png)

Gebouwen
  
![image](https://user-images.githubusercontent.com/49196256/197179935-69c2b201-4c0b-4e58-b01d-a3da77939fbc.png)

Gebouweenheden
  
![image](https://user-images.githubusercontent.com/49196256/197179965-0ba75a23-0ee1-42b7-86ad-3e04ab34f890.png)
 
 Percelen
 
 ![image](https://user-images.githubusercontent.com/49196256/211315191-f58977a6-66e2-4cc8-86f9-8139da3b4299.png)

