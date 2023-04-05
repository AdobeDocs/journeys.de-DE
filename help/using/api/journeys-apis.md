---
product: adobe campaign
title: Erste Schritte mit Journey-APIs
description: Weitere Informationen zu Journey-APIs
products: journeys
feature: Journeys
role: User
level: Intermediate
source-git-commit: fa493cf1e856378e4d79a6932c30cebf5e11e028
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 47%

---

# Erste Schritte mit Journey-APIs

## Informationen zu Begrenzungs- und Einschränkungs-APIs

Beim Konfigurieren einer Datenquelle oder einer Aktion stellen Sie eine Verbindung zu einem System her, um entweder zusätzliche Informationen abzurufen, die in Ihren Journey verwendet werden, oder Nachrichten oder API-Aufrufe zu senden.

Journey-APIs unterstützen bis zu 5.000 Ereignisse pro Sekunde, einige externe Systeme oder APIs weisen jedoch möglicherweise keinen gleichwertigen Durchsatz auf. Um eine Überlastung dieser Systeme zu vermeiden, können Sie die **Begrenzung** und **Einschränken** APIs zur Begrenzung der Anzahl der pro Sekunde gesendeten Ereignisse.

Jedes Mal, wenn Journey einen API-Aufruf ausführen, wird er über die API-Engine weitergeleitet. Wenn das in der API festgelegte Limit erreicht wird, wird der Aufruf entweder abgelehnt, wenn Sie die Capping-API verwenden, oder bis zu sechs Stunden in die Warteschlange gestellt und so bald wie möglich in der Reihenfolge verarbeitet, in der sie empfangen wurden, wenn Sie die Drosselungs-API verwenden.

Nehmen wir beispielsweise an, Sie haben eine Begrenzungs- oder Einschränkungsregel von 100 Aufrufen pro Sekunde für Ihr externes System definiert. Eine benutzerdefinierte Aktion führt in 10 verschiedenen Journeys Aufrufe an Ihr System aus. Wenn eine Journey 200 Aufrufe pro Sekunde erhält, werden die 100 verfügbaren Slots verwendet und die 100 verbleibenden Slots verworfen oder in die Warteschlange gestellt. Da die Höchstrate überschritten wurde, sind für die anderen 9 Journeys keine Slots mehr übrig. Durch diese Granularität ist das externe System vor Überlastung und Abstürzen geschützt.

>[!IMPORTANT]
>
>**Begrenzungsregeln** werden auf Sandbox-Ebene für einen bestimmten Endpunkt (die URL genannt) konfiguriert, aber global für alle Journey dieser Sandbox.
>
>**Einschränkungsregeln** werden nur für Produktions-Sandboxes konfiguriert, für einen bestimmten Endpunkt, aber global für alle Journey über alle Sandboxes hinweg. Pro Organisation kann nur eine Einschränkungskonfiguration verwendet werden.

Weitere Informationen zum Arbeiten mit diesen APIs finden Sie in diesen Abschnitten:

* [Capping-API](capping.md)
* [Einschränkungs-API](throttling.md)

Beide APIs werden auch in einer Swagger-Datei beschrieben, die verfügbar ist. [here](https://adobedocs.github.io/JourneyAPI/docs/).

## Kapazität von Datenquellen und benutzerdefinierten Aktionen {#capacity}

Für **externe Datenquellen** festgelegt ist, ist die maximale Anzahl von Anrufen pro Sekunde auf 15 beschränkt. Wenn diese Grenze überschritten wird, werden alle zusätzlichen Aufrufe je nach verwendeter API entweder verworfen oder in die Warteschlange gestellt. Es ist möglich, diesen Grenzwert für private externe Datenquellen zu erhöhen, indem Sie sich an die Adobe wenden, um den Endpunkt in die Zulassungsliste aufzunehmen. Dies ist jedoch keine Option für öffentliche externe Datenquellen. * [Erfahren Sie, wie Sie Datenquellen konfigurieren](../datasource/about-data-sources.md).

>[!NOTE]
>
>Wenn eine Datenquelle eine benutzerdefinierte Authentifizierung mit einem anderen Endpunkt als dem verwendet, der für die Datenquelle verwendet wird, müssen Sie sich an Adobe wenden, um diesen Endpunkt ebenfalls in die Zulassungsliste aufzunehmen.

Für **benutzerdefinierte Aktionen** müssen Sie die Kapazität Ihrer externen API bewerten. Wenn Journey Optimizer beispielsweise 1000 Aufrufe pro Sekunde sendet und Ihr System nur 100 Aufrufe pro Sekunde unterstützen kann, müssen Sie eine Begrenzungs- oder Drosselkonfiguration definieren, damit Ihr System nicht überfordert wird. [Erfahren Sie, wie Sie Aktionen konfigurieren](../action/action.md)

## Einrichten von API-Zugriff {#api}

So verwenden Sie diese APIs mit Ihren [!DNL Journey Orchestration] müssen Sie die Adobe I/O-Konsole verwenden. Der API-Zugriff für [!DNL Journey Orchestration] wird wie folgt eingerichtet: Jeder dieser Schritte wird in der [Adobe I/O-Dokumentation](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) beschrieben.

>[!CAUTION]
>
>Wenn Sie Zertifikate in Adobe I/O verwalten möchten, vergewissern Sie sich, dass Sie in der Admin Console über <b>Systemadministrator</b>-Rechte für das Unternehmen oder ein [Entwicklerkonto](https://helpx.adobe.com/de/enterprise/using/manage-developers.html) verfügen.

1. **Überprüfen Sie, ob Sie ein digitales Zertifikat haben**, oder erstellen Sie bei Bedarf eines. Die mit dem Zertifikat bereitgestellten öffentlichen und privaten Schlüssel werden in den folgenden Schritten benötigt.
1. **Erstellen Sie eine neue Integration mit dem [!DNL Journey Orchestration]-Service** in Adobe I/O und konfigurieren Sie sie. Der Produktprofilzugriff wird für [!DNL Journey Orchestration] und Adobe Experience Platform benötigt. Dann werden Ihre Zugangsdaten generiert (API-Schlüssel, Client-Geheimnis...).
1. **Erstellen Sie einen JSON-Web-Token (JWT)** aus den zuvor erstellten Anmeldedaten und signieren Sie ihn mit Ihrem privaten Schlüssel. Der JWT kodiert alle Identitäts- und Sicherheitsdaten, die Adobe zum Überprüfen Ihrer Identität und zum Erteilen des Zugriffs auf die API benötigt. Dieser Schritt wird in diesem [Abschnitt](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) genau beschrieben.
1. **Ersetzen Sie Ihr JWT durch einen Zugriffstoken**, und zwar über eine POST-Anfrage oder über die Developer Console-Oberfläche. Dieser Zugriffstoken muss in allen Kopfzeilen Ihrer API-Anfragen verwendet werden.

Um eine sichere Service-to-Service-Adobe I/O-API-Sitzung herzustellen, muss jede Anfrage an einen Adobe-Dienst folgende Informationen in der Autorisierungskopfzeile umfassen.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**: Dies ist Ihre persönliche Organisationskennung. Eine Organisationskennung wird von der Adobe für jede Ihrer Instanzen bereitgestellt. Wenden Sie sich an Ihren Administrator oder Ihren technischen Ansprechpartner bei Adobe, um den Wert Ihrer Organisationskennung zu erhalten. Sie können sie auch beim Erstellen einer neuen Integration in Adobe I/O abrufen, und zwar in der Lizenzliste (siehe <a href="https://www.adobe.io/authentication.html">Adobe I/O-Dokumentation</a>).

* **&lt;ACCESS_TOKEN>**: Ihr persönlicher Zugriffstoken, der beim Austausch Ihres JWT über eine POST-Anfrage abgerufen wurde.

* **&lt;API_KEY>**: Ihr persönlicher API-Schlüssel. Er wird in Adobe I/O bereitgestellt, nachdem eine neue Integration mit dem [!DNL Journey Orchestration]-Service erstellt wurde.
