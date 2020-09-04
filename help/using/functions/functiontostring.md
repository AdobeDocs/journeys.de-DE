---
title: toString
description: Erfahren Sie mehr über die Funktion „toString“
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: 239efa9592b011c70e2fc331df8f33820301253d
workflow-type: ht
source-wordcount: '112'
ht-degree: 100%

---


# toString {#toString}

Konvertiert einen Argumentwert je nach Typ in einen Zeichenfolgenwert. Weitere Informationen zu Datentypen finden Sie unter [](../expression/data-types.md).

## Kategorie

Konversion

## Funktionssyntax

`toString(<parameter>)`

## Parameter

| Parameter | Beschreibung |
|--- |--- |
| dateTime | konvertiert das Datum in das UTC-Datumsformat |
| dateTimeOnly | konvertiert das Datum in das UTC-Datumsformat |
| duration | konvertiert in die entsprechende Anzahl von Millisekunden als Zeichenfolge |
| time zone | konvertiert in die Zeichenfolgendarstellung der Zeitzonen-ID (JODA-ID) |
| integer | konvertiert den Wert in eine Zeichenfolgendarstellung (1 wird zu &quot;1&quot;) |
| decimal | konvertiert den Wert in eine Zeichenfolgendarstellung (1.5 wird zu &quot;1,5&quot;) |
| boolean | konvertiert den booleschen Wert in &#39;true&#39;, wenn „true“, in &#39;false&#39;, wenn „false“ |

## Signaturen und zurückgegebener Typ

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<timeZone>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

Gibt eine Zeichenfolge zurück.

## Beispiel

`toString(4)`

Gibt „4“ zurück.
