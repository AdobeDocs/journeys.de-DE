---
product: adobe campaign
title: toInteger
description: Erfahren Sie mehr über die Funktion „toInteger“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3fcbf4dd-3ca5-4f4b-b774-af6ac3170768
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: ht
source-wordcount: '75'
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

`toInteger("4")`

Gibt 4 zurück.
