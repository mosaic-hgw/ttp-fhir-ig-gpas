# deletePseudonyms - v2025.1.0



## Resource Content

```json
{
  "resourceType" : "OperationDefinition",
  "id" : "DeletePseudonyms",
  "url" : "https://ths-greifswald.de/fhir/OperationDefinition/gpas/deletePseudonyms",
  "version" : "2025.1.0",
  "name" : "DeletePseudonyms",
  "title" : "deletePseudonyms",
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
  "affectsState" : true,
  "code" : "deletePseudonyms",
  "comment" : "Löscht eine gegebene Liste von 1-n Einträgen (identifiziert durch den Originalwert) in der angegebenen Domäne, sofern die Konfiguration dieser Domäne dies erlaubt.",
  "system" : true,
  "type" : false,
  "instance" : false,
  "parameter" : [
    {
      "name" : "target",
      "use" : "in",
      "min" : 1,
      "max" : "1",
      "documentation" : "Angabe der Domäne innerhalb derer die angegebenen Originalwerte gelöscht werden.",
      "type" : "string",
      "searchType" : "string"
    },
    {
      "name" : "original",
      "use" : "in",
      "min" : 1,
      "max" : "*",
      "documentation" : "Angabe der Originalwerte für die in der angegebenen Domäne eine Löschung durchgeführt werden soll.",
      "type" : "string",
      "searchType" : "string"
    },
    {
      "name" : "successStatus",
      "use" : "out",
      "min" : 1,
      "max" : "*",
      "documentation" : "Status-Rückgabe der einzelnen durchgeführten Löschungen",
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
