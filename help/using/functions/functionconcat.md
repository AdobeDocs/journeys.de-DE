---
title: concat
description: Erfahren Sie mehr über das Funktionskonzat
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


# concat {#concat}

Verkettet zwei Zeichenfolgenparameter oder eine Liste von Zeichenfolgen.

## Kategorie

String

## Funktionssyntax

`concat(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Liste | listString |
| string | string |

## Unterschrift und zurückgegebener Typ

`concat(<string>,<string>)`

`concat(<listString>)`

Gibt eine Zeichenfolge zurück.

## Beispiel

`concat("Hello","World")`

Gibt &quot;HelloWorld&quot;zurück.

`concat(["Hello"," ","World"])`

Gibt &quot;Hello World&quot;zurück.
