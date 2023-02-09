---
product: adobe campaign
title: substr
description: Erfahren Sie mehr über die Funktion „substr“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: dda01de5-b865-4323-ac36-2e3d90d213ee
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 100%

---

# substr {#substr}

Gibt die Unterzeichenfolge des Zeichenfolgenausdrucks zwischen dem Anfangsindex und dem Endindex zurück. Wenn der Endindex nicht definiert ist, wird die Zeichenfolge zwischen dem Anfangsindex und dem Ende zurückgegeben.

## Kategorie

Zeichenfolge

## Funktionssyntax

`substr(<parameters>)`

## Parameter

| Parameter | type |
|-------------|----------|
| string | string |
| beginIndex | integer |
| endIndex | integer |

## Signatur und zurückgegebener Typ

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

Gibt eine Zeichenfolge zurück.

## Beispiel

`substr("Hello World",6)`

Gibt „World“ zurück.

`substr("Hello World", 0, 5)`

Gibt „Hello“ zurück.
