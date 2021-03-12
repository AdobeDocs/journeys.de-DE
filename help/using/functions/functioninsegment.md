---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: Erfahren Sie mehr über die Funktion „inSegment“
feature: Journeys
role: Dateningenieur
level: Erfahren
translation-type: tm+mt
source-git-commit: a99ad6a589bcd1f3083eabbcac35dd5c0497093d
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 70%

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
>Als Mitglieder des Segments werden nur Personen mit den Segmentteilsstatus **Realized** und **Vorhandene** betrachtet. Weitere Informationen zum Auswerten eines Segments finden Sie in der Dokumentation zum [Segmentierungsdienst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

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
