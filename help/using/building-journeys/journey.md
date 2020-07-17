---
title: Informationen zum Erstellen von Journeys
description: Erfahren Sie, wie Sie eine Journey erstellen
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
source-wordcount: '367'
ht-degree: 95%

---



# Erstellen einer Journey {#concept_gq5_sqt_52b}

Dieser Schritt wird vom **Business-Anwender** ausgeführt. Hier erstellen Sie Ihre Journeys. Kombinieren Sie die verschiedenen Ereignis-, Orchestrierungs- und Aktionsaktivitäten, um Ihre mehrstufigen kanalübergreifenden Szenarien zu erstellen.

Die Benutzeroberfläche für die Journey ermöglicht es Ihnen, Aktivitäten einfach von der Palette in die Arbeitsfläche zu ziehen. Sie können auch auf eine Aktivität doppelklicken, um sie im nächsten verfügbaren Schritt der Arbeitsfläche hinzuzufügen. Jede Aktivität hat eine bestimmte Rolle und eine bestimmte Position im Prozess. Die Aktivitäten werden sequenziert. Nach Beendigung einer Aktivität wird der Fluss fortgesetzt und die nächste Aktivität verarbeitet usw.

Pro Journey ist nur ein Namespace zulässig. Wenn Sie das erste Ereignis ablegen, werden Ereignisse mit unterschiedlichen Namespaces grau dargestellt. Wenn das erste Ereignis keinen Namespace hat, werden alle Ereignisse mit einem Namespace grau dargestellt. Siehe [](../event/selecting-the-namespace.md). Außerdem werden Feldgruppen für Adobe Experience Platformen ausgegraut, wenn die Reise Ereignisse ohne Namensraum hat. Wenn Sie mehrere Ereignisse in derselben Journey verwenden, müssen diese denselben Namespace verwenden.

## Schnellstart {#creating_journey}

Hier finden Sie die wichtigsten Schritte für das Erstellen und Veröffentlichen einer Journey.

1. Klicken Sie oben im Menü auf den Tab **[!UICONTROL Startseite]**.

   Die Liste der Journeys wird angezeigt. Weitere Informationen zur Benutzeroberfläche finden Sie unter [](../building-journeys/using-the-journey-designer.md).

   ![](../assets/journey30.png)

1. Klicken Sie auf **[!UICONTROL Erstellen]**, um eine neue Journey zu erstellen.

   ![](../assets/journey31.png)

1. Bearbeiten Sie im Konfigurationsbereich auf der rechten Seite die Eigenschaften der Journey. Siehe [](../building-journeys/changing-properties.md).

   ![](../assets/journey32.png)

1. Ziehen Sie zuerst eine Ereignisaktivität aus der Palette in die Arbeitsfläche. Sie können auch auf eine Aktivität doppelklicken, um sie der Arbeitsfläche hinzuzufügen.

   ![](../assets/journey33.png)

1. Ziehen Sie Ihre anderen Aktivitäten per Drag-and-Drop und konfigurieren Sie sie. Siehe [](../building-journeys/event-activities.md), [](../building-journeys/about-orchestration-activities.md) und [](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. Ihre Journey wird automatisch gespeichert. Testen und veröffentlichen Sie Ihre Journey. Siehe [](../building-journeys/testing-the-journey.md) und [](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## Beenden einer Journey {#ending_a_journey}

Es gibt zwei Möglichkeiten, eine Journey zu beenden:

* Die Person kommt bei der letzten Aktivität eines Pfades an. Diese letzte Aktivität kann eine Endaktivität oder eine andere Aktivität sein. Sie müssen einen Pfad nicht mit einer Endaktivität beenden. Siehe [](../building-journeys/end-activity.md).
* Die Person kommt bei einer Bedingungsaktivität (oder einer Warteaktivität mit einer Bedingung) an und erfüllt keine der Bedingungen.

Die Person kann dann wieder in die Journey eintreten, wenn der erneute Zutritt erlaubt ist. Siehe [](../building-journeys/changing-properties.md).
