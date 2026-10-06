# Artifacts Summary - v2026.2.0

 ![](assets/images/Design-Logo-THS-deutsch-271-padding.png) 

 
 2026.2.0 - ci-build  

* [**Table of Contents**](toc.md)
* **Artifacts Summary**

## Artifacts Summary

This page provides a list of the FHIR artifacts defined as part of this implementation guide.

### Behavior: Operation Definitions 

These are custom operations that can be supported by and/or invoked by systems conforming to this implementation guide.

| | |
| :--- | :--- |
| [anonymizeOriginals](OperationDefinition-AnonymizeOriginals.md) | Anonymisiert eine gegebene Liste von 1-n Originalwerten innerhalb der angegebenen Domäne. Dabei wird der Bezug von Originalwert und Pseudonym dauerhaft únd irreversibel gelöscht. |
| [dePseudonymize](OperationDefinition-DePseudonymize.md) | Abfrage je eines Originalwertes für eine Liste von 1-n Pseudonymen und eine spezifische Domäne. |
| [deletePseudonyms](OperationDefinition-DeletePseudonyms.md) | Löscht eine gegebene Liste von 1-n Einträgen (identifiziert durch den Originalwert) in der angegebenen Domäne, sofern die Konfiguration dieser Domäne dies erlaubt. |
| [insertValuePseudonymPairs](OperationDefinition-InsertValuePseudonymPairs.md) | Fügt ein Wertepaar bestehend aus Originalwert und Pseudonym in eine vorkonfigurierte Domäne ein, z.B. für die Migration von Bestandspseudonymen |
| [pseudonymize](OperationDefinition-Pseudonymize.md) | Abfrage je eines Pseudonym-Wertes für eine gegebene Liste von 1-n Originalwerten und eine spezifische Domäne. |
| [pseudonymize-secondary](OperationDefinition-PseudonymizeSecondary.md) | Erzeugung einer spezifischen Anzahl von Pseudonymen in einem vorhandenen Pseudonymisierungskontext bei gleichzeitiger Zuordnung zum übermittelten Originalwert. |
| [pseudonymizeAllowCreate](OperationDefinition-PseudonymizeAllowCreate.md) | Generierung je eines Pseudonyms für eine Liste von Originalwerten und eine spezifische Domäne sofern es noch nicht vorhanden ist. Sofern die Zuordnung Originalwert und Domäne bereits bekannt ist, wird das zugeordnete vorhandene Pseudonym zurückgegeben. |

### Example: Example Instances 

These are example instances that show what data produced and consumed by systems conforming with this implementation guide might look like.

| |
| :--- |
| [Parameters-AnonymizeOriginals-request-example-1](Parameters-Parameters-AnonymizeOriginals-request-example-1.md) |
| [Parameters-AnonymizeOriginals-response-example-1](Parameters-Parameters-AnonymizeOriginals-response-example-1.md) |
| [Parameters-DePseudonymize-request-example-1](Parameters-Parameters-DePseudonymize-request-example-1.md) |
| [Parameters-DePseudonymize-response-example-1](Parameters-Parameters-DePseudonymize-response-example-1.md) |
| [Parameters-DePseudonymize-response-example-2](Parameters-Parameters-DePseudonymize-response-example-2.md) |
| [Parameters-DeletePseudonyms-request-example-1](Parameters-Parameters-DeletePseudonyms-request-example-1.md) |
| [Parameters-DeletePseudonyms-response-example-1](Parameters-Parameters-DeletePseudonyms-response-example-1.md) |
| [Parameters-InsertValuePseudonymPairs-request-example-1](Parameters-Parameters-InsertValuePseudonymPairs-request-example-1.md) |
| [Parameters-InsertValuePseudonymPairs-response-example-1](Parameters-Parameters-InsertValuePseudonymPairs-response-example-1.md) |
| [Parameters-InsertValuePseudonymPairs-response-example-2](Parameters-Parameters-InsertValuePseudonymPairs-response-example-2.md) |
| [Parameters-Pseudonymize-request-example-1](Parameters-Parameters-Pseudonymize-request-example-1.md) |
| [Parameters-Pseudonymize-response-example-1](Parameters-Parameters-Pseudonymize-response-example-1.md) |
| [Parameters-Pseudonymize-response-example-2](Parameters-Parameters-Pseudonymize-response-example-2.md) |
| [Parameters-PseudonymizeAllowCreate-request-example-1](Parameters-Parameters-PseudonymizeAllowCreate-request-example-1.md) |
| [Parameters-PseudonymizeAllowCreate-response-example-1](Parameters-Parameters-PseudonymizeAllowCreate-response-example-1.md) |
| [Parameters-PseudonymizeSecondary-request-example-1](Parameters-Parameters-PseudonymizeSecondary-request-example-1.md) |
| [Parameters-PseudonymizeSecondary-response-example-1](Parameters-Parameters-PseudonymizeSecondary-response-example-1.md) |
| [Parameters-PseudonymizeSecondary-response-example-2](Parameters-Parameters-PseudonymizeSecondary-response-example-2.md) |

