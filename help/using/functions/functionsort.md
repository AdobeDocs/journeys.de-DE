---
product: adobe campaign
title: sort
description: Erfahren Sie mehr über die Funktion „sort“
feature: Journeys
role: Developer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 100%

---

# sort {#sort}

Sortiert eine Liste von Werten oder Objekten in ihrer natürlichen Reihenfolge.

## Kategorie

Liste

## Funktionssyntax

`sort(<parameters>)`

## Parameter

| Parameter | Typ | Beschreibung |
|-----------|------------------|------------------|
| listToSort | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly oder listObject | Zu sortierende Liste. Bei listObject muss es sich um einen Feldverweis handeln. |
| keyAttributeName | Zeichenfolge | Dieser Parameter ist nur für listObject. Der Attributname in den Objekten der angegebenen Liste wird als Schlüssel zum Filtern verwendet. |
| sortingOrder | Boolescher Wert | Aufsteigend (true) oder absteigend (false) |

## Signatur und zurückgegebener Typ

`sort(<listInteger>,<boolean>)`

Gibt eine Liste mit Ganzzahlen zurück.

`sort(<listDecimal>,<boolean>)`

Gibt eine Liste mit Dezimalzahlen zurück.

`sort(<listString>,<boolean>)`

Gibt eine Liste mit Zeichenfolgen zurück.

`sort(<listDateTimeOnly>,<boolean>)`

Gibt eine Liste mit Datum/Uhrzeit-Werten ohne Berücksichtigung der Zeitzone zurück.

`sort(<listDateTime>,<boolean>)`

Gibt eine Liste mit Datum/Uhrzeit-Werten zurück.

`sort(<listDateOnly>,<boolean>)`

Gibt eine Liste mit Datumsangaben zurück.

`sort(<listBoolean>,<boolean>)`

Gibt eine Liste mit booleschen Werten zurück.

`sort(<listObject>,<string>,<boolean>)`

Gibt eine Liste mit Objekten zurück.

## Beispiel

`sort(["A", "C", "B"], true)`

Gibt `["A","B","C"]` zurück.

`sort([1, 3, 2], false)`

Gibt `[3, 2, 1]` zurück.

