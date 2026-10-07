---
product: adobe campaign
title: getListItem
description: Erfahren Sie mehr über die Funktion „gstListItem“.
feature: Journeys
role: Developer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
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
source-wordcount: '93'
ht-degree: 100%
---
# getListItem {#gestListItem}

Gibt das Element der Liste am angegebenen Index zurück.

## Kategorie

Liste

## Funktionssyntax

`getListItem(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| list | listString |
| list | listBoolean |
| list | listInteger |
| list | listDecimal |
| list | listDuration |
| list | listDateTime |
| list | listDateTimeOnly |
| list | listDateOnly |
| index | integer |

## Signaturen und zurückgegebener Typ

`getListItem(<listInteger>,<index>)`

Gibt eine Ganzzahl zurück.

`getListItem(<listDecimal>,<index>)`

Gibt eine Dezimalzahl zurück.

`getListItem(<listString>,<index>)`

Gibt eine Zeichenfolge zurück.

`getListItem(<listDateTimeOnly>,<index>)`

Gibt einen Datum/Uhrzeit-Wert ohne Berücksichtigung der Zeitzone zurück.

`getListItem(<listDateTime>,<index>)`

Gibt einen Datum/Uhrzeit-Wert zurück.

`getListItem(<listDateOnly>,<index>)`

Gibt eine Liste mit Datumsangaben zurück.

`getListItem(<listBoolean>,<index>)`

Gibt einen booleschen Wert zurück.

`getListItem(<listDuration>,<index>)`

Gibt eine Dauer zurück.

## Beispiel

`getListItem([10, 2, 3], 1)`

Gibt „2“ zurück

`getListItem(["A", "B", "C"], 2)`
Gibt „C“ zurück

Beispiele mit dem Ereignisfeld „event.appVersion“ mit dem Wert: 20.45.2.3434

`split(@{event.appVersion}, "\\.")`

Gibt `["20", "45", "2", "3434"]` zurück

`getListItem(split(@{event.appVersion}, "\\."), 0)`

Gibt „20“ zurück
