---
product: adobe campaign
solution: Journey Orchestration
title: Informationen zum Erstellen von Journeys
description: Erfahren Sie, wie Sie als Business-Anwender Ereignis-, Orchestrierungs- und Aktions-Aktivitäten kombinieren, um eine Journey zu gestalten.
translation-type: tm+mt
source-git-commit: c41b49e2208727f5e3a562b838c4b052c70e8412
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 92%

---


# Erstellen einer Journey {#concept_gq5_sqt_52b}

Dieser Schritt wird vom **Business-Anwender** ausgeführt. Hier erstellen Sie Ihre Journeys. Kombinieren Sie die verschiedenen Ereignis-, Orchestrierungs- und Aktionsaktivitäten, um Ihre mehrstufigen kanalübergreifenden Szenarien zu erstellen.

Die Benutzeroberfläche für die Journey ermöglicht es Ihnen, Aktivitäten einfach von der Palette in die Arbeitsfläche zu ziehen. Sie können auch auf eine Aktivität doppelklicken, um sie im nächsten verfügbaren Schritt der Arbeitsfläche hinzuzufügen. Jede Aktivität hat eine bestimmte Rolle und eine bestimmte Position im Prozess. Die Aktivitäten werden sequenziert. Nach Beendigung einer Aktivität wird der Fluss fortgesetzt und die nächste Aktivität verarbeitet usw.

Pro Journey ist nur ein Namespace zulässig. Wenn Sie das erste Ereignis ablegen, werden Ereignisse mit unterschiedlichen Namespaces grau dargestellt. Wenn das erste Ereignis keinen Namespace hat, werden alle Ereignisse mit einem Namespace grau dargestellt. Weitere Informationen finden Sie auf [dieser Seite](../event/selecting-the-namespace.md). Außerdem werden die Feldergruppen für Adobe Experience Platform grau dargestellt, wenn die Journey Ereignisse ohne Namespace enthält. Wenn Sie mehrere Ereignisse in derselben Journey verwenden, müssen diese denselben Namespace verwenden.

Beim Starten einer neuen Journey werden Elemente ausgeblendet, die nicht als erster Schritt auf der Arbeitsfläche abgelegt werden können. Dies betrifft alle Aktionen, die Bedingungs-Aktivität, die Wartezeit und die Reaktion.

## Schnellstart {#creating_journey}

Hier finden Sie die wichtigsten Schritte für das Erstellen und Veröffentlichen einer Journey.

1. Klicken Sie oben im Menü auf den Tab **[!UICONTROL Startseite]**.

   Die Liste der Journeys wird angezeigt. Weitere Informationen zur Benutzeroberfläche finden Sie auf [dieser Seite](../building-journeys/using-the-journey-designer.md).

   ![](../assets/journey30.png)

1. Klicken Sie auf **[!UICONTROL Erstellen]**, um eine neue Journey zu erstellen.

   ![](../assets/journey31.png)

1. Bearbeiten Sie im Konfigurationsbereich auf der rechten Seite die Eigenschaften der Journey. Weitere Informationen finden Sie auf [dieser Seite](../building-journeys/changing-properties.md).

   ![](../assets/journey32.png)

1. Ziehen Sie zuerst eine Ereignisaktivität aus der Palette in die Arbeitsfläche. Sie können auch auf eine Aktivität doppelklicken, um sie der Arbeitsfläche hinzuzufügen.

   ![](../assets/journey33.png)

1. Ziehen Sie Ihre anderen Aktivitäten per Drag-and-Drop und konfigurieren Sie sie. Weitere Informationen finden Sie auf den Seiten [Ereignisaktivitäten](../building-journeys/event-activities.md), [Informationen zu Orchestrierungsaktivitäten](../building-journeys/about-orchestration-activities.md) und [Informationen zu Aktionsaktivitäten](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. Ihre Journey wird automatisch gespeichert. Testen und veröffentlichen Sie Ihre Journey. Siehe [Testen der Reise](../building-journeys/testing-the-journey.md) und [Veröffentlichen der Journey](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## Beenden einer Journey {#ending_a_journey}

Es gibt zwei Möglichkeiten, eine Journey zu beenden:

* Die Person kommt bei der letzten Aktivität eines Pfades an. Diese letzte Aktivität kann eine Endaktivität oder eine andere Aktivität sein. Sie müssen einen Pfad nicht mit einer Endaktivität beenden. Weitere Informationen finden Sie auf [dieser Seite](../building-journeys/end-activity.md).
* Die Person kommt bei einer Bedingungsaktivität (oder einer Warteaktivität mit einer Bedingung) an und erfüllt keine der Bedingungen.

Die Person kann dann wieder in die Journey eintreten, wenn der erneute Zutritt erlaubt ist. Weitere Informationen finden Sie auf [dieser Seite](../building-journeys/changing-properties.md).
