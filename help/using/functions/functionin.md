---
title: in
description: Erfahren Sie mehr über die Funktion „in“
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: ht
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: ht
source-wordcount: '111'
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
| Zeichenfolge | Zeichenfolge |
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

## Signatur und zurückgegebener Typ

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<duration>,<listDuration>)`

Geben einen booleschen Wert zurück.

## Beispiel

`in(4,[4,5,3,4])`

Gibt „true“ zurück.

`in(8,[4,5,3,4])`

Gibt „false“ zurück.

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
