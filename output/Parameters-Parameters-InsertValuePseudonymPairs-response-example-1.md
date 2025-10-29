# Parameters-InsertValuePseudonymPairs-response-example-1 - v2025.1.0



## Resource Content

```json
{
  "resourceType" : "Parameters",
  "id" : "Parameters-InsertValuePseudonymPairs-response-example-1",
  "parameter" : [
    {
      "name" : "successStatus",
      "part" : [
        {
          "name" : "target",
          "valueIdentifier" : {
            "system" : "https://ths-greifswald.de/gpas",
            "value" : "MIRACUM"
          }
        },
        {
          "name" : "original",
          "valueIdentifier" : {
            "system" : "https://ths-greifswald.de/gpas",
            "value" : "1001000000022"
          }
        },
        {
          "name" : "value",
          "valueIdentifier" : {
            "system" : "https://ths-greifswald.de/gpas",
            "value" : "mrcm_T0TYNV21"
          }
        },
        {
          "name" : "result-code",
          "valueCoding" : {
            "system" : "http://terminology.hl7.org/CodeSystem/operation-outcome",
            "code" : "MSG_CREATED"
          }
        }
      ]
    }
  ]
}

```
