**Gebouwen- en adressenregister**

De read endpoints zijn anoniem raadpleegbaar. Er is echter een beperking aanwezig op het aantal verzoeken dat u tegelijkertijd kan versturen naar deze endpoints. Wanneer u een API key meegeeft dan zal u meer requests kunnen versturen.

Voor de feed endpoints is het verplicht om een API key mee te geven. Als u dit niet doet, krijgt u een errormelding 401 als response terug.

Om dus optimaal gebruik te maken van de endpoints vraagt u best een API key aan. Dit kan door uw gegevens in volgende link achter te laten: [Vraag hier uw API key aan.] [1]

U kan deze API key op 2 manieren meegeven:
* Via de header x-api-key.
* In de URL. Bijvoorbeeld: https://api.basisregisters.vlaanderen.be/v2/adressen?apikey={apikey} waarbij {apikey} vervangen wordt door de unieke code van uw API key.

[1]:https://dynamicforms.crmiv.vlaanderen.be/DynamicForms/Page/Show/CfDJ8M4Eu9v84l9JmW3p7WGylS-u2ToCLC5KvqQZmZ4G99X5TBULO4n0LCDpm7870eDUOk90hogqVcE7BCVQf2u_4WlsZ7B8friBrkyuAqmXYpIX_BzvQVVo8eUZyNd-njc33Y-Z-B87y03Y2Jgukp2AN5U93jT1Xv2l0afgvenLD9k0fasSMJkt4uNzKmlr_gILGrOy%2FJSqnRom_MLu0h7sALJ8uNvPywCMsZ1zy5Lal4h63?path=APIKey-aanvraag
