---
title: containsWithIgnoreCase
description: Informationen zur Funktion containsWithIgnoreCase
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
source-git-commit: a844adc1a073aebfb7fd8a719e52f305079260b7

---


# containsWithIgnoreCase {#containWithIgnoreCase}

Überprüft, ob die zweite Argumentzeichenfolge in der ersten Argumentzeichenfolge enthalten ist, ohne die Groß-/Kleinschreibung zu berücksichtigen.

## Kategorie

String

## Funktionssyntax

`containWithIgnoreCase(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| string | string |
| gesuchte Zeichenfolge | string |

## Unterschrift und zurückgegebener Typ

`containWithIgnoreCase(<string>,<string>)`

Gibt einen booleschen Wert zurück.

## Beispiel

`containWithIgnoreCase("rowing is great', "GREAT")`

Gibt TRUE zurück.
