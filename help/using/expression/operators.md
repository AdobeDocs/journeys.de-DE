---
product: adobe campaign
solution: Journey Orchestration
title: Operatoren
description: Erfahren Sie mehr über Operatoren in erweiterten Ausdrücken
translation-type: ht
source-git-commit: 062b4648e2eb3a4270f9c09e4478d541209e1247
workflow-type: ht
source-wordcount: '435'
ht-degree: 100%

---



# Operatoren {#concept_wd5_pj5_dgb}

Es gibt zwei Arten von Operatoren: unäre Operatoren und binäre Operatoren. Es gibt unäre Operatoren auf der linken und auf der rechten Seite.

```
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

Im Folgenden finden Sie eine Liste der unterstützten Operatoren:

## Logisch      {#logical}

### and

```
<expression1> and <expression2>
```

Sowohl &lt;Ausdruck1> als auch &lt;Ausdruck2> müssen boolesch sein. Das Ergebnis ist boolesch.

Beispiel:

```
3.14 > 2 and 3.15 < 1
```

### or



```
<expression1> or <expression2>
```

Sowohl &lt;Ausdruck1> als auch &lt;Ausdruck2> müssen boolesch sein. Das Ergebnis ist boolesch.

Beispiel:

```
3.14 > 2 or 3.15 < 1
```

### not



```
not <expression>
```

&lt;Ausdruck> muss boolesch sein. Das Ergebnis ist boolesch.

Beispiel:

```
not 3.15 < 1
```

## Vergleich {#comparison}

### is null



```
<expression> is null
```

Das Ergebnis ist boolesch.

Beachten Sie, dass null bedeutet, dass der Ausdruck keinen ausgewerteten Wert hat.

Beispiel:

```
@{BarBeacon.location} is null
```

### is not null



```
<expression> is not null
```

Das Ergebnis ist boolesch.

Beachten Sie, dass null bedeutet, dass der Ausdruck keinen ausgewerteten Wert hat.

Beispiel:

```
@ is not null
```

### has null



```
<expression> has null
```

&lt;Ausdruck> muss eine Liste sein. Das Ergebnis ist boolesch.

Nützlich, um zu ermitteln, dass eine Liste mindestens einen Nullwert enthält.

Beispiel:

```
["foo", "bar", null] has null --  returns true.
```

```
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```
<expression1> == <expression2>
```

Sowohl &lt;Ausdruck1> als auch &lt;Ausdruck2> müssen denselben Datentyp aufweisen. Das Ergebnis ist boolesch.

Beispiel:

```
3.14 == 42
```

```
"foo" == "bar"
```

### !=



```
<expression1> != <expression2>
```

Sowohl &lt;Ausdruck1> als auch &lt;Ausdruck2> müssen denselben Datentyp aufweisen. Das Ergebnis ist boolesch.

Beispiel:

```
3.14 != 42
```

```
"foo" != "bar"
```

### >



```
<expression1> > <expression2>
```

Datum/Uhrzeit kann mit Datum/Uhrzeit verglichen werden.

Datum/Uhrzeit ohne Zeitzone kann mit Datum/Uhrzeit ohne Zeitzone verglichen werden.

Sowohl Ganzzahl als auch Dezimalzahl können mit Ganzzahl oder Dezimalzahl verglichen werden.

Jede andere Kombination ist unzulässig.

Das Ergebnis ist boolesch.

Beispiel:

```
3.14 > 42
```

### >=



```
<expression1> >= <expression2>
```

Datum/Uhrzeit kann mit Datum/Uhrzeit verglichen werden.

Datum/Uhrzeit ohne Zeitzone kann mit Datum/Uhrzeit ohne Zeitzone verglichen werden.

Sowohl Ganzzahl als auch Dezimalzahl können mit Ganzzahl oder Dezimalzahl verglichen werden.

Jede andere Kombination ist unzulässig.

Das Ergebnis ist boolesch.

Beispiel:

```
42 >= 3.14
```

### &lt;



```
<expression1> < <expression2>
```

Datum/Uhrzeit kann mit Datum/Uhrzeit verglichen werden.

Datum/Uhrzeit ohne Zeitzone kann mit Datum/Uhrzeit ohne Zeitzone verglichen werden.

Sowohl Ganzzahl als auch Dezimalzahl können mit Ganzzahl oder Dezimalzahl verglichen werden.

Jede andere Kombination ist unzulässig.

Das Ergebnis ist boolesch.

Beispiel:

```
42 < 3.14
```

### &lt;=



```
<expression1> <= <expression2>
```

Datum/Uhrzeit kann mit Datum/Uhrzeit verglichen werden.

Datum/Uhrzeit ohne Zeitzone kann mit Datum/Uhrzeit ohne Zeitzone verglichen werden.

Sowohl Ganzzahl als auch Dezimalzahl können mit Ganzzahl oder Dezimalzahl verglichen werden.

Jede andere Kombination ist unzulässig.

Das Ergebnis ist boolesch.

Beispiel:

```
42 <= 3.14
```

## Arithmetisch {#arithmetic}

### +



```
<expression1> + <expression2>
```

Beide Ausdrücke müssen numerischer Art sein (Ganzzahl oder Dezimalzahl).

Das Ergebnis ist ebenfalls numerisch.

Beispiel:

```
1 + 2 -- returns 3
```

### -



```
<expression1> - <expression2>
```

Beide Ausdrücke müssen numerischer Art sein (Ganzzahl oder Dezimalzahl).

Das Ergebnis ist ebenfalls numerisch.

Beispiel:

```
2 - 1 -- returns 1
```

### /



```
<expression1> / <expression2>
```

Beide Ausdrücke müssen numerischer Art sein (Ganzzahl oder Dezimalzahl).

Das Ergebnis ist ebenfalls numerisch.

&lt;Ausdruck2> darf nicht gleich 0 sein (gibt 0 zurück).

Beispiel:

```
4 / 2 -- returns 2
```

### *



```
<expression1> * <expression2>
```

Beide Ausdrücke müssen numerischer Art sein (Ganzzahl oder Dezimalzahl).

Das Ergebnis ist ebenfalls numerisch.

Beispiel:

```
3 * 4 -- returns 12
```

### %



```
<expression1> % <expression2>
```

Beide Ausdrücke müssen numerischer Art sein (Ganzzahl oder Dezimalzahl).

Das Ergebnis ist ebenfalls numerisch.

Beispiel:

```
3 % 2 -- returns 1.
```

## Mathematisch {#math}

### is numeric



```
<expression> is numeric
```

Der Typ des Ausdrucks ist Ganzzahl oder Dezimalzahl.

Beispiel:

```
@ is numeric
```

### is integer



```
<expression> is integer
```

Der Typ des Ausdrucks ist Ganzzahl.

Beispiel:

```
@ is integer
```

### is decimal



```
<expression> is decimal
```

Der Typ des Ausdrucks ist Dezimalzahl.

Beispiel:

```
@ is decimal
```

## Zeichenfolge {#string}

### +



```
<string> + <expression>
```

```
<expression> + <string>
```

Damit werden zwei Ausdrücke verkettet.

Ein Ausdruck muss eine verkettete Zeichenfolge sein.

Beispiel:

```
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## Datum {#date}

### +



```
<expression + <duration>
```

Anhängen einer Dauer an einen „dateTime“, einen „dateTimeOnly“ oder eine Dauer.

Beispiel:

```
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
