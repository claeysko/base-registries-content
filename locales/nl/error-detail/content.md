De basisregisters endpoints gebruiken Problem Details for HTTP APIs (RFC7807) om foutmeldingen te ontsluiten. Een foutmelding zal resulteren in volgende datastructuur:

```
{{
  "type": "string",
  "title": "string",
  "detail": "string",
  "status": number,
  "instance": "string"
}}
```

## Overzicht foutmeldingen
Binnen de aangeboden endpoints zijn er een aantal foutmeldingen die kunnen voorkomen. U moet naar het veld ‘Detail’ kijken voor meer informatie.

| Foutmelding | Wanneer | 
|:-:|:-:|
| 401 | Wanneer er geen API key in de feed wordt meegegeven. | 
| 403 | Wanneer het formaat in de URL wordt meegegeven of wanneer u een API key meegeeft die niet correct is.| 
| 404 | Wanneer het objectid niet gevonden kan worden.| 
| 406 | Wanneer het verkeerde formaat wordt meegegeven in de accept header. | 
| 410 | Wanneer het objectid verwijderd is. | 
| 500 | Wanneer de response groter is dan 10MB of wanneer er een interne fout is gebeurd of wanneer de GRB WFS-service niet kan gecontacteerd worden.| 
