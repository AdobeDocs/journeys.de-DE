---
product: adobe campaign
title: toBool
description: Erfahren Sie mehr über die Funktion „toBool“
feature: Journeys
role: Developer
level: Experienced
exl-id: 490144c2-1ecd-4772-ab15-e23b1b7d8f0c
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
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
