---
product: adobe campaign
title: distinct
description: Erfahren Sie mehr über die Funktion „distinct“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 034e4d77-2f0e-4117-9fd4-b9e35ef71a39
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 44%

---

# distinct {#distinct}

Gibt die eindeutigen Werte oder Objekte einer angegebenen Liste zurück. Null-Einträge werden ignoriert.

## Kategorie

Liste

## Funktionssyntax

`distinct(<parameters>)`

## Parameter

| Parameter | Typ | Beschreibung |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly oder listObject | Zu verarbeitende Liste. Bei listObject muss es sich um einen Feldverweis handeln. |
| keyAttributeName | Zeichenfolge | Dieser Parameter ist optional und nur für listObject. Wenn der Parameter nicht angegeben wird, wird ein Objekt als dupliziert betrachtet, wenn alle Attribute dieselben Werte aufweisen. Andernfalls wird ein Objekt als dupliziert betrachtet, wenn das angegebene Attribut denselben Wert aufweist. |

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

`distinct(<listObject>)`

`distinct(<listObject>,<string>)`

Gibt eine Liste von Objekten zurück.


## Beispiele

`distinct([10,2,10,null])`

Gibt `[10, 2]` zurück.
