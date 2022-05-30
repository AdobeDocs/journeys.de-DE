---
product: adobe campaign
title: limit
description: Erfahren Sie mehr über die Funktionsbeschränkung
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 45%

---

# limit {#limit}

Gibt die ersten oder letzten N Elemente einer Liste zurück.

## Kategorie

Liste

## Funktionssyntax

`limit(<parameters>)`

## Parameter

| Parameter | Typ | Beschreibung |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly oder listObject | Liste zum Sortieren. Bei listObject muss es sich um einen Feldverweis handeln. |
| numberOfItems | integer | Anzahl der aus der angegebenen Liste zurückzugebenden Elemente. |
| firstOrLastItems | boolean | Dieser Parameter ist optional (standardmäßig &quot;true&quot;). &quot;true&quot;gibt die ersten Elemente zurück. false gibt die letzten Elemente zurück. |

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

Gibt eine Liste von Objekten zurück.

## Beispiel

`limit(["A", "B", "C", "D", "E"], 3)`

Gibt `["A","B","C"]` zurück.

`limit(["A", "B", "C", "D", "E"], 3, false)`

Gibt `["C","D","E"]` zurück.
