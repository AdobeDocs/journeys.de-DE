---
product: adobe campaign
solution: Journey Orchestration
title: endWithIgnoreCase
description: Erfahren Sie mehr über die Funktion „endWithIgnoreCase“
feature: Journeys
role: Dateningenieur
level: Erfahren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 94%

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
| string | Zeichenfolge |
| suffix | Zeichenfolge |

## Signatur und zurückgegebener Typ

`endWithIgnoreCase(<string>,<string>)`

Gibt einen booleschen Wert zurück.

## Beispiel

`endWithIgnoreCase("rowing is great', "AT")`

Gibt „true“ zurück.
