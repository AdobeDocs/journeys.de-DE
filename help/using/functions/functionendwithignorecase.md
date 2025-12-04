---
product: adobe campaign
title: endWithIgnoreCase
description: Erfahren Sie mehr über die Funktion „endWithIgnoreCase“
feature: Journeys
role: Developer
level: Experienced
exl-id: 3d14fe82-e287-4474-8d78-10efbf55d338
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 100%

---

# endWithIgnoreCase {#endWithIgnoreCase}

Überprüft, ob die erste Argumentzeichenfolge mit einer bestimmten Zeichenfolge endet (zweite Argumentzeichenfolge), wobei Groß-/Kleinschreibung nicht berücksichtigt wird.

## Kategorie

Zeichenfolge

## Funktionssyntax

`endWithIgnoreCase(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| string | string |
| suffix | string |

## Signatur und zurückgegebener Typ

`endWithIgnoreCase(<string>,<string>)`

Gibt einen booleschen Wert zurück.

## Beispiel

`endWithIgnoreCase("rowing is great", "AT")`

Gibt „true“ zurück.
