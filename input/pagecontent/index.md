# FHIR-Support für gPAS

Stand 05.02.2026

Die Softwarelösungen E-PIX, gPAS und gICS werden in zahlreichen Forschungseinrichtungen und Projekten für die Realisierung von Treuhandstellen-Services (THS) eingesetzt. Um die Verwendung dieser Lösungen in FHIR-basierten Infrastrukturen zu unterstützen, werden ausgewählte THS-Funktionalitäten in durch FHIR-basierte Operations, Profile, Erweiterungen und Terminologien realisiert.

Diese werden in entsprechenden [Implementierungsleitfäden](https://www.ths-greifswald.de/fhir) themenspezifisch beschrieben und zahlreiche Details erläutert.

Der vorliegende **Implementation Guide gPAS** setzt den Fokus auf Operations, CodeSysteme und ValueSets von [gPAS].
          
### Endpunkt

Der FHIR-Endpunkt (```base```) für das Pseudonymmanagement ist

<strong>```http[s]://\<host\>:\<port\>/ttp-fhir/fhir/gpas```</strong>

<p align="center">
  <img width="500" style="float: none;" src="assets/images/fhirgw-gpas.png">
</p>

### Package

Das automatisch erzeugte Package (TGZ) steht als Download zur Verfügung unter: [Link](package.tgz).

### Implementierung

Peter Penndorf, Martin Bialke, Christoper Hampf, Frank Michael Moser

### Autoren

Martin Bialke, Stefan Lang

### Kontakt

kontakt-ths (at) med.uni-greifswald.de
