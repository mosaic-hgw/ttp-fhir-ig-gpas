# pseudonymize-secondary - v2026.2.0

 ![](assets/images/Design-Logo-THS-deutsch-271-padding.png) 

 
 2026.2.0 - ci-build  

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **pseudonymize-secondary**

## OperationDefinition: pseudonymize-secondary 

| | |
| :--- | :--- |
| *Official URL*:https://ths-greifswald.de/fhir/OperationDefinition/gpas/pseudonymize-secondary | *Version*:2026.2.0 |
| Active as of 2025-06-12 | *Computable Name*:PseudonymizeSecondary |

 
Erzeugung einer spezifischen Anzahl von Pseudonymen in einem vorhandenen Pseudonymisierungskontext bei gleichzeitiger Zuordnung zum übermittelten Originalwert. 

**Unterstützt ab TTP-FHIR Gateway Version 2025.1.0**

Erzeugung einer spezifischen Anzahl von Pseudonymen in einem vorhandenen Pseudonymisierungskontext bei gleichzeitiger Zuordnung zum übermittelten Originalwert

### Voraussetzung

* Der oder die erforderlichen Pseudonymisierungskontexte (target) wurden im Vorfeld bereits konfiguriert und sind vorhanden
* Die target-Domänen sind als "MultiPsn"-Domänen konfiguriert (mehrere Pseudonyme pro Originalwert innerhalb derselben Domäne gestattet)

### Hinweise

### Aufruf und Rückgabe

Die bereitgestellte Funktionalität kann per POST-Request aufgerufen werden. Die erforderlichen Angaben werden per POST-BODY in Form von [FHIR Parameters](https://www.hl7.org/fhir/parameters.html) übermittelt.

Je nach Werteangaben (target, count) erfolgt bei der Verarbeitung intern eine Gruppierung der angefragten Werte, um die Vorteile des Batch-Processing nutzen zu können. Einheitliche count- und target-Angaben führen zu besserer Performance.

`<HOST>:<PORT>/ttp-fhir/fhir/gpas/$pseudonymize-secondary`

Im Erfolgsfall wird der HTTP Statuscode 200 zurückgegeben.

Im Fehlerfall wird einer der folgenden HTTP Statuscodes in Verbindung mit einer OperationOutcome-Ressource zurückgegeben:

* 400: Fehlende oder fehlerhafte Parameter.
* 401: Fehlende Authentifizierung oder Autorisierung.
* 404: Parameter mit unbekanntem Inhalt.

### Beispiel

* [Request-Body](Parameters-Parameters-PseudonymizeSecondary-request-example-1.md)
* [Rückmeldung](Parameters-Parameters-PseudonymizeSecondary-response-example-1.md)
* [Fehler-Rückmeldung](Parameters-Parameters-PseudonymizeSecondary-response-example-2.md) (hier: unbekannte target-Angabe)



## Resource Content

```json
{
  "resourceType" : "OperationDefinition",
  "id" : "PseudonymizeSecondary",
  "url" : "https://ths-greifswald.de/fhir/OperationDefinition/gpas/pseudonymize-secondary",
  "version" : "2026.2.0",
  "name" : "PseudonymizeSecondary",
  "title" : "pseudonymize-secondary",
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
  "description" : "Erzeugung einer spezifischen Anzahl von Pseudonymen in einem vorhandenen Pseudonymisierungskontext bei gleichzeitiger Zuordnung zum übermittelten Originalwert.",
  "affectsState" : true,
  "code" : "pseudonymize-secondary",
  "comment" : "Erzeugung einer spezifischen Anzahl von Pseudonymen in einem vorhandenen Pseudonymisierungskontext bei gleichzeitiger Zuordnung zum übermittelten Originalwert.",
  "system" : true,
  "type" : false,
  "instance" : false,
  "parameter" : [{
    "name" : "original",
    "use" : "in",
    "min" : 1,
    "max" : "*",
    "documentation" : "Originalwerte",
    "part" : [{
      "name" : "target",
      "use" : "in",
      "min" : 1,
      "max" : "1",
      "documentation" : "Pseudonymisierungskontext auf Basis dessen für den angegebenen Original-Identifikator n Sekundärpseudonyme erzeugt werden sollen. Ist bei allen Tripeln eines Requests der target-Parameter identisch, erfolgt die interne Verarbeitung mit erhöhter Performance.",
      "type" : "string"
    },
    {
      "name" : "value",
      "use" : "in",
      "min" : 1,
      "max" : "1",
      "documentation" : "Original-Identifikator für den n Sekundärpseudonyme erzeugt werden sollen.",
      "type" : "string"
    },
    {
      "name" : "count",
      "use" : "in",
      "min" : 1,
      "max" : "1",
      "documentation" : "Anzahl der zu erzeugenden Sekundärpseudonyme.",
      "type" : "integer"
    }]
  },
  {
    "name" : "secondarypseudonym",
    "use" : "out",
    "min" : 1,
    "max" : "*",
    "documentation" : "erzeugte SekundärPersonenpseudonyme",
    "part" : [{
      "name" : "target",
      "use" : "out",
      "min" : 1,
      "max" : "1",
      "documentation" : "Pseudonymisierungskontext (Teil des Requests).",
      "type" : "Identifier"
    },
    {
      "name" : "original",
      "use" : "out",
      "min" : 1,
      "max" : "1",
      "documentation" : "Original-Identifikator (Teil des Requests).",
      "type" : "Identifier"
    },
    {
      "name" : "value",
      "use" : "out",
      "min" : 1,
      "max" : "1",
      "documentation" : "Sekundär-Pseudonym.",
      "type" : "Identifier"
    },
    {
      "name" : "result-code",
      "use" : "out",
      "min" : 0,
      "max" : "1",
      "documentation" : "Erfolgsstatus",
      "type" : "Coding"
    }]
  },
  {
    "name" : "error",
    "use" : "out",
    "min" : 0,
    "max" : "*",
    "documentation" : "Aufgetretene Fehler",
    "part" : [{
      "name" : "target",
      "use" : "out",
      "min" : 1,
      "max" : "1",
      "documentation" : "Fehlerhafte Domänenangabe",
      "type" : "Identifier"
    },
    {
      "name" : "error-code",
      "use" : "out",
      "min" : 0,
      "max" : "1",
      "documentation" : "Fehlerdetails",
      "type" : "Coding"
    }]
  }]
}

```
