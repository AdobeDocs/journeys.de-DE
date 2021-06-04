---
product: adobe campaign
title: Arbeiten mit Adobe Campaign
description: Erfahren Sie mehr über Adobe Campaign-Aktionen
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: c49908d36ecbc68ae11b5621305f39dd59c67871
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 63%

---

# Arbeiten mit Adobe Campaign {#using_adobe_campaign}

## Verwenden von Adobe Campaign Standard {#using_adobe_campaign_standard}

Mit den Transaktionsnachrichten von Adobe Campaign Standard können Sie E-Mails, Push-Benachrichtigungen und SMS senden.

Für [!DNL Journey Orchestration] steht eine native Aktion zur Verfügung, die die Verbindung mit Adobe Campaign Standard ermöglicht. 

Die Transaktionsnachricht in Campaign Standard und das zugehörige Ereignis müssen veröffentlicht werden, damit sie in Journey Orchestration verwendet werden können. Wenn das Ereignis veröffentlicht wird, die Nachricht jedoch nicht, wird sie nicht in der Benutzeroberfläche von Journey Orchestration angezeigt. Wenn die Nachricht veröffentlicht wird, das zugehörige Ereignis jedoch nicht, wird sie in der Benutzeroberfläche von Journey Orchestration angezeigt, sie kann jedoch nicht verwendet werden.

>[!NOTE]
>
>Für Adobe Campaign Standard-Aktionen wird automatisch eine Begrenzungsregel von 13 Aufrufen pro Sekunde definiert, sobald die Adobe Campaign Standard-Integration eingerichtet ist. Dies entspricht dem offiziellen Umfang von Transaktionsnachrichten in Adobe Campaign Standard.
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
   >Der Host ist „.campaign.adobe.com“, „.campaign-sandbox.adobe.com“, „.campaign-demo.adobe.com“, „.ats.adobe.com“ oder „.adls.adobe.com“.
   >
   >die URL beginnt mit https,
   >
   >die mit dieser Adobe Campaign Standard-Instanz verknüpfte ORG ist identisch mit der ORG von Journey Orchestration.

Bei der Gestaltung Ihrer Journey stehen in der Kategorie **[!UICONTROL Aktion]** drei Aktionen zur Verfügung: **[!UICONTROL E-Mail]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (siehe [Verwenden von Adobe Campaign-Aktionen](../building-journeys/using-adobe-campaign-actions.md)). Das **Reaktionsereignis** ermöglicht es Ihnen auch, auf das Anklicken, Öffnen usw. von Nachrichten zu reagieren (siehe [Reaktionsereignisse](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

Wenn Sie zum Senden von Nachrichten ein Drittanbietersystem verwenden, müssen Sie eine benutzerdefinierte Aktion hinzufügen und konfigurieren. Siehe [Informationen zur Konfiguration einer benutzerdefinierten Aktion](../action/about-custom-action-configuration.md).

## Verwenden von Adobe Campaign v7/v8 {#using_adobe_campaign_v7_v8}

Diese Integration ist für Adobe Campaign Classic v7 ab Version 21.1 und Adobe Campaign v8 verfügbar. Sie ermöglicht den Versand von E-Mails, Push-Benachrichtigungen und SMS mithilfe von Transaktionsnachrichten in Adobe Campaign.

Die Verbindung zwischen der Journey Orchestration- und der Campaign-Instanz wird von Adobe zum Zeitpunkt der Bereitstellung eingerichtet.

Ein durchgängiges Anwendungsbeispiel wird in diesem [Abschnitt](../usecase/campaign-v7-v8-use-case.md) vorgestellt.

Für jede konfigurierte Aktion ist eine Aktionsaktivität in der Journey-Designer-Palette verfügbar. Siehe diesen [Abschnitt](../building-journeys/using-adobe-campaign-actions.md).

### Wichtige Hinweise     

* Es gibt keine Drosselung der Nachrichten. Wir begrenzen die Anzahl der Nachrichten, die versendet werden können, basierend auf unserem aktuellen Campaign SLA auf 50.000/Stunde. Aus diesem Grund sollte Journey Orchestration nur in unitären Anwendungsfällen (einzelne Ereignisse, nicht Segmente) verwendet werden.

* Sie müssen für jede Vorlage, die Sie verwenden möchten, eine Aktion auf der Arbeitsfläche konfigurieren. Sie müssen für jede Vorlage, die Sie in Adobe Campaign verwenden möchten, eine Aktion in Journey Orchestration konfigurieren.

* Es wird empfohlen, eine dedizierte Message-Center-Instanz zu verwenden, die für diese Integration gehostet wird, um mögliche andere Campaign-Vorgänge nicht zu beeinträchtigen. Der Marketing-Server kann gehostet oder On-Premise bereitgestellt werden. Der erforderliche Build ist Release-Kandidat 21.1 oder höher.

* Es gibt keine Überprüfung, ob die Payload- oder die Campaign-Nachricht korrekt ist.

* Sie können keine Kampagnenaktion mit einem Segmentqualifikationsereignis verwenden.

### Voraussetzungen

In Campaign müssen Sie eine Transaktionsnachricht und das zugehörige Ereignis erstellen und veröffentlichen. Weitere Informationen finden Sie in der [Adobe Campaign-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=de#transactional-messaging).

Sie können Ihre JSON-Nutzlast entsprechend den folgenden Mustern für jede Nachricht erstellen. Sie fügen diese Payload dann beim Konfigurieren der Aktion in Journey Orchestration ein (siehe unten)

Hier ein Beispiel:

```
{
    "channel": "email",
    "eventType": "welcome",
    "email": "example@adobe.com",
    "ctx": {
        "firstName": "John"
    }
}
```

* **channel**: den für Ihre Campaign-Transaktionsvorlage definierten Kanal
* **eventType**: den internen Namen Ihres Campaign-Ereignisses
* **ctx**: -Variable basierend auf der Personalisierung, die Sie in Ihrer Nachricht haben.

### Konfigurieren der Aktion

In Journey Orchestration müssen Sie eine Aktion pro Transaktionsnachricht konfigurieren. Führen Sie folgende Schritte aus:

1. Erstellen Sie eine neue Aktion. Siehe diesen [Abschnitt](../action/action.md).
1. Geben Sie einen Namen und eine Beschreibung ein.
1. Wählen Sie im Feld **Aktionstyp** **Adobe Campaign Classic** aus.
1. Klicken Sie in das Feld **Payload** und fügen Sie ein Beispiel der JSON-Payload ein, die der Campaign-Nachricht entspricht. Wenden Sie sich an Adobe, um diese Payload zu erhalten.
1. Passen Sie die verschiedenen Felder je nach gewünschter Zuordnung auf der Journey-Arbeitsfläche als statisch oder variabel an. Bestimmte Felder, wie z. B. Kanalparameter für E-Mail-Adressen- und Personalisierungsfelder (ctx), sollten wahrscheinlich als Variablen für die Zuordnung im Kontext der Journey definiert werden.
1. Klicken Sie auf **Speichern**.

![](../assets/accintegration1.png)


