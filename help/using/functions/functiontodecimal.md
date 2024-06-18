---
product: adobe campaign
title: toDecimal
description: Erfahren Sie mehr über die Funktion „toDecimal“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 11d7013c-2190-4654-8466-920861c836f5
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: ht
source-wordcount: '76'
ht-degree: 100%

---

# toDecimal {#toDecimal}

Konvertiert einen Argumentwert je nach Typ in einen Dezimalwert.

## Kategorie

Konversion

## Funktionssyntax

`toDecimal(<parameter>)`

## Parameter

| Parameter | Beschreibung |
|--- |--- |
| string | konvertiert den Zeichenfolgenwert in eine Dezimalzahl |
| dateTime | konvertiert das Datum in die Zahl der Millisekunden (Millisekunden der Epoche) |
| boolean | wandelt den booleschen Wert in 1 um, wenn „true“, und in 0, wenn „false“ |
| integer | konvertiert in eine Dezimalzahl (Beispiel: 1 wird zu 1.0) |

## Signaturen und zurückgegebene Typen

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

Gibt eine Dezimalzahl zurück.

## Beispiele

`toDecimal("4.0")`

Gibt 4.0 zurück.
