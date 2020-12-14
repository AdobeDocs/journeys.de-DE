---
product: adobe campaign
solution: Journey Orchestration
title: toDateTime
description: Erfahren Sie mehr über die Funktion „toDateTime“
translation-type: ht
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: ht
source-wordcount: '93'
ht-degree: 100%

---

# toDateTime {#toDateTime}

Konvertiert Parameter je nach Typ in einen Datum/Uhrzeit-Wert.

## Kategorie

Konversion

## Funktionssyntax

`toDateTime(<parameters>)`

## Parameter

| Parameter | Typ |
|-----------|------------------|
| Datum/Uhrzeit im ISO 8601-Format | Zeichenfolge |
| Zeitzonen-ID | Zeichenfolge |
| Datum/Uhrzeit ohne Zeitzone | dateTimeOnly |
| ganzzahliger Wert einer Epoche in Millisekunden | Ganzzahl |

>[!NOTE]
>
>Die Zeitzonen-ID muss eine Zeichenfolgenkonstante sein. Sie darf weder ein Feldverweis noch ein Ausdruck sein. Weitere Informationen zu Datentypen finden Sie auf [dieser Seite](../expression/data-types.md).

## Signaturen und zurückgegebene Typen

`toDateTime(<string>)`

`toDateTime(<dateTimeOnly>,<stringified time zone id>)`

`toDateTime(<integer>)`

Gibt einen **Datum/Uhrzeit-Wert** zurück.

<!--`toDateTime(<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`

Returns a date time with default time zone UTC.

`toDateTime(<year>,<month>,<dayOfMonth>)`
`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>)`
`toDateTime(<timeZone>,<year>,<month>,<dayOfMonth>)`

Return a datetime where hour, minute and second set to 0.

`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`
`toDateTime(<string>)`
`toDateTime(<string>,<integer>)`
`toDateTime(<stringified timeZone>,<dateTimeOnly)`

`toDateTime(<timeZone>,<integer>)`

Return a datetime.

-->

## Beispiele

`toDateTime ("2016-08-18T23:17:59.123Z")`

Gibt 2016-08-18T23:17:59.123Z zurück

`toDateTime(toDateTimeOnly("2016-08-18T23:17:59.123"),"UTC")`

Gibt 2016-08-18T23:17:59.123Z zurück

`toDateTime(1560762190189)`

Gibt 2019-06-17T09:03:10.189Z zurück

<!--`toDateTime ("2016-08-18T23:17:59.123", "UTC")`

Returns 2016-08-18T23:17:59.123Z.

`toDateTime("Z",2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000Z.

`toDateTime("Z",2016,8,18)`

Returns 2016-08-18T00:00:00.000Z.-->
