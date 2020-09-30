---
title: Export API-Beschreibung importieren
description: Weitere Informationen zur Import Export API.
contentOwner: sauviat
products: journeys
audience: audiences
content-type: reference
topic-tags: journeys
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c92d7a4e5ef02f87f705871cd0fdb8c2523966d2
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 35%

---


# Arbeiten mit der Export Import API

Exportieren Sie eine Reiseversion und alle zugehörigen Objekte (Reise, Ereignisse, Datenquellen, Feldgruppen, benutzerdefinierte Aktionen) mit einem einzigen API-Aufruf. Die exportierte Nutzlast kann verwendet werden, um die Reise einfach in eine andere Umgebung (Instanz oder Sandbox) zu importieren.
Mit dieser Funktion können Sie Ihre Reisen über mehrere Instanzen hinweg oder für mehrere Umgebung Workflows verwalten.


## Ressourcen

Die Journey Orchestration Import Export API wird in einer Swagger-Datei beschrieben, die [hier](https://adobedocs.github.io/JourneyAPI/docs/)verfügbar ist.

Um diese API mit Ihrer Journey Orchestration-Instanz zu verwenden, müssen Sie die AdobeI/O-Konsole verwenden. Sie können damit beginnen, indem Sie zuerst [Erste Schritte mit Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) und dann die Abschnitte auf dieser Seite befolgen.

Um Ihre Integration zu testen und vorzubereiten, steht Ihnen [hier](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json) eine Postman-Kollektion zur Verfügung.


## Export-Import-Fluss

Wir empfehlen, die folgenden Schritte auszuführen, um Ihre Reisen über Umgebung hinweg zu exportieren und zu importieren:

1. Erstellen und parametrieren Sie eine Reise in Ihrer Beginn-Umgebung. [Weitere Informationen hier](https://docs.adobe.com/content/help/de-DE/journeys/using/building-journeys/about-journey-building/journey.html)
1. Überprüfen Sie, ob die Reiseversion keinen Fehler enthält. [Weitere Informationen hier](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/testing-the-journey.html)
1. Rufen Sie **/Liste/Reise** API auf, um die UID-Reise und die UID Ihrer neuesten Reiseversion abzurufen. Bei Bedarf können Sie die UID Ihrer aktuellen Reiseversion anrufen **/Reisen/`{uid}`/zuletzt** .
1. Rufen Sie die **Export** -API mit Ihren Parametern für die Umgebung des Beginns auf (orgID und sandboxName).
1. Öffnen Sie die Rückgabenutzlast und überprüfen Sie dann die folgenden Elemente:
   * Wenn Ihre exportierte Reise **bestimmte Anmeldeinformationen** enthält, müssen Sie diese durch die der neuen Umgebung entsprechenden Anmeldeinformationen ersetzen.
   * Wenn Ihre exportierte Reise **Ereignis** enthält, die auf ein **XDM-Schema** verweisen, müssen Sie die Schema-ID-Referenz manuell mit der Schema-ID der neuen Umgebung im Knoten xdmEntity aktualisieren, wenn die IDs unterschiedlich sind. Diese Aktualisierung muss für jedes Ereignis durchgeführt werden. [Weitere Informationen hier](https://docs.adobe.com/content/help/en/journeys/using/events-journeys/experience-event-schema.html)
   * Wenn Ihre Reise E-Mail-, SMS- oder Push-Aktionen enthält, müssen Sie möglicherweise den Vorlagennamen oder den mobileApp-Namen aktualisieren, wenn der Name in der Umgebung &quot;Zielgruppe&quot;sich von dem in der Umgebung &quot;Beginn&quot;unterscheidet.
1. Rufen Sie die **Import** -API mit Ihrer Zielgruppe-Umgebung auf. Beachten Sie, dass Sie die Import-API so oft aufrufen können, wie Sie möchten. Die UUID und der Name der einzelnen Knoten, die in der Reise enthalten sind, werden jedes Mal generiert, wenn Sie die Import-API aufrufen.
1. Sobald die Reise importiert wurde, können Sie sie in der neuen Sandbox oder Umgebung veröffentlichen.


## Authentifizierung

### Einrichten von API-Zugriff

Der Zugriff auf die Journey Orchestration-API wird wie folgt eingerichtet: Jeder dieser Schritte wird in der [Adobe I/O-Dokumentation](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) beschrieben.

>[!CAUTION]
>
>Wenn Sie Zertifikate in Adobe I/O verwalten möchten, vergewissern Sie sich, dass Sie in der Admin Console über <b>Systemadministrator</b>-Rechte für das Unternehmen oder ein [Entwicklerkonto](https://helpx.adobe.com/de/enterprise/using/manage-developers.html) verfügen.

1. **Überprüfen Sie, ob Sie ein digitales Zertifikat haben**, oder erstellen Sie bei Bedarf eines. Die mit dem Zertifikat bereitgestellten öffentlichen und privaten Schlüssel werden in den folgenden Schritten benötigt.
1. **Erstellen Sie eine neue Integration mit dem[!DNL Journey Orchestration]-Service** in Adobe I/O und konfigurieren Sie sie. Der Produktzugriff auf das Profil ist für Journey Orchestration und Adobe Experience Platform erforderlich. Dann werden Ihre Zugangsdaten generiert (API-Schlüssel, Client-Geheimnis...).
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



## Beschreibung der Import-API exportieren

Mit dieser API können Sie eine Reiseversion und alle zugehörigen Objekte (Reise, Ereignisse, Datenquellen, Feldgruppen, benutzerdefinierte Aktionen) nach ihrer ID exportieren.
Die resultierende Nutzlast kann verwendet werden, um die Reiseversion in eine andere Umgebung (Sandbox oder Instanz) zu importieren.

| Vorgehensweise | Pfad | Beschreibung |
|---|---|---|
| `[POST]` | /travelVersions/import | Importieren Sie Inhalt einer Reiseversion, der aus einem Export einer Reiseversion resultiert. |
| `[GET]` | /travelVersions/`{uid}`/export | Eine Reiseversion exportieren |
| `[GET]` | /travel/`{uid}`/last | Die aktuellste Reiseversion für eine Reise |
| `[POST]` | /Liste/Reisen | Liste der Metadaten der Reisen und der Reiseversionen |


### Ausfuhrmerkmale und Garantien

* Die Anmeldeinformationen werden nicht exportiert und ein Platzhalter (z. B. INSERT_SECRET_HERE) wird eingefügt.
Nach dem Payload-Export müssen Sie die neuen Anmeldeinformationen (entsprechend der Zielgruppe-Umgebung) manuell einfügen, bevor Sie die Payload in die Zielgruppe-Umgebung importieren.

* Wenn die Datenquelle den Parameter **buildIn:true** enthält, müssen Sie &quot;INSERT_SECRET_HERE&quot;nicht ersetzen. Dies ist eine Systemdatenquelle, die automatisch von der Umgebung der Reise verwaltet wird.

* Die folgenden Objekte werden exportiert, sie werden jedoch nie in die Zielgruppe-Umgebung importiert:
   * **DataProviders**:  acsDataProvider und acppsDataProvider
   * **Feldgruppen**: acppsFieldGroup
   * **Benutzerdefinierte Aktionen**: acsAction

* Die Reise muss vor dem Export gültig sein.

### Einfuhrmerkmale

* Während des Imports werden die Reiseobjekte mit einer neuen UUID und einem neuen Namen erstellt, um die Eindeutigkeit in der Umgebung der Zielgruppe (Instanz oder Sandbox) sicherzustellen.

* Wenn die Import-Payload geheime Platzhalter enthält, wird ein Fehler ausgegeben. Sie müssen die Anmeldeinformationen vor dem Aufruf der POST ersetzen, um die Reise zu importieren.

## Warnung und Fehler

Mögliche Fehler sind:

* Bei **Export**: error 500

* Wenn die Payload zum **Zeitpunkt** des Imports nach Änderungen nicht gültig ist oder wenn die Anmeldeinformationen in der Payload nicht genau definiert sind: error 400

* Wenn Sie nach dem Importschritt versuchen, die Reise in der Umgebung Zielgruppe zu veröffentlichen, ohne die XDM-Schema-ID für Ihre Ereignis zu ändern, wird ein Fehler angezeigt.

