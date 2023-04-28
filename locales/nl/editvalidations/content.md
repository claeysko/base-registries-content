Op deze pagina vindt u een overzicht van alle geldende validaties per edit API.

## Straatnamen

#### Stel een straatnaam voor 

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Straatnaam leeg of null meegegeven|Error 400 |StraatnaamNietLeegValidatie|Straatnaam in '<taal>' kan niet leeg zijn.| 
|Meegegeven straatnaam > 60 tekens|Error 400 |StraatnaamMaxlengteValidatie|Maximum lengte van een straatnaam in '<taal>' is 60          tekens. U heeft momenteel <aantaltekens> tekens.| 
|Niet Vlaamse gemeente meegegeven|Error 400 |StraatnaamVlaamsGewestValidatie|De gemeente '<gemeenteId>' is geen Vlaamse gemeente.|
|Onbestaande gemeente meegegeven|Error 400 |StraatnaamGemeenteNietGekendValidatie|De gemeente '<gemeenteId>' is niet gekend in het gemeenteregister. |
|Het veld gemeenteId niet meegegeven/het veld straatnamen niet meegegeven/onbestaande taal meegegeven|Error 400 |JsonInvalid| Json is not valid.|
|Straatnaam bestaat reeds in de gemeente|Ticketing error |StraatnaamBestaatReedsInGemeente|Straatnaam '<straatnaam>' bestaat reeds in de gemeente.|
|De meegegeven taal is geen officiële of faciliteitentaal van de gemeente|Ticketing error |StraatnaamTaalNietInOfficieleOfFaciliteitenTaal|'Straatnamen' kunnen enkel voorkomen in de officiële of   faciliteitentaal van de gemeente.|
|Er ontbreekt een officiële- of faciliteitentaal|Ticketing error |StraatnaamOntbreektOfficieleOfFaciliteitenTaal|In 'Straatnamen' ontbreekt een officiële of faciliteitentaal. |
|Gehistoreerde Vlaamse gemeente meegegeven|Ticketing error |StraatnaamGemeenteVoorgesteldOfInGebruik|Deze actie is enkel toegestaan binnen gemeenten met       status 'voorgesteld' of 'inGebruik'.|
  
#### Keur een straatnaam goed 

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig straatnaamId meegegeven   |Error 400  |/ |De waarde 'straatnaamId' is ongeldig.  |
|Onbestaand straatnaamId meegegeven  |Error 404 |/  |/  |
|Status straatnaamId gehistoreerd/afgekeurd|Ticketing error|StraatnaamGehistoreerdOfAfgekeurd| Deze actie is enkel toegestaan op straatnamen met status 'voorgesteld' . |
|Verwijderd straatnaamId meegegeven |Ticketing error |VerwijderdeStraatnaam  |Verwijderde straatnaam.  |

 #### Keur een straatnaam af 

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig straatnaamId meegegeven   |Error 400  |/ |De waarde 'straatnaamId' is ongeldig.  |
|Onbestaand straatnaamId meegegeven  |Error 404 |/  |/  |
|Status straatnaamId gehistoreerd/inGebruik|Ticketing error|StraatnaamInGebruikOfGehistoreerd| Deze actie is enkel toegestaan op straatnamen met status 'voorgesteld'. |
|Verwijderd straatnaamId meegegeven |Ticketing error |VerwijderdeStraatnaam  |Verwijderde straatnaam.  |
  
#### Hef een straatnaam op 

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig straatnaamId meegegeven   |Error 400  |/ |De waarde 'straatnaamId' is ongeldig.  |
|Onbestaand straatnaamId meegegeven  |Error 404 |/  |/  |
|Status straatnaamId voorgesteld/afgekeurd|Ticketing error|StraatnaamVoorgesteldOfAfgekeurd| Deze actie is enkel toegestaan op straatnamen met status 'inGebruik'. |
|Verwijderd straatnaamId meegegeven |Ticketing error |VerwijderdeStraatnaam  |Verwijderde straatnaam.  |
  
#### Corrigeer de goedkeuring van een straatnaam 

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig straatnaamId meegegeven   |Error 400  |/ |De waarde 'straatnaamId' is ongeldig.  |
|Onbestaand straatnaamId meegegeven  |Error 404 |/  |/  |
|Status straatnaamId gehistoreerd/inGebruik|Ticketing error|StraatnaamInGebruikOfGehistoreerd| Deze actie is enkel toegestaan op straatnamen met status 'inGebruik'. |
|Verwijderd straatnaamId meegegeven |Ticketing error |VerwijderdeStraatnaam  |Verwijderde straatnaam.  |
  
