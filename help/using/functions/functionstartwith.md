---
product: adobe campaign
title: startWith
description: Erfahren Sie mehr über die Funktion „startWith“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: bf0e75d6-cc7c-4a76-b215-8735eb62163b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '44'
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
