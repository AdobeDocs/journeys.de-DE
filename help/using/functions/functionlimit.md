---
product: adobe campaign
title: limit
description: Erfahren Sie mehr über die Funktion „limit“.
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7e006660-1206-4b8a-9e5b-c6fbeee9cc8f
source-git-commit: 9f5ef0497227a370e2e1f4a62450611ae2e336b9
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 100%

---

# limit {#limit}

Gibt die ersten oder letzten n Elemente einer Liste zurück.

## Kategorie

Liste

## Funktionssyntax

`limit(<parameters>)`

## Parameter

| Parameter | Typ | Beschreibung |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly oder listObject | Zu sortierende Liste. Bei listObject muss es sich um einen Feldverweis handeln. |
| numberOfItems | integer | Anzahl der aus der angegebenen Liste zurückzugebenden Elemente. |
| firstOrLastItems | Boolescher Wert | Dieser Parameter ist optional (standardmäßig „true“). „True“ gibt die ersten Elemente zurück. „False“ gibt die letzten Elemente zurück. |

## Signatur und zurückgegebener Typ

`limit(<listString>,<integer>)`
`limit(<listString>,<integer>,<boolean>)`

Gibt eine Liste mit Zeichenfolgen zurück.

`limit(<listInteger>,<integer>)`
`limit(<listInteger>,<integer>,<boolean>)`

Gibt eine Liste mit Ganzzahlen zurück.

`limit(<listDecimal>,<integer>)`
`limit(<listDecimal>,<integer>,<boolean>)`

Gibt eine Liste mit Dezimalzahlen zurück.

`limit(<listBoolean>,<integer>)`
`limit(<listBoolean>,<integer>,<boolean>)`

Gibt eine Liste mit booleschen Werten zurück.

`limit(<listDateOnly>,<integer>)`
`limit(<listDateOnly>,<integer>,<boolean>)`

Gibt eine Liste mit Datumsangaben zurück.

`limit(<listDateTimeOnly>,<integer>)`
`limit(<listDateTimeOnly>,<integer>,<boolean>)`

Gibt eine Liste mit Datum/Uhrzeit-Werten ohne Berücksichtigung der Zeitzone zurück.

`limit(<listDateTime>,integer>)`
`limit(<listDateTime>,<integer>,<boolean>)`

Gibt eine Liste mit Datum/Uhrzeit-Werten zurück.

`limit(<listDuration>,<integer>)`
`limit(<listDuration>,<integer>,<boolean>)`

Gibt eine Liste der Dauer zurück.

`limit(<listObject>,<integer>)`
`limit(<listObject>,<integer>,<boolean>)`

Gibt eine Liste mit Objekten zurück.

## Beispiel

`limit(["A", "B", "C", "D", "E"], 3)`

Gibt `["A","B","C"]` zurück.

`limit(["A", "B", "C", "D", "E"], 3, false)`

Gibt `["C","D","E"]` zurück.
