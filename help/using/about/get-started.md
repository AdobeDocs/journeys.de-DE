---
title: Erste Schritte
description: Entdecken Sie die wichtigsten Schritte zum Einrichten von Journey Orchestration und zum Aufbau Ihrer ersten Journey.
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e353d593ab2710f50a88a3715378c86c2e37b4f6
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 92%

---


# Erste Schritte{#concept_y4b_4qt_52b}

Bei [!DNL Journey Orchestration] gibt es zwei Arten von Benutzern, die jeweils eigene Aufgaben erledigen: den **technischen Anwender** und den **Business-Anwender**. Der Benutzerzugriff wird mithilfe von Produktprofilen und Berechtigungen verwaltet. Refer to [this page](../about/access-management.md) to learn how to configure user access.

Im Folgenden finden Sie die wichtigsten Schritte zum Konfigurieren und Verwenden von [!DNL Journey Orchestration]:

1. **Ereignis konfigurieren**

   Sie müssen die erwarteten Informationen sowie deren Verarbeitungsmethode definieren. Die Konfiguration ist obligatorisch. Dieser Schritt wird von einem **technischen Anwender** ausgeführt.

   Weiterführende Informationen hierzu finden Sie auf dieser [Seite](../event/about-events.md).

   ![](../assets/journey7.png)

1. **Konfigurieren der Datenquelle**

   Sie müssen eine Verbindung zu einem System definieren, um zusätzliche Informationen abrufen zu können, die bei Ihren Journeys verwendet werden (z. B. in Ihren Bedingungen). Außerdem wird zur Bereitstellungszeit eine integrierte Adobe Experience Platform-Datenquelle konfiguriert. Dieser Schritt ist nicht erforderlich, wenn Sie ausschließlich Daten aus den Ereignissen Ihrer Journey nutzen. Dieser Schritt wird von einem **technischen Anwender** ausgeführt.

   Weiterführende Informationen hierzu finden Sie auf dieser [Seite](../datasource/about-data-sources.md).

   ![](../assets/journey22.png)

1. **Konfigurieren einer Aktion**

   Wenn Sie zum Versand Ihrer Nachrichten ein Drittanbietersystem verwenden möchten, müssen Sie dessen Verbindung zu [!DNL Journey Orchestration] konfigurieren. Weiterführende Informationen finden Sie auf [dieser Seite](../action/about-custom-action-configuration.md).

   Wenn Sie Adobe Campaign Standard zum Senden von Nachrichten verwenden möchten, müssen Sie die integrierte Aktion konfigurieren. Weiterführende Informationen finden Sie auf [dieser Seite](../action/working-with-adobe-campaign.md).

   Diese Schritte werden von einem **technischen Anwender** ausgeführt.

   ![](../assets/custom2.png)

1. **Gestalten Ihrer Journey**

   Kombinieren Sie die verschiedenen Ereignis-, Orchestrierungs- und Aktionsaktivitäten, um Ihre mehrstufigen kanalübergreifenden Szenarien zu erstellen. Dieser Schritt wird von einem **Business-Anwender** ausgeführt.

   Weiterführende Informationen hierzu finden Sie auf [dieser Seite](../building-journeys/journey.md).

   ![](../assets/journeyuc2_24.png)

1. **Testen und Veröffentlichen der Journey**

   Sie müssen die Journey validieren und aktivieren. Dieser Schritt wird von einem **Business-Anwender** ausgeführt.

   Weitere Informationen finden Sie auf den Seiten [Testen der Reise](../building-journeys/testing-the-journey.md) und [Veröffentlichen der Reise](../building-journeys/publishing-the-journey.md).

   ![](../assets/journeyuc2_32bis.png)

1. **Überwachen Ihrer Journey**

   Verwenden Sie die dedizierten Reporting-Tools, um zu messen, ob Ihre Journey effektiv ist. Dieser Schritt wird von einem **Business-Anwender** ausgeführt.

   Weiterführende Informationen hierzu finden Sie auf [dieser Seite](../reporting/about-journey-reports.md).

   ![](../assets/dynamic_report_journey_12.png)

