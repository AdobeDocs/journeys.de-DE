---
title: Regelbasierte Ereignisse
description: Erfahren Sie mehr über regelbasierte Ereignisse.
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
source-wordcount: '687'
ht-degree: 97%

---


# Regelbasierte Ereignisse{#simplified-events}

Die Einrichtung von Erlebnisereignissen wurde vereinfacht. Bei der neuen Methode muss keine eventID verwendet werden. Wenn Sie Ihr Ereignis in Journey Orchestration einrichten, können Sie jetzt ein regelbasiertes Ereignis definieren.

Dieser neue Ereignistyp generiert keine eventID. Mit dem einfachen Ausdruckseditor definieren Sie jetzt einfach eine Regel, anhand derer das System die relevanten Ereignisse identifiziert, die Ihre Journeys auslösen. Diese Regel kann auf einem beliebigen Feld basieren, das in der Ereignis-Payload verfügbar ist, z. B. dem Standort des Profils oder der Anzahl der Artikel, die dem Warenkorb des Profils hinzugefügt wurden.

Diese neue Methode ist für Benutzer weitgehend transparent. Die einzige Änderung ist ein neues Feld im Bildschirm zur Ereignisdefinition.

>[!CAUTION]
>
>Für regelbasierte Ereignisse wird eine Deckelungsregel definiert. Die Anzahl der qualifizierten Ereignisse, die eine Journey verarbeiten kann, wird auf 400.000 pro Minute begrenzt. Für weitere Informationen wenden Sie sich an Ihren Ansprechpartner bei Ihrem Alpha-Programm.

## Nutzung von Adobe Analytics-Daten{#analytics-data}

>[!NOTE]
>
>Dieser Abschnitt richtet sich nur an Kunden, die mit Adobe Analytics-Daten arbeiten müssen.

Sie können alle verhaltensbezogenen Ereignisdaten, die Sie in Adobe Analytics bereits erfassen und an Platform streamen, zum Auslösen von Journeys und zur Automatisierung von Erlebnissen für Ihre Kunden nutzen.

Voraussetzung hierfür ist, dass Sie in Adobe Experience Platform die Report Suite aktivieren, die Sie nutzen möchten:

1. Wählen Sie in Adobe Experience Platform **[!UICONTROL Quellen]** und anschließend im **[!UICONTROL Daten hinzufügen]** im Adobe Analytics-Bereich. Daraufhin wird die Liste der in Adobe Analytics verfügbaren Report Suites angezeigt.

1. Wählen Sie die zu aktivierende Report Suite aus, klicken Sie auf **[!UICONTROL Weiter]** und dann auf **[!UICONTROL Fertigstellen]**.

1. Geben Sie die Daten-ID der Quelle für Ihren dem Alpha-Programm zugehörigen Kontaktpunkt frei.

Dadurch wird der Analytics-Quell-Connector für diese Report Suite aktiviert. Sobald die Daten eingehen, werden sie in ein Erlebnisereignis umgewandelt und an Adobe Experience Platform gesendet.

![](../assets/alpha-event9.png)

Weitere Informationen zum Quell-Connector von Adobe Analytics finden Sie in der [Dokumentation](https://docs.adobe.com/help/de-DE/experience-platform/sources/connectors/adobe-applications/analytics.translate.html) und im [Tutorial](https://docs.adobe.com/content/help/de-DE/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.translate.html).

## Konfigurieren eines regelbasierten Ereignisses{#configuring-rule-based}

1. Klicken Sie im linken Menü auf das Symbol **[!UICONTROL Admin]** und dann auf **[!UICONTROL Ereignis]**. Die Liste der Ereignisse wird angezeigt.

   ![](../assets/alpha-event1.png)

1. Klicken Sie auf **[!UICONTROL Hinzufügen]**, um ein neues Ereignis zu erstellen. Der Bereich für die Ereigniskonfiguration wird auf der rechten Seite des Bildschirms geöffnet.

   ![](../assets/alpha-event2.png)

1. Geben Sie den Namen Ihres Ereignisses ein. Sie können auch eine Beschreibung hinzufügen.

   ![](../assets/alpha-event3.png)

1. Wählen Sie im neuen Feld **[!UICONTROL Ereignis-ID-Typ]** die Option **[!UICONTROL Regelbasiert]** aus.

   ![](../assets/alpha-event4.png)

   >[!NOTE]
   >
   >Der **[!UICONTROL systemgenerierte]** Typ ist die bestehende Methode, für die eine eventID erforderlich ist. Siehe [diesen Abschnitt](../event/about-events.md).

1. Definieren Sie die **[!UICONTROL Schema]**- und **[!UICONTROL Payload]**-Felder. Siehe [diesen Abschnitt](../event/defining-the-payload-fields.md).

   ![](../assets/alpha-event5.png)

   >[!NOTE]
   >
   >Wenn Sie den **[!UICONTROL systemgenerierten Typ]** auswählen, sind nur Schemata mit dem eventID-Typ „mixin“ verfügbar. Wenn Sie den **[!UICONTROL regelbasierten]** Typ auswählen, sind nur Erlebnisereignisschemata verfügbar.

1. Klicken Sie in das Feld **[!UICONTROL Ereignis-ID-Bedingung]**. Mit dem einfachen Ausdruckseditor definieren Sie eine Bedingung, anhand derer das System die Ereignisse identifiziert, die Ihre Journey auslösen.

   ![](../assets/alpha-event6.png)

   In unserem Beispiel haben wir eine Bedingung basierend auf der Stadt des Profils verwendet. Dies bedeutet, dass das System jedes Mal, wenn es ein Ereignis empfängt, das dieser Bedingung entspricht (Feld **[!UICONTROL Stadt]** und Wert **[!UICONTROL Paris]**), dieses an Journey Orchestration weiterleitet.

1. Geben Sie den **[!UICONTROL Namespace]** und den **[!UICONTROL Schlüssel]** an. Siehe [Auswählen des Namespace](../event/selecting-the-namespace.md) und [Definieren des Ereignisschlüssels](../event/defining-the-event-key.md).

   ![](../assets/alpha-event7.png)

Die anderen Schritte für die Ereigniskonfiguration und Journey-Erstellung bleiben unverändert.

Das Ereignis ist jetzt konfiguriert und kann wie jedes andere Ereignis in einer Journey abgelegt werden. Jedes Mal, wenn ein Ereignis, das der Regel entspricht, an das System gesendet wird, wird es an Journey Orchestration übergeben, um Ihre Journeys auszulösen.

## Testmodus für regelbasierte Ereignisse{#test-rule-based}

Der Testmodus ist für Journeys, bei denen ein regelbasiertes Ereignis verwendet wird, ebenfalls verfügbar.

Beim Auslösen eines Ereignisses können Sie im Bildschirm **Ereigniskonfiguration** die Ereignisparameter definieren, nach denen der Test als bestanden gilt. Durch Klicken auf das QuickInfo-Symbol oben rechts können Sie die Ereignis-ID-Bedingung anzeigen. Außerdem ist neben jedem Feld, das Teil der Regelauswertung ist, ebenfalls eine QuickInfo verfügbar.

![](../assets/alpha-event8.png)

For more information on how to use the test mode, refer to [this page](../building-journeys/testing-the-journey.md).
