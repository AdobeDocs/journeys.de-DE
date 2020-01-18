---
title: toDuration
description: Informationen zur Funktion toDuration
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

---


# toDuration {#toDuration}

Konvertiert einen Argumentwert in eine Dauer. For more information on data types, refer to [](../expression/data-types.md).

## Kategorie

Konversion

## Funktionssyntax

`toDuration(<parameter>)`

## Parameter

| Parameter | Description |
|--- |--- |
| string | Formate, die auf dem ISO-8601-Längenformat PnDTnHnMn.nS basieren, wobei die Tage als genau 24 Stunden betrachtet werden |
| integer | Anzahl der Millisekunden |

Wenn Zeichenfolgenausdruck: akzeptierte Formate basieren auf dem ISO-8601-Format PnDTnHnMn.nS mit Tagen als genau 24 Stunden.

Die Zeichenfolge beginnt mit einem optionalen Zeichen, gekennzeichnet durch das negative oder positive ASCII-Symbol. Bei negativen Werten wird der gesamte Zeitraum negiert. Der ASCII-Buchstabe &quot;P&quot;ist der nächste in Groß- oder Kleinschreibung. Es gibt dann vier Abschnitte, die jeweils aus einer Zahl und einem Suffix bestehen. Die Abschnitte haben Suffixe in ASCII von &quot;D&quot;, &quot;H&quot;, &quot;M&quot; und &quot;S&quot; für Tage, Stunden, Minuten und Sekunden, akzeptiert in Groß- oder Kleinschreibung. Die Suffixe müssen in der richtigen Reihenfolge auftreten. Der ASCII-Buchstabe &quot;T&quot;muss vor dem ersten Vorkommen, falls vorhanden, einer Stunde, einer Minute oder eines zweiten Abschnitts stehen. Es muss mindestens einer der vier Abschnitte vorhanden sein, und wenn &quot;T&quot; vorhanden ist, muss mindestens ein Abschnitt nach dem &quot;T&quot; vorhanden sein. Der Zahlenbereich jedes Abschnitts muss aus einer oder mehreren ASCII-Ziffern bestehen. Der Zahl kann das negative oder positive ASCII-Symbol vorangestellt werden. Die Anzahl der Tage, Stunden und Minuten muss analysiert werden. Die Anzahl der Sekunden muss zusammen mit der optionalen Fraktion analysiert werden. Der Dezimalpunkt kann ein Punkt oder ein Komma sein. Der Bruchteil kann zwischen null und neun Stellen liegen.

## Signaturen und zurückgegebener Typ

`toDuration(<string>)`

`toDuration(<integer>)`

Gibt eine Dauer zurück.

## Beispiele

`toDuration("PT10H")`

Gibt die Dauer von 10 Stunden zurück.

`toDuration("PT4S")`

Gibt die Dauer von 4s zurück.

`toDuration(4000)`

Gibt die Dauer von 4s zurück.
