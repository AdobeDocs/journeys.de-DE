---
product: adobe campaign
title: Verwenden von Segmenten in Bedingungen
description: Erfahren Sie, wie Sie ein Segment verwenden
feature: Journeys
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
source-git-commit: 9db330405130b14d1d8a8cbed59f612fd1f6767b
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 100%

---

# Verwenden von Segmenten in Bedingungen {#using-a-segment}

In diesem Abschnitt wird erläutert, wie sich ein Segment in einer Journey-Bedingung verwenden lässt. Informationen zur Nutzung eines Ereignisses vom Typ **[!UICONTROL Segmentqualifizierung]** in Ihrer Journey finden Sie in diesem [Abschnitt](../building-journeys/segment-qualification-events.md).

Gehen Sie wie folgt vor, um in einer Journey-Bedingung ein Segment zu verwenden:

1. Öffnen Sie eine Journey, legen Sie eine Aktivität vom Typ **[!UICONTROL Bedingung]** ab und wählen Sie die **Bedingung der Datenquelle**.
   ![](../assets/journey47.png)

1. Klicken Sie für jeden zusätzlichen Pfad auf **[!UICONTROL Pfad hinzufügen]**. Klicken Sie für jeden Pfad auf das Feld **[!UICONTROL Ausdruck]**.

   ![](../assets/segment3.png)

1. Erweitern Sie auf der linken Seite den Knoten **[!UICONTROL Segmente]**. Legen Sie das Segment, das Sie für Ihre Bedingung verwenden möchten, im Arbeitsbereich ab. Standardmäßig lautet die Bedingung für das Segment „true“.

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >Nur Personen mit den Segmentteilnahmestatus **Realisiert** und **Vorhanden** werden als Mitglieder des Segments betrachtet. Weitere Informationen zum Auswerten eines Segments finden Sie in der [Dokumentation zum Segmentierungs-Service](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=de#interpret-segment-results).

Weiterführende Informationen zu Journey-Bedingungen und zur Verwendung des einfachen Ausdruckseditors finden Sie unter [Bedingungsaktivität](../building-journeys/condition-activity.md#about_condition).
