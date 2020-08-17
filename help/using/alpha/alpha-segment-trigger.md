---
title: Segmentauslöser-Aktivität
description: Weitere Informationen zum Segmentauslöser
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
source-git-commit: b66cdb31b62b4627ff7378e48879ffadfedda5cb
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 87%

---


# Segmentauslöser-Aktivität {#segment-trigger-activity}

## Informationen zur Segmentauslöser-Aktivität {#about-segment-trigger-actvitiy}

>[!NOTE]
>
>Wenn zum Zeitpunkt der Veröffentlichung oder zur Aktivierung des Testmodus eine Out-of-the-Box-Aktion-Aktivität von Adobe Campaign Standard auf der Arbeitsfläche vorhanden ist, wird die Fahrt bei 13 Eingängen pro Sekunde gedrosselt. <br>Wenn zum Zeitpunkt der Veröffentlichung oder zur Aktivierung des Testmodus keine vordefinierte Adobe Campaign Standard-Aktionsoption auf der Arbeitsfläche vorhanden ist, wird die Aktivität um 1000 Ereignis pro Sekunde gedrosselt.

Mit der Segmentauslöser-Aktivität können Sie alle Personen, die zu einem Adobe Experience Platform-Segment gehören, in eine Journey eintreten lassen. Der Eintritt in eine Journey kann entweder einmalig oder regelmäßig erfolgen.

Nehmen wir an, Sie verfügen über ein Segment für „Gold-Kunden“ in Adobe Experience Platform. Mit der Segmentauslöser-Aktivität können Sie alle Einzelanwender, die zum Gold-Kundensegment gehören, in eine Journey eintreten lassen und durch individuelle Journeys führen, die alle Journey-Funktionen nutzen: Bedingungen, Timer, Ereignisse, Aktionen.

## Konfigurieren der Aktivität {#configuring-segment-trigger-activity}

>[!NOTE]
>
>Aufgrund von Latenzen beim Segmentexport ist es nicht möglich, eine segmentbasierte Journey in einem kürzeren Zeitraum als einer Stunde auszulösen.

1. Erweitern Sie die Kategorie **[!UICONTROL Orchestrierung]** und legen Sie eine Aktivität vom Typ **[!UICONTROL Segmentauslöser]** auf Ihrer Arbeitsfläche ab.

   Die Aktivität muss als erster Schritt einer Journey positioniert werden.

1. Konfigurieren Sie den **[!UICONTROL Planungstyp]** der Aktivität.

   Standardmäßig tritt das Segment **[!UICONTROL so bald wie möglich]** in die Journey ein, d. h. eine Stunde nach der Veröffentlichung der Journey. Wenn das Segment zu einem bestimmten Datum/zu einer bestimmten Uhrzeit oder wiederholt in die Journey eintreten soll, wählen Sie die gewünschte Option aus der Liste aus.

   Bei wiederkehrenden Journeys können Sie auch den Beginn und das Ende der Journey festlegen.

   ![](../assets/segment-trigger-schedule.png)

1. Wählen Sie im Feld **[!UICONTROL Segment]** das Adobe Experience Platform-Segment aus, das in die Journey eintreten soll, und klicken Sie dann auf **[!UICONTROL Speichern]**.

   ![](../assets/segment-trigger-segment-selection.png)

1. Wählen Sie im Feld **[!UICONTROL Namespace]** den Namespace aus, der zur Identifizierung der Einzelanwender verwendet werden soll. Weitere Informationen zu Namespaces finden Sie in [diesem Abschnitt](../event/selecting-the-namespace.md).

   >[!NOTE]
   >
   >Einzelanwender, die zu einem Segment gehören, das nicht die ausgewählte Identität (den ausgewählten Namespace) hat, können nicht in die Journey eintreten.

1. Wählen Sie zum Bestätigen **[!UICONTROL OK]** aus. Sie können dann die verfügbaren Aktivitäten nutzen, um Ihre Journey zu erstellen.

1. Sobald die Journey fertig ist, können Sie sie testen (siehe [Testen der Journey](../building-journeys/testing-the-journey.md)).

   Wenn der Testmodus in einer Journey aktiviert ist, die mit einer **[!UICONTROL Segmentauslöser]**-Aktivität beginnt, werden 100 Testprofile zufällig aus den für das ausgewählte Segment qualifizierten Profilen ausgewählt. In den Testprotokollen können Sie den Pfad von Einzelanwendern in der Journey und mögliche Fehler anzeigen (siehe [Anzeigen der Protokolle](../building-journeys/testing-the-journey.md#viewing_logs)).

   >[!NOTE]
   >
   >Beachten Sie, dass Sie die 100 Personen, die dieser Journey folgen, mit der visuellen Flussfunktion, die in auf einheitlichen Ereignissen beruhenden Journeys vorhanden ist, nicht sehen können.

1. Anschließend können Sie Ihre Journey veröffentlichen (siehe [Veröffentlichen der Journey](../building-journeys/publishing-the-journey.md)). Einzelanwender, die zum Segment gehören, treten an dem Datum/zu der Uhrzeit in die Journey ein, die in der Planung für die Segmentauslöser-Aktivität angegeben ist.

   >[!IMPORTANT]
   >
   >Beachten Sie, dass Adobe Experience Platform-Segmente entweder einmal täglich (**Batch**-Segmente) oder in Echtzeit (**gestreamte** Segmente) berechnet werden.
   >
   >Wenn das ausgewählte Segment gestreamt wird, betreten die zu diesem Segment gehörenden Einzelanwender die Journey in Echtzeit. Wenn es sich bei dem Segment um ein Batch-Segment handelt, treten für dieses Segment neu qualifizierte Personen in die Journey ein, wenn die Segmentberechnung in Adobe Experience Platform ausgeführt wird.
