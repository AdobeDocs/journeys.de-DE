---
product: adobe campaign
title: replace
description: Erfahren Sie mehr über die Funktion „replace“
feature: Journeys
role: Developer
level: Experienced
exl-id: f30377c2-4d5e-4905-a972-8f4ccb272bc0
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
source-wordcount: '148'
ht-degree: 100%
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
| replacement | Zeichenfolge |

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
