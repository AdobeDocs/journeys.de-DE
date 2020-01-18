---
title: in
description: Informationen zur Funktion in
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


# in {#in}

Überprüft, ob der erste Argumentwert in der Liste enthalten ist. Die Prüfung wird mit einem Equal für jeden Argumentwert durchgeführt. Gibt TRUE zurück, wenn der Argumentwert gefunden wurde, andernfalls FALSE.

Der Typ der Liste `<expression>` muss mit Elementen der Liste übereinstimmen. Elemente der Liste müssen als Erinnerung übereinstimmen.

## Kategorie

Liste

## Funktionssyntax

`in(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| String | String |
| Boolesch | Boolesch |
| Integer | Integer |
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

## Unterschrift und zurückgegebener Typ

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<duration>,<listDuration>)`

Gib einen Booleschen zurück.

## Beispiel

`in(4,[4,5,3,4])`

Gibt TRUE zurück.

`in(8,[4,5,3,4])`

Gibt false zurück.

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
