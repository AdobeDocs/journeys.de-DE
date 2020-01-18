---
title: toDecimal
description: Informationen zur Funktion toDecimal
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


# toDecimal {#toDecimal}

Konvertiert einen Argumentwert je nach Typ in einen Dezimalwert.

## Kategorie

Konversion

## Funktionssyntax

`toDecimal(<parameter>)`

## Parameter

| Parameter | Description |
|--- |--- |
| string | wandelt den Zeichenfolgenwert als Dezimalzahl um |
| dateTime | Konvertiert das Datum als Anzahl der Millisekunden (etwa Millisekunden) |
| boolean | wandelt den booleschen Wert in 1 um, wenn true, 0, wenn false |
| integer | wird in eine Dezimalstelle umgewandelt (Beispiel).: 1 wird 1.0) |

## Signaturen und zurückgegebene Typen

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

Gibt eine Dezimalstelle zurück.

## Beispiele

`toDecimal("4.0")`

Gibt 4.0 zurück.
