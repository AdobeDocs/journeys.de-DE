---
title: containWithIgnoreCase
description: Erfahren Sie mehr über die Funktion „containWithIgnoreCase“
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: a844adc1a073aebfb7fd8a719e52f305079260b7

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
