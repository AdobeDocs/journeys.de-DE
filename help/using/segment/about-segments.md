---
product: adobe campaign
title: Informationen zu Adobe Experience Platform-Segmenten
description: Erfahren Sie, wie Sie ein Adobe Experience Platformen-Segment konfigurieren
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '407'
ht-degree: 100%

---

# Informationen zu Adobe Experience Platform-Segmenten {#about-segments}


>[!CAUTION]
>
>**Sie möchten mehr über Adobe Journey Optimizer erfahren**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um auf die Journey Optimizer-Dokumentation zuzugreifen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Accountteam, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._


Wenn Sie zur Erstellung Ihrer Segmente den [Segmentierungsdienst von Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=de) verwenden, können Sie die Segmente in [!DNL Journey Orchestration] nutzen. Mit einer speziellen Ereignisaktivität können Sie Kontakte dazu bringen, anhand von Ein- und Austritten in Adobe Experience Platform-Segmenten in eine Journey einzutreten oder in einer Journey fortzufahren. Dadurch können Sie mit dem einfachen oder erweiterten Ausdruckseditor auch komplexe Bedingungen für Ihre Journeys erstellen.

Nehmen wir an, Sie verfügen über ein Segment für „Silber-Kunden“. Mit dieser Aktivität können Sie dafür sorgen, dass alle neuen Silber-Kunden eine Journey beginnen, und ihnen eine Reihe personalisierter Nachrichten senden. Auf Grundlage dieses Segments können Sie auch mühelos Bedingungen erstellen.

Im Folgenden finden Sie die Möglichkeiten von [!DNL Journey Orchestration] bei der Nutzung von Segmenten:

* Zugreifen auf die Liste von Adobe Experience Platform-Segmenten. Lesen Sie diesbezüglich auch den Abschnitt [Erstellen eines Segments](../segment/creating-a-segment.md).
* Erstellen von Segmenten direkt in [!DNL Journey Orchestration] auf gleiche Weise wie mit dem Segmentierungsdienst. Lesen Sie diesbezüglich auch den Abschnitt [Erstellen eines Segments](../segment/creating-a-segment.md).
* Verwenden von Segmenten in Bedingungen Ihrer Journey mit dem einfachen oder erweiterten Ausdruckseditor. Siehe [Verwenden von Segmenten in Bedingungen](../segment/using-a-segment.md).
* Hinzufügen eines Ereignisses vom Typ **[!UICONTROL Segmentqualifikation]** zu Ihrer Journey, um die Ein- und Austritte von Profilen in Adobe Experience Platform-Segmenten zu beobachten. Siehe [Ereignisaktivitäten](../building-journeys/segment-qualification-events.md).

## Auswertungsmethode in Journey Orchestration {#evaluation-method-in-journey-orchestration}

In Journey Orchestration werden Zielgruppen aus Segmentdefinitionen mithilfe einer der folgenden Auswertungsmethoden erzeugt:

* Streaming-Segmentierung: Die Zielgruppen-Liste für das Segment wird in Echtzeit auf dem neuesten Stand gehalten, während neue Daten in das System fließen.
* Batch-Segmentierung: Die Zielgruppen-Liste für das Segment wird stündlich aktualisiert, basierend auf Daten, die in der letzten Stunde erfasst wurden.

Die Entscheidung zwischen Batch- und Streaming-Segmentierung wird für jede Segmentdefinition abhängig von der Komplexität und den Kosten für die Auswertung der Segmentregel vom System getroffen.

Sie können die Auswertungsmethode für jedes Segment in der Spalte **[!UICONTROL Auswertungsmethode]** der Segmentliste anzeigen.

Nachdem Sie ein Segment zum ersten Mal definiert haben, werden Profile zur Zielgruppe hinzugefügt, wenn sie sich qualifizieren.

Das Auffüllen der Zielgruppe anhand früherer Daten kann bis zu 24 Stunden dauern. Nachdem die Audience aufgefüllt wurde, wird sie kontinuierlich aktuell gehalten und ist immer für die Zielgruppenbestimmung bereit.