---
product: adobe campaign
title: distinctWithNull
description: Erfahren Sie mehr über die Funktion „distinctWithNull“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 65a904c1-14ff-42b3-8f03-abb97ef47625
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 100%

---

# distinctWithNull {#distinctWithNull}

Gibt die eindeutigen Werte der Liste zurück. Wenn die Liste mindestens einen Nullwert enthält, wird ein Nullwert in der zurückgegebenen Liste angezeigt.

## Kategorie

Liste

## Funktionssyntax

`distinctWithNull(<parameter>)`

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

## Signaturen und zurückgegebene Typen

`distinctWithNull(<listInteger>)`

Gibt eine Liste mit Ganzzahlen zurück.

`distinctWithNull(<listDecimal>)`

Gibt eine Liste mit Dezimalzahlen zurück.

`distinctWithNull(<listString>)`

Gibt eine Liste mit Zeichenfolgen zurück.

`distinctWithNull(<listDateTimeOnly>)`

Gibt eine Liste mit Datum/Uhrzeit-Werten ohne Berücksichtigung der Zeitzone zurück.

`distinctWithNull(<listDateTime>)`

Gibt eine Liste mit Datum/Uhrzeit-Werten zurück.

`distinctWithNull(<listBoolean>)`

Gibt eine Liste mit booleschen Werten zurück.

`distinctWithNull(<listDuration>)`

Gibt eine Liste der Dauer zurück.

## Beispiele

`distinctWithNull([10,2,10,null])`

Gibt [10, 2, null] zurück.
