---
product: adobe campaign
solution: Journey Orchestration
title: serializeList
description: Erfahren Sie mehr über die Funktion „serializeList“
feature: Journeys
role: Dateningenieur
level: Erfahren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 96%

---


# serializeList {#serializeList}

Konvertiert die im ersten Parameter angegebene Liste (beliebiger Typ) in eine Zeichenfolge. Der zweite Parameter stellt das zu verwendende Trennzeichen dar. Der dritte Parameter ist ein boolescher Wert, der angibt, ob die einzelnen Elemente des Ausdrucks Anführungszeichen umfassen sollen.

## Kategorie

Liste

## Funktionssyntax

`serializeList(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Zeichenfolge | Zeichenfolge |
| Boolesch | Boolesch |
| DateTimeOnly | DateTimeOnly |
| Liste | listString |
| Liste | listBoolean |
| Liste | listPoint |
| Liste | listDecimal |
| Liste | listDuration |
| Liste | listDateTime |
| Liste | listDateTimeOnly |

## Signatur und zurückgegebener Typ

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

Gibt eine Zeichenfolge zurück.

## Beispiel

`serializeList(["Hello","World"], " ", false)`

Gibt „Hello World“ zurück.

`serializeList(["Hello", "World"], ",", true)`

Gibt „&quot;Hello&quot;,&quot;World&quot;“ zurück.