#### Corrigeer de afkeuring van een straatnaam 

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig straatnaamId meegegeven   |Error 400  |/ |De waarde 'straatnaamId' is ongeldig.  |
|Onbestaand straatnaamId meegegeven  |Error 404 |/  |/  |
|Status straatnaamId gehistoreerd/inGebruik|Ticketing error|StraatnaamInGebruikOfGehistoreerd| Deze actie is enkel toegestaan op straatnamen met status 'afgekeurd'. |
|Straatnaam bestaat in gemeente met status voorgesteld/inGebruik |Ticketing error |StraatnaamBestaatReedsInGemeente  |Straatnaam 'straatnaam' bestaat reeds in de gemeente. |
|Verwijderd straatnaamId meegegeven |Ticketing error |VerwijderdeStraatnaam  |Verwijderde straatnaam.  |
  
#### Corrigeer de opheffing van een straatnaam 

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig straatnaamId meegegeven   |Error 400  |/ |De waarde 'straatnaamId' is ongeldig.  |
|Onbestaand straatnaamId meegegeven  |Error 404 |/  |/  |
|Status straatnaamId voorgesteld/afgekeurd|Ticketing error|StraatnaamVoorgesteldOfAfgekeurd| Deze actie is enkel toegestaan op straatnamen met status 'gehistoreerd'. |
|Straatnaam bestaat in gemeente met status voorgesteld/inGebruik |Ticketing error |StraatnaamBestaatReedsInGemeente  |Straatnaam 'straatnaam' bestaat reeds in de gemeente. |
|Straatnaam in gemeente met status gehistoreerd |Ticketing error |StraatnaamGemeenteInGebruik  |Deze actie is enkel toegestaan binnen gemeenten met       status 'inGebruik'. |
|Verwijderd straatnaamId meegegeven |Ticketing error |VerwijderdeStraatnaam  |Verwijderde straatnaam.  |
  
 #### Verwijder een straatnaam

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig straatnaamId meegegeven   |Error 400  |/ |De waarde 'straatnaamId' is ongeldig.  |
|Onbestaand straatnaamId meegegeven  |Error 404 |/  |/  |
  
#### Corrigeer de straatnaam van een straatnaam 

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig straatnaamId meegegeven   |Error 400  |/ |De waarde 'straatnaamId' is ongeldig.  |
|Het veld straatnamen niet meegegeven/onbestaande taal meegegeven   |Error 400  |JsonInvalid |Json is not valid |
|Meegegeven straatnaam > 60 tekens |Error 400  |StraatnaamMaxlengteValidatie |De waarde 'straatnaamId' is ongeldig.  |
|Straatnaam leeg of null meegegeven   |Error 400  |StraatnaamNietLeegValidatie |De waarde 'straatnaamId' is ongeldig.  |
|Onbestaand straatnaamId meegegeven  |Error 404 |/  |/  |
|Status straatnaamId gehistoreerd/afgekeurd|Ticketing error|StraatnaamGehistoreerdOfAfgekeurd| Deze actie is enkel toegestaan op straatnamen met status 'voorgesteld' of 'inGebruik'. |
|Straatnaam bestaat in gemeente met status voorgesteld/inGebruik |Ticketing error |StraatnaamBestaatReedsInGemeente  |Straatnaam 'straatnaam' bestaat reeds in de gemeente. |
|De meegegeven taal is geen officiële of faciliteitentaal van de gemeente|Ticketing error |StraatnaamTaalNietInOfficieleOfFaciliteitenTaal|'Straatnamen' kunnen enkel voorkomen in de officiële of faciliteitentaal van de gemeente.|
|Verwijderd straatnaamId meegegeven |Ticketing error |VerwijderdeStraatnaam  |Verwijderde straatnaam.  |
  
 #### Corrigeer de homoniemtoevoeging van een straatnaam 

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig straatnaamId meegegeven   |Error 400  |/ |De waarde 'straatnaamId' is ongeldig.  |
|Het veld homoniemtoevoegingen niet meegegeven/onbestaande taal meegegeven   |Error 400  |JsonInvalid |Json is not valid |
|Meegegeven homoniemToevoeging > 20 tekens  |Error 400  |StraatnaamHomoniemToevoegingMaxlengteValidatie |Maximum lengte van een homoniemToevoeging in 'taal' is 20 tekens. U heeft momenteel <aantalTekens> tekens.  |
|Onbestaand straatnaamId meegegeven  |Error 404 |/  |/  |
|Status straatnaamId gehistoreerd/afgekeurd|Ticketing error|StraatnaamGehistoreerdOfAfgekeurd| Deze actie is enkel toegestaan op straatnamen met status 'voorgesteld' of 'inGebruik'. |
|Homoniemtoevoeging bestaat reeds in deze gemeente voor dezelfde straatnaam |Ticketing error |StraatnaamHomoniemToevoegingBestaatReedsInGemeente  |Binnen deze gemeente bestaat er reeds een straatnaam met status 'voorgesteld' of 'inGebruik' met dezelfde straatnaam en homoniemToevoeging.   |
|Geen homoniemtoevoeging voor bepaalde taal aanwezig |Ticketing error |StraatnaamHomoniemToevoeging  |Er kan geen homoniemToevoeging worden toegevoegd    voor taalcode 'taal'. |
|Verwijderd straatnaamId meegegeven |Ticketing error |VerwijderdeStraatnaam  |Verwijderde straatnaam.  |


