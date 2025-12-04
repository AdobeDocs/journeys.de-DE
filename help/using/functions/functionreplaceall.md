---
product: adobe campaign
title: replaceAll
description: Erfahren Sie mehr über die Funktion „replaceAll“
feature: Journeys
role: Developer
level: Experienced
exl-id: d60059e5-6bf8-4a57-88a4-5323d5f0fa0b
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 100%

---

# replaceAll {#replaceAll}

Ersetzt jedes Auftreten, das mit der Zielzeichenfolge übereinstimmt, in der Basiszeichenfolge durch die Ersatzzeichenfolge.

Die Ersetzung verläuft vom Anfang der Zeichenfolge zum Ende. Wenn Sie z. B. in der Zeichenfolge „aaa“ „aa“ durch „b“ ersetzen, erhalten Sie „ba“ und nicht „ab“.

## Kategorie

Zeichenfolge

## Funktionssyntax

`replaceAll(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|--------------|
| base | string |
| target | string (RegExp) |
| replacement | string |

## Signatur und zurückgegebener Typ

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

Gibt eine Zeichenfolge zurück.

## Beispiel{#example}

`replaceAll("Hello World", "l", "x")`

Gibt „Hexxo Worxd“ zurück.

Da der Zielparameter ein regulärer Ausdruck ist, müssen Sie je nach der Zeichenfolge, die Sie ersetzen möchten, möglicherweise einige Zeichen auslassen. Siehe Beispiel auf [diese Seite](../functions/functionreplace.md#example_2).
