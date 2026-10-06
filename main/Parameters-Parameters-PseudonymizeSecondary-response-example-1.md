# Parameters-PseudonymizeSecondary-response-example-1 - v2026.2.0

 ![](assets/images/Design-Logo-THS-deutsch-271-padding.png) 

 
 2026.2.0 - ci-build  

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **Parameters-PseudonymizeSecondary-response-example-1**

## Example Parameters: Parameters-PseudonymizeSecondary-response-example-1



## Resource Content

```json
{
  "resourceType" : "Parameters",
  "id" : "Parameters-PseudonymizeSecondary-response-example-1",
  "parameter" : [{
    "name" : "secondarypseudonym",
    "part" : [{
      "name" : "target",
      "valueIdentifier" : {
        "system" : "https://sample/psn-system",
        "value" : "Datensatz-Ebene"
      }
    },
    {
      "name" : "original",
      "valueIdentifier" : {
        "system" : "https://sample/psn-system",
        "value" : "H3RAU56A8E"
      }
    },
    {
      "name" : "value",
      "valueIdentifier" : {
        "system" : "https://ths-greifswald.de/gpas",
        "value" : "53KUNDA3RP5N1"
      }
    },
    {
      "name" : "result-code",
      "valueCoding" : {
        "system" : "http://terminology.hl7.org/CodeSystem/operation-outcome",
        "code" : "MSG_CREATED"
      }
    }]
  },
  {
    "name" : "secondarypseudonym",
    "part" : [{
      "name" : "target",
      "valueIdentifier" : {
        "system" : "https://sample/psn-system",
        "value" : "Datensatz-Ebene"
      }
    },
    {
      "name" : "original",
      "valueIdentifier" : {
        "system" : "https://sample/psn-system",
        "value" : "H3RAU56A8E"
      }
    },
    {
      "name" : "value",
      "valueIdentifier" : {
        "system" : "https://sample/psn-system",
        "value" : "53KUNDA3RP5N2"
      }
    },
    {
      "name" : "result-code",
      "valueCoding" : {
        "system" : "http://terminology.hl7.org/CodeSystem/operation-outcome",
        "code" : "MSG_CREATED"
      }
    }]
  }]
}

```
