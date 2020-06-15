---
title: startWithIgnoreCase
description: Erfahren Sie mehr über die Funktion „startWithIgnoreCase“
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 100%

---


# startWithIgnoreCase {#startWithIgnoreCase}

Gibt „true“ zurück, wenn der zweite Parameter ein Präfix des ersten Parameters ist (ohne Berücksichtigung der Groß-/Kleinschreibung).

## Kategorie

Zeichenfolge

## Funktionssyntax

`startWithIgnoreCase(<parameters>)`

## Parameter

| Parameter | Typ |
|-------------|--------|
| string | Zeichenfolge |
| prefix | Zeichenfolge |

## Signatur und zurückgegebener Typ

`startWithIgnoreCase(<string>,<string>)`

Geben einen booleschen Wert zurück.

## Beispiel

`startWith("rowing is great', "RO")`

Gibt „true“ zurück.
