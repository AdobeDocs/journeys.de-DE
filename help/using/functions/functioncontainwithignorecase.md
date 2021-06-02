---
product: adobe campaign
title: containWithIgnoreCase
description: Erfahren Sie mehr über die Funktion „containWithIgnoreCase“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '49'
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
