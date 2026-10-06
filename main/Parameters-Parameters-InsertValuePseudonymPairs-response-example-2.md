# Parameters-InsertValuePseudonymPairs-response-example-2 - v2026.2.0

 ![](assets/images/Design-Logo-THS-deutsch-271-padding.png) 

 
 2026.2.0 - ci-build  

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **Parameters-InsertValuePseudonymPairs-response-example-2**

## Example Parameters: Parameters-InsertValuePseudonymPairs-response-example-2



## Resource Content

```json
{
  "resourceType" : "Parameters",
  "id" : "Parameters-InsertValuePseudonymPairs-response-example-2",
  "parameter" : [{
    "name" : "successStatus",
    "part" : [{
      "name" : "target",
      "valueIdentifier" : {
        "system" : "https://ths-greifswald.de/gpas",
        "value" : "DOMAINXY"
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
