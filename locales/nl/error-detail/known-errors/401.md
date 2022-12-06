## Wat is een 401 error?
Een "401 Unauthorized Error" betreft een "HTTP response status code" welke aangeeft dat de verstuurde aanvraag door de aanvrager niet geauthenticeerd of geverifieerd kon worden.

Wil je weten wat een HTTP response status code inhoud? Kijk dan gauw in het volgende artikel genaamd Wat is een HTTP response status code?.

Bij een 401 melding kon de server niet bevestigen dat je geautoriseerd bent voor toegang naar het opgevraagde bestand of adres. Het is mogelijk  (bijv. verkeerde wachtwoord) verstrekt, of uw browser begrijpt niet hoe de verplichte gegevens verstrekt moeten worden. De 401 status code lijkt op een 403 status code, maar zijn toch weer verschillend. 

### Client-side of server-side?
De betreffende status code 401 valt in de categorie voor "client error responses", oftewel foutmeldingen die kunnen voorkomen aan de kant van de eind gebruiker. Dit betekent niet gelijk dat er een probleem is aan de client side, maar houd het simpelweg in dat er geen toegang verleend kan/mag worden.

### Oorzaak 
De oorzaak van een 401 status code kan een van de volgende punten zijn:

- De aanvrager heeft netjes de authenticatie ingevuld echter heeft de server deze authenticatie poging afgewezen wegens mogelijke foutieve authenticatie gegevens
- De aanvrager heeft geen geen gegevens doorgegeven voor het authenticeren van de aanvraag.
- De aanvrager is verbannen van de omgeving en zal ook geen mogelijkheid hebben om zichzelf te kunnen authenticeren. 

Het verbannen van een aanvrager voor de betreffende locatie kan worden gedaan door het ip adres van de aanvrager te blokkeren. 

### Oplossen

...
