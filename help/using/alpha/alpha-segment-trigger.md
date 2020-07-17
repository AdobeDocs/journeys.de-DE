---
title: Segmentauslöser-Aktivität
description: Erfahren Sie xxxx
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 74%

---


# Segmentauslöser-Aktivität {#segment-trigger-activity}

## Informationen zur Segmentauslöser-Aktivität {#about-segment-trigger-actvitiy}

Mit der Segmentauslöser-Aktivität können Sie alle Adobe Experience Platformen, die zu einem Segmentsegment gehören, in eine Reise einbinden. Der Eintritt in eine Journey kann entweder einmalig oder regelmäßig erfolgen.

Nehmen wir an, Sie haben ein Gold-Kundensegment auf der Adobe Experience Platform. Mit der Segmentauslöser-Aktivität können Sie alle Einzelanwender, die zum Gold-Kundensegment gehören, in eine Journey eintreten lassen und durch individuelle Journeys führen, die alle Journey-Funktionen nutzen: Bedingungen, Timer, Ereignisse, Aktionen.

>[!NOTE]
>
>Aufgrund von Latenzen beim Segmentexport ist es nicht möglich, eine segmentbasierte Journey in einem kürzeren Zeitraum als einer Stunde auszulösen.

## Konfigurieren der Aktivität {#configuring-segment-trigger-activity}

1. Erweitern Sie die Kategorie **[!UICONTROL Orchestrierung]** und legen Sie eine Aktivität vom Typ **[!UICONTROL Segmentauslöser]** auf Ihrer Arbeitsfläche ab.

   Die Aktivität muss als erster Schritt einer Journey positioniert werden.

1. Konfigurieren Sie den **[!UICONTROL Planungstyp]** der Aktivität.

   Standardmäßig tritt das Segment **[!UICONTROL so bald wie möglich]** in die Journey ein, d. h. eine Stunde nach der Veröffentlichung der Journey. Wenn das Segment zu einem bestimmten Datum/zu einer bestimmten Uhrzeit oder wiederholt in die Journey eintreten soll, wählen Sie die gewünschte Option aus der Liste aus.

   Bei wiederkehrenden Journeys können Sie auch den Beginn und das Ende der Journey festlegen.

   ![](../assets/segment-trigger-schedule.png)

1. In the **[!UICONTROL Segment]** field, choose the Adobe Experience Platform segment that will enter the journey, then click **[!UICONTROL Save]**.

   ![](../assets/segment-trigger-segment-selection.png)

1. Wählen Sie im Feld **[!UICONTROL Namespace]** den Namespace aus, der zur Identifizierung der Einzelanwender verwendet werden soll. Weitere Informationen zu Namespaces finden Sie in [diesem Abschnitt](../event/selecting-the-namespace.md).

   >[!NOTE]
   >
   >Personen, die zu einem Segment gehören, das nicht über die jeweilige Namensraum-ID verfügt, können nicht an der Reise teilnehmen.

1. Wählen Sie zum Bestätigen **[!UICONTROL OK]** aus. Sie können dann die verfügbaren Aktivitäten nutzen, um Ihre Journey zu erstellen.

1. Sobald die Journey fertig ist, können Sie sie testen (siehe [Testen der Journey](../building-journeys/testing-the-journey.md)).

   Wenn der Testmodus in einer Journey aktiviert ist, die mit einer **[!UICONTROL Segmentauslöser]**-Aktivität beginnt, werden 100 Testprofile zufällig aus den für das ausgewählte Segment qualifizierten Profilen ausgewählt. In den Testprotokollen können Sie den Pfad von Einzelanwendern in der Journey und mögliche Fehler anzeigen (siehe [Anzeigen der Protokolle](../building-journeys/testing-the-journey.md#viewing_logs)).

   >[!NOTE]
   >
   >Beachten Sie, dass Sie die 100 Personen, die dieser Journey folgen, mit der visuellen Flussfunktion, die in auf einheitlichen Ereignissen beruhenden Journeys vorhanden ist, nicht sehen können.

1. Anschließend können Sie Ihre Journey veröffentlichen (siehe [Veröffentlichen der Journey](../building-journeys/publishing-the-journey.md)). Einzelanwender, die zum Segment gehören, treten an dem Datum/zu der Uhrzeit in die Journey ein, die in der Planung für die Segmentauslöser-Aktivität angegeben ist.

   >[!IMPORTANT]
   >
   >Keep in mind that Adobe Experience Platform segments are calculated either once a day (**batch** segments) or in real-time (**streamed** segments).
   >
   >Wenn das ausgewählte Segment gestreamt wird, betreten die zu diesem Segment gehörenden Einzelanwender die Journey in Echtzeit. Wenn es sich bei dem Segment um einen Stapel handelt, können Personen, die für dieses Segment neu qualifiziert wurden, möglicherweise die Reise aufrufen, wenn die Segmentberechnung auf der Adobe Experience Platform ausgeführt wird.
