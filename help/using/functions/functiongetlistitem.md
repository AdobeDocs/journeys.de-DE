---
product: adobe campaign
solution: Journey Orchestration
title: getListItem
description: Informationen zur Funktion gstListItem
translation-type: tm+mt
source-git-commit: 5539ea0e8f124896f5599dba63babaa3e5b0229b
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 69%

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
| liste | listBoolean |
| liste | listInteger |
| liste | listDecimal |
| liste | listDuration |
| liste | listDateTime |
| liste | listDateTimeOnly |
| index | integer |

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

Gibt &quot;2&quot;zurück

`getListItem(["A", "B", "C"], 3)`
Gibt &quot;C&quot;zurück

Beispiele mit dem Ereignis &quot;Ereignis.appVersion&quot;mit dem Wert: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Gibt zurück.`["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

Gibt &quot;20&quot;zurück