---
title: Konfigurieren der Ereignisse
description: Erfahren Sie, wie Sie die Ereignisse für den erweiterten Anwendungsfall konfigurieren
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# Konfigurieren der Ereignisse {#concept_sbp_5cy_w2b}

In unserem Szenario müssen wir jedes Mal, wenn eine Person das Hotel und das Restaurant Marlton betritt, eine Veranstaltung empfangen. Der **technische Benutzer** muss die beiden Ereignisse konfigurieren, auf die das System während unserer Reise hören soll.

Weitere Informationen zur Ereigniskonfiguration finden Sie unter [](../event/about-events.md).

1. Klicken Sie im oberen Menü auf die Registerkarte **[!UICONTROL Ereignisse]**und dann auf**[!UICONTROL  Hinzufügen]** , um ein neues Ereignis zu erstellen.

   ![](../assets/journeyuc1_1.png)

1. Wir geben den Namen ohne Leerzeichen oder Sonderzeichen ein: &quot;LobbyBeacon&quot;.

   ![](../assets/journeyuc2_1.png)

<!--li>Select the **[!UICONTROL Mobile - Streaming Ingestion APIs]** event type. Events are sent from the customers' mobile phone through the Mobile SDK.![](../assets/journeyuc2_3.png" placement="break" width="800" id="image_is5_2sn_z2b"/></li-->

1. Anschließend wählen wir das Schema aus und definieren die für dieses Ereignis erwartete Nutzlast. Wir wählen die erforderlichen Felder aus dem XDM normalisierten Modell. Wir benötigen die Experience Cloud ID, um die Person in der Echtzeit-Kundenprofildatenbank zu identifizieren: &quot;endUserIDs > _experience > mcid > id&quot;.

   Außerdem benötigen wir ein Registrierungstoken, um Push-Nachrichten zu senden: &quot;_experience > campaign > message > profile > pushNotificationTokens > token&quot;

   Für dieses Ereignis wird automatisch eine ID generiert. Diese ID wird im Feld **[!UICONTROL eventID]**(&quot;_experience > campaign > orchestration > eventID&quot;) gespeichert. Das System, das das Ereignis durchführt, sollte keine ID generieren. Es sollte die ID verwenden, die in der Nutzdatenvorschau verfügbar ist. In unserem Anwendungsfall wird diese ID zur Identifizierung des Beacon-Speicherorts verwendet. Jedes Mal, wenn eine Person in der Nähe des Lobby-Beacons geht, wird ein Ereignis mit dieser spezifischen Ereignis-ID gesendet. Dasselbe Prinzip gilt auch für die Beacon-Veranstaltungen im Restaurant. Dadurch kann das System erkennen, welcher Beacon das Senden des Ereignisses ausgelöst hat.

   ![](../assets/journeyuc2_2.png)

   >[!NOTE]
   >
   >Die Feldliste variiert von Schema zu Schema. Gemäß der Schemadefinition können einige Felder obligatorisch und vorausgewählt sein.

1. Wir müssen einen Namespace auswählen. Ein Namespace wird basierend auf Schemaeigenschaften vorab ausgewählt. Sie können die Auswahl beibehalten. Weitere Informationen zu Namespaces finden Sie unter [](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc2_4.png)

1. Ein Schlüssel wird basierend auf den Schemaeigenschaften und dem ausgewählten Namespace vorausgewählt. Du kannst es behalten.

   ![](../assets/journeyuc2_4bis.png)

1. Wählen Sie **[!UICONTROL Speichern]**aus.

1. Klicken Sie auf das Symbol **[!UICONTROL Payload]**anzeigen, um eine Vorschau der vom System erwarteten Nutzlast anzuzeigen und diese an die für das Senden des Ereignisses verantwortliche Person freizugeben.  Diese Nutzlast muss im Postback von Mobile Services Administration Console konfiguriert werden.

   ![](../assets/journeyuc2_5.png)

Auf die gleiche Weise erstellen Sie die Veranstaltung &quot;RestaurantBeacon&quot;. Ihre beiden Beacon-Ereignisse werden erstellt und können jetzt in unserer Reise genutzt werden. Sie müssen die mobile Anwendung jetzt so konfigurieren, dass sie die erwartete Nutzlast an den Endpunkt der Streaming Ingestion APIs senden kann. Näheres wird im Abschnitt [](../event/additional-steps-to-send-events-to-journey-orchestration.md) beschrieben.
