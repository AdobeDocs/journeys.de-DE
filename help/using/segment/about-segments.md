---
title: Informationen zu Adobe Experience Platformen
description: Erfahren Sie, wie Sie ein Adobe Experience Platformen-Segment konfigurieren
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
source-git-commit: a65a5db5b35291cbc2635f9ae67fd8c8c5284575
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 48%

---


# Informationen zu Adobe Experience Platformen {#about-segments}

If you&#39;re using the [Adobe Experience Platform Segmentation Service](https://docs.adobe.com/content/help/de-DE/experience-platform/segmentation/home.html) to create your segments, you can leverage them in [!DNL Journey Orchestration]. Dank einer dedizierten Ereignis-Aktivität können Sie Einzelpersonen dazu bringen, auf der Grundlage der Ein- und Ausstiege von Adobe Experience Platformen in eine Reise einzusteigen oder sich vorwärts zu bewegen. Dadurch können Sie mit dem einfachen oder erweiterten Ausdruckseditor auch komplexe Bedingungen für Ihre Journeys erstellen.

Nehmen wir an, Sie verfügen über ein Segment für „Silber-Kunden“. Mit dieser Aktivität können Sie dafür sorgen, dass alle neuen Silber-Kunden eine Journey beginnen, und ihnen eine Reihe personalisierter Nachrichten senden. Auf Grundlage dieses Segments können Sie auch mühelos Bedingungen erstellen.

Im Folgenden finden Sie die Möglichkeiten von [!DNL Journey Orchestration] bei der Nutzung von Segmenten:

* Greifen Sie auf die Liste von Adobe Experience Platformen-Segmenten zu. Lesen Sie diesbezüglich auch den Abschnitt [Erstellen eines Segments](../segment/creating-a-segment.md).
* Erstellen von Segmenten direkt in [!DNL Journey Orchestration] auf gleiche Weise wie mit dem Segmentierungsdienst. Lesen Sie diesbezüglich auch den Abschnitt [Erstellen eines Segments](../segment/creating-a-segment.md).
* Nutzen Sie Segmente in den Reisebedingungen mit dem einfachen oder erweiterten Ausdruck-Editor. Siehe [Verwenden von Segmenten in Bedingungen](../segment/using-a-segment.md).
* Add a **[!UICONTROL Segment qualification]** event to your journey in order to listen to the entrances and exits of profiles in Adobe Experience Platform segments. Siehe [Ereignisaktivitäten](../building-journeys/segment-qualification-events.md).
