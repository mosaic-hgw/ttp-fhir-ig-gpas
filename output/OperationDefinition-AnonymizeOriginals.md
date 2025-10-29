# anonymizeOriginals - v2025.1.0



## Resource Content

```json
{
  "resourceType" : "OperationDefinition",
  "id" : "AnonymizeOriginals",
  "url" : "https://ths-greifswald.de/fhir/OperationDefinition/gpas/anonymizeOriginals",
  "version" : "2025.1.0",
  "name" : "AnonymizeOriginals",
  "title" : "anonymizeOriginals",
  "status" : "active",
  "kind" : "operation",
  "date" : "2025-06-12",
  "publisher" : "Unabhängige Treuhandstelle der Universitätsmedizin Greifswald",
  "contact" : [
    {
      "name" : "Unabhängige Treuhandstelle der Universitätsmedizin Greifswald",
      "telecom" : [
        {
          "system" : "url",
          "value" : "https://www.ths-greifswald.de/"
        }
      ]
    }
  ],
  "description" : "Anonymisiert eine gegebene Liste von 1-n Originalwerten innerhalb der angegebenen Domäne. Dabei wird der Bezug von Originalwert und Pseudonym dauerhaft únd irreversibel gelöscht.",
  "affectsState" : true,
  "code" : "anonymizeOriginals",
  "comment" : "Anonymisiert eine gegebene Liste von 1-n Originalwerten innerhalb der angegebenen Domäne. Dabei wird der Bezug von Originalwert und Pseudonym dauerhaft únd irreversibel gelöscht.",
  "system" : true,
  "type" : false,
  "instance" : false,
  "parameter" : [
    {
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
      "part" : [
        {
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
        }
      ]
    }
  ]
}

```
