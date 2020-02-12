---
title: toDecimal
description: Erfahren Sie mehr über die Funktion „toDecimal“
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

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
| Zeichenfolge | konvertiert den Zeichenfolgenwert in eine Dezimalzahl |
| dateTime | konvertiert das Datum in die Zahl der Millisekunden (Millisekunden der Epoche) |
| boolean | wandelt den booleschen Wert in 1 um, wenn „true“, und in 0, wenn „false“ |
| Ganzzahl | konvertiert in eine Dezimalzahl (Beispiel: 1 wird zu 1.0) |

## Signaturen und zurückgegebene Typen

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

Gibt eine Dezimalzahl zurück.

## Beispiele

`toDecimal("4.0")`

Gibt 4.0 zurück.
