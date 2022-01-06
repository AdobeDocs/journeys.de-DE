---
product: adobe campaign
title: getListItem
description: Erfahren Sie mehr über die Funktion „gstListItem“.
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: ht
source-wordcount: '90'
ht-degree: 100%

---

# getListItem {#gestListItem}

Gibt das Element der Liste an der angegebenen Indexposition zurück.

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
