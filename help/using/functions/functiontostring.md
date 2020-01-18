---
title: toString
description: Informationen zur Funktion toString
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


# toString {#toString}

Konvertiert einen Argumentwert je nach Typ in einen Zeichenfolgenwert. Weitere Informationen zu Datentypen finden Sie unter [](../expression/data-types.md).

## Kategorie

Konversion

## Funktionssyntax

`toString(<parameter>)`

## Parameter

| Parameter | Description |
|--- |--- |
| dateTime | konvertiert das Datum im UTC-Datumsformat |
| dateTimeOnly | konvertiert das Datum im UTC-Datumsformat |
| duration | in die entsprechende Anzahl von Millisekunden als Zeichenfolge konvertieren |
| Zeitzone | in die Zeichenfolgendarstellung der Zeitzone-ID konvertieren (JODA-ID) |
| integer | konvertiert den Wert in eine Zeichenfolgendarstellung (1 wird zu &quot;1&quot;) |
| decimal | konvertiert den Wert in eine Zeichenfolgendarstellung (1.5 wird zu 1.5) |
| boolean | den booleschen Wert als &quot;true&quot;, wenn &quot;true&quot;, &quot;false&quot;, wenn &quot;false&quot; |

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

Gibt &quot;4&quot;zurück.
