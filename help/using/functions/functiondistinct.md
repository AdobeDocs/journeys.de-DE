---
product: adobe campaign
title: distinct
description: Erfahren Sie mehr über die Funktion „distinct“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 034e4d77-2f0e-4117-9fd4-b9e35ef71a39
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: ht
source-wordcount: '90'
ht-degree: 100%

---

# distinct {#distinct}

Gibt die eindeutigen Werte der Liste ohne Nullwerte zurück.

## Kategorie

Liste

## Funktionssyntax

`distinct(<parameter>)`

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
| Liste | listDateOnly |

## Signaturen und zurückgegebene Typen

`distinct(<listInteger>)`

Gibt eine Liste mit Ganzzahlen zurück.

`distinct(<listDecimal>)`

Gibt eine Liste mit Dezimalzahlen zurück.

`distinct(<listString>)`

Gibt eine Liste mit Zeichenfolgen zurück.

`distinct(<listDateTimeOnly>)`

Gibt eine Liste mit Datum/Uhrzeit-Werten ohne Berücksichtigung der Zeitzone zurück.

`distinct(<listDateTime>)`

Gibt eine Liste mit Datum/Uhrzeit-Werten zurück.

`distinct(<listDateOnly>)`

Gibt eine Liste mit Datumsangaben zurück.

`distinct(<listBoolean>)`

Gibt eine Liste mit booleschen Werten zurück.

`distinct(<listDuration>)`

Gibt eine Liste der Dauer zurück.

## Beispiele

`distinct([10,2,10,null])`

Gibt `[10, 2]` zurück.
