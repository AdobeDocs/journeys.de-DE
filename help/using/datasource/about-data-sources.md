---
product: adobe campaign
title: Informationen zu Datenquellen
description: 'Erfahren Sie, wie Sie eine Datenquelle konfigurieren '
feature: Journeys
role: User
level: Intermediate
exl-id: 2371d2c9-3035-46ac-9c76-755fb453c24e
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 97%

---

# Informationen zu Datenquellen {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="Informationen zu Datenquellen"
>abstract="Mit der Datenquellenkonfiguration können Sie eine Verbindung zu einem System definieren, um zusätzliche Informationen zur Verwendung in Ihren Journeys abzurufen."

Mit der Datenquellenkonfiguration können Sie eine Verbindung zu einem System definieren, um zusätzliche Informationen abzurufen, die in Ihren Journeys verwendet werden, zum Beispiel für:

* [Definition von Bedingungen](../building-journeys/condition-activity.md)
* Parameter- und Personalisierungsdaten in [Aktionen](../action/action.md)
* [Definition benutzerdefinierter Wartezeiten](../building-journeys/wait-activity.md#custom)
* [Definition von Zeitzonen](../building-journeys/timezone-management.md)

Diese Konfiguration ist nicht erforderlich, wenn Ihre Journeys nur lokale Daten aus einer Ereignis-Payload nutzen. Wenn Ihre Journey beispielsweise aus einem Ereignis und einer E-Mail-Aktivität besteht, die nur Daten aus dem Ereignis verwendet, müssen Sie keine Datenquelle konfigurieren.

Es gibt zwei Arten von Datenquellen:

* Die vorkonfigurierte Datenquelle von Adobe Experience Platform, die die Verbindung zum Echtzeit-Kundenprofildienst definiert. Dies ist eine integrierte Datenquelle. Weitere Informationen finden Sie auf [dieser Seite](../datasource/adobe-experience-platform-data-source.md).
* Die externen Datenquellen, mit denen Sie eine Verbindung zu externen Systemen definieren können. Diese können Sie erstellen. Weitere Informationen finden Sie auf [dieser Seite](../datasource/external-data-sources.md).

Für jede Datenquelle definieren Sie die Informationen, die mit Feldergruppen abgerufen werden sollen. Feldergruppen sind Gruppen von Feldern, die aus einer Datenquelle abgerufen werden können. Weitere Informationen finden Sie auf [dieser Seite](../datasource/field-groups.md).

Weitere Informationen zum Konfigurieren einer Adobe Experience Platform-Datenquelle und einer externen Datenquelle sowie zum Suchen und Verwenden von Daten in einer Journey finden Sie in diesem [Tutorial-Video](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/configure-data-sources.html).

Im Folgenden finden Sie die wichtigsten Schritte zur Konfiguration der Datenquelle:

>[!NOTE]
>
>Die Konfiguration von Datenquellen wird immer von einem **technischen Anwender** durchgeführt.

1. Klicken Sie oben im Menü auf den Tab **[!UICONTROL Datenquellen]**.

   Die Liste der Datenquellen wird angezeigt. Weitere Informationen zur Benutzeroberfläche finden Sie auf [dieser Seite](../about/user-interface.md).

   ![](../assets/journey18.png)

1. Anschließend können Sie der integrierten Datenquelle entweder Feldergruppen hinzufügen (siehe [diese Seite](../datasource/adobe-experience-platform-data-source.md)) oder eine neue Datenquelle (siehe [diese Seite](../datasource/external-data-sources.md)) und die assoziierten Feldergruppen (siehe [diese Seite](../datasource/field-groups.md)) hinzufügen.

   ![](../assets/journey23.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   Die Datenquelle ist jetzt konfiguriert und kann in Ihren Journeys verwendet werden.
