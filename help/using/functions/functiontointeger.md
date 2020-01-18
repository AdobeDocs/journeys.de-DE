---
title: toInteger
description: Informationen zur Funktion toInteger
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

---


# toInteger {#toInteger}

Konvertiert einen Argumentwert in eine Ganzzahl.

## Kategorie

Konversion

## Funktionssyntax

`toInteger(<parameter>)`

## Parameter

| Parameter | Description |
|--- |--- |
| string | konvertiert den Zeichenfolgenwert als Ganzzahl |
| dateTime | Konvertiert das Datum als Anzahl der Millisekunden (etwa Millisekunden) |
| decimal | wird in eine Ganzzahl umgewandelt, indem der Dezimalteil entfernt wird (Beispiel: 1.5 wird zu 1) |
| boolean | wandelt den booleschen Wert in 1 um, wenn true, 0, wenn false |

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
