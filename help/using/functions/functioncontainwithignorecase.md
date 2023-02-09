---
product: adobe campaign
title: containIgnoreCase
description: Erfahren Sie mehr über die Funktion „containIgnoreCase“.
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
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
| string searched | string |

## Signatur und zurückgegebener Typ

`containIgnoreCase(<string>,<string>)`

Gibt einen booleschen Wert zurück.

## Beispiel

`containIgnoreCase("rowing is great", "GREAT")`

Gibt „true“ zurück.
