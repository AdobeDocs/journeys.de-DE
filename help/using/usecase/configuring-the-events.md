---
product: adobe campaign
title: Konfigurieren der Ereignisse
description: Erfahren Sie, wie Sie die Ereignisse für die Journey mit dem erweiterten Anwendungsfall konfigurieren
feature: Journeys
role: User
level: Intermediate
exl-id: 90139c72-8fae-4e6e-a79b-7c510f41fe38
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 100%

---

# Konfigurieren der Ereignisse {#concept_sbp_5cy_w2b}

In unserem Szenario soll jedes Mal, wenn eine Person das Marlton-Hotel sowie das Restaurant betritt, ein Ereignis empfangen werden. Der **technische Anwender** konfiguriert die beiden Ereignisse, auf die das System in unserer Journey überwachen soll.

Weitere Informationen zur Ereigniskonfiguration finden Sie auf [dieser Seite](../event/about-events.md).

1. Klicken Sie im oberen Menü auf den Tab **[!UICONTROL Ereignisse]** und dann auf **[!UICONTROL Hinzufügen]**, um ein neues Ereignis zu erstellen.

   ![](../assets/journeyuc1_1.png)

1. Geben Sie den Namen ohne Leer- oder Sonderzeichen ein: „LobbyBeacon“.

   ![](../assets/journeyuc2_1.png)

1. Wählen Sie anschließend das Schema aus und definieren Sie die für das Ereignis erwartete Payload. Wählen Sie die erforderlichen Felder aus dem mit XDM normalisierten Modell. Sie benötigen die Experience Cloud-ID, um die Person in der Echtzeit-Kundenprofildatenbank zu identifizieren: endUserIDs > _experience > mcid > id.

   Außerdem benötigen Sie das Anmeldetoken, um Push-Benachrichtigungen senden zu können: _experience > campaign > message > profile > pushNotificationTokens > token.

   Für dieses Ereignis wird automatisch eine ID generiert. Diese ID wird im Feld **[!UICONTROL eventID]** gespeichert (_experience > campaign > orchestration > eventID). Das System, das das Ereignis per Push sendet, sollte keine ID generieren, sondern die ID verwenden, die in der Payload-Vorschau verfügbar ist. In unserem Anwendungsfall dient diese ID zur Identifizierung des Beacon-Standorts. Jedes Mal, wenn eine Person den Lobby-Beacon passiert, wird ein Ereignis mit dieser bestimmten Ereignis-ID gesendet. Dasselbe gilt auch für Ereignisse für den Restaurant-Beacon. So kann das System erkennen, welcher Beacon das Senden des Ereignisses ausgelöst hat.

   ![](../assets/journeyuc2_2.png)

   >[!NOTE]
   >
   >Die Liste der Felder variiert von Schema zu Schema. Gemäß der Schemadefinition können einige Felder obligatorisch und vorausgewählt sein.

1. Ein Namespace muss ausgewählt werden. Basierend auf Schemaeigenschaften ist schon vorab ein Namespace ausgewählt. Sie können die Auswahl beibehalten. Weitere Informationen zu Namespaces finden Sie auf [dieser Seite](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc2_4.png)

1. Je nach den Schemaeigenschaften und dem ausgewählten Namespace wird ein Schlüssel vorausgewählt. Sie können ihn beibehalten.

   ![](../assets/journeyuc2_4bis.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

1. Klicken Sie auf das Symbol **[!UICONTROL Payload zeigen]**, um eine Vorschau der vom System erwarteten Payload anzuzeigen und mit der Person zu teilen, die für das Senden des Ereignisses verantwortlich ist.  Diese Payload muss im Postback der Mobile Services-Administrationskonsole konfiguriert werden.

   ![](../assets/journeyuc2_5.png)

Auf gleiche Weise erstellen Sie das Ereignis „RestaurantBeacon“. Ihre beiden Beacon-Ereignisse wurden erstellt und können nun in der Journey genutzt werden. Jetzt müssen Sie die App so konfigurieren, dass sie die erwartete Payload an den Endpunkt der Streaming-Aufnahme-APIs senden kann. Weitere Informationen finden Sie auf [dieser Seite](../event/additional-steps-to-send-events-to-journey-orchestration.md).
