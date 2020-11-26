---
product: adobe campaign
solution: Journey Orchestration
title: Datentypen
description: Erfahren Sie mehr über die Datentypen in erweiterten Ausdrücken
translation-type: tm+mt
source-git-commit: 062b4648e2eb3a4270f9c09e4478d541209e1247
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 89%

---


# Datentypen {#concept_gp3_rj5_dgb}

Technisch gesehen enthält eine Konstante immer einen Datentyp. Wörtlich genommen geben wir nur den Wert an. Der Datentyp kann aus dem Wert abgeleitet werden (z. B. Zeichenfolge, Ganzzahl, Dezimalzahl usw.). Für bestimmte Fälle wie Datum und Uhrzeit verwenden wir spezielle Funktionen für die Darstellung.

Die folgenden Abschnitte enthalten Informationen zu den verschiedenen Ausdrücken des Datentyps und zur Darstellung.

## Zeichenfolge {#string}

**Beschreibung**

Allgemeine Zeichenfolge. Er hat keine bestimmte Größe außer der impliziten Größe, die aus der Umgebung stammt, z. B. die verfügbare Speicherkapazität.

JSON-Format: Zeichenfolge

Serialisierungsformat: UTF-8

**Literale Darstellung**

```
"<value>"
```

```
'<value>'
```

**Beispiel**

```
"hello world"
```

```
'hello world'
```

## Ganzzahl {#integer}

**Beschreibung**

Ganzzahlwert von -2^63 bis 2^63-1.

JSON-Format: Zahl

**Literale Darstellung**

```
<integer value>
```

**Beispiel**

```
42
```

## decimal {#decimal}

**Beschreibung**

Dezimalzahl. Stellt einen Gleitkommawert dar:

* größter positiver endlicher Wert des Typs „double“, (2-2^-52)x2^1023
* kleinster positiver Normalwert des Typs „double“, 2-1022
* kleinster positiver Wert ungleich null vom Typ „double“, 2 p-1074

JSON-Format: Zahl

Serialisierungsformat: mit &#39;.&#39; als Dezimaltrennzeichen.

**Literale Darstellung**

```
<integer value>.<integer value>
```

**Beispiel**

```
3.14
```

## boolean {#boolean}

**Beschreibung**

Boolescher Wert in Kleinbuchstaben: true (wahr) oder false (falsch)

JSON-Format: Boolesch

**Literale Darstellung**

```
true
```

```
false
```

**Beispiel**

```
true
```

## dateTimeOnly {#date-time-only}

**Beschreibung**

Stellt Datum und Uhrzeit ohne Zeitzone dar, die als Jahr-Monat-Tag-Stunde-Minute-Sekunde-Millisekunde interpretiert wird.

Es wird keine Zeitzone gespeichert oder dargestellt. Stattdessen handelt es sich um eine Beschreibung des Datums, wie es für Geburtstage verwendet wird, kombiniert mit der Ortszeit, wie sie auf einer Wanduhr angezeigt wird.

Ohne zusätzliche Informationen wie Versatz oder Zeitzone kann kein Zeitpunkt auf der Zeitachse dargestellt werden.

Serialisierungsformat: ISO-8601, erweitertes Versatz-Datums-/Uhrzeitformat.

Es verwendet DateTimeFormatter ISO_LOCAL_DATE_TIME, um den Wert zu deserialisieren und zu serialisieren. [Mehr dazu](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**Literale Darstellung**

```
toDateTimeOnly("<dateTimeOnly in ISO-8601 format>")  
```

## dateTime {#date-time}

**Beschreibung**

Datums-/Zeitkonstante, die auch die Zeitzone berücksichtigt. Es wird Datum + Uhrzeit mit einem Versatz relativ zur UTC dargestellt.

Mit den zusätzlichen Informationen zum Versatz kann ein bestimmter Zeitpunkt dargestellt werden. Bietet eine Möglichkeit, einen bestimmten Zeitpunkt an einem bestimmten Ort der Welt darzustellen.

JSON-Format: Zeichenfolge.

Muss in einer toDateTime-Funktion gekapselt sein.

Serialisierungsformat: ISO-8601, erweitertes Versatz-Datums-/Uhrzeitformat.

Es verwendet DateTimeFormatter ISO_OFFSET_DATE_TIME, um den Wert zu deserialisieren und zu serialisieren. [Mehr dazu](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

Sie können auch eine Ganzzahl übergeben, die einen Epochenwert übergibt. [Mehr dazu](https://www.epochconverter.com)

Die Zeitzone kann durch einen Versatz oder einen Zeitzonen-Code angegeben werden (Beispiel: Europa/Paris, Z – bedeutet UTC).

**Literale Darstellung**

```
toDateTime("<dateTime in ISO-8601 format>")
```

```
toDateTime(<integer value of an epoch in milliseconds>)
```

**Beispiel**

```
toDateTime("1977-04-22T06:00:00Z")
```

```
toDateTime("2011-12-03T15:15:30Z")
```

```
toDateTime("2011-12-03T15:15:30.123Z")
```

```
toDateTime("2011-12-03T15:15:30.123+02:00")
```

```
toDateTime("2011-12-03T15:15:30.123-00:20")
```

```
toDateTime(1560762190189)
```

## duration {#duration}

**Beschreibung**

Stellt eine zeitbasierte Dauer dar, z. B. „34,5 Sekunden“. Modelliert eine Menge oder Dauer in Millisekunden.

Folgende Zeiteinheiten werden unterstützt: Millisekunden, Sekunden, Minuten, Stunden, Tage, wobei ein Tag 24 Stunden entspricht. Jahre und Monate werden nicht unterstützt, da sie keine feste Dauer haben.

JSON-Format: Zeichenfolge.

Muss in einer toDuration-Funktion gekapselt sein.

Serialisierungsformat: Zur Deserialisierung einer Zeitzonen-ID wird die Java-Funktion java.time verwendet.

Duration.parse: Die akzeptierten Formate basieren auf dem ISO-8601-Dauerformat „PnDTnHnMn.nS“, wobei Tage als genau 24 Stunden angesehen werden. [Mehr dazu](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**Literale Darstellung**

```
toDuration("<duration in ISO-8601 format>")
```

```
toDuration(<duration in milliseconds>)
```

**Beispiel**

```
toDuration("PT5S") -- parses as 5 seconds
```

```
toDuration(500) -- parses as 500ms
```

```
toDuration("PT20.345S") -- parses as "20.345 seconds"
```

```
toDuration("PT15M") -- parses as "15 minutes" (where a minute is 60 seconds)
```

```
toDuration("PT10H")  -- parses as "10 hours" (where an hour is 3600 seconds)
```

```
toDuration("P2D") -- parses as "2 days" (where a day is 24 hours or 86400 seconds)
```

```
toDuration("P2DT3H4M") -- parses as "2 days, 3 hours and 4 minutes"
```

```
toDuration("P-6H3M") -- parses as "-6 hours and +3 minutes"
```

```
toDuration("-P6H3M") -- parses as "-6 hours and -3 minutes"
```

```
toDuration("-P-6H+3M") -- parses as "+6 hours and -3 minutes"
```

## Liste {#list}

**Beschreibung**

Kommagetrennte Liste von Ausdrücken mit eckigen Klammern als Trennzeichen.

Polymorphismus wird nicht unterstützt. Daher sollten alle in der Liste enthaltenen Ausdrücke denselben Typ haben.

**Literale Darstellung**

```
[<expression>, <expression>, ... ]
```

**Beispiel**

```
["value1","value2"]
```

```
[3,5]
```

```
[toDuration(500),toDuration(800)]
```
