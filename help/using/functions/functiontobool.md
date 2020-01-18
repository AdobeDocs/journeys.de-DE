---
title: toBool
description: Erfahren Sie mehr über die Funktion toBool
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


# toBool {#toBool}

Konvertiert einen Argumentwert je nach Typ in einen booleschen Wert.

* Aus Zeichenfolge: versuchen Sie, den Zeichenfolgenwert als booleschen Wert zu konvertieren, von &quot;true&quot;, wenn der Zeichenfolgenwert &quot;true&quot; ist, andernfalls &quot;false&quot;
* Von numerisch: true, wenn der numerische Wert nicht gleich 0 ist, andernfalls false

## Kategorie

Konversion

## Funktionssyntax

`toBool(<parameter>)`

## Parameter

* decimal
* boolean
* string
* integer

## Signaturen und zurückgegebene Typen

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

Gib einen Booleschen zurück.

## Beispiele

`toBool("true")`

`toBool(1)`

Gibt TRUE zurück.

`toBool("this is not a boolean")`

Gibt false zurück.
