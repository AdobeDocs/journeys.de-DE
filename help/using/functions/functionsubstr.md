---
title: substr
description: Erfahren Sie mehr über die Funktion „substr“
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: ht
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: ht
source-wordcount: '64'
ht-degree: 100%

---


# substr {#substr}

Gibt die Unterzeichenfolge des Zeichenfolgenausdrucks zwischen dem Anfangsindex und dem Endindex zurück. Wenn der Endindex nicht definiert ist, wird die Zeichenfolge zwischen dem Anfangsindex und dem Ende zurückgegeben.

## Kategorie

Zeichenfolge

## Funktionssyntax

`substr(<parameters>)`

## Parameter

| Parameter | type |
|-------------|----------|
| string | Zeichenfolge |
| beginIndex | Ganzzahl |
| endIndex | Ganzzahl |

## Signatur und zurückgegebener Typ

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

Gibt eine Zeichenfolge zurück.

## Beispiel

`substr("Hello World",6)`

Gibt „World“ zurück.

`substr("Hello World", 0, 5)`

Gibt „Hello“ zurück.