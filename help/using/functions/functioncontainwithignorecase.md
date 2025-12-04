---
product: adobe campaign
title: containIgnoreCase
description: Erfahren Sie mehr über die Funktion „containIgnoreCase“.
feature: Journeys
role: Developer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 100%

---

# containIgnoreCase {#containIgnoreCase}

Überprüft, ob die zweite Argumentzeichenfolge in der ersten Argumentzeichenfolge enthalten ist, ohne Groß-/Kleinschreibung zu berücksichtigen.

## Kategorie

Zeichenfolge

## Funktionssyntax

`containIgnoreCase(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| string | string |
| string searched | Zeichenfolge |

## Signatur und zurückgegebener Typ

`containIgnoreCase(<string>,<string>)`

Gibt einen booleschen Wert zurück.

## Beispiel

`containIgnoreCase("rowing is great", "GREAT")`

Gibt „true“ zurück.
