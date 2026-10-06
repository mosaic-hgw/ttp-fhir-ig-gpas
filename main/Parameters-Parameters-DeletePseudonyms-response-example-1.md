# Parameters-DeletePseudonyms-response-example-1 - v2026.2.0

 ![](assets/images/Design-Logo-THS-deutsch-271-padding.png) 

 
 2026.2.0 - ci-build  

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **Parameters-DeletePseudonyms-response-example-1**

## Example Parameters: Parameters-DeletePseudonyms-response-example-1



## Resource Content

```json
{
  "resourceType" : "Parameters",
  "id" : "Parameters-DeletePseudonyms-response-example-1",
  "parameter" : [{
    "name" : "successStatus",
    "part" : [{
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
      "name" : "result-code",
      "valueCoding" : {
        "system" : "http://terminology.hl7.org/CodeSystem/operation-outcome",
        "code" : "MSG_DELETED"
      }
    }]
  },
  {
    "name" : "successStatus",
    "part" : [{
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
        "value" : "1001000000033"
      }
    },
    {
      "name" : "result-code",
      "valueCoding" : {
        "system" : "http://hl7.org/fhir/issue-type",
        "code" : "not-found",
        "display" : "Not Found"
      }
    }]
  }]
}

```
