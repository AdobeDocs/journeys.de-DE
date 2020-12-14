---
product: adobe campaign
solution: Journey Orchestration
title: Beschreibung der Import-Export-API
description: Weitere Informationen zur Import-Export-API.
products: journeys
translation-type: ht
source-git-commit: 8da1d4a6c01279bf502c3ec39bdaba8fcc8e64f8
workflow-type: ht
source-wordcount: '1131'
ht-degree: 100%

---


# Arbeiten mit der Export-Import-API

Exportieren Sie eine Version der Journey und all ihre zugehörigen Objekte (Journey, Ereignisse, Datenquellen, Feldgruppen, benutzerdefinierte Aktionen) mit einem einzigen API-Aufruf. Die aus dem Export resultierende Payload kann verwendet werden, um die Journey einfach in eine andere Umgebung (Instanz oder Sandbox) zu importieren.
Mit dieser Funktion können Sie Ihre Journeys über mehrere Instanzen oder für mehrere Testumgebungs-Workflows verwalten.


## Ressourcen

Die Journey Orchestration Export-Import-API wird in einer Swagger-Datei beschrieben, die [hier](https://adobedocs.github.io/JourneyAPI/docs/) verfügbar ist.

Um diese API mit Ihrer Journey Orchestration-Instanz verwenden zu können, müssen Sie die Adobe I/O-Konsole verwenden. Sie können damit beginnen, indem Sie zuerst [Erste Schritte mit Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) und dann die Abschnitte auf dieser Seite befolgen.

Um Ihre Integration zu testen und vorzubereiten, steht Ihnen [hier](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json) eine Postman-Kollektion zur Verfügung.


## Export-Import-Fluss

Wir empfehlen, die folgenden Schritte auszuführen, um Ihre Journeys über Umgebungen hinweg zu exportieren und zu importieren:

1. Erstellen und parametrieren Sie eine Journey in Ihrer Startumgebung. [Weitere Informationen hier](https://docs.adobe.com/content/help/de-DE/journeys/using/building-journeys/about-journey-building/journey.html)
1. Stellen Sie sicher, dass die Version der Journey keinen Fehler enthält. [Weitere Informationen hier](https://docs.adobe.com/content/help/de-DE/journeys/using/building-journeys/testing-the-journey.html)
1. Rufen Sie **/list/journeys** API auf, um die UID-Journey und die UID Ihrer aktuellen Journey-Version abzurufen. Bei Bedarf können Sie **/journeys/`{uid}`/latest** aufrufen, um die UID Ihrer aktuellen Journey-Version zu finden.
1. Rufen Sie die **Export**-API mit den Parametern Ihrer Startumgebung auf (orgID und sandboxName).
1. Öffnen Sie die Rückgabe-Payload und überprüfen Sie dann die folgenden Elemente:
   * Wenn Ihre exportierte Journey **bestimmte Anmeldeinformationen** enthält, müssen Sie diese durch die entsprechenden Anmeldeinformationen der neuen Umgebung ersetzen.
   * Wenn Ihre exportierte Journey **Ereignisse** enthält, die auf ein **XDM-Schema** verweisen, müssen Sie die Schema-ID-Referenz manuell mit der Schema-ID der neuen Umgebung im Knoten xdmEntity aktualisieren, wenn die IDs unterschiedlich sind. Diese Aktualisierung muss für jedes Ereignis durchgeführt werden. [Weitere Informationen hier](https://docs.adobe.com/content/help/de-DE/journeys/using/events-journeys/experience-event-schema.html)
   * Wenn Ihre Journey E-Mail-, SMS- oder Push-Aktionen enthält, müssen Sie möglicherweise den Vorlagennamen oder den mobileApp-Namen aktualisieren, wenn der Name in der Zielumgebung sich von dem in Ihrer Startumgebung unterscheidet.
1. Rufen Sie die **Import**-API mit den Parametern Ihrer Zielumgebung auf (orgID und sandboxName). Beachten Sie, dass Sie die Import-API so oft aufrufen können, wie Sie möchten. Die UUID und der Name der einzelnen Objekte, die in der Journey enthalten sind, werden jedes Mal generiert, wenn Sie die Import-API aufrufen.
1. Sobald die Journey importiert wurde, können Sie sie in Journey Orchestration veröffentlichen. Weitere Informationen finden Sie [hier](https://docs.adobe.com/content/help/de-DE/journeys/using/building-journeys/publishing-the-journey.html).


## Authentifizierung

### Einrichten von API-Zugriff

Der API-Zugriff für Journey Orchestration wird wie folgt eingerichtet: Jeder dieser Schritte wird in der [Adobe I/O-Dokumentation](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) beschrieben.

>[!CAUTION]
>
>Wenn Sie Zertifikate in Adobe I/O verwalten möchten, vergewissern Sie sich, dass Sie in der Admin Console über <b>Systemadministrator</b>-Rechte für das Unternehmen oder ein [Entwicklerkonto](https://helpx.adobe.com/de/enterprise/using/manage-developers.html) verfügen.

1. **Überprüfen Sie, ob Sie ein digitales Zertifikat haben**, oder erstellen Sie bei Bedarf eines. Die mit dem Zertifikat bereitgestellten öffentlichen und privaten Schlüssel werden in den folgenden Schritten benötigt.
1. **Erstellen Sie eine neue Integration mit dem [!DNL Journey Orchestration]-Service** in Adobe I/O und konfigurieren Sie sie. Der Produktprofilzugriff wird für Journey Orchestration und Adobe Experience Platform benötigt. Dann werden Ihre Zugangsdaten generiert (API-Schlüssel, Client-Geheimnis...).
1. **Erstellen Sie einen JSON-Web-Token (JWT)** aus den zuvor erstellten Anmeldedaten und signieren Sie ihn mit Ihrem privaten Schlüssel. Der JWT kodiert alle Identitäts- und Sicherheitsdaten, die Adobe zum Überprüfen Ihrer Identität und zum Erteilen des Zugriffs auf die API benötigt. Dieser Schritt wird in diesem [Abschnitt](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) genau beschrieben.
1. **Ersetzen Sie Ihr JWT durch einen Zugriffstoken**, und zwar über eine POST-Anfrage oder über die Developer Console-Oberfläche. Dieser Zugriffstoken muss in allen Kopfzeilen Ihrer API-Anfragen verwendet werden.

Um eine sichere Service-to-Service-Adobe I/O-API-Sitzung herzustellen, muss jede Anfrage an einen Adobe-Dienst folgende Informationen in der Autorisierungskopfzeile umfassen.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>**: Dies ist Ihre persönliche Organisationskennung; von Adobe erhalten Sie für jede Ihrer Instanzen eine Organisationskennung:

   * &lt;ORGANIZATION>: Ihre Produktionsinstanz
   Wenden Sie sich an Ihren Administrator oder Ihren technischen Ansprechpartner bei Adobe, um den Wert Ihrer Organisationskennung zu erhalten. Sie können sie auch beim Erstellen einer neuen Integration in Adobe I/O abrufen, und zwar in der Lizenzliste (siehe [Adobe I/O-Dokumentation](https://www.adobe.io/authentication.html)).

* **&lt;ACCESS_TOKEN>**: Ihr persönlicher Zugriffstoken, der beim Austausch Ihres JWT über eine POST-Anfrage abgerufen wurde.

* **&lt;API_KEY>**: Ihr persönlicher API-Schlüssel. Er wird in Adobe I/O bereitgestellt, nachdem eine neue Integration mit dem [!DNL Journey Orchestration]-Service erstellt wurde.



## Beschreibung der Export-Import-API

Mit dieser API können Sie eine Journey-Version, die durch ihre UID identifiziert wird, exportieren, ebenso wie alle zugehörigen Objekte (Journey, Ereignisse, Datenquellen, Feldergruppen, benutzerdefinierte Aktionen).
Die resultierende Payload kann verwendet werden, um die Version der Journey in einer anderen Umgebung (Sandbox oder Instanz) zu importieren.

| Vorgehensweise | Pfad | Beschreibung |
|---|---|---|
| `[POST]` | /journeyVersions/import | Importieren von Inhalt aus einer Journey-Version, der aus einem Export einer Journey-Version resultiert. |
| `[GET]` | /journeyVersions/`{uid}`/export | Journey-Version exportieren |
| `[GET]` | /journeys/`{uid}`/latest | Die aktuelle Journey-Version für eine Journey erhalten |
| `[POST]` | /list/journeys | Metadaten der Journeys und der Journey-Versionen auflisten |


### Exportmerkmale und Limits

* Die Journey muss vor dem Export gültig sein.

* Die Anmeldeinformationen werden nicht exportiert und ein Platzhalter (z. B. INSERT_SECRET_HERE) wird in die Antwort-Payload eingefügt.
Nach dem Export-Aufruf müssen Sie die neuen Anmeldeinformationen (entsprechend der Zielumgebung) manuell einfügen, bevor Sie die Payload in die Zielumgebung importieren.

* Die folgenden Objekte werden exportiert, sie werden jedoch nie in die Zielumgebung importiert. Diese Systemressourcen werden automatisch von Journey Orchestration verwaltet. Sie müssen „INSERT_SECRET_HERE“ nicht ersetzen.
   * **DataProviders**:  „Adobe Campaign Standard Data Provider“ (acsDataProvider) und „Experience Platform“ (acppsDataProvider)
   * **Feldergruppen** (dataEntities): „ProfileFieldGroup“ (acppsDataPack)



### Import-Merkmale

* Während des Imports werden die Objekte der Journey mit einer neuen UID und einem neuen Namen erstellt, um die Eindeutigkeit in der Zielumgebung (Instanz oder Sandbox) sicherzustellen.

* Wenn die Import-Payload geheime Platzhalter enthält, wird ein Fehler ausgegeben. Sie müssen die Anmeldeinformationen vor dem POST-Aufruf zum Import der Journey ersetzen.

## Warnung und Fehler

Mögliche Fehler sind:

* Zum **Zeitpunkt des Exports**, wenn die Journey-Version nicht gültig ist: Fehler 500

* Zum **Zeitpunkt des Imports**, wenn die Payload nach Änderungen nicht gültig ist oder wenn die Anmeldeinformationen in der Payload nicht gut definiert sind: Fehler 400

* Wenn nach dem Importschritt die XDM-Schema-ID für Ihre Ereignisse in der Zielumgebung nicht gültig ist, wird in Journey Orchestration ein Fehler angezeigt. In diesem Fall kann die Journey nicht veröffentlicht werden.