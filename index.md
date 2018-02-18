# Octowise® ContactAPI V2

Unsere ContactAPI ist ein JSON Webservice, bei welchem alle Abfragen über eine zentrale URL durchgeführt werden. Die API Abfrage erfolgt als POST Request, mit den zwei Pflichtfeldern api_key & contact_data.

## API URL

https://api.contactapi.de/v1.5/parse.php

## POST Felder

- api_key= Zur Nutzung der ContactAPI wird ein API-Key benötigt. Wenn du noch keinen API-Key besitzt, kannst du diesen hier kostenlos beantragen.
- contact_data Es kann jede Art von Text an die API übergeben werden. Um jedoch zu­frie­den­stel­lende Ergebnisse zu erhalten, solltest du unsere unten gesammelten Hinweise beachten.


## API Ausgabe

Bei einer erfolgreichen Abfrage erhältst du ein JSON Objekt mit dem status:1 sowie den gewünschten Daten als data von der API zurück. Sollte die Abfrage fehlschlagen, wird ein anderer Status Code sowie eine Fehlermeldung als error zurückgegeben.

```markdown
{
   "status":"1",
   "data":{
      "Prefix":null,
      "FirstName":"Peter",
      "MiddleName":null,
      "LastName":"Mustermann",
      "Suffix":null,
      "Company":null,
      "Company2":null,
      "Position":null,
      "StreetAddress1":"Musterweg 12",
      "StreetAddress2":null,
      "PostboxAddress":null,
      "PostboxPostCode":null,
      "PostCode":"123456",
      "PlaceName":"Berlin",
      "Province":null,
      "Country":"Deutschland",
      "Phone1":null,
      "Phone2":null,
      "Mobile":null,
      "Fax":null,
      "Email":"mail@example.com",
      "Url":null,
      "Gender":"M",
      "CountryIsoCode":"DE"
   }
}
```

## Abfrage Beispiele

```markdown
curl --data "api_key=DeinApiKey&contact_data=Peter Mustermann,Musterweg 12, 12356 Berlin, mail@example.com" https://api.contactapi.de/v1.5/parse.php
```
