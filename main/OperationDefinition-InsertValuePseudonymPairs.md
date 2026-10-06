# insertValuePseudonymPairs - v2026.2.0

 ![](assets/images/Design-Logo-THS-deutsch-271-padding.png) 

 
 2026.2.0 - ci-build  

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **insertValuePseudonymPairs**

## OperationDefinition: insertValuePseudonymPairs 

| | |
| :--- | :--- |
| *Official URL*:https://ths-greifswald.de/fhir/OperationDefinition/gpas/insertValuePseudonymPairs | *Version*:2026.2.0 |
| Active as of 2025-06-12 | *Computable Name*:InsertValuePseudonymPairs |

 
Fügt ein Wertepaar bestehend aus Originalwert und Pseudonym in eine vorkonfigurierte Domäne ein, z.B. für die Migration von Bestandspseudonymen 

**Unterstützt ab TTP-FHIR Gateway Version 2024.3.0**

Fügt ein Wertepaar bestehend aus Originalwert und Pseudonym in eine vorkonfigurierte Domäne ein, z.B. für die Migration von Bestandspseudonymen. Das Pseudonym muss den konfigurierten Vorgaben der Zieldomäne entsprechend und wird im Regelfall vor dem Einfügen durch den gPAS validiert.

### Voraussetzung

* Domäne muss konfiguriert sein
* Pseudonym muss den Vorgaben der Domäne entsprechen und wird vor dem Einfügen im Regelfall validiert.

### Hinweise

### Aufruf und Rückgabe

Die bereitgestellte Funktionalität kann per POST-Request aufgerufen werden. Die erforderlichen Angaben werden per POST-BODY in Form von [FHIR Parameters](https://www.hl7.org/fhir/parameters.html) übermittelt.

Im Erfolgsfall wird der HTTP Statuscode 200 zurückgegeben.

Im Fehlerfall wird einer der folgenden HTTP Statuscodes in Verbindung mit einer OperationOutcome-Ressource zurückgegeben:

* 400: Fehlende oder fehlerhafte Parameter.
* 401: Fehlende Authentifizierung oder Autorisierung.
* 404: Parameter mit unbekanntem Inhalt.

Auftretende Fehler (z.B. angegebene Domain ist unbekannt oder Pseudonym ist nicht valide) werden im Einzelnen entsprechend per Coding vom Typ [Issue-Type](http://hl7.org/fhir/issue-type) signalisiert.

### Beispiel

* [Request-Body](Parameters-Parameters-InsertValuePseudonymPairs-request-example-1.md)
* [Rückmeldung](Parameters-Parameters-InsertValuePseudonymPairs-response-example-1.md)
* [Fehler-Rückmeldung](Parameters-Parameters-InsertValuePseudonymPairs-response-example-2.md)



## Resource Content

```json
{
  "resourceType" : "OperationDefinition",
  "id" : "InsertValuePseudonymPairs",
  "url" : "https://ths-greifswald.de/fhir/OperationDefinition/gpas/insertValuePseudonymPairs",
  "version" : "2026.2.0",
  "name" : "InsertValuePseudonymPairs",
  "title" : "insertValuePseudonymPairs",
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
  "description" : "Fügt ein Wertepaar bestehend aus Originalwert und Pseudonym in eine vorkonfigurierte Domäne ein, z.B. für die Migration von Bestandspseudonymen",
  "affectsState" : true,
  "code" : "insertValuePseudonymPairs",
  "system" : true,
  "type" : false,
  "instance" : false,
  "parameter" : [{
    "name" : "pseudonym",
    "use" : "in",
    "min" : 1,
    "max" : "*",
    "documentation" : "Tripel mit den Angaben zu Original und zu setzendem Pseudonym.",
    "part" : [{
      "name" : "target",
      "use" : "in",
      "min" : 1,
      "max" : "1",
      "documentation" : "Angabe der Domäne, in welche das Wertepaare Original-Wert & Pseudonym eingefügt werden soll. Ist bei allen Tripeln eines Requests der target-Parameter identisch, erfolgt die interne Verarbeitung mit erhöhter Performance.",
      "type" : "string",
      "searchType" : "string"
    },
    {
      "name" : "original",
      "use" : "in",
      "min" : 1,
      "max" : "1",
      "documentation" : "Angabe des Originalwertes des Werte-Paares",
      "type" : "string",
      "searchType" : "string"
    },
    {
      "name" : "value",
      "use" : "in",
      "min" : 1,
      "max" : "1",
      "documentation" : "Angabe des Pseudonyms des Werte-Paares. Das Pseudonym muss den konfigurierten Vorgaben der Zieldomäne entsprechend und wird im Regelfall vor dem Einfügen durch den gPAS validiert.",
      "type" : "string",
      "searchType" : "string"
    }]
  },
  {
    "name" : "successStatus",
    "use" : "out",
    "min" : 0,
    "max" : "*",
    "documentation" : "Ermitteltes bzw. generiertes studien- und standort-spezifisches Pseudonym",
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
      "name" : "value",
      "use" : "out",
      "min" : 0,
      "max" : "1",
      "documentation" : "Pseudonym",
      "type" : "Identifier"
    },
    {
      "name" : "result-code",
      "use" : "out",
      "min" : 1,
      "max" : "1",
      "documentation" : "Erfolgsstatus",
      "type" : "Coding"
    }]
  }]
}

```