## Adressen

![image](https://user-images.githubusercontent.com/49196256/230035405-5cc4461a-5d55-46fc-aa1c-3c03715b64c8.png)

![image](https://user-images.githubusercontent.com/49196256/230019084-52348ad6-32f3-4cce-91eb-1f89186f29b3.png)

![image](https://user-images.githubusercontent.com/49196256/230019118-27b12a19-30ee-451d-a2be-1a1df0a51aa2.png)

![image](https://user-images.githubusercontent.com/49196256/230019187-49da849f-5149-4d72-8239-b2686b3c4955.png)

![image](https://user-images.githubusercontent.com/49196256/234558775-c075fb2e-8c24-4469-b441-a958e8445193.png)

![image](https://user-images.githubusercontent.com/49196256/230021742-e8e162ed-7aed-4eea-bc18-54f4b824bda8.png)

![image](https://user-images.githubusercontent.com/49196256/230021787-256c8bc5-9420-46e8-be0a-56ea6a55f675.png)

![image](https://user-images.githubusercontent.com/49196256/230021831-abdf6aa9-2716-47b2-943d-6163b5c7d3d7.png)

![image](https://user-images.githubusercontent.com/49196256/230023592-e4f5936a-6de8-4948-a806-dcdbfc72dbb5.png)

![image](https://user-images.githubusercontent.com/49196256/230023688-b3aa4e31-3763-4fec-b0fd-5c0cf30a9b89.png)

![image](https://user-images.githubusercontent.com/49196256/230024850-b30397f7-6fff-4c22-887a-abc9a81bade6.png)

![image](https://user-images.githubusercontent.com/49196256/230025148-561c1cea-2239-4422-9445-97a616cf3279.png)

![image](https://user-images.githubusercontent.com/49196256/230024911-8812c8ac-2a66-46cd-addb-7c88828b25db.png)

![image](https://user-images.githubusercontent.com/49196256/230029836-da1538c7-fa3a-4209-a7eb-59de7178ecff.png)

![image](https://user-images.githubusercontent.com/49196256/230030336-5b2861b2-685b-4187-87cd-e945a5c858ea.png)

![image](https://user-images.githubusercontent.com/49196256/230033275-24372c0b-08c2-414e-b702-0f915e803312.png)

![image](https://user-images.githubusercontent.com/49196256/230033308-d14eca70-ae00-468d-bdc2-d399cfc0291b.png)

![image](https://user-images.githubusercontent.com/49196256/230034840-caacaeb6-83b4-4bf3-a499-183f37da02e9.png)


## Gebouwen

#### Plan een gebouw in 

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Parameter geometriePolygoon ontbreekt   |Error 400  |JsonInvalid  |Json is not valid.  |
|GeometriePolygoon leeg/niet correct meegegeven |Error 400 |GebouwPolygoonValidatie  |Ongeldig formaat geometriePolygoon. |

#### Plaats een gebouw in aanbouw

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouwId meegegeven   |Error 400  |/ |De waarde 'gebouwId' is ongeldig.  |
|Onbestaand gebouwId meegegeven  |Error 404 |/  |/  |
|Status gebouwId gerealiseerd/gehistoreerd/nietGerealiseerd|Ticketing error|GebouwGehistoreerdGerealiseerdOfNietGerealiseerd| Deze actie is enkel toegestaan op gebouwen met status 'gepland'. |
|Verwijderd gebouwId meegegeven |Ticketing error |VerwijderdGebouw  |Verwijderd gebouw.  |

#### Realiseer een gebouw

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouwId meegegeven   |Error 400  |/ |De waarde 'gebouwId' is ongeldig.  |
|Onbestaand gebouwId meegegeven  |Error 404 |/  |/  |
|Status gebouwId gepland/gehistoreerd/nietGerealiseerd|Ticketing error|GebouwGehistoreerdGeplandOfNietGerealiseerd
| Deze actie is enkel toegestaan op gebouwen met status 'inAanbouw'. |
|Verwijderd gebouwId meegegeven |Ticketing error |VerwijderdGebouw  |Verwijderd gebouw.  |
  
#### Realiseer een gebouw niet

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouwId meegegeven   |Error 400  |/ |De waarde 'gebouwId' is ongeldig.  |
|Onbestaand gebouwId meegegeven  |Error 404 |/  |/  |
|Status gebouwId gerealiseerd/gehistoreerd|Ticketing error|GebouwGehistoreerdOfGerealiseerd| Deze actie is enkel toegestaan op gebouwen met status 'gepland' of ‘inAanbouw’.  |
|Verwijderd gebouwId meegegeven |Ticketing error |VerwijderdGebouw  |Verwijderd gebouw.  |
  
 #### Verwijder een geschetst gebouw

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouwId meegegeven   |Error 400  |/ |De waarde 'gebouwId' is ongeldig.  |
|Onbestaand gebouwId meegegeven  |Error 404 |/  |/  |
|GeometrieMethode = ingemetenGRB|Ticketing error|GebouwGeometrieMethodeIngemetenGRB| Deze actie is enkel toegestaan op gebouwen met geometrieMethode 'ingeschetst'.|
  
#### Corrigeer de realisering van een gebouw

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouwId meegegeven   |Error 400  |/ |De waarde 'gebouwId' is ongeldig.  |
|Onbestaand gebouwId meegegeven  |Error 404 |/  |/  |
|Status gebouwId gepland/gehistoreerd/nietGerealiseerd|Ticketing error|GebouwGeplandGehistoreerdOfNietGerealiseerd | Deze actie is enkel toegestaan op gebouwen met status 'gerealiseerd'.  |
|GeometrieMethode = ingemetenGRB|Ticketing error|GebouwGeometrieMethodeIngemetenGRB| Deze actie is enkel toegestaan op gebouwen met geometrieMethode 'ingeschetst'.|
|Gebouw heeft gekoppelde gehistoreerde gebouweenheden|Ticketing error|GebouwBevatGehistoreerdeGebouweenheden| Deze actie is niet toegestaan wanneer er            gehistoreerde gebouweenheden aanwezig zijn.|
|Verwijderd gebouwId meegegeven |Ticketing error |VerwijderdGebouw  |Verwijderd gebouw.  |
 
#### Corrigeer de niet realisering van een gebouw

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouwId meegegeven   |Error 400  |/ |De waarde 'gebouwId' is ongeldig.  |
|Onbestaand gebouwId meegegeven  |Error 404 |/  |/  |
|Status gebouwId inAanbouw/gehistoreerd/gerealiseerd|Ticketing error|GebouwInAanbouwGerealiseerdOfGehistoreerd | Deze actie is enkel toegestaan op geschetste    gebouwen met status 'nietGerealiseerd’. |
|GeometrieMethode = ingemetenGRB|Ticketing error|GebouwGeometrieMethodeIngemetenGRB| Deze actie is enkel toegestaan op gebouwen met geometrieMethode 'ingeschetst'.|
|Verwijderd gebouwId meegegeven |Ticketing error |VerwijderdGebouw  |Verwijderd gebouw.  |

#### Corrigeer de in aanbouw plaatsing van een gebouw

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouwId meegegeven   |Error 400  |/ |De waarde 'gebouwId' is ongeldig.  |
|Onbestaand gebouwId meegegeven  |Error 404 |/  |/  |
|Status gebouwId gerealiseerd/gehistoreerd/nietGerealiseerd|Ticketing error|GebouwGerealiseerdGehistoreerdOfNietGerealiseerd | Deze actie is enkel toegestaan op geschetste    gebouwen met status 'inAanbouw’. |
|Verwijderd gebouwId meegegeven |Ticketing error |VerwijderdGebouw  |Verwijderd gebouw.  |
  
#### Corrigeer de geometrie van een geschetst gebouw

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouwId meegegeven   |Error 400  |/ |De waarde 'gebouwId' is ongeldig.  |
|Onbestaand gebouwId meegegeven  |Error 404 |/  |/  |
|Status gebouwId gehistoreerd/gerealiseerd|Ticketing error|GebouwGehistoreerdOfNietGerealiseerd | Deze actie is enkel toegestaan op gebouwen met status 'gepland', 'inAanbouw' of 'gerealiseerd'. |
|GeometrieMethode = ingemetenGRB|Ticketing error|GebouwGeometrieMethodeIngemetenGRB| Deze actie is enkel toegestaan op gebouwen met geometrieMethode 'ingeschetst'.|
|Geometrie gekoppelde gebouweenheden ligt niet in nieuwe geometrie |Ticketing error|GebouweenheidGeomtrieBuitenGebouwGeometrie| Het gebouw heeft onderliggende gebouweenheden met status 'gepland' of 'gerealiseerd' buiten de nieuw geschetste gebouwgeometrie. |
|Verwijderd gebouwId meegegeven |Ticketing error |VerwijderdGebouw  |Verwijderd gebouw.  |


## Gebouweenheden
  
#### Realiseer een gebouweenheid

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouweenheidId meegegeven   |Error 400  |/ |De waarde 'gebouweenheidId' is ongeldig.  |
|Onbestaand gebouweenheidId meegegeven  |Error 404 |/  |/  |
|Gebouweenheid met functie gemeenschappelijkDeel meegegeven |Ticketing error |GebouweenheidGemeenschappelijkDeel  |Deze actie is niet toegestaan op gebouweenheden me functie gemeenschappelijkDeel.  |
|Gebouweenheid ligt in gebouw met status gepland/inAanbouw/gehistoreerd/nietGerealiseerd |Ticketing error |GebouwStatusNietInGerealiseerd  |Deze actie is enkel toegestaan binnen een gerealiseerd gebouw.  |
|Status gebouweenheidId gehistoreerd/nietGerealiseerd|Ticketing error|GebouweenheidGehistoreerdOfNietGerealiseerd
| Deze actie is enkel toegestaan op gebouweenheden met status 'gepland'. |
|Verwijderd gebouweenheidId meegegeven |Ticketing error |VerwijderdeGebouweenheid  |Verwijderde gebouweenheid.  |
  
#### Realiseer een gebouweenheid niet

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouweenheidId meegegeven   |Error 400  |/ |De waarde 'gebouweenheidId' is ongeldig.  |
|Onbestaand gebouweenheidId meegegeven  |Error 404 |/  |/  |
|Gebouweenheid met functie gemeenschappelijkDeel meegegeven |Ticketing error |GebouweenheidGemeenschappelijkDeel  |Deze actie is niet toegestaan op gebouweenheden me functie gemeenschappelijkDeel.  |
|Status gebouweenheidId gehistoreerd/gerealiseerd|Ticketing error|GebouweenheidGehistoreerdOfGerealiseerd
| Deze actie is enkel toegestaan op gebouweenheden met status 'gepland'. |
|Verwijderd gebouweenheidId meegegeven |Ticketing error |VerwijderdeGebouweenheid  |Verwijderde gebouweenheid.  |
  
#### Hef een gebouweenheid op

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouweenheidId meegegeven   |Error 400  |/ |De waarde 'gebouweenheidId' is ongeldig.  |
|Onbestaand gebouweenheidId meegegeven  |Error 404 |/  |/  |
|Gebouweenheid met functie gemeenschappelijkDeel meegegeven |Ticketing error |GebouweenheidGemeenschappelijkDeel  |Deze actie is niet toegestaan op gebouweenheden me functie gemeenschappelijkDeel.  |
|Gebouweenheid ligt in gebouw met status gehistoreerd/nietGerealiseerd |Ticketing error |GebouwStatusNietInGeplandInAanbouwOfGerealiseerd| Deze actie is enkel toegestaan binnen een gepland,                inAanbouw of gerealiseerd gebouw.  |
|Status gebouweenheidId gepland/nietGerealiseerd|Ticketing error|GebouweenheidGeplandOfNietGerealiseerd
| Deze actie is enkel toegestaan op gebouweenheden met status 'gerealiseerd'. |
|Verwijderd gebouweenheidId meegegeven |Ticketing error |VerwijderdeGebouweenheid  |Verwijderde gebouweenheid.  |

![image](https://user-images.githubusercontent.com/49196256/230095814-f3f83299-8f15-41f2-9aa3-c8150cbd8333.png)

![image](https://user-images.githubusercontent.com/49196256/230092242-3fa3e9f5-4779-40be-a586-7f46b555a1a6.png)

![image](https://user-images.githubusercontent.com/49196256/230092271-d6870725-cf76-44ae-a58e-f408bff82607.png)

![image](https://user-images.githubusercontent.com/49196256/230092313-1ad00f23-e828-4978-8e95-e2bad97c8f2e.png)

![image](https://user-images.githubusercontent.com/49196256/230092377-4ac7575f-c72a-4d32-852f-949e66677e27.png)

![image](https://user-images.githubusercontent.com/49196256/230093557-b29467b8-7365-4052-9b77-749ad40d9329.png)

![image](https://user-images.githubusercontent.com/49196256/230093653-2ad38c9a-c6b9-4d96-8ba9-364a9a75bba4.png)

![image](https://user-images.githubusercontent.com/49196256/230093690-d8bbba90-10b1-42c1-b00f-793178cc0af3.png)

![image](https://user-images.githubusercontent.com/49196256/230093718-a3e3ff5f-f640-45f1-80ef-b119c5907d3b.png)

![image](https://user-images.githubusercontent.com/49196256/230095076-117b84a8-dd71-4aea-abb4-c14467ea31e8.png)

#### Koppel een adres aan een gebouweenheid

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouweenheidId meegegeven   |Error 400  |/ |De waarde 'gebouweenheidId' is ongeldig.  |
|Het veld adresId niet meegegeven of met waarde leeg of null meegegeven|Error 400|JsonInvalid|Json is not valid.|
|Ongeldige waarde bij adresId / verwijderd adresId meegegeven |Error 400|GebouweenheidAdresOngeldig|Ongeldig adresId.|
|AdresId met status afgekeurd/gehistoreerd meegegeven|Error 400|GebouweenheidAdresAfgekeurdOfGehistoreerd|Het adres is afgekeurd of gehistoreerd.|
|Onbestaand gebouweenheidId meegegeven  |Error 404|/  |/  |
|Status gebouweenheidId gehistoreerd/nietGerealiseerd|Ticketing error|GebouweenheidNietGerealiseerdOfGehistoreerd|Deze actie is enkel toegestaan op percelen met status 'gepland' of 'gerealiseerd'.|
|Verwijderd gebouweenheidId meegegeven |Ticketing error|VerwijderdeGebouweenheid|Verwijderde gebouweenheid.|
  
#### Ontkoppel een adres van een gebouweenheid

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Ongeldig gebouweenheidId meegegeven   |Error 400  |/ |De waarde 'gebouweenheidId' is ongeldig.  |
|Het veld adresId niet meegegeven of met waarde leeg of null meegegeven|Error 400|JsonInvalid|Json is not valid.|
|Ongeldige waarde bij adresId / verwijderd adresId meegegeven |Error 400|GebouweenheidAdresOngeldig|Ongeldig adresId.|
|Onbestaand gebouweenheidId meegegeven  |Error 404|/  |/  |
|Verwijderd gebouweenheidId meegegeven |Ticketing error|VerwijderdeGebouweenheid|Verwijderde gebouweenheid.|
  
## Percelen

#### Koppel een adres van een perceel

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Het veld adresId niet meegegeven of met waarde leeg of null meegegeven   |Error 400  |JsonInvalid  |Json is not valid.  |
|Ongeldige waarde bij adresId / verwijderd adresId meegegeven |Error 400 |PerceelAdresOngeldig  |Ongeldig adresId.  |
|AdresId met status afgekeurd/gehistoreerd meegegeven|Error 400|PerceelAdresAfgekeurdOfGehistoreerd |Het adres is afgekeurd of gehistoreerd.|
|Onbestaand perceelId meegegeven  |Error 404 |/  |/  |
|Status perceelId gehistoreerd|Ticketing error|PerceelGehistoreerd|Deze actie is enkel toegestaan op percelen met status 'gerealiseerd'.|
|Verwijderd perceelId meegegeven |Ticketing error |VerwijderdPerceel  |Verwijderd perceel.  |

#### Ontkoppel een adres van een perceel

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Het veld adresId niet meegegeven of met waarde leeg of null meegegeven|Error 400|JsonInvalid|Json is not valid.|
|Ongeldige waarde bij adresId / verwijderd adresId meegegeven |Error 400|PerceelAdresOngeldig|Ongeldig adresId.|
|Onbestaand perceelId meegegeven  |Error 404|/  |/  |
|Verwijderd perceelId meegegeven |Ticketing error|VerwijderdPerceel|Verwijderd perceel.|
