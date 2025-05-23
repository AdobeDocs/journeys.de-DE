---
product: adobe campaign
title: Ereignis erstellen
description: Erfahren Sie, wie Sie ein Ereignis erstellen.
feature: Journeys
role: User
level: Intermediate
exl-id: 2ae8854a-c3e7-469d-9f89-25b54bc3e894
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '612'
ht-degree: 100%

---

# Erstellen eines neuen Ereignisses {#section_tbk_5qt_pgb}


>[!CAUTION]
>
>**Sie möchten mehr über Adobe Journey Optimizer erfahren**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um auf die Journey Optimizer-Dokumentation zuzugreifen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Accountteam, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._


Im Folgenden finden Sie die wichtigsten Schritte zum Konfigurieren eines neuen Ereignisses:

1. Klicken Sie oben im Menü auf den Tab **[!UICONTROL Ereignisse]**. Die Liste der Ereignisse wird angezeigt. Weitere Informationen zur Benutzeroberfläche finden Sie auf [dieser Seite](../about/user-interface.md).

   ![](../assets/journey5.png)

1. Klicken Sie auf **[!UICONTROL Hinzufügen]**, um ein neues Ereignis zu erstellen. Der Bereich für die Ereigniskonfiguration wird auf der rechten Seite des Bildschirms geöffnet. Geben Sie einen Namen für Ihr Ereignis ein. Sie können auch eine Beschreibung hinzufügen.

   ![](../assets/journey6.png)

   >[!NOTE]
   >
   >Verwenden Sie keine Leerzeichen oder Sonderzeichen. Verwenden Sie nicht mehr als 30 Zeichen.

1. Wählen Sie im Feld **[!UICONTROL Ereignis-ID-Typ]** den zu verwendenden Ereignistyp aus.

   ![](../assets/journey6bis.png)

   * **Regelbasierte** Ereignisse: Dieser Ereignistyp generiert keine eventID. Im Feld **Ereignis-ID-Bedingung** definieren Sie einfach eine Regel, die vom System verwendet wird, um die relevanten Ereignisse zu identifizieren, die Ihre Journeys auslösen werden. Diese Regel kann auf einem beliebigen Feld basieren, das in der Ereignis-Payload verfügbar ist, z. B. dem Standort des Profils oder der Anzahl der Artikel, die dem Warenkorb des Profils hinzugefügt wurden.

   * **Systemgenerierte** Ereignisse: dieser Typ erfordert eine eventID. Dieses eventID-Feld wird beim Erstellen des Ereignisses automatisch generiert und der Payload-Vorschau hinzugefügt. Das System, das das Ereignis per Push sendet, sollte keine ID generieren, sondern die ID übergeben, die in der Payload-Vorschau verfügbar ist. Weitere Informationen finden Sie in [diesem Abschnitt](../event/previewing-the-payload.md).

   >[!NOTE]
   >
   >Weitere Informationen zu Ereignistypen finden Sie in [diesem Abschnitt](../event/about-events.md).
1. Die Anzahl der Journeys, die dieses Ereignis verwenden, wird im Feld **[!UICONTROL Verwendet in]** angezeigt. Sie können auf **[!UICONTROL Customer Journeys anzeigen]** klicken, um die Liste der Journeys mit diesem Ereignis anzuzeigen.
1. Definieren Sie das Schema und die Payload-Felder: Hier wählen Sie die Ereignisinformationen aus (normalerweise als Payload bezeichnet), die von [!DNL Journey Orchestration] erwartet werden. Anschließend können Sie diese Informationen in Ihrer Journey verwenden. Weitere Informationen finden Sie auf [dieser Seite](../event/defining-the-payload-fields.md).
   >[!NOTE]
   >
   >Wenn Sie den **[!UICONTROL systemgenerierten]** Typ auswählen, sind nur Schemata mit dem eventID-Typ „mixin“ verfügbar. Wenn Sie den **[!UICONTROL regelbasierten]** Typ auswählen, sind nur Erlebnisereignisschemata verfügbar.

1. Klicken Sie bei regelbasierten Ereignissen in das Feld **[!UICONTROL Ereignis-ID-Bedingung]**. Mit dem einfachen Ausdruckseditor definieren Sie eine Bedingung, anhand derer das System die Ereignisse identifiziert, die Ihre Journey auslösen.
   ![](../assets/alpha-event6.png)

   In unserem Beispiel haben wir eine Bedingung basierend auf der Stadt des Profils verwendet. Dies bedeutet, dass das System jedes Mal, wenn es ein Ereignis empfängt, das dieser Bedingung entspricht (Feld **[!UICONTROL Stadt]** und Wert **[!UICONTROL Paris]**), dieses an Journey Orchestration weiterleitet.

   >[!NOTE]
   >
   >Der erweiterte Ausdruckseditor ist beim Definieren der **[!UICONTROL Ereignis-ID-Bedingung]** nicht verfügbar. Im einfachen Ausdruckseditor sind nicht alle Operatoren verfügbar. Sie hängen vom Datentyp ab. Beispielsweise können Sie für ein Feld vom Typ Zeichenfolge „enthält“ oder „ist gleich“ verwenden.

1. Fügen Sie einen Namespace hinzu. Dieser Schritt ist optional, wird jedoch empfohlen, da das Hinzufügen eines Namespace es Ihnen ermöglicht, die im Echtzeit-Kundenprofildienst gespeicherten Informationen zu nutzen. Er definiert den Typ des Schlüssels, den das Ereignis hat. Weitere Informationen finden Sie auf [dieser Seite](../event/selecting-the-namespace.md).
1. Definieren Sie den Schlüssel: Wählen Sie ein Feld aus Ihren Payload-Feldern aus oder definieren Sie eine Formel, um die mit dem Ereignis verbundene Person zu identifizieren. Dieser Schlüssel wird automatisch eingerichtet (kann aber weiterhin bearbeitet werden), wenn Sie einen Namespace auswählen. [!DNL Journey Orchestration] wählt den Schlüssel aus, der dem Namespace entsprechen soll (wenn Sie beispielsweise einen E-Mail-Namespace auswählen, wird der E-Mail-Schlüssel ausgewählt). Weitere Informationen finden Sie auf [dieser Seite](../event/defining-the-event-key.md).
1. Klicken Sie auf **[!UICONTROL Speichern]**.

   ![](../assets/journey7.png)

   Das Ereignis ist jetzt konfiguriert und kann in einer Journey abgelegt werden. Für den Empfang von Ereignissen sind zusätzliche Konfigurationsschritte erforderlich. Weitere Informationen finden Sie auf [dieser Seite](../event/additional-steps-to-send-events-to-journey-orchestration.md).
