---
title: inSegment
description: Informationen zur Funktion in Segment
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
source-git-commit: 7e69b19f2b7099e5c015dd1052a58728cf143ffa

---


# inSegment {#inSegment}

Überprüft, ob eine Person zu einem bestimmten Segment gehört.

Der Segmentname muss eine String-Konstante sein. Es kann weder ein Feldverweis noch ein Ausdruck sein.

Segmente werden in der [Adobe Experience Platform](https://platform.adobe.com/segment/overview)definiert. Der Ausdruckseditor stellt eine automatisch ausgefüllte Segmentliste bereit.

>[!NOTE]
>
>Sie können bis zu 100 Segmente abrufen.

## Kategorie

Adobe Experience Platform

## Funktionssyntax

`inSegment(<parameter>)`

## Parameter

| Parameter | Description | Typ |
|--- |--- |--- |
| Segment | Der Segmentname | `<string>` |

## Unterschrift und zurückgegebener Typ

`inSegment(<string>)`

Gibt einen booleschen Wert zurück.

## Beispiel

`inSegment("men over 50")`

Erklärung:

Die Funktion gibt &quot; **[!UICONTROL true]**&quot;zurück, wenn die Person in der Reiseinstanz Teil des Plattformsegments &quot;Herren über 50&quot;ist, andernfalls &quot;**[!UICONTROL  false]** &quot;.
