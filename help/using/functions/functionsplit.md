---
product: adobe campaign
solution: Journey Orchestration
title: split
description: Informationen zur Funktionsaufteilung
translation-type: tm+mt
source-git-commit: 135485c097f99483c2ddb3d03e0552f9ac134b44
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 25%

---


# split {#split}

Teilt die erste Argumentzeichenfolge mit einer Trennzeichenfolge (zweite Argumentzeichenfolge, bei der es sich um einen regulären Ausdruck handeln kann), um eine Liste von Zeichenfolgen (Token) zu erstellen.

## Kategorie

Zeichenfolge

## Funktionssyntax

`split(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| input string | Zeichenfolge |
| Trennzeichenfolge | string |

## Signaturen und zurückgegebener Typ

`split(<input string>, <separator string>)`

Gibt eine listString zurück.

## Beispiel

`split(["A_B_C"], "_")`

Gibt zurück.`["A","B","C"]`

Beispiel mit dem Ereignis &quot;Ereignis.appVersion&quot;mit dem Wert: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Gibt zurück.`["20", "45", "2", "3434"]`
