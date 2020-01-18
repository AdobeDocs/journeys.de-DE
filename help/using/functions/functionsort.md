---
title: Sortierung
description: Informationen zur Funktionssortierung
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

---


# Sortierung {#sort}

Sortiert eine Liste von Werten in der natürlichen Reihenfolge. Das erste Argument ist die Liste der Werte, das zweite ist ein boolescher Wert, der angibt, ob die Sortierung aufsteigend (true) oder absteigend (false) ist.

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

## Unterschrift und zurückgegebener Typ

`sort(<listInteger>,<boolean>)`

Gibt eine Liste mit Ganzzahlen zurück.

`sort(<listDecimal>,<boolean>)`

Gibt eine Liste mit Dezimalstellen zurück.

`sort(<listString>,<boolean>)`

Gibt eine Liste mit Zeichenfolgen zurück.

`sort(<listDateTimeOnly>,<boolean>)`

Gibt eine Liste der Datenzeiten ohne Berücksichtigung der Zeitzone zurück.

`sort(<listDateTime>,<boolean>)`

Gibt eine Liste der Datenzeiten zurück.

`sort(<listBoolean>,<boolean>)`

Gibt eine Liste der Booleschen Elemente zurück.

## Beispiel

`sort(["A", "C", "B"], true)`

Gibt zurück `["A","B","C"]`.

`sort([1, 3, 2], false)`

Gibt zurück `[3, 2, 1]`.
