---
product: adobe campaign
title: Datentypen
description: Erfahren Sie mehr über die Datentypen in erweiterten Ausdrücken
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 343f61b8-2315-4971-8b2b-6aa815bd9ced
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '656'
ht-degree: 100%

---

# Datentypen {#concept_gp3_rj5_dgb}


>[!CAUTION]
>
>**Sie möchten mehr über Adobe Journey Optimizer erfahren**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um auf die Journey Optimizer-Dokumentation zuzugreifen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Accountteam, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._


Technisch gesehen enthält eine Konstante immer einen Datentyp. Wörtlich genommen geben wir nur den Wert an. Der Datentyp kann aus dem Wert abgeleitet werden (z. B. Zeichenfolge, Ganzzahl, Dezimalzahl usw.). Für bestimmte Fälle wie Datum und Uhrzeit verwenden wir spezielle Funktionen für die Darstellung.

In den folgenden Abschnitten finden Sie Informationen zu den verschiedenen Ausdrücken von Datentypen und wie sie dargestellt werden.

## Zeichenfolge {#string}

**Beschreibung**

Allgemeine Zeichenfolge. Er hat keine bestimmte Größe außer der impliziten Größe, die aus der Umgebung stammt, z. B. die verfügbare Speicherkapazität.

JSON-Format: Zeichenfolge

Serialisierungsformat: UTF-8

**Wörtliche Darstellung**

```json
"<value>"
```

```json
'<value>'
```

**Beispiel**

```json
"hello world"
```

```json
'hello world'
```

## integer {#integer}

**Beschreibung**

Ganzzahlwert von -2^63 bis 2^63-1.

JSON-Format: Zahl

**Wörtliche Darstellung**

```json
<integer value>
```

**Beispiel**

```json
42
```

## decimal {#decimal}

**Beschreibung**

Dezimalzahl. Stellt einen Gleitkommawert dar:

* größter positiver endlicher Wert des Typs „double“, (2-2^-52)x2^1023
* kleinster positiver Normalwert des Typs „double“, 2-1022
* kleinster positiver Wert ungleich null vom Typ „double“, 2 p-1074

JSON-Format: Zahl

Serialisierungsformat: mit „.“ als Dezimaltrennzeichen.

**Wörtliche Darstellung**

```json
<integer value>.<integer value>
```

**Beispiel**

```json
3.14
```

## boolean {#boolean}

**Beschreibung**

Boolescher Wert in Kleinbuchstaben: true (wahr) oder false (falsch)

JSON-Format: Boolesch

**Wörtliche Darstellung**

```json
true
```

```json
false
```

**Beispiel**

```json
true
```

## dateOnly {#date-only}

**Beschreibung**

Stellt ein reines Datum ohne Zeitzone dar, das als Jahr-Monat-Tag angezeigt wird.

Es ist eine Beschreibung des Datums, wie es beispielsweise für den Geburtstag verwendet wird.

JSON-Format: Zeichenfolge.

Format ist: JJJJ-MM-TT (ISO-8601), z. B.: „2021-03-11“.

Kann ausschließlich in einer toDateOnly -Funktion gekapselt sein.

Es wird das DateTimeFormatter ISO_LOCAL_DATE_TIME zur Deserialisierung und Serialisierung des Wertes verwendet. [Weitere Informationen](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6)

**Wörtliche Darstellung**

```json
date("<dateOnly in ISO-8601 format>")  
```

**Beispiel**

```json
date("2021-02-19")
```

## dateTimeOnly {#date-time-only}

**Beschreibung**

Stellt Datum und Uhrzeit ohne Zeitzone dar, die als Jahr-Monat-Tag-Stunde-Minute-Sekunde-Millisekunde interpretiert wird.

JSON-Format: Zeichenfolge.

Es wird keine Zeitzone gespeichert oder dargestellt. Stattdessen handelt es sich um eine Beschreibung des Datums, wie es für Geburtstage verwendet wird, kombiniert mit der Ortszeit, wie sie auf einer Wanduhr angezeigt wird.

Ohne zusätzliche Informationen wie Versatz oder Zeitzone kann kein Zeitpunkt auf der Zeitachse dargestellt werden.

Kann in einer toDateTimeOnly-Funktion gekapselt sein.

Serialisierungsformat: ISO-8601, erweitertes Versatz-Datums-/Uhrzeitformat.

