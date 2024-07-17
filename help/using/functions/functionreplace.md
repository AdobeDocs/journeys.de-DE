---
product: adobe campaign
title: replace
description: Erfahren Sie mehr über die Funktion „replace“
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: f30377c2-4d5e-4905-a972-8f4ccb272bc0
source-git-commit: 8980df5cc238a7195f01a1631e418a8de677fbea
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 98%

---

# replace {#replace}

Ersetzt das erste Auftreten, das mit der Zielzeichenfolge übereinstimmt, in der Basiszeichenfolge durch die Ersatzzeichenfolge.

Die Ersetzung verläuft vom Anfang der Zeichenfolge zum Ende. Wenn Sie z. B. in der Zeichenfolge „aaa“ „aa“ durch „b“ ersetzen, erhalten Sie „ba“ und nicht „ab“.

## Kategorie

Zeichenfolge

## Funktionssyntax

`replace(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|--------------|
| base | string |
| target | string (RegExp) |
| replacement | string |

## Signatur und zurückgegebener Typ

`replace(<base>,<target>,<replacement>)`

Gibt eine Zeichenfolge zurück.

## Beispiel 1

`replace("Hello World", "l", "x")`

Gibt „Hexlo World“ zurück.

## Beispiel 2 {#example_2}

Da der Zielparameter ein regulärer Ausdruck ist, müssen Sie je nach der Zeichenfolge, die Sie ersetzen möchten, möglicherweise einige Zeichen auslassen. Siehe folgendes Beispiel:

* auszuwertende Zeichenfolge: `|OFFER_A|OFFER_B`
* bereitgestellt von einem Profilattribut `#{ExperiencePlatform.myFieldGroup.profile.myOffers}`
* Zeichenfolge, die ersetzt werden soll: `|OFFER_A`
* Zeichenfolge ersetzt durch: `''`
* Sie müssen `\\` vor dem Zeichen `|` hinzufügen.

Der Ausdruck lautet:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|OFFER_A', '')`

Die zurückgegebene Zeichenfolge lautet: `|OFFER_B`

Sie können auch die Zeichenfolge erstellen, die mit einem bestimmten Attribut ersetzt werden soll:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|' + #{ExperiencePlatform.myFieldGroup.profile.myOfferCode}, '')`
