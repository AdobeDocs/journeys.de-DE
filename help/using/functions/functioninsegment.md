---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: Erfahren Sie mehr über die Funktion „inSegment“
feature: Journeys
role: Dateningenieur
level: Erfahren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 97%

---


# inSegment {#inSegment}

Überprüft, ob ein Kontakt zu einem bestimmten Segment gehört.

Der Segmentname muss eine Zeichenfolgenkonstante sein. Er darf weder ein Feldverweis noch ein Ausdruck sein.

Segmente werden in [Adobe Experience Platform](https://platform.adobe.com/segment/overview) definiert. Der Ausdruckseditor bietet eine automatisch ausgefüllte Segmentliste.

>[!NOTE]
>
>Sie können bis zu 100 Segmente abrufen.

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