Es wird das DateTimeFormatter ISO_LOCAL_DATE_TIME zur Deserialisierung und Serialisierung des Wertes verwendet. [Weitere Informationen](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**Wörtliche Darstellung**

```json
date("<dateTimeOnly in ISO-8601 format>")  
```

**Beispiele**

```json
date("2021-02-19T00.00.000")
date("2021-02-19T00.00")
```

## dateTime {#date-time}

**Beschreibung**

Datums-/Zeitkonstante, die auch die Zeitzone berücksichtigt. Es wird Datum + Uhrzeit mit einem Versatz relativ zur UTC dargestellt.

Mit den zusätzlichen Informationen zum Versatz kann ein bestimmter Zeitpunkt dargestellt werden. Sie bieten die Möglichkeit, einen bestimmten Zeitpunkt an einem bestimmten Ort der Welt darzustellen.

JSON-Format: Zeichenfolge.

Kann in einer toDateTime-Funktion gekapselt sein.

Serialisierungsformat: ISO-8601, erweitertes Versatz-Datums-/Uhrzeitformat.

Verwendet das DateTimeFormatter ISO_OFFSET_DATE_TIME zur Deserialisierung und Serialisierung des Wertes. [Weitere Informationen](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

Sie können auch eine Ganzzahl übergeben, die einen Epochenwert übergibt. [Mehr dazu](https://www.epochconverter.com)

Die Zeitzone kann durch einen Versatz oder einen Zeitzonen-Code angegeben werden (Beispiel: Europa/Paris, Z – bedeutet UTC).

**Wörtliche Darstellung**

```json
toDateTime("<dateTime in ISO-8601 format>")
```

```json
date("<dateTime in ISO-8601 format>")
```

```json
toDateTime(<integer value of an epoch in milliseconds>)
```

**Beispiele**

```json
date("2021-02-19T00.00.000Z")
```

```json
toDateTime("1977-04-22T06:00:00Z")
```

```json
toDateTime("2011-12-03T15:15:30Z")
```

```json
toDateTime("2011-12-03T15:15:30.123Z")
```

```json
toDateTime("2011-12-03T15:15:30.123+02:00")
```

```json
toDateTime("2011-12-03T15:15:30.123-00:20")
```

```json
toDateTime(1560762190189)
```

## Dauer {#duration}

**Beschreibung**

Stellt eine zeitbasierte Dauer dar, z. B. „34,5 Sekunden“. Modelliert eine Menge oder Dauer in Millisekunden.

Folgende Zeiteinheiten werden unterstützt: Millisekunden, Sekunden, Minuten, Stunden, Tage, wobei ein Tag 24 Stunden entspricht. Jahre und Monate werden nicht unterstützt, da sie keine feste Dauer haben.

JSON-Format: Zeichenfolge.

Muss in einer toDuration-Funktion gekapselt sein.

Serialisierungsformat: Zur Deserialisierung einer Zeitzonen-ID wird die Java-Funktion java.time verwendet.

Duration.parse: Die akzeptierten Formate basieren auf dem ISO-8601-Dauerformat „PnDTnHnMn.nS“, wobei Tage als genau 24 Stunden angesehen werden. [Weitere Informationen](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**Wörtliche Darstellung**

```json
toDuration("<duration in ISO-8601 format>")
```

```json
toDuration(<duration in milliseconds>)
```

**Beispiel**

```json
toDuration("PT5S") -- parses as 5 seconds
```

```json
toDuration(500) -- parses as 500ms
```

```json
toDuration("PT20.345S") -- parses as "20.345 seconds"
```

```json
toDuration("PT15M") -- parses as "15 minutes" (where a minute is 60 seconds)
```

```json
toDuration("PT10H")  -- parses as "10 hours" (where an hour is 3600 seconds)
```

```json
toDuration("P2D") -- parses as "2 days" (where a day is 24 hours or 86400 seconds)
```

```json
toDuration("P2DT3H4M") -- parses as "2 days, 3 hours and 4 minutes"
```

```json
toDuration("P-6H3M") -- parses as "-6 hours and +3 minutes"
```

```json
toDuration("-P6H3M") -- parses as "-6 hours and -3 minutes"
```

```json
toDuration("-P-6H+3M") -- parses as "+6 hours and -3 minutes"
```

## list {#list}

**Beschreibung**

Kommagetrennte Liste von Ausdrücken mit eckigen Klammern als Trennzeichen.

Polymorphismus wird nicht unterstützt. Daher sollten alle in der Liste enthaltenen Ausdrücke denselben Typ haben.

**Wörtliche Darstellung**

```json
[<expression>, <expression>, ... ]
```

**Beispiel**

```json
["value1","value2"]
```

```json
[3,5]
```

```json
[toDuration(500),toDuration(800)]
```
