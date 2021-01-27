---
product: adobe campaign
solution: Journey Orchestration
title: containWithIgnoreCase
description: Erfahren Sie mehr über die Funktion „containWithIgnoreCase“
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '48'
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
