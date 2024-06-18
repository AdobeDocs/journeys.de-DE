---
product: adobe campaign
title: Operatoren
description: Erfahren Sie mehr über Operatoren in erweiterten Ausdrücken
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: fd86b6ab-76cf-4b35-9e87-f441e914f20b
source-git-commit: a0b6ab595bc16a75aa5a56a858900418e2381ab9
workflow-type: ht
source-wordcount: '459'
ht-degree: 100%

---

# Operatoren {#concept_wd5_pj5_dgb}

Es gibt zwei Arten von Operatoren: unäre Operatoren und binäre Operatoren. Es gibt unäre Operatoren auf der linken und auf der rechten Seite.

```json
    // left-hand unary operators
    <operator> <operand> // operand is an expression
    not (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example@adobe.com")

    // right-hand unary operators
    <operand> <operator> // operand is an expression
    @{LobbyBeacon.endUserIDs._experience.emailid.id} is not null

    // binary operators
    <operand1> <operator> <operand2>
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example1@adobe.com") or
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example2@adobe.com")
```

## Wichtige Hinweise{#important-notes}

* Bei Verwendung einer Multiplikation (`*`) müssen beide Operationsfelder denselben Typ aufweisen, entweder Ganzzahl oder Dezimalzahl. Beispiel:
   * Das folgende Beispiel ist korrekt: `3.0 * 4.0`
   * `3 * 4.0` führt zu einem Fehler

## Logisch        {#logical}

### und

```json
<expression1> and <expression2>
```

Sowohl &lt;Ausdruck1> als auch &lt;Ausdruck2> müssen boolesch sein. Das Ergebnis ist boolesch.

Beispiel:

```json
3.14 > 2 and 3.15 < 1
```

### oder



```json
<expression1> or <expression2>
```

Sowohl &lt;Ausdruck1> als auch &lt;Ausdruck2> müssen boolesch sein. Das Ergebnis ist boolesch.

Beispiel:

```json
3.14 > 2 or 3.15 < 1
```

### not



```json
not <expression>
```

&lt;Ausdruck> muss boolesch sein. Das Ergebnis ist boolesch.

Beispiel:

```json
not 3.15 < 1
```

## Vergleich {#comparison}

### is null



```json
<expression> is null
```

Das Ergebnis ist boolesch.

Beachten Sie, dass null bedeutet, dass der Ausdruck keinen ausgewerteten Wert hat.

Beispiel:

```json
@{BarBeacon.location} is null
```

### is not null



```json
<expression> is not null
```

Das Ergebnis ist boolesch.

Beachten Sie, dass null bedeutet, dass der Ausdruck keinen ausgewerteten Wert hat.

Beispiel:

```json
@ is not null
```

### has null



```json
<expression> has null
```

&lt;Ausdruck> muss eine Liste sein. Das Ergebnis ist boolesch.

Nützlich, um zu ermitteln, dass eine Liste mindestens einen Nullwert enthält.

Beispiel:

```json
["foo", "bar", null] has null --  returns true.
```

