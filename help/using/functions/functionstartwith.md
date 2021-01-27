---
product: adobe campaign
solution: Journey Orchestration
title: startWith
description: Erfahren Sie mehr über die Funktion „startWith“
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 100%

---


# startWith {#startWith}

Gibt „true“ zurück, wenn der zweite Parameter ein Präfix des ersten Parameters ist.

## Kategorie

Zeichenfolge

## Funktionssyntax

`startWith(<parameters>)`

## Parameter

| Parameter | Typ |
|-------------|--------|
| string | Zeichenfolge |
| prefix | Zeichenfolge |

## Signatur und zurückgegebener Typ

`startWith(<string>,<string>)`

Geben einen booleschen Wert zurück.

## Beispiel

`startWith("Hello World", "Hello")`

Gibt „true“ zurück.

`startWith("Hello World", "World")`

Gibt „false“ zurück.
