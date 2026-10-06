# dePseudonymize - v2026.2.0

 ![](assets/images/Design-Logo-THS-deutsch-271-padding.png) 

 
 2026.2.0 - ci-build  

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **dePseudonymize**

## OperationDefinition: dePseudonymize 

| | |
| :--- | :--- |
| *Official URL*:https://ths-greifswald.de/fhir/OperationDefinition/gpas/dePseudonymize | *Version*:2026.2.0 |
| Active as of 2025-06-12 | *Computable Name*:DePseudonymize |

 
Abfrage je eines Originalwertes für eine Liste von 1-n Pseudonymen und eine spezifische Domäne. 

**Unterstützt ab TTP-FHIR Gateway Version 1.0.0**

### Suche von Originalwerten

Abfrage **je eines** Originalwertes für **eine Liste von 1-n Pseudonymen** und eine spezifische Domäne.

### Voraussetzung

Die angegebene Pseudonym-Domäne muss in gPAS konfiguriert und das angegebene Pseudonym in dieser Domäne bereits vorhanden sein.

### Hinweise

### Aufruf und Rückgabe

Die bereitgestellte Funktionalität kann per POST-Request aufgerufen werden. Die erforderlichen Angaben werden per POST-BODY in Form von [FHIR Parameters](https://www.hl7.org/fhir/parameters.html) übermittelt.

`<HOST>:<PORT>/ttp-fhir/fhir/gpas/$dePseudonymize`

Der Funktionsaufruf liefert ein ParameterSet bestehend aus multiplen benannten Parametern zurück:

1. target = die genutzte Ziel-Domäne (Teil des Requests)
1. pseudonym = das angefragte Pseudonym (Teil des Requests)
1. original = der ermittelte Originalwert

Im Erfolgsfall wird der HTTP Statuscode 200 zurückgegeben.

Im Fehlerfall wird einer der folgenden HTTP Statuscodes in Verbindung mit einer OperationOutcome-Ressource zurückgegeben:

* 400: Fehlende oder fehlerhafte Parameter.
* 401: Fehlende Authentifizierung oder Autorisierung.
* 404: Parameter mit unbekanntem Inhalt.
* 422: Fehlende oder falsche Patienten-Attribute.

Auftretende Fehler (z.B. angegebenes Pseudonym ist unbekannt) werden im Einzelnen entsprechend per Coding vom Typ [Issue-Type](http://hl7.org/fhir/issue-type) signalisiert.

### Beispiel

* [Request-Body](Parameters-Parameters-DePseudonymize-request-example-1.md)
* [Rückmeldung](Parameters-Parameters-DePseudonymize-response-example-1.md)
* [Fehler-Rückmeldung](Parameters-Parameters-DePseudonymize-response-example-2.md)



## Resource Content

```json
{
  "resourceType" : "OperationDefinition",
  "id" : "DePseudonymize",
  "url" : "https://ths-greifswald.de/fhir/OperationDefinition/gpas/dePseudonymize",
  "version" : "2026.2.0",
  "name" : "DePseudonymize",
  "title" : "dePseudonymize",
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
  "description" : "Abfrage je eines Originalwertes für eine Liste von 1-n Pseudonymen und eine spezifische Domäne.",
  "affectsState" : false,
  "code" : "dePseudonymize",
  "comment" : "Abfrage je eines Originalwertes für eine Liste von 1-n Pseudonymen und eine spezifische Domäne.",
  "system" : true,
  "type" : false,
  "instance" : false,
  "parameter" : [{
    "name" : "target",
    "use" : "in",
    "min" : 1,
    "max" : "1",
    "documentation" : "Angabe der Domäne auf Basis derer für das angegebene Pseudonym ein vorhandener eindeutiger Originalwert gesucht wird",
    "type" : "string",
    "searchType" : "string"
  },
  {
    "name" : "pseudonym",
    "use" : "in",
    "min" : 1,
    "max" : "*",
    "documentation" : "Angabe einer Liste von 1-n Pseudonymen für die in der angegebenen Domäne zugeordnete eindeutige Originalwerte gesucht werden",
    "type" : "string",
    "searchType" : "string"
  },
  {
    "name" : "original",
    "use" : "out",
    "min" : 0,
    "max" : "*",
    "documentation" : "Original-Identifikation zum übermittelten Pseudonym",
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
      "documentation" : "Patient-Identifier",
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
      "name" : "original",
      "use" : "out",
      "min" : 0,
      "max" : "1",
      "documentation" : "Original-Identifikator",
      "type" : "Identifier"
    },
    {
      "name" : "target",
      "use" : "out",
      "min" : 0,
      "max" : "1",
      "documentation" : "Target-Identifikator",
      "type" : "Identifier"
    },
    {
      "name" : "pseudonym",
      "use" : "out",
      "min" : 0,
      "max" : "1",
      "documentation" : "Patient-Identifikator",
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
