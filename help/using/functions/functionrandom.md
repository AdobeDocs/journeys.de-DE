---
title: random
description: Informationen zur Funktion random
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


# random {#random}

Erstellt eine Zufallszahl zwischen 0 und 1.

## Kategorie

Mathematik

## Funktionssyntax

`random(<parameters>)`

## Unterschrift und zurückgegebener Typ

`random()`

Gibt eine Dezimalstelle zurück.

## Beispiel

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

Erklärung: Wenn das Erfolgsverhältnis keinen Wert/null hat, wird der Standardwert angewendet und eine zufällige Zahl zwischen 0 und 1 * 100 (d. h. 0 bis 100) ist.
