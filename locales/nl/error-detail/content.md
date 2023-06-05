De basisregisters endpoints gebruiken Problem Details for HTTP APIs (RFC7807) om foutmeldingen te ontsluiten. De meerderheid van de foutmeldingen zal resulteren in volgende datastructuur:

```
{
  "type": "string",
  "title": "string",
  "detail": "string",
  "status": integer,
  "instance": "string"
}
```

Uitzonderingen op deze structuur zijn error 304, error 400 en error 406.

## Overzicht foutmeldingen

Binnen de aangeboden endpoints zijn er een aantal foutmeldingen die kunnen voorkomen. Hieronder is er een overzicht van mogelijke foutmeldingen. Er kan naar elke foutmelding gegaan worden, om meer te weten te komen wanneer deze foutmelding zal plaatsvinden. 
