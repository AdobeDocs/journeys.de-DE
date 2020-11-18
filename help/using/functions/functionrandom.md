---
title: random
description: Erfahren Sie mehr über die Funktion „random“
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
source-wordcount: '51'
ht-degree: 100%

---


# random {#random}

Generiert eine zufällige Zahl zwischen 0 und 1.

## Kategorie

Mathematisch

## Funktionssyntax

`random(<parameters>)`

## Signatur und zurückgegebener Typ

`random()`

Gibt eine Dezimalzahl zurück.

## Beispiel

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

Erklärung: Wenn das Erfolgsverhältnis keinen Wert hat/null lautet, wird der Standardwert angewendet und ist eine zufällige Zahl zwischen 0 und 1 * 100 (d. h. zwischen 0 und 100).
