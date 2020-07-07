---
title: Arbeiten mit Adobe Campaign
description: Erfahren Sie mehr über Adobe Campaign-Aktionen
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6685565797a6cdc43b9c8fc39c9354ae6d213f1f
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 40%

---


# Arbeiten mit Adobe Campaign {#using_adobe_campaign_standard}

Mit den Transaktionsnachrichten von Adobe Campaign Standard können Sie E-Mails, Push-Benachrichtigungen und SMS senden.

Für [!DNL Journey Orchestration] steht eine vordefinierte Aktion zur Verfügung, die die Verbindung mit Adobe Campaign Standard ermöglicht. 

Die Transaktionsnachricht des Campaign Standards und das zugehörige Ereignis müssen veröffentlicht werden, damit sie in der Journey Orchestration verwendet werden können. Wenn das Ereignis veröffentlicht wird, die Meldung jedoch nicht, wird sie nicht in der Benutzeroberfläche der Journey Orchestration angezeigt. Wenn die Nachricht veröffentlicht wird, das zugehörige Ereignis jedoch nicht, wird sie in der Benutzeroberfläche der Journey Orchestration angezeigt, sie kann jedoch nicht verwendet werden.

>[!NOTE]
>
>Um zu vermeiden, dass Adobe Campaign Standard-Transaktionsnachrichten überladen werden, wird empfohlen, eine **Deckelungsregel** für die Campaign Standard-Integration einzurichten.
>
>Lesen Sie mehr über SLAs für Transaktionsnachrichten in der [Produktbeschreibung](https://helpx.adobe.com/de/legal/product-descriptions/campaign-standard.html)des Adobe Campaign Standards.

Im Folgenden werden die Konfigurationsschritte beschrieben:

1. Klicken Sie in der Liste **[!UICONTROL Aktionen]** auf die integrierte Aktion **[!UICONTROL AdobeCampaignStandard]**. Der Bereich für die Konfiguration der Aktion wird auf der rechten Seite des Bildschirms geöffnet.

   ![](../assets/actioncampaign.png)

1. Kopieren Sie die URL der Adobe Campaign Standard-Instanz und fügen Sie sie in das Feld **[!UICONTROL URL]** ein.

1. Klicken Sie auf **[!UICONTROL Instanz-URL testen]**, um die Gültigkeit der Instanz zu testen.

   >[!NOTE]
   >
   >Mit diesem Test wird Folgendes überprüft:
   >
   >* Der Host ist &quot;.Kampagne.adobe.com&quot;oder &quot;.Kampagne-Sandbox.adobe.com&quot;,
   >* Die URL-Beginn mit HTTPS,
   >* Der mit der Instanz dieses Adobe Campaign Standards verknüpfte ORG ist identisch mit dem ORG der Journey Orchestration.


When designing your journey, three actions will be available in the **[!UICONTROL Action]** category: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (see [Using Adobe Campaign actions](../building-journeys/using-adobe-campaign-actions.md)). **Mit dem Ereignis** &quot;Reaktionen&quot;können Sie auch auf Nachrichten-Klicks, Öffnen usw. reagieren. (siehe [Ereignisse](../building-journeys/event-activities.md#section_dhx_gss_dgb)zu Reaktionen).

![](../assets/journey58.png)

Wenn Sie zum Senden von Nachrichten ein Drittanbietersystem verwenden, müssen Sie eine benutzerdefinierte Aktion hinzufügen und konfigurieren. See [About custom action configuration](../action/about-custom-action-configuration.md).
