## Overzicht pagina
* [Meldingsmodel](#meldingsmodel)
* [Meldingsobjectmodel](#meldingsobjectmodel)
* [Dataseteigenschappen van het gebouwen- en adressenregister](#dataseteigenschappen)
* [Levensloop van een melding](#levensloop)
* [Authenticatie](#authenticatie)
* [Authorisatie](#authorisatie)
* [Meer technische documentatie](#technischedoc)
* [Uw applicatie aansluiten](#aansluiten)

## Meldingsmodel {#meldingsmodel}

## Meldingsobjectmodel {#meldingsobjectmodel}

## Dataseteigenschappen van het gebouwen- en adressenregister {#dataseteigenschappen}

Bij het aanmaken van een gebouwen- en adressenregister terugmelding, dient de melder exact één meldingsobject toe te voegen. Via het meldingstype duidt de melder aan of gaat om een fout of een onvolledigheid. De lijst van meldingstypes kan u [hier](https://prod.api.melding.vlaanderen.be/api/v1/meldingstypes) terugvinden. Voor terugmelding voor het gebouwen- en adressenregister dient u steeds meldingstype Fout te gebruiken.

De dataseteigenschappen beschreven in de gebouwen- en adressenregister dataset vindt u hieronder terug. De volledige datasetbeschrijving voor het gebouwen- en adressenregister vindt u [hier](https://prod.api.melding.vlaanderen.be/api/v1/datasets/GRAR) terug.

### Oorzaak
- Dit is verplicht.
- De reden waarom u een meldingsobject aanmaakt:
|Reden|Betekenis|
|:---:|:---:|
| Nieuw / Ontbrekend |Er is een nieuw gebouwen- en adressenregisterobject ontstaan.   |
| Attribuut gewijzigd / foutief | Er is iets gewijzigd aan de codering of attributen dat impact heeft op de opname in het gebouwen- en adressenregister. |
|Geometrie gewijzigd / foutief  | Er is iets gewijzigd aan de geometrie dat impact heeft op de opname in het gebouwen- en adressenregister. |
|Attribuut & geometrie gewijzigd / foutief  | Er is iets gewijzigd aan de codering, attributen of geometrie dat impact heeft op de opname in het gebouwen- en adressenregister. |
|Verwijderd / Overbodig  | Er is iets verdwenen.|

### Thema
- Dit is verplicht.
- De entiteit waar de ‘Oorzaak’ impact op heeft. De thema’s zijn:
 - Adressen
 - Straatnamen
 - Gebouweenheden

### OVO-code
- Dit is verplicht.
- De OVO-code van de stad of gemeente waarvoor de terugmelding is bestemd. Een codelijst wordt voorzien met daarin de OVO-codes van de steden en gemeenten in Vlaanderen.

## Levensloop van een melding {#levensloop}

## Authenticatie {#authenticatie}
De GTMF endpoints zijn beveiligd via ACM/IDM:
- Indien u zich als gebruiker wenst te authenticeren, kan u de [Namens een gebruiker](#namensgebruiker) flow volgen. 
- Wenst u meldingen aan te maken en/of op te volgen via een achtergrond proces, dan kan u terugvallen op de [Server-naar-server](#servernaarserver) flow.
 
### Flow 'Namens een gebruiker' {#namensgebruiker}
In het geval dat u zich als gebruiker wenst te authenticeren, dan zal u terugvallen op token exchange. Meer informatie over token exchange kan u terugvinden in de documentatie van ACM/IDM. Hieronder vindt u alvast twee interessante links.
- https://authenticatie.vlaanderen.be/docs/beveiligen-van-api/oauth-rest/rest-namens-gebruiker/. 
- https://authenticatie.vlaanderen.be/docs/beveiligen-van-toepassingen/integratie-methoden/oidc/technische-info/client-authenticatie/. 

### Flow 'Server-naar-server' {#servernaarserver}
In het geval dat u zich als achtergrond proces wenst te authenticeren, dan zal u terugvallen op de Client Credentials Grant of CCG. Meer informatie over CCG kan u terugvinden in de documentatie van ACM/IDM. Hieronder vindt u alvast een link:
- https://authenticatie.vlaanderen.be/docs/beveiligen-van-api/oauth-rest/rest-server2server/.

## Authorisatie {#authorisatie}

Eens geauthenticeerd, zal het GTMF endpoint bepalen welke informatie u mag zien en welke acties u mag nemen. Deze logica is gebaseerd op de scopes aanwezig in het access token. De relevante scopes zijn:

|Scopes|Betekenis|
|:---:|:---:|
| Medewerker | U hebt het recht een terugmelding aan te maken. De API zal in dit geval ook de OVO-code en/of KBO-nummer scopes uitlezen om uw organisatie te bepalen.   |
| GTMF_Beh_GRAR_OVOCODE | Deze scope zal worden toegekend aan behandelende stad- en gemeentemedewerkers. Dit recht staat een medewerker toe om op te treden als behandelaar van een melding. Ook hier zal de API de OVO-code en/of KBO-nummer scopes uitlezen zodat u enkel de meldingen te zien krijgt die bestemd zijn voor uw organisatie. |
|GTMF_Bro_GRAR_Alle  | Dit recht zal worden toegekend aan de bronhouder. In dit geval medewerkers van de Basisregisters binnen Digitaal Vlaanderen. |

><font size="5">Indien u gebruik maakt van token exchange, zal u ook steeds onderstaande scopes dienen te bevragen.
>- vo_ovocode
>- vo_kbonummer  </font>


## Meer technische documentatie {#technischedoc}

Meer technische details kan u vinden op de swagger documentatie van de GTMF API:
- **Bèta omgeving:** https://beta.api.melding.dev-vlaanderen.be/swagger/index.html.
- **Productie omgeving:** https://prod.api.melding.vlaanderen.be/swagger/index.html.

Een lijst van foutcodes die kunnen voorkomen in de API is [hier](https://prod.api.melding.vlaanderen.be/Documentatie/ErrorCodesPagina) te vinden.

## Uw applicatie aansluiten {#aansluiten}

De endpoints voor het registreren van een terugmelding zijn beveiligd via ACM/IDM, zie ook meer informatie bij de secties ‘[Authenticatie](#authenticatie)’ en ‘[Authorisatie](#authorisatie)’.

Het GTMF team kent per aansluitende applicatie een uniek Id toe voor de meldingsapplicatie en meldingsorganisatie. Wenst u via uw eigen applicatie meldingen aan te maken voor het gebouwen- en adressenregister, gelieve dan contact op te nemen via digitaal.vlaanderen@vlaanderen.be met als onderwerp ‘Meldingen aanmaken voor het gebouwen- en adressenregister via mijn eigen applicatie'. 
