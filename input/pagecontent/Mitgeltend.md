### Hintergrund
                                  
In der MII wurde, initiiert durch die MII TF "Übergreifende Schnittstellen", eine einheitliche Schnittstelle zur Pseudonymisierung konzeptioniert, mittels FHIR spezifiziert und offiziell im April 2026 abschließend ballotiert.

Die Schnittstelle zur Pseudonymisierung der MII definiert grundlegende FHIR-Operationen, die zur Erzeugung und 
Verwaltung von Pseudonymen genutzt werden können. Ziel ist es, eine FHIR-native Spezifikation für typische 
Pseudonymisierungsoperationen bereitzustellen, die einheitlich von Entwicklern von De-Identifizierungstools 
implementiert werden kann, um die Anwendung derartiger Lösungen für Anwenderinnen und Anwender zu vereinfachen
und die Interoperabilität der Lösungen in diesem Themenfeld zu verbessern.

Die finale Version der abgestimmten HL7-FHIR Pseudonymisierungsschnittstelle der MII (v2026.1.0) ist verfügbar unter https://medizininformatik-initiative.github.io/mii-interface-module-pseudonymization/

### Zusätzlicher Endpunkt

Unterstützt ab v2026.2.0.

Für gPAS wurde ein zweiter FHIR-Endpunkt im Frühjahr 2026 ergänzt, der diese Spezifikation technisch umsetzt.
Der bisherige FHIR-Endpunkt des gPAS bleibt parallel unverändert bestehen. Der zusätzliche FHIR-Endpunkt (```base```) für die generische Pseudonymisierungsschnittstelle (der MII) ist wie folgt verfügbar.

<strong>```http[s]://\<host\>:\<port\>/ttp-fhir/fhir/gpas/v2```</strong>

<p align="center">
  <img width="700" style="float: none;" src="assets/images/gpas-architecture.png">
</p>

Der zusätzliche Endpunkt kann individuell per Konfiguration aktiviert/deaktiviert werden (Datei `ttp_fhir.env`; Variable `TTP_FHIR_GPAS_GENERIC_ENDPOINT_ENABLED` mit Default `TRUE`).

### Übersicht der Funktionalitäten

Es werden alle im IG für die Schnittstelle zur Pseudonymisierung in der MII spezifizierten FHIR Operations
unterstützt (Stand vom 01. Oktober 2026). 

Details dazu im offiziellen IG zum [MII PSN Interface](https://medizininformatik-initiative.github.io/mii-interface-module-pseudonymization/Funktionen.html).

| Operation         | 	Link zur Spezifikation |
|-------------------|------------------------|
| *$pseudonymize*   | 	[Details](https://medizininformatik-initiative.github.io/mii-interface-module-pseudonymization/OperationDefinition-Pseudonymize.html)|
| *$pseudonymize-multiple* | [Details](https://medizininformatik-initiative.github.io/mii-interface-module-pseudonymization/OperationDefinition-PseudonymizeMultiple.html)|
| *$get-pseudonym*  | [Details](https://medizininformatik-initiative.github.io/mii-interface-module-pseudonymization/OperationDefinition-GetPseudonym.html)|
| *$de-pseudonymize* | [Details](https://medizininformatik-initiative.github.io/mii-interface-module-pseudonymization/OperationDefinition-DePseudonymize.html)|
| *$delete-pseudonym* | [Details](https://medizininformatik-initiative.github.io/mii-interface-module-pseudonymization/OperationDefinition-DeletePseudonym.html)|
| *$anonymize-original* | [Details](https://medizininformatik-initiative.github.io/mii-interface-module-pseudonymization/OperationDefinition-AnonymizeOriginal.html)|

### Besonderheiten der gPAS MII Implementierung

- Es werden entsprechend dne Vorgaben des MII PSN IGs Bundles mit Parameters-Ressourcen für die Batch-Verarbeitung unterstützt. Zusätzlich können auch einzelne Parameters-Ressourcen (wie bekannt aus der allgemeinen gPAS Umsetzung) in Requests verwendet werden.
- Abweichend von der allgemeinen gPAS Umsetzung, werden Pseudonyme, Domänen und Originalwerte nur in Form von Identifiern akzeptiert. Die Verwendung von StringTypes führt zu InvalidRequest. Damit folgt die Umsetzung den Vorgaben des MII PSN IGs. 

### Publikationen und weitergehende Informationen

Eine Publikation zum Thema ist in Vorbereitung.