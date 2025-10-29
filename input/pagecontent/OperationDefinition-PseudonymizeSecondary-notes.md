#### Aufruf und Rückgabe

Die bereitgestellte Funktionalität kann per POST-Request aufgerufen werden. Die erforderlichen Angaben werden per POST-BODY in Form von [FHIR Parameters](https://www.hl7.org/fhir/parameters.html) übermittelt.

Je nach Werteangaben (target, count) erfolgt bei der Verarbeitung intern eine Gruppierung der angefragten Werte, um die Vorteile des Batch-Processing nutzen zu können.
Einheitliche count- und target-Angaben führen zu besserer Performance.

`<HOST>:<PORT>/ttp-fhir/fhir/gpas/$pseudonymize-secondary`

Im Erfolgsfall wird der HTTP Statuscode 200 zurückgegeben.

Im Fehlerfall wird einer der folgenden HTTP Statuscodes in Verbindung mit einer OperationOutcome-Ressource zurückgegeben:
* 400: Fehlende oder fehlerhafte Parameter.
* 401: Fehlende Authentifizierung oder Autorisierung.
* 404: Parameter mit unbekanntem Inhalt.

#### Beispiel

* [Request-Body](Parameters-Parameters-PseudonymizeSecondary-request-example-1.html)
* [Rückmeldung](Parameters-Parameters-PseudonymizeSecondary-response-example-1.html)
* [Fehler-Rückmeldung](Parameters-Parameters-PseudonymizeSecondary-response-example-2.html) (hier: unbekannte target-Angabe)
