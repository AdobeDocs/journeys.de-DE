---
title: Informationen zum Reiseaufbau
description: Erfahren Sie, wie Sie eine Reise bauen
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---



# Eine Reise erstellen {#concept_gq5_sqt_52b}

Dieser Schritt wird vom **Geschäftsbenutzer** ausgeführt. Hier kreieren Sie Ihre Reisen. Kombinieren Sie die verschiedenen Ereignis-, Orchestrierungs- und Aktionsaktivitäten, um Ihre mehrstufigen kanalübergreifenden Szenarien zu erstellen.

Die Benutzeroberfläche für die Reise ermöglicht Ihnen, Aktivitäten einfach von der Palette in die Arbeitsfläche zu ziehen. Sie können auch auf eine Aktivität doppelklicken, um sie im nächsten verfügbaren Schritt auf der Arbeitsfläche hinzuzufügen. Jede Aktivität hat eine bestimmte Rolle und einen bestimmten Platz im Prozess. Die Aktivitäten werden sequenziert. Nach Abschluss einer Aktivität wird der Fluss fortgesetzt und die nächste Aktivität verarbeitet usw.

Pro Fahrt ist nur ein Namespace zulässig. Wenn Sie das erste Ereignis abbrechen, werden Ereignisse mit unterschiedlichen Namespaces grau dargestellt. Wenn das erste Ereignis keinen Namespace hat, werden alle Ereignisse mit einem Namespace grau ausgeblendet. Näheres wird im Abschnitt [](../event/selecting-the-namespace.md) beschrieben. Außerdem werden Feldgruppen für Erlebnisplattformen ausgegraut, wenn die Reise Ereignisse ohne Namespace enthält. Und schließlich müssen mehrere Ereignisse auf derselben Reise denselben Namespace verwenden.

## Quickstart {#creating_journey}

Hier sind die wichtigsten Schritte, um eine Reise zu erstellen und zu veröffentlichen.

1. Klicken Sie im oberen Menü auf die Registerkarte **[!UICONTROL Start]**.

   Die Liste der Reisen wird angezeigt. Weitere Informationen [](../building-journeys/using-the-journey-designer.md) zur Benutzeroberfläche finden Sie unter .

   ![](../assets/journey30.png)

1. Klicken Sie auf **[!UICONTROL Erstellen]**, um eine neue Reise zu erstellen.

   ![](../assets/journey31.png)

1. Bearbeiten Sie die Eigenschaften der Reise im Konfigurationsbereich auf der rechten Seite. Näheres wird im Abschnitt [](../building-journeys/changing-properties.md) beschrieben.

   ![](../assets/journey32.png)

1. Ziehen Sie zuerst eine Ereignisaktivität aus der Palette in die Arbeitsfläche. Sie können auch auf eine Aktivität doppelklicken, um sie der Arbeitsfläche hinzuzufügen.


   ![](../assets/journey33.png)

1. Ziehen Sie Ihre anderen Aktivitäten per Drag &amp; Drop und konfigurieren Sie sie. See [](../building-journeys/event-activities.md), [](../building-journeys/about-orchestration-activities.md) and [](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. Ihre Reise wird automatisch gespeichert. Testen Sie Ihre Reise und veröffentlichen Sie sie. Siehe [](../building-journeys/testing-the-journey.md) und [](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## Ende einer Reise{#ending_a_journey}

Es gibt zwei Möglichkeiten, eine Reise zu beenden:

* Die Person kommt bei der letzten Aktivität eines Pfades an. Diese letzte Aktivität kann eine Endaktivität oder eine andere Aktivität sein. Es besteht keine Verpflichtung, einen Pfad mit einer Endaktivität zu beenden. Näheres wird im Abschnitt [](../building-journeys/end-activity.md) beschrieben.
* Die Person gelangt zu einer Bedingungsaktivität (oder einer Warteaktivität mit einer Bedingung) und erfüllt keine der Bedingungen.

Die Person kann dann wieder in die Reise einreisen, wenn der Wiedereintritt erlaubt ist. Näheres wird im Abschnitt [](../building-journeys/changing-properties.md) beschrieben.

