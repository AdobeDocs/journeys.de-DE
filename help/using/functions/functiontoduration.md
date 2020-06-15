---
title: toDuration
description: Erfahren Sie mehr über die Funktion „toDuration“
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
source-git-commit: 239efa9592b011c70e2fc331df8f33820301253d
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 100%

---


# toDuration {#toDuration}

Konvertiert einen Argumentwert in eine Dauer. Weiterführende Informationen finden Sie im Abschnitt [](../expression/data-types.md).

## Kategorie

Konversion

## Funktionssyntax

`toDuration(<parameter>)`

## Parameter

| Parameter | Beschreibung |
|--- |--- |
| Zeichenfolge | Formate, die auf dem ISO 8601-Dauerformat PnDTnHnMn.nS basieren, wobei Tage als genau 24 Stunden betrachtet werden. |
| Ganzzahl | Zahl der Millisekunden |

Wenn Zeichenfolgenausdruck: Akzeptierte Formate basieren auf dem ISO 8601-Dauerformat PnDTnHnMn.nS, wobei Tage als genau 24 Stunden betrachtet werden.

Die Zeichenfolge beginnt mit einem optionalen Zeichen, markiert durch das negative oder positive ASCII-Symbol. Bei negativen Werten wird der gesamte Zeitraum negiert. Der ASCII-Buchstabe „P“ folgt in Groß- oder Kleinschreibung. Dann gibt es vier Bereiche, die jeweils aus einer Zahl und einem Suffix bestehen. Die Bereiche weisen die ASCII-Suffixe von „D“, „H“, „M“ und „S“ für Tage, Stunden, Minuten und Sekunden auf, akzeptiert in Groß- oder Kleinschreibung. Die Suffixe müssen in richtiger Reihenfolge erscheinen. Der ASCII-Buchstabe „T“ muss vor dem ersten Auftreten, so vorhanden, einer Stunde, einer Minute oder eines zweiten Bereichs stehen. Es muss mindestens einer der vier Bereiche vorhanden sein und wenn „T“ vorhanden ist, muss mindestens ein Bereich auf das „T“ folgen. Der Zahlenteil der einzelnen Bereiche muss aus einer oder mehreren ASCII-Ziffern bestehen. Der Zahl kann das negative oder positive ASCII-Symbol vorangestellt werden. Die Zahl der Tage, Stunden und Minuten muss zu einem „long“ ausgewertet werden. Die Zahl der Sekunden muss zu einem „long“ mit optionalem Bruch ausgewertet werden. Das Dezimalzeichen kann ein Punkt oder ein Komma sein. Der Bruchteil kann zwischen null und neun Stellen aufweisen.

## Signaturen und zurückgegebener Typ

`toDuration(<string>)`

`toDuration(<integer>)`

Gibt eine Dauer zurück.

## Beispiele

`toDuration("PT10H")`

Gibt eine Dauer von 10 Stunden zurück.

`toDuration("PT4S")`

Gibt eine Dauer von 4 Sekunden zurück.

`toDuration(4000)`

Gibt eine Dauer von 4 Sekunden zurück.