```json
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```json
<expression1> == <expression2>
```

Sowohl &lt;Ausdruck1> als auch &lt;Ausdruck2> müssen denselben Datentyp aufweisen. Das Ergebnis ist boolesch.

Beispiel:

```json
3.14 == 42
```

```json
"foo" == "bar"
```

### !=



```json
<expression1> != <expression2>
```

Sowohl &lt;Ausdruck1> als auch &lt;Ausdruck2> müssen denselben Datentyp aufweisen. Das Ergebnis ist boolesch.

Beispiel:

```json
3.14 != 42
```

```json
"foo" != "bar"
```

### >



```json
<expression1> > <expression2>
```

Datum/Uhrzeit kann mit Datum/Uhrzeit verglichen werden.

Datum/Uhrzeit ohne Zeitzone kann mit Datum/Uhrzeit ohne Zeitzone verglichen werden.

Sowohl Ganzzahl als auch Dezimalzahl können mit Ganzzahl oder Dezimalzahl verglichen werden.

Jede andere Kombination ist unzulässig.

Das Ergebnis ist boolesch.

Beispiel:

```json
3.14 > 42
```

### >=



```json
<expression1> >= <expression2>
```

Datum/Uhrzeit kann mit Datum/Uhrzeit verglichen werden.

Datum/Uhrzeit ohne Zeitzone kann mit Datum/Uhrzeit ohne Zeitzone verglichen werden.

Sowohl Ganzzahl als auch Dezimalzahl können mit Ganzzahl oder Dezimalzahl verglichen werden.

Jede andere Kombination ist unzulässig.

Das Ergebnis ist boolesch.

Beispiel:

```json
42 >= 3.14
```

### &lt;



```json
<expression1> < <expression2>
```

Datum/Uhrzeit kann mit Datum/Uhrzeit verglichen werden.

Datum/Uhrzeit ohne Zeitzone kann mit Datum/Uhrzeit ohne Zeitzone verglichen werden.

Sowohl Ganzzahl als auch Dezimalzahl können mit Ganzzahl oder Dezimalzahl verglichen werden.

Jede andere Kombination ist unzulässig.

Das Ergebnis ist boolesch.

Beispiel:

```json
42 < 3.14
```

### &lt;=



```json
<expression1> <= <expression2>
```

Datum/Uhrzeit kann mit Datum/Uhrzeit verglichen werden.

Datum/Uhrzeit ohne Zeitzone kann mit Datum/Uhrzeit ohne Zeitzone verglichen werden.

Sowohl Ganzzahl als auch Dezimalzahl können mit Ganzzahl oder Dezimalzahl verglichen werden.

Jede andere Kombination ist unzulässig.

Das Ergebnis ist boolesch.

Beispiel:

```json
42 <= 3.14
```

## Arithmetisch {#arithmetic}

### +



```json
<expression1> + <expression2>
```

Beide Ausdrücke müssen numerischer Art sein (Ganzzahl oder Dezimalzahl).

Das Ergebnis ist ebenfalls numerisch.

Beispiel:

```json
1 + 2 -- returns 3
```

### –



```json
<expression1> - <expression2>
```

Beide Ausdrücke müssen numerischer Art sein (Ganzzahl oder Dezimalzahl).

Das Ergebnis ist ebenfalls numerisch.

Beispiel:

```json
2 - 1 -- returns 1
```

### /



```json
<expression1> / <expression2>
```

Beide Ausdrücke müssen numerischer Art sein (Ganzzahl oder Dezimalzahl).

Das Ergebnis ist ebenfalls numerisch.

&lt;Ausdruck2> darf nicht gleich 0 sein (gibt 0 zurück).

Beispiel:

```json
4 / 2 -- returns 2
```

### *



```json
<expression1> * <expression2>
```

Beide Ausdrücke müssen numerischer Art sein (Ganzzahl oder Dezimalzahl).

Das Ergebnis ist ebenfalls numerisch.

Beispiel:

```json
3 * 4 -- returns 12
```

### %



```json
<expression1> % <expression2>
```

Beide Ausdrücke müssen numerischer Art sein (Ganzzahl oder Dezimalzahl).

Das Ergebnis ist ebenfalls numerisch.

Beispiel:

```json
3 % 2 -- returns 1.
```

## Math {#math}

### is numeric



```json
<expression> is numeric
```

Der Typ des Ausdrucks ist Ganzzahl oder Dezimalzahl.

Beispiel:

```json
@ is numeric
```

### is integer



```json
<expression> is integer
```

Der Typ des Ausdrucks ist Ganzzahl.

Beispiel:

```json
@ is integer
```

### is decimal



```json
<expression> is decimal
```

Der Typ des Ausdrucks ist Dezimalzahl.

Beispiel:

```json
@ is decimal
```

## Zeichenfolge {#string}

### +



```json
<string> + <expression>
```

```json
<expression> + <string>
```

Damit werden zwei Ausdrücke verkettet.

Ein Ausdruck muss eine verkettete Zeichenfolge sein.

Beispiel:

```json
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```json
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```json
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## Datum {#date}

### +



```json
<expression> + <duration>
```

Anhängen einer Dauer an einen „dateTime“, einen „dateTimeOnly“ oder eine Dauer.

Beispiel:

```json
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```json
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```json
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```json
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
