---
product: adobe campaign
solution: Journey Orchestration
title: sort
description: Erfahren Sie mehr über die Funktion „sort“
feature: Journeys
role: Dateningenieur
level: Erfahren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 97%

---


# sort {#sort}

Sortiert eine Liste von Werten in ihrer natürlichen Reihenfolge. Das erste Argument ist die Liste der Werte, das zweite ist ein boolescher Wert, der angibt, ob die Sortierung aufsteigend (true) oder absteigend (false) ist.

## Kategorie

Liste

## Funktionssyntax

`sort(<parameters>)`

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
| Boolesch | Boolesch |

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

`sort(<listBoolean>,<boolean>)`

Gibt eine Liste mit booleschen Werten zurück.

## Beispiel

`sort(["A", "C", "B"], true)`

Gibt `["A","B","C"]` zurück.

`sort([1, 3, 2], false)`

Gibt `[3, 2, 1]` zurück.
