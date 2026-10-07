---
product: adobe campaign
title: split
description: Erfahren Sie mehr über die Funktion „Aufspaltung“.
feature: Journeys
role: Developer
level: Experienced
exl-id: 44499a09-19e2-4085-bf2f-7d9080ec382d
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 100%
---
# split {#split}

Spaltet die erste Argumentzeichenfolge mit einer Trennzeichenfolge (zweite Argumentzeichenfolge, die ein regulärer Ausdruck sein kann) auf, um eine Liste von Zeichenfolgen (Token) zu erzeugen.

## Kategorie

Zeichenfolge

## Funktionssyntax

`split(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Eingabezeichenfolge | Zeichenfolge |
| Trennzeichenfolge | string |

## Signaturen und zurückgegebener Typ

`split(<input string>, <separator string>)`

Gibt eine listString zurück.

## Beispiel

`split(["A_B_C"], "_")`

Gibt `["A","B","C"]` zurück

Beispiel mit dem Ereignisfeld „event.appVersion“ mit dem Wert: 20.45.2.3434

`split(@{event.appVersion}, "\\.")`

Gibt `["20", "45", "2", "3434"]` zurück
