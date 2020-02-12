---
title: endWith
description: Erfahren Sie mehr über die Funktion „endWith“
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


# endWith {#endWith}

Gibt „true“ zurück, wenn der zweite Parameter ein Suffix des ersten Parameters ist.

## Kategorie

Zeichenfolge

## Funktionssyntax

`endWith(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| string | Zeichenfolge |
| suffix | Zeichenfolge |

## Signatur und zurückgegebener Typ

`endWith(<string>,<string>)`

Gibt einen booleschen Wert zurück.

## Beispiel

`endWith("Hello World", "World")`

Gibt „true“ zurück.

`endWith("Hello World", "Hello")`

Gibt „false“ zurück.
