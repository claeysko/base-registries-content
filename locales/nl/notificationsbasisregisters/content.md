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

Iedere melding wordt aangemaakt voor een dataset. De dataset beschrijft het model waarbinnen de terugmelding voor een bepaalde databron moet passen. Deze beschrijving is in de vorm van dataseteigenschappen. De dataset beschrijft dus welke informatie kan en moet aanwezig zijn bij het aanmaken van een melding en in welke vorm (datatype). Verder bepaalt de dataset de levensloop van een melding en welke acties mogelijk zijn.

## Meldingsobjectmodel {#meldingsobjectmodel}

Een melding bestaat uit één of meerdere meldingsobjecten. Het zijn de meldingsobjecten die concrete informatie  omtrent de gemelde fout of onvolledigheid bevatten. Welke informatie een meldingsobject kan bevatten wordt beschreven in de dataset.

GTMF biedt een endpoint aan waarlangs de dataset kan worden opgevraagd. De dataset voor het gebouwen- en adressenregister vindt u [hier](https://prod.api.melding.vlaanderen.be/api/v1/datasets/GRAR) terug. 

**Belangrijk: Het gebouwen- en adressenregister houdt de granulariteit tussen een melding en een meldingsobject op één meldingsobject per melding.** 

Belangrijke velden per dataseteigenschap zijn:
|Velden|Betekenis|
|:---:|:---:|
| Id | Id van de dataseteigenschap door te geven bij het registreren van een terugmelding.  |
| Label | Leesbaar label van de dataseteigenschap voor weergave in meldingsfront. |
|Verplicht | Geeft aan of een dataseteigenschap verplicht moet meegegeven worden om een terugmelding voor de bron te kunnen registreren. |
|Meldbaar | Geeft aan of de melder een nieuwe waarde voor de dataseteigenschap kan voorstellen of de huidige waarde achterliggend aangevuld moet worden door de meldingsapplicatie. Meldingen voor de bron gebouwen- en adressenregister zal steeds een nieuwe waarde moeten worden meegegeven. Het is dan aan de behandelaar om het correcte object te selecteren (o.b.v. de meegegeven geometrie) en de melding te analyseren. |
|Datatype  | Datatype waaraan de waarde voor de dataseteigenschap moet voldoen. Hier kunnen ook codelijsten voorkomen.|

Naast specifieke dataseteigenschappen hebben een terugmelding en onderliggende meldingsobjecten generieke eigenschappen. Eigenschappen die ongeacht de databron waarvoor een terugmelding wordt gemaakt kunnen voorkomen. Voor de bron gebouwen- en adressenregister kan een meldingsobject volgende generieke eigenschappen hebben:
- **Geometrie:** geometrie horende bij het meldingsobject. De geometrie dient steeds een polygoon te zijn.
- **Url:** link naar een bijlage.

Op het niveau van de terugmelding kan een melder volgende meegeven:
|Velden|Betekenis|
|:---:|:---:|
| Referentie melder | 	Een eigen referentie waarmee de melder de terugmelding later makkelijker kan opzoeken of identificeren. |
| Samenvatting | 	Kan gebruikt worden om de terugmelding en de informatie die eraan gekoppeld is samen te vatten en de behandeling ervan te vergemakkelijken. |

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

- Bij het indienen van een terugmelding (status Ingediend) wordt de melding automatisch toegewezen aan een behandelaar (status Toegewezen). De toewijzing is steeds aan een stad of gemeente en verloopt via de waarde meegegeven in het OVO-code veld.
- Bij het behandelen plaatst de behandelaar de terugmelding in status In onderzoek. 
- Na het onderzoek, zal de behandelaar:
 - de melding sluiten (status Gesloten)
 - aanduiden als opgelost (status Opgelost) 
 - of afwijzen (status Afgewezen).

### Meldingen indienen {#meldingenindienen}
 
### Meldingen opvragen {#meldingenopvragen}

Wie wenst kan de status van zijn terugmelding en zijn meldingsobject(en) opvolgen in de eigen meldingsfront. GTMF biedt hier verschillende endpoints voor aan. Ook deze endpoints zijn beveiligd via ACM/IDM.

De meldingen die een gebruiker te zien krijgt zijn de volgende:
- U bent indiener van de melding.
- De melding werd ingediend door een medewerker van jouw organisatie.
- U bent behandelaar van de melding.
- U bent bronhouder van de dataset waartoe de melding behoort.

De mogelijke statussen van een meldingsobject zijn:
|Status|Betekenis|
|:---:|:---:|
| Toegewezen |Het meldingsobject is opgenomen en wordt door de behandelende stad of gemeente nagekeken en indien mogelijk opgelost..   |
| In onderzoek | Het meldingsobject is nog in behandeling door de stad of gemeente. |
|Afgewezen  |Het meldingsobject werd niet aanvaard OF niet opgelost. Indien opportuun, geven we de reden van afwijzing mee. |
|Opgelost | De meldingsopbject is opgelost door de stad of gemeente. |
|Gesloten  | Het meldingsobject kon niet behandeld worden en is gesloten. Het is mogelijk dat de situatie reeds werd opgelost of in de toekomst zal opgelost worden, omdat deze ook door een andere gebruiker/organisatie gemeld werd.|

De status van de melding wordt afgeleid van de statussen van de meldingsobjecten. De laagste meldingsobjectstatus is hier leidend.

Ophalen van een lijst van terugmeldingen kan via onderstaande URL's:
- Bèta omgeving: https://beta.api.melding.dev-vlaanderen.be/api/v2/meldingen
- Productie omgeving: https://prod.api.melding.vlaanderen.be/api/v2/meldingen

Ophalen detail van een terugmelding:
- Bèta omgeving: https://beta.api.melding.dev-vlaanderen.be/api/v2/meldingen/{id}
- Productie omgeving: https://prod.api.melding.vlaanderen.be/api/v2/meldingen/{id}

### Meldingen behandelen {#meldingenbehandelen}

Meldingsobjecten worden toegekend aan behandelende steden en gemeente. Indien een melding is toegekend aan uw organisatie en u beschikt over de rol behandelaar (zie sectie Authorisatie), dan kan u de terugmelding behandelen door deze van status te veranderen. Bij het wijzigen van de status kan u twee toelichtingen meegeven: één voor de indiener en één voor intern gebruik.

Om de status te wijzigen, kan u een POST request uitvoeren tegen endpoint `</api/v1/meldingen/{meldingId}/meldingsobjecten/{meldingsobjectId}/status/{statusCode}>`. De mogelijke waarden voor het onderdeel `<statusCode>` vindt u hieronder. Het is de numerieke waarde die u dient te gebruiken.
- In onderzoek: 2
- Afgewezen: 3
- Opgelost: 4
- Gesloten: 5

De toelichten dient u mee te geven in de request body, zie een voorbeeld hieronder.

`<{
  "toelichtingStatusWijzigingMelder": "Toelichting statuswijziging voor de melder."
  "toelichtingIntern": "Toelichting statuswijziging voor intern gebruik." 
}>`

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
