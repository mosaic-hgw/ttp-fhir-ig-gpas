# Parameters-PseudonymizeSecondary-response-example-2 - v2025.2.0



## Resource Content

```json
{
  "resourceType" : "Parameters",
  "id" : "Parameters-PseudonymizeSecondary-response-example-2",
  "parameter" : [
    {
      "name" : "error",
      "part" : [
        {
          "name" : "target",
          "valueIdentifier" : {
            "system" : "https://ths-greifswald.de/gpas",
            "value" : "DOMAINXY"
          }
        },
        {
          "name" : "error-code",
          "valueCoding" : {
            "system" : "http://hl7.org/fhir/issue-type",
            "code" : "not-found",
            "display" : "Not Found"
          }
        }
      ]
    }
  ]
}

```
