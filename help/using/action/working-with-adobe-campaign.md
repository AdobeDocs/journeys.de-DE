---
product: adobe campaign
solution: Journey Orchestration
title: Arbeiten mit Adobe Campaign
description: Erfahren Sie mehr über Adobe Campaign-Aktionen
translation-type: tm+mt
source-git-commit: 723c30865a5039bd68a8ac2e45d4c87a760e694d
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 97%

---


# Arbeiten mit Adobe Campaign {#using_adobe_campaign_standard}

Mit den Transaktionsnachrichten von Adobe Campaign Standard können Sie E-Mails, Push-Benachrichtigungen und SMS senden.

Für [!DNL Journey Orchestration] steht eine native Aktion zur Verfügung, die die Verbindung mit Adobe Campaign Standard ermöglicht. 

Die Transaktionsnachricht in Campaign Standard und das zugehörige Ereignis müssen veröffentlicht werden, damit sie in Journey Orchestration verwendet werden können. Wenn das Ereignis veröffentlicht wird, die Nachricht jedoch nicht, wird sie nicht in der Benutzeroberfläche von Journey Orchestration angezeigt. Wenn die Nachricht veröffentlicht wird, das zugehörige Ereignis jedoch nicht, wird sie in der Benutzeroberfläche von Journey Orchestration angezeigt, sie kann jedoch nicht verwendet werden.

>[!NOTE]
>
>Transaktionsnachrichten in Adobe Campaign Standard sind für eine bestimmte Instanz auf maximal 50.000 Nachrichten pro Stunde über alle Kanäle hinweg begrenzt. Um das Risiko einer Überlastung zu verringern, empfehlen wir, eine **Begrenzungsregel** für die Campaign Standard-Integration einzurichten.
>
>Lesen Sie mehr über Service-Level-Vereinbarungen für Transaktionsnachrichten in der [Produktbeschreibung von Adobe Campaign Standard](https://helpx.adobe.com/de/legal/product-descriptions/campaign-standard.html).

Im Folgenden werden die Konfigurationsschritte beschrieben:

1. Klicken Sie in der Liste **[!UICONTROL Aktionen]** auf die integrierte Aktion **[!UICONTROL AdobeCampaignStandard]**. Der Bereich für die Konfiguration der Aktion wird auf der rechten Seite des Bildschirms geöffnet.

   ![](../assets/actioncampaign.png)

1. Kopieren Sie die URL der Adobe Campaign Standard-Instanz und fügen Sie sie in das Feld **[!UICONTROL URL]** ein.

1. Klicken Sie auf **[!UICONTROL Instanz-URL testen]**, um die Gültigkeit der Instanz zu testen.

   >[!NOTE]
   >
   >Dieser Test bestätigt Folgendes:
   >
   >Der Host ist &quot;.Kampagne.adobe.com&quot;, &quot;.Kampagne-sandbox.adobe.com&quot;oder &quot;Kampagne-demo.adobe.com&quot;.
   >
   >die URL beginnt mit https,
   >
   >die mit dieser Adobe Campaign Standard-Instanz verknüpfte ORG ist identisch mit der ORG von Journey Orchestration.

Bei der Gestaltung Ihrer Journey stehen in der Kategorie **[!UICONTROL Aktion]** drei Aktionen zur Verfügung: **[!UICONTROL E-Mail]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (siehe [Verwenden von Adobe Campaign-Aktionen](../building-journeys/using-adobe-campaign-actions.md)). Das **Reaktionsereignis** ermöglicht es Ihnen auch, auf das Anklicken, Öffnen usw. von Nachrichten zu reagieren (siehe [Reaktionsereignisse](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

Wenn Sie zum Senden von Nachrichten ein Drittanbietersystem verwenden, müssen Sie eine benutzerdefinierte Aktion hinzufügen und konfigurieren. Siehe [Informationen zur Konfiguration einer benutzerdefinierten Aktion](../action/about-custom-action-configuration.md).
