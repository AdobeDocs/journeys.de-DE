---
product: adobe campaign
title: toInteger
description: Erfahren Sie mehr über die Funktion „toInteger“
feature: Journeys
role: Developer
level: Experienced
exl-id: 3fcbf4dd-3ca5-4f4b-b774-af6ac3170768
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
# toInteger {#toInteger}

Konvertiert einen Argumentwert in eine Ganzzahl.

## Kategorie

Konversion

## Funktionssyntax

`toInteger(<parameter>)`

## Parameter

| Parameter | Beschreibung |
|--- |--- |
| string | konvertiert den Zeichenfolgenwert in eine Ganzzahl |
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
