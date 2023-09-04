## Wegsegmenten

### Koppel een straatnaam aan een wegsegment

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Veld linkerstraatnaam niet meegegeven en veld rechterstraatnaam niet meegegeven   |Error 400  |JsonInvalid  |Ongeldig JSON formaat.  |
|Wegsegment bestaat niet of werd verwijderd|Error 404 |/ |/ |
|Wegsegment heeft reeds linkerstraatnaam |Ticketing error |LinkerstraatnaamNietOntkoppeld |Het wegsegment heeft reeds een linkerstraatnaam. Gelieve deze eerst te ontkoppelen. |
|Wegsegment heeft reeds rechterstraatnaam |Ticketing error |RechterstraatnaamNietOntkoppeld |Het wegsegment heeft reeds een rechterstraatnaam. Gelieve deze eerst te ontkoppelen. |
|Linker- of rechterstraatnaam verwijderd of niet gekend |Ticketing error |StraatnaamNietGekend |De straatnaam is niet gekend in het Straatnamenregister.|
|Straatnaam afgekeurd of gehistoreerd |Ticketing error |WegsegmentStraatnaamNietVoorgesteldOfInGebruik |Deze actie is enkel toegelaten voor straatnamen met status 'voorgesteld' of 'in gebruik'. |

### Ontkoppel een straatnaam van een wegsegment

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Veld linkerstraatnaam niet meegegeven en veld rechterstraatnaam niet meegegeven   |Error 400  |JsonInvalid  |Ongeldig JSON formaat.  |
|Wegsegment bestaat niet of werd verwijderd|Error 404 |/ |/ |
|Opgegeven linkerstraatnaam is momenteel niet gekoppeld aan wegsegment |Ticketing error |LinkerstraatnaamNietGekoppeld |Het wegsegment is niet gekoppeld aan de linkerstraatnaam. |
|Opgegeven linkerstraatnaam is momenteel niet gekoppeld aan wegsegment |Ticketing error |LinkerstraatnaamNietGekoppeld |Het wegsegment is niet gekoppeld aan de linkerstraatnaam. |

### Schets een wegsegment

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Het veld middellijnGeometrie/ wegsegmentstatus/ morfologischeWegklasse/ toegangsbeperking/ wegbeheerder/ wegverharding/ wegbreedte/ aantalRijstroken/ aantal/ richting niet meegegeven |Error 400 |'veld'Verplicht |'veld' is verplicht. |
|Ongeldige geometrie |Error 400 |MiddellijnGeometrieNietCorrect |De opgegeven geometrie is geen geldige LineString in gml 3.2. |
|Ongeldige CRS |Error 400 |MiddellijnGeometrieCRSNietCorrect |De opgegeven geometrie heeft niet het coördinatenstelsel Lambert 72. |
|Geometrie <2m |Error 400 |MiddellijnGeometrieKorterDanMinimum |De opgegeven geometrie heeft niet de minimale lengte van 2 meter.|
|Ongeldige wegsegmentstatus |Error 400 |WegsegmentStatusNietCorrect |Wegsegment status is foutief. 'waarde' is geen geldige waarde. |
|Ongeldige morfologische wegklasse |Error 400 |MorfologischeWegklasseNietCorrect |Morfologische wegklasse is foutief. 'waarde' is geen geldige waarde. |
|Ongeldige toegangsbeperking |Error 400 |ToegangsbeperkingNietCorrect |Toegangsbeperking is foutief. 'waarde' is geen geldige waarde. |
|Ongeldige wegbeheerder |Error 400 |WegbeheerderNietCorrect |Wegbeheerder is foutief. 'waarde' is geen geldige waarde. |
|Ongeldig wegverhardingstype |Error 400 |WegverhardingNietCorrect | Wegverharding is foutief. 'waarde' is geen geldige waarde.|
|Ongeldige wegbreedte |Error 400 |WegbreedteNietCorrect |Wegbreedte is foutief. 'waarde' is geen geldige waarde. |
|Wegbreedte te groot |Error 400 |WegbreedteTeGroot | Wegbreedte mag niet groter dan 50 meter zijn.|
|Ongeldige richting bij aantal rijstroken |Error 400 |AantalRijstrokenRichtingNietCorrect |Aantal rijstroken richting is foutief. 'waarde' is geen geldige waarde. |
               
### Wijzig de geometrie van een ingeschetst wegsegment

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Het veld middellijnGeometrie niet meegegeven |Error 400 |MiddellijnGeometrieVerplicht |MiddellijnGeometrie is verplicht. |
|Ongeldige geometrie |Error 400 |MiddellijnGeometrieNietCorrect |De opgegeven geometrie is geen geldige LineString in gml 3.2. |
|Ongeldige CRS |Error 400 |MiddellijnGeometrieCRSNietCorrect |De opgegeven geometrie heeft niet het coördinatenstelsel Lambert 72. |
|Geometrie <2m |Error 400 |MiddellijnGeometrieKorterDanMinimum |De opgegeven geometrie heeft niet de minimale lengte van 2 meter.|
|Geometriemethode <> ingeschetst |Error 400 |GeometriemethodeNietIngeschetst |De geometriemethode van dit wegsegment komt niet overeen met 'ingeschetst'. |
|Wegsegment bestaat niet of werd verwijderd|Error 404 |/ |/ |
  
### Verwijder een ingeschetst wegsegment

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Geometriemethode <> ingeschetst |Error 400 |GeometriemethodeNietIngeschetst |De geometriemethode van dit wegsegment komt niet overeen met 'ingeschetst'. |
|Wegsegment bestaat niet of werd verwijderd|Error 404 |/ |/ |

### Wijzig een attribuutwaarde voor één of meerdere wegsegmenten

|Validatie|Soort error|ErrorCode|ErrorMessage|
|:---:|:---:|:---:|:---:|
|Wegsegment bestaat niet of werd verwijderd |Error 400 |NotFound |Onbestaande of verwijderde wegsegmenten gevonden 'waarde'.|
|Ongeldige wegbeheerder |Error 400 |WegbeheerderNietCorrect |Wegbeheerder is foutief. 'waarde' is geen geldige waarde. |
|Ongeldige wegsegmentstatus |Error 400 |WegsegmentStatusNietCorrect |Wegsegment status is foutief. 'waarde' is geen geldige waarde. |
|Ongeldige wegcategorie |Error 400 |WegcategorieNietCorrect |Wegcategorie is foutief. 'waarde' is geen geldige waarde. |
|Ongeldige toegangsbeperking |Error 400 |ToegangsbeperkingNietCorrect |Toegangsbeperking is foutief. 'waarde' is geen geldige waarde. |
|Ongeldige morfologische wegklasse |Error 400 |MorfologischeWegklasseNietCorrect |Morfologische wegklasse is foutief. 'waarde' is geen geldige waarde. |

