---
product: adobe campaign
solution: Journey Orchestration
title: containWithIgnoreCase
description: Erfahren Sie mehr über die Funktion „containWithIgnoreCase“
feature: Journeys
role: Data Engineer
level: Erfahren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 100%

---


# containWithIgnoreCase {#containWithIgnoreCase}

Überprüft, ob die zweite Argumentzeichenfolge in der ersten Argumentzeichenfolge enthalten ist, ohne Groß-/Kleinschreibung zu berücksichtigen.

## Kategorie

Zeichenfolge

## Funktionssyntax

`containWithIgnoreCase(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| string | Zeichenfolge |
| string searched | Zeichenfolge |

## Signatur und zurückgegebener Typ

`containWithIgnoreCase(<string>,<string>)`

Gibt einen booleschen Wert zurück.

## Beispiel

`containWithIgnoreCase("rowing is great', "GREAT")`

Gibt „true“ zurück.
