# anonymizeOriginals - v2026.2.0

 ![](assets/images/Design-Logo-THS-deutsch-271-padding.png) 

 
 2026.2.0 - ci-build  

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **anonymizeOriginals**

## OperationDefinition: anonymizeOriginals 

| | |
| :--- | :--- |
| *Official URL*:https://ths-greifswald.de/fhir/OperationDefinition/gpas/anonymizeOriginals | *Version*:2026.2.0 |
| Active as of 2025-06-12 | *Computable Name*:AnonymizeOriginals |

 
Anonymisiert eine gegebene Liste von 1-n Originalwerten innerhalb der angegebenen Domäne. Dabei wird der Bezug von Originalwert und Pseudonym dauerhaft únd irreversibel gelöscht. 

**Unterstützt ab TTP-FHIR Gateway Version 2024.2.0**

Anonymisiert eine gegebene Liste von 1-n Originalwerten innerhalb der angegebenen Domäne. Dabei wird der Bezug von Originalwert und Pseudonym dauerhaft únd irreversibel gelöscht.

### Voraussetzung

Die angegebene Pseudonym-Domäne muss in gPAS konfiguriert und der angegebene Originalwert in dieser Domäne bereits vorhanden sein.

### Hinweise

### Aufruf und Rückgabe

Die bereitgestellte Funktionalität kann per POST-Request aufgerufen werden. Die erforderlichen Angaben werden per POST-BODY in Form von [FHIR Parameters](https://www.hl7.org/fhir/parameters.html) übermittelt.

`<HOST>:<PORT>/ttp-fhir/fhir/gpas/$anonymizeOriginals`

Der Funktionsaufruf liefert ein ParameterSet bestehend aus multiplen benannten Parametern zurück:

1. original = der zu pseudonymisierende Werte (Teil des Requests)
1. target = die genutzte Ziel-Domäne (Teil des Requests)
1. result-code = Ergebnisstatus (Erfolg oder Fehler).

Im Erfolgsfall wird der HTTP Statuscode 200 zurückgegeben.

Im Fehlerfall wird einer der folgenden HTTP Statuscodes in Verbindung mit einer OperationOutcome-Ressource zurückgegeben:

* 400: Fehlende oder fehlerhafte Parameter.
* 401: Fehlende Authentifizierung oder Autorisierung.
* 404: Parameter mit unbekanntem Inhalt.
* 422: Fehlende oder falsche Patienten-Attribute.

Auftretende Fehler (z.B. angegebenes Pseudonym ist unbekannt) werden im Einzelnen entsprechend per Coding vom Typ [Issue-Type](http://hl7.org/fhir/issue-type) signalisiert.

### Beispiel

* [Request-Body](Parameters-Parameters-AnonymizeOriginals-request-example-1.md)
* [Rückmeldung](Parameters-Parameters-AnonymizeOriginals-response-example-1.md)



## Resource Content

```json
{
  "resourceType" : "OperationDefinition",
  "id" : "AnonymizeOriginals",
  "url" : "https://ths-greifswald.de/fhir/OperationDefinition/gpas/anonymizeOriginals",
  "version" : "2026.2.0",
  "name" : "AnonymizeOriginals",
  "title" : "anonymizeOriginals",
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
  "description" : "Anonymisiert eine gegebene Liste von 1-n Originalwerten innerhalb der angegebenen Domäne. Dabei wird der Bezug von Originalwert und Pseudonym dauerhaft únd irreversibel gelöscht.",
  "affectsState" : true,
  "code" : "anonymizeOriginals",
  "comment" : "Anonymisiert eine gegebene Liste von 1-n Originalwerten innerhalb der angegebenen Domäne. Dabei wird der Bezug von Originalwert und Pseudonym dauerhaft únd irreversibel gelöscht.",
  "system" : true,
  "type" : false,
  "instance" : false,
  "parameter" : [{
    "name" : "target",
    "use" : "in",
    "min" : 1,
    "max" : "1",
    "documentation" : "Angabe der Domäne innerhalb derer für die angegebenen Originalwerte eine Anonymisierung durchgeführt werden soll.",
    "type" : "string",
    "searchType" : "string"
  },
  {
    "name" : "original",
    "use" : "in",
    "min" : 1,
    "max" : "*",
    "documentation" : "Angabe der Originalwerte für die in der angegebenen Domäne eine Anonymisierung durchgeführt werden soll.",
    "type" : "string",
    "searchType" : "string"
  },
  {
    "name" : "successStatus",
    "use" : "out",
    "min" : 1,
    "max" : "*",
    "documentation" : "Status-Rückgabe der einzelnen durchgeführten Anonymisierungen",
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
      "min" : 1,
      "max" : "1",
      "documentation" : "Original-Identifikator",
      "type" : "Identifier"
    },
    {
      "name" : "result-code",
      "use" : "out",
      "min" : 1,
      "max" : "1",
      "documentation" : "Erfolgs- bzw. Fehlercode",
      "type" : "Coding"
    }]
  }]
}

```
