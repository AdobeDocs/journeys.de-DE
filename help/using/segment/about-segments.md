---
product: adobe campaign
title: Über Adobe Experience Platform-Segmente
description: Erfahren Sie, wie Sie ein Adobe Experience Platformen-Segment konfigurieren
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: e5c0db2e1f85ea72fd54f91e4a26cc287377fb0e
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 100%

---

# Über Adobe Experience Platform-Segmente {#about-segments}

Wenn Sie zur Erstellung Ihrer Segmente den [Segmentierungsdienst von Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=de) verwenden, können Sie die Segmente in [!DNL Journey Orchestration] nutzen. Mit einer speziellen Ereignisaktivität können Sie Kontakte dazu bringen, anhand von Ein- und Austritten in Adobe Experience Platform-Segmenten in eine Journey einzutreten oder in einer Journey fortzufahren. Dadurch können Sie mit dem einfachen oder erweiterten Ausdruckseditor auch komplexe Bedingungen für Ihre Journeys erstellen.

Nehmen wir an, Sie verfügen über ein Segment für „Silber-Kunden“. Mit dieser Aktivität können Sie dafür sorgen, dass alle neuen Silber-Kunden eine Journey beginnen, und ihnen eine Reihe personalisierter Nachrichten senden. Auf Grundlage dieses Segments können Sie auch mühelos Bedingungen erstellen.

Im Folgenden finden Sie die Möglichkeiten von [!DNL Journey Orchestration] bei der Nutzung von Segmenten:

* Zugreifen auf die Liste von Adobe Experience Platform-Segmenten. Lesen Sie diesbezüglich auch den Abschnitt [Erstellen eines Segments](../segment/creating-a-segment.md).
* Erstellen von Segmenten direkt in [!DNL Journey Orchestration] auf gleiche Weise wie mit dem Segmentierungsdienst. Lesen Sie diesbezüglich auch den Abschnitt [Erstellen eines Segments](../segment/creating-a-segment.md).
* Verwenden von Segmenten in Bedingungen Ihrer Journey mit dem einfachen oder erweiterten Ausdruckseditor. Siehe [Verwenden von Segmenten in Bedingungen](../segment/using-a-segment.md).
* Hinzufügen eines Ereignisses vom Typ **[!UICONTROL Segmentqualifikation]** zu Ihrer Journey, um die Ein- und Austritte von Profilen in Adobe Experience Platform-Segmenten zu beobachten. Siehe [Ereignisaktivitäten](../building-journeys/segment-qualification-events.md).

## Auswertungsmethode in Journey Orchestration {#evaluation-method-in-journey-orchestration}

In Journey Orchestration werden Audiences aus Segmentdefinitionen mithilfe einer der folgenden Auswertungsmethoden erzeugt:

* Streaming-Segmentierung: Die Audiences-Liste für das Segment wird in Echtzeit auf dem neuesten Stand gehalten, während neue Daten in das System fließen.
* Batch-Segmentierung: Die Audiences-Liste für das Segment wird stündlich aktualisiert, basierend auf Daten, die in der letzten Stunde erfasst wurden.

Die Entscheidung zwischen Batch- und Streaming-Segmentierung wird für jede Segmentdefinition abhängig von der Komplexität und den Kosten für die Auswertung der Segmentregel vom System getroffen.

Sie können die Auswertungsmethode für jedes Segment in der Spalte **[!UICONTROL Auswertungsmethode]** der Segmentliste anzeigen.

Nachdem Sie ein Segment zum ersten Mal definiert haben, werden Profile zur Audience hinzugefügt, wenn sie sich qualifizieren.

Das Auffüllen der Audience anhand früherer Daten kann bis zu 24 Stunden dauern. Nachdem die Audience aufgefüllt wurde, wird sie kontinuierlich aktuell gehalten und ist immer für die Zielgruppenbestimmung bereit.