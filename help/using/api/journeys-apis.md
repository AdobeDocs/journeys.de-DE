---
product: adobe campaign
title: Erste Schritte mit Journeys-APIs
description: Erfahren Sie mehr über Journeys-APIs
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: a5dd3d23-c820-4ab7-bc6c-b1dcfe15022c
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 94%

---

# Erste Schritte mit Journeys-APIs


>[!CAUTION]
>
>**Suche nach Adobe Journey Optimizer**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um die Dokumentation zu Journey Optimizer anzuzeigen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Account-Team, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._


## Über Begrenzungs- und Drosselungs-APIs

Beim Konfigurieren einer Datenquelle oder einer Aktion stellen Sie eine Verbindung zu einem System her, um entweder zusätzliche Informationen abzurufen, die in Ihren Journeys verwendet werden, oder um Nachrichten oder API-Aufrufe zu senden.

Journey-APIs unterstützen bis zu 5.000 Ereignisse pro Sekunde, einige externe Systeme oder APIs weisen jedoch möglicherweise nicht den entsprechenden Durchsatz auf. Um eine Überlastung dieser Systeme zu vermeiden, können Sie die APIs für **Begrenzung** und **Drosselung** zum Begrenzen der Anzahl der pro Sekunde gesendeten Ereignisse verwenden.

Jedes Mal, wenn Journeys einen API-Aufruf ausführen, wird er über die API-Engine weitergeleitet. Wenn das in der API festgelegte Limit erreicht wird, wird der Aufruf entweder abgelehnt, falls Sie die Begrenzungs-API verwenden, oder für bis zu 6 Stunden in die Warteschlange gestellt und so bald wie möglich in der Reihenfolge verarbeitet, in der die Aufrufe empfangen wurden, falls Sie die Drosselungs-API verwenden.

Nehmen wir beispielsweise an, Sie haben eine Begrenzungs- oder Drosselungsregel von 100 Aufrufen pro Sekunde für Ihr externes System definiert. Eine benutzerdefinierte Aktion führt in 10 verschiedenen Journeys Aufrufe an Ihr System aus. Wenn eine Journey 200 Aufrufe pro Sekunde erhält, verwendet sie die 100 verfügbaren Slots und verwirft die 100 verbleibenden Slots oder stellt sie in die Warteschlange. Da die Höchstrate überschritten wurde, sind für die anderen 9 Journeys keine Slots mehr übrig. Durch diese Granularität ist das externe System vor Überlastung und Abstürzen geschützt.

>[!IMPORTANT]
>
>**Begrenzungsregeln** werden auf Sandbox-Ebene für einen bestimmten Endpunkt (die aufgerufene URL), jedoch global für alle Journeys dieser Sandbox konfiguriert.
>
>**Drosselungsregeln** werden nur für Produktions-Sandboxes und für einen bestimmten Endpunkt konfiguriert, jedoch global für alle Journeys über alle Sandboxes hinweg. Pro Organisation kann nur eine Drosselungskonfiguration verwendet werden.

Weiterführende Informationen zur Verwendung dieser APIs finden Sie in diesen Abschnitten:

* [Capping-API](capping.md)
* [Drosselungs-API](throttling.md)

