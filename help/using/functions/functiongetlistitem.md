---
product: adobe campaign
solution: Journey Orchestration
title: getListItem
description: Erfahren Sie mehr über die Funktion „gstListItem“.
translation-type: tm+mt
source-git-commit: 5539ea0e8f124896f5599dba63babaa3e5b0229b
workflow-type: tm+mt
source-wordcount: '97'
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
| Liste | listString |
| Liste | listBoolean |
| Liste | listInteger |
| Liste | listDecimal |
| Liste | listDuration |
| Liste | listDateTime |
| Liste | listDateTimeOnly |
| Index | integer |

## Signaturen und zurückgegebener Typ

`getListItem(<listInteger>,<index>)`

Gibt eine Liste mit Ganzzahlen zurück.

`getListItem(<listDecimal>,<index>)`

Gibt eine Liste mit Dezimalzahlen zurück.

`getListItem(<listString>,<index>)`

Gibt eine Liste mit Zeichenfolgen zurück.

`getListItem(<listDateTimeOnly>,<index>)`

Gibt eine Liste mit Datum/Uhrzeit-Werten ohne Berücksichtigung der Zeitzone zurück.

`getListItem(<listDateTime>,<index>)`

Gibt eine Liste mit Datum/Uhrzeit-Werten zurück.

`getListItem(<listBoolean>,<index>)`

Gibt eine Liste mit booleschen Werten zurück.

`getListItem(<listDuration>,<index>)`

Gibt eine Liste der Dauer zurück.

## Beispiel

`getListItem([10, 2, 3], 1)`

Gibt „2“ zurück

`getListItem(["A", "B", "C"], 3)`
Gibt „C“ zurück

Beispiele mit dem Ereignisfeld „event.appVersion“ mit dem Wert: 20.45.2.3434

`split(@{event.appVersion}, "\\.")`

Gibt `["20", "45", "2", "3434"]` zurück

`getListItem(split(@{event.appVersion}, "\\."), 0)`

Gibt „20“ zurück