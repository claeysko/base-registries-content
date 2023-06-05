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
