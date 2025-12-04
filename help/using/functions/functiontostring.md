---
product: adobe campaign
title: toString
description: Erfahren Sie mehr über die Funktion „toString“
feature: Journeys
role: Developer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 100%

---

# toString {#toString}

Konvertiert einen Argumentwert je nach Typ in einen Zeichenfolgenwert. Weitere Informationen zu Datentypen finden Sie auf [dieser Seite](../expression/data-types.md).

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
| integer | konvertiert den Wert in eine Zeichenfolgendarstellung (1 wird zu &quot;1&quot;) |
| decimal | konvertiert den Wert in eine Zeichenfolgendarstellung (1.5 wird zu &quot;1,5&quot;) |
| boolean | konvertiert den booleschen Wert in &#39;true&#39;, wenn „true“, in &#39;false&#39;, wenn „false“ |

## Signaturen und zurückgegebener Typ

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

Gibt eine Zeichenfolge zurück.

## Beispiel

`toString(4)`

Gibt „4“ zurück.