Beide APIs werden auch in einer Swagger-Datei beschrieben, die [hier](https://adobedocs.github.io/JourneyAPI/docs/) verfügbar ist.

## Kapazität von Datenquellen und benutzerdefinierten Aktionen {#capacity}

Bei **externen Datenquellen** ist die maximale Anzahl von Aufrufen pro Sekunde auf 15 begrenzt. Wenn diese Grenze überschritten wird, werden alle zusätzlichen Aufrufe je nach verwendeter API entweder verworfen oder in die Warteschlange gestellt. Es ist möglich, diesen Grenzwert für private externe Datenquellen zu erhöhen, indem Sie sich an Adobe wenden, um den Endpunkt in die Zulassungsliste aufzunehmen. Dies ist jedoch keine Option für öffentliche externe Datenquellen. * [Erfahren Sie, wie Sie Datenquellen konfigurieren](../datasource/about-data-sources.md).

>[!NOTE]
>
>Wenn eine Datenquelle eine benutzerdefinierte Authentifizierung mit einem anderen Endpunkt als dem verwendet, der für die Datenquelle verwendet wird, müssen Sie sich an Adobe wenden, um diesen Endpunkt ebenfalls in die Zulassungsliste aufzunehmen.

Für **benutzerdefinierte Aktionen** müssen Sie die Kapazität Ihrer externen API auswerten. Wenn Journey Optimizer beispielsweise 1.000 Aufrufe pro Sekunde sendet und Ihr System nur 100 Aufrufe pro Sekunde unterstützt, müssen Sie eine Begrenzungs- oder Drosselungskonfiguration definieren, damit Ihr System nicht überlastet wird. [Erfahren Sie, wie Sie Aktionen konfigurieren](../action/action.md)

## Einrichten von API-Zugriff {#api}

Um diese API mit Ihrer [!DNL Journey Orchestration]-Instanz verwenden zu können, müssen Sie die Adobe I/O-Konsole verwenden. Der API-Zugriff für [!DNL Journey Orchestration] wird wie folgt eingerichtet: Jeder dieser Schritte wird in der [Adobe I/O-Dokumentation](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) beschrieben.

>[!CAUTION]
>
>Wenn Sie Zertifikate in Adobe I/O verwalten möchten, vergewissern Sie sich, dass Sie in der Admin Console über <b>Systemadministrator</b>-Rechte für das Unternehmen oder ein [Entwicklerkonto](https://helpx.adobe.com/de/enterprise/using/manage-developers.html) verfügen.

1. **Überprüfen Sie, ob Sie ein digitales Zertifikat haben**, oder erstellen Sie bei Bedarf eines. Die mit dem Zertifikat bereitgestellten öffentlichen und privaten Schlüssel werden in den folgenden Schritten benötigt.
1. **Erstellen Sie eine neue Integration mit dem [!DNL Journey Orchestration]-Service** in Adobe I/O und konfigurieren Sie sie. Der Produktprofilzugriff wird für [!DNL Journey Orchestration] und Adobe Experience Platform benötigt. Dann werden Ihre Anmeldedaten generiert (API-Schlüssel, Client-Geheimnis...).

>[!CAUTION]
>
>Die JWT-Methode zum Generieren von Zugriffs-Token wird nicht mehr unterstützt. Alle neuen Integrationen müssen mit der [Authentifizierungsmethode OAuth-Server-zu-Server](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html?lang=de#select-oauth-server-to-server) erstellt werden. Adobe empfiehlt auch, Ihre vorhandenen Integrationen zur OAuth-Methode zu migrieren.
>
>Lesen Sie die folgenden wichtigen Dokumentationen:
>[Handbuch für die Migration Ihrer Anwendungen von JWT zu OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/),
>[Implementierungshandbuch für neue und alte Programme mit OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/),
>[Vorteile der Verwendung der Anmeldemethode OAuth-Server-zu-Server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/#why-oauth-server-to-server-credentials)

Um eine sichere Service-to-Service-Adobe I/O-API-Sitzung herzustellen, muss jede Anfrage an einen Adobe-Dienst folgende Informationen in der Autorisierungskopfzeile umfassen.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>**: Dies ist Ihre persönliche Organisationskennung; von Adobe erhalten Sie für jede Ihrer Instanzen eine Organisationskennung. Wenden Sie sich an Ihren Administrator oder Ihren technischen Ansprechpartner bei Adobe, um den Wert Ihrer Organisationskennung zu erhalten. Sie können sie auch beim Erstellen einer neuen Integration in Adobe I/O abrufen, und zwar in der Lizenzliste (siehe [Adobe I/O-Dokumentation](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)).

* **&lt;ACCESS_TOKEN>**: Ihr persönliches Zugriffs-Token

* **&lt;API_KEY>**: Ihr persönlicher API-Schlüssel. Er wird in Adobe I/O bereitgestellt, nachdem eine neue Integration mit dem [!DNL Journey Orchestration]-Service erstellt wurde.
