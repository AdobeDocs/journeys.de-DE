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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9c3b8f2d88646372e69ae4f24a5dbb5d45721c55
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 58%

---


# Regelbasierte Ereignisse{#simplified-events}

Die Einrichtung von Erlebnisereignissen wurde vereinfacht. Bei der neuen Methode muss keine eventID verwendet werden. Wenn Sie Ihr Ereignis in Journey Orchestration einrichten, können Sie jetzt ein regelbasiertes Ereignis definieren.

Dieser neue Ereignistyp generiert keine eventID. Mit dem einfachen Ausdruckseditor definieren Sie jetzt einfach eine Regel, anhand derer das System die relevanten Ereignisse identifiziert, die Ihre Journeys auslösen. Diese Regel kann auf einem beliebigen Feld basieren, das in der Ereignis-Payload verfügbar ist, z. B. dem Standort des Profils oder der Anzahl der Artikel, die dem Warenkorb des Profils hinzugefügt wurden.

Diese neue Methode ist für Benutzer weitgehend transparent. Die einzige Änderung ist ein neues Feld im Bildschirm zur Ereignisdefinition.

## Nutzung von Adobe Analytics-Daten{#analytics-data}

>[!NOTE]
>
>Dieser Abschnitt gilt nur für Kunden, die Adobe Analytics-Daten verwenden müssen.

Sie können alle Adobe Analytics-Verhaltensdaten nutzen, die Sie bereits erfassen und an die Plattform streamen, um Reisen auszulösen und Erlebnisse für Ihre Ereignis zu automatisieren.

Damit dies funktioniert, müssen Sie in Adobe Experience Platform die Report Suite aktivieren, die Sie nutzen möchten:

1. Wählen Sie in Adobe Experience Platform **[!UICONTROL Quellen]** und dann **[!UICONTROL Hinzufügen Daten]** im Abschnitt Adobe Analytics. Die Liste der verfügbaren Adobe Analytics Report Suites wird angezeigt.

1. Wählen Sie die zu aktivierende Report Suite aus, klicken Sie auf **[!UICONTROL Weiter]** und dann auf **[!UICONTROL Fertig stellen]**.

1. Geben Sie die Quelldaten-ID für Ihren Alpha-Programm-Kontaktpunkt frei.

Dadurch wird der Analytics-Quell-Connector für diese Report Suite aktiviert. Sobald die Daten eingehen, werden sie in ein Experience Ereignis umgewandelt und an Adobe Experience Platform gesendet.

![](../assets/alpha-event9.png)

Weitere Informationen zum Adobe Analytics-Quellanschluss finden Sie in der [Dokumentation](https://docs.adobe.com/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html) und im [Tutorial](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html).

## Regelbasiertes Ereignis konfigurieren{#configuring-rule-based}

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

## Testmodus für regelbasierte Ereignis{#test-rule-based}

Der Testmodus ist auch für Fahrten mit einem regelbasierten Ereignis verfügbar.

Beim Auslösen eines Ereignisses können Sie im Bildschirm &quot; **Ereignis-Konfiguration** &quot;die Ereignis-Parameter definieren, die der Test bestehen soll. Sie können die Ereignis-ID-Bedingung durch Klicken auf das QuickInfo-Symbol oben rechts Ansicht werden. Neben jedem Feld, das Teil der Regelauswertung ist, steht auch eine QuickInfo zur Verfügung.

![](../assets/alpha-event8.png)

For more information on how to use the test mode, refer to [](../building-journeys/testing-the-journey.md).

