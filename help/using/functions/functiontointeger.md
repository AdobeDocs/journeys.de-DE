---
product: adobe campaign
solution: Journey Orchestration
title: toInteger
description: Erfahren Sie mehr über die Funktion „toInteger“
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 100%

---


# toInteger {#toInteger}

Konvertiert einen Argumentwert in eine Ganzzahl.

## Kategorie

Konversion

## Funktionssyntax

`toInteger(<parameter>)`

## Parameter

| Parameter | Beschreibung |
|--- |--- |
| Zeichenfolge | konvertiert den Zeichenfolgenwert in eine Ganzzahl |
| dateTime | konvertiert das Datum in die Zahl der Millisekunden (Millisekunden der Epoche) |
| decimal | konvertiert in eine Ganzzahl, indem der Dezimalteil entfernt wird (Beispiel: 1.5 wird zu 1) |
| boolean | wandelt den booleschen Wert in 1 um, wenn „true“, und in 0, wenn „false“ |

## Signaturen und zurückgegebener Typ

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

Gibt eine Ganzzahl zurück.

## Beispiele

`toInteger(4)`

Gibt 4 zurück.
