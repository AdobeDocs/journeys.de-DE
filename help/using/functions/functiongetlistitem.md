---
product: adobe campaign
solution: Journey Orchestration
title: getListItem
description: Erfahren Sie mehr über die Funktion „gstListItem“.
feature: Journeys
role: Dateningenieur
level: Erfahren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 97%

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