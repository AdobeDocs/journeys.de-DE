---
product: adobe campaign
title: toBool
description: Erfahren Sie mehr über die Funktion „toBool“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 490144c2-1ecd-4772-ab15-e23b1b7d8f0c
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: ht
source-wordcount: '75'
ht-degree: 100%

---

# toBool {#toBool}

Konvertiert einen Argumentwert je nach Typ in einen booleschen Wert.

* Von Zeichenfolge: Versucht, den Zeichenfolgenwert in einen booleschen Wert zu konvertieren, von „true“, wenn der Zeichenfolgenwert „true“ ist, andernfalls „false“
* Von numerisch: „true“, wenn der numerische Wert ungleich 0 ist, andernfalls „false“

## Kategorie

Konversion

## Funktionssyntax

`toBool(<parameter>)`

## Parameter

* decimal
* boolean
* string
* Ganzzahl

## Signaturen und zurückgegebene Typen

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

Geben einen booleschen Wert zurück.

## Beispiele

`toBool("true")`

`toBool(1)`

Gibt „true“ zurück.

`toBool("this is not a boolean")`

Gibt „false“ zurück.
