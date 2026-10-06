# pseudonymizeAllowCreate - v2026.2.0

 ![](assets/images/Design-Logo-THS-deutsch-271-padding.png) 

 
 2026.2.0 - ci-build  

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **pseudonymizeAllowCreate**

## OperationDefinition: pseudonymizeAllowCreate 

| | |
| :--- | :--- |
| *Official URL*:https://ths-greifswald.de/fhir/OperationDefinition/gpas/pseudonymizeAllowCreate | *Version*:2026.2.0 |
| Active as of 2025-06-12 | *Computable Name*:PseudonymizeAllowCreate |

 
Generierung je eines Pseudonyms für eine Liste von Originalwerten und eine spezifische Domäne sofern es noch nicht vorhanden ist. Sofern die Zuordnung Originalwert und Domäne bereits bekannt ist, wird das zugeordnete vorhandene Pseudonym zurückgegeben. 

**Unterstützt ab TTP-FHIR Gateway Version 1.0.0**

### Suche und ggf. Erzeugung von Pseudonymen

Generierung **je eines** Pseudonyms für **eine Liste von 1-n Originalwerten** und eine spezifische Domäne sofern es noch nicht vorhanden ist. Sofern die Zuordnung Originalwert und Domäne bereits bekannt ist, wird das zugeordnete vorhandene Pseudonym zurückgegeben.

### Voraussetzung

Die angegebene Pseudonym-Domäne muss in gPAS konfiguriert sein.

### Hinweise

### Aufruf und Rückgabe

Die bereitgestellte Funktionalität kann per POST-Request aufgerufen werden. Die erforderlichen Angaben werden per POST-BODY in Form von [FHIR Parameters](https://www.hl7.org/fhir/parameters.html) übermittelt.

`<HOST>:<PORT>/ttp-fhir/fhir/gpas/$pseudonymizeAllowCreate`

Der Funktionsaufruf liefert ein ParameterSet bestehend aus multiplen benannten Parametern zurück:

1. target = die genutzte Ziel-Domäne (Teil des Requests)
1. original = der zu pseudonymisierende Werte (Teil des Requests)
1. pseudonym = das erzeugte Pseudonym.

Im Erfolgsfall wird der HTTP Statuscode 200 zurückgegeben.

Im Fehlerfall wird einer der folgenden HTTP Statuscodes in Verbindung mit einer OperationOutcome-Ressource zurückgegeben:

* 400: Fehlende oder fehlerhafte Parameter.
* 401: Fehlende Authentifizierung oder Autorisierung.
* 404: Parameter mit unbekanntem Inhalt.
* 422: Fehlende oder falsche Patienten-Attribute.

### Beispiel

* [Request-Body](Parameters-Parameters-PseudonymizeAllowCreate-request-example-1.md)
* [Rückmeldung](Parameters-Parameters-PseudonymizeAllowCreate-response-example-1.md)



## Resource Content

```json
{
  "resourceType" : "OperationDefinition",
  "id" : "PseudonymizeAllowCreate",
  "url" : "https://ths-greifswald.de/fhir/OperationDefinition/gpas/pseudonymizeAllowCreate",
  "version" : "2026.2.0",
  "name" : "PseudonymizeAllowCreate",
  "title" : "pseudonymizeAllowCreate",
  "status" : "active",
  "kind" : "operation",
  "date" : "2025-06-12",
  "publisher" : "Unabhängige Treuhandstelle der Universitätsmedizin Greifswald",
  "contact" : [{
    "name" : "Unabhängige Treuhandstelle der Universitätsmedizin Greifswald",
    "telecom" : [{
      "system" : "url",
      "value" : "https://www.ths-greifswald.de/"
    }]
  }],
  "description" : "Generierung je eines Pseudonyms für eine Liste von Originalwerten und eine spezifische Domäne sofern es noch nicht vorhanden ist. Sofern die Zuordnung Originalwert und Domäne bereits bekannt ist, wird das zugeordnete vorhandene Pseudonym zurückgegeben.",
  "affectsState" : true,
  "code" : "pseudonymizeAllowCreate",
  "comment" : "Generierung je eines Pseudonyms für eine Liste von 1-n Originalwerten und eine spezifische Domäne sofern es noch nicht vorhanden ist. Sofern die Zuordnung Originalwert und Domäne bereits bekannt ist, wird das zugeordnete vorhandene Pseudonym zurückgegeben.",
  "system" : true,
  "type" : false,
  "instance" : false,
  "parameter" : [{
    "name" : "target",
    "use" : "in",
    "min" : 1,
    "max" : "1",
    "documentation" : "Angabe der Domäne auf Basis derer für den angegebenen Originalwert ein vorhandenens eindeutiges Pseudonym gesucht wird",
    "type" : "string",
    "searchType" : "string"
  },
  {
    "name" : "original",
    "use" : "in",
    "min" : 1,
    "max" : "*",
    "documentation" : "Angabe der Originalwerte auf Basis derer in der zusätzlich angegebenen Domäne eindeutige Pseudonym gesucht und sofern noch nicht vorhanden erzeugt werden",
    "type" : "string",
    "searchType" : "string"
  },
  {
    "name" : "pseudonym",
    "use" : "out",
    "min" : 0,
    "max" : "*",
    "documentation" : "Ermitteltes bzw. generiertes studien- und standort-spezifisches Pseudonym",
    "part" : [{
      "name" : "original",
      "use" : "out",
      "min" : 1,
      "max" : "1",
      "documentation" : "Original-Identifikator",
      "type" : "Identifier"
    },
    {
      "name" : "target",
      "use" : "out",
      "min" : 1,
      "max" : "1",
      "documentation" : "Target-Identifikator",
      "type" : "Identifier"
    },
    {
      "name" : "pseudonym",
      "use" : "out",
      "min" : 1,
      "max" : "1",
      "documentation" : "Pseudonym",
      "type" : "Identifier"
    }]
  },
  {
    "name" : "error",
    "use" : "out",
    "min" : 0,
    "max" : "*",
    "documentation" : "Fehlerrückgabe bei Teil-Fehlern",
    "part" : [{
      "name" : "target",
      "use" : "out",
      "min" : 0,
      "max" : "1",
      "documentation" : "Target-Identifikator",
      "type" : "Identifier"
    },
    {
      "name" : "original",
      "use" : "out",
      "min" : 0,
      "max" : "1",
      "documentation" : "Original-Identifikator",
      "type" : "Identifier"
    },
    {
      "name" : "error-code",
      "use" : "out",
      "min" : 1,
      "max" : "1",
      "documentation" : "Fehlercode",
      "type" : "Coding"
    }]
  }]
}

```
