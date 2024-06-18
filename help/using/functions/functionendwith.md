---
product: adobe campaign
title: endWith
description: Erfahren Sie mehr über die Funktion „endWith“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 6eee6057-1daf-4b9d-ae94-2b35843e3a49
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: ht
source-wordcount: '43'
ht-degree: 100%

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
| string | string |
| suffix | string |

## Signatur und zurückgegebener Typ

`endWith(<string>,<string>)`

Gibt einen booleschen Wert zurück.

## Beispiel

`endWith("Hello World", "World")`

Gibt „true“ zurück.

`endWith("Hello World", "Hello")`

Gibt „false“ zurück.
