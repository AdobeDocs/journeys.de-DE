---
product: adobe campaign
title: in
description: Erfahren Sie mehr über die Funktion „in“
feature: Journeys
role: Developer
level: Experienced
exl-id: 6a19ae25-99c9-47f9-8417-c3d247dbbe3f
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
source-wordcount: '113'
ht-degree: 100%
---
# in {#in}

Überprüft, ob sich der erste Argumentwert in der Liste befindet. Die Prüfung wird mithilfe eines Gleichzeichens für jeden Argumentwert durchgeführt. Gibt „true“ zurück, wenn der Argumentwert gefunden wurde, andernfalls „false“.

Der Typ von `<expression>` muss mit Elementen der Liste übereinstimmen. Zur Erinnerung: Typen von Elementen in der Liste müssen miteinander übereinstimmen.

## Kategorie

Liste

## Funktionssyntax

`in(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| String | String |
| Boolesch | Boolesch |
| Ganzzahl | Ganzzahl |
| Dezimal | Dezimal |
| Dauer | Dauer |
| DateTime | DateTime |
| DateTimeOnly | DateTimeOnly |
| Liste | listString |
| Liste | listBoolean |
| Liste | listInteger |
| Liste | listDecimal |
| Liste | listDuration |
| Liste | listDateTime |
| Liste | listDateTimeOnly |
| Liste | listDateOnly |

## Signatur und zurückgegebener Typ

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<dateOnly>,<listDateOnly>)`

`in(<duration>,<listDuration>)`

Geben einen booleschen Wert zurück.

## Beispiel

`in(4,[4,5,3,4])`

Gibt „true“ zurück.

`in(8,[4,5,3,4])`

Gibt „false“ zurück.

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
