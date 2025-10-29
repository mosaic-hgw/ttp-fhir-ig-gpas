#### Aufruf und Rückgabe

Die bereitgestellte Funktionalität kann per POST-Request aufgerufen werden. Die erforderlichen Angaben werden per POST-BODY in Form von [FHIR Parameters](https://www.hl7.org/fhir/parameters.html) übermittelt.

Im Erfolgsfall wird der HTTP Statuscode 200 zurückgegeben.

Im Fehlerfall wird einer der folgenden HTTP Statuscodes in Verbindung mit einer OperationOutcome-Ressource zurückgegeben:
* 400: Fehlende oder fehlerhafte Parameter.
* 401: Fehlende Authentifizierung oder Autorisierung.
* 404: Parameter mit unbekanntem Inhalt.

Auftretende Fehler (z.B. angegebene Domain ist unbekannt oder Pseudonym ist nicht valide) werden im Einzelnen entsprechend per Coding vom Typ [Issue-Type](http://hl7.org/fhir/issue-type) signalisiert.

#### Beispiel

* [Request-Body](Parameters-Parameters-InsertValuePseudonymPairs-request-example-1.html)
* [Rückmeldung](Parameters-Parameters-InsertValuePseudonymPairs-response-example-1.html)
* [Fehler-Rückmeldung](Parameters-Parameters-InsertValuePseudonymPairs-response-example-2.html)
