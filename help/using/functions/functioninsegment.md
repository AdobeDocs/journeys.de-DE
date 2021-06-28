---
product: adobe campaign
title: inSegment
description: Erfahren Sie mehr über die Funktion „inSegment“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: ht
source-wordcount: '152'
ht-degree: 100%

---

# inSegment {#inSegment}

Überprüft, ob ein Kontakt zu einem bestimmten Segment gehört.

>[!NOTE]
>
>Sie können bis zu 100 Segmente abrufen.

Der Segmentname muss eine Zeichenfolgenkonstante sein. Er darf weder ein Feldverweis noch ein Ausdruck sein.

Segmente werden in [Adobe Experience Platform](https://platform.adobe.com/segment/overview) definiert. Der Ausdruckseditor bietet eine automatisch ausgefüllte Segmentliste.

>[!NOTE]
>
>Nur Personen mit den Segmentteilnahmestatus **Realisiert** und **Vorhanden** werden als Mitglieder des Segments betrachtet. Weitere Informationen zum Auswerten eines Segments finden Sie in der [Dokumentation zum Segmentierungsdienst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=de#interpret-segment-results).

## Kategorie

Adobe Experience Platform

## Funktionssyntax

`inSegment(<parameter>)`

## Parameter

| Parameter | Beschreibung | Typ |
|--- |--- |--- |
| Segment | Der Segmentname | `<string>` |

## Signatur und zurückgegebener Typ

`inSegment(<string>)`

Gibt einen booleschen Wert zurück.

## Beispiel

`inSegment("men over 50")`

Erklärung:

Die Funktion gibt **[!UICONTROL true]** zurück, wenn der Kontakt in der Journey-Instanz Teil des Adobe Experience Platform-Segments namens „Herren über 50“ ist, andernfalls wird **[!UICONTROL false]** zurückgegeben.
