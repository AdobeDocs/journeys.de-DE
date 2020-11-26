---
product: adobe campaign
solution: Journey Orchestration
title: Operatoren
description: Erfahren Sie mehr über Operatoren in erweiterten Ausdrücken
translation-type: tm+mt
source-git-commit: 20498e89eb9c95dd19a11e42150a0bbf67024f67
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 83%

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

## Logisch  {#logical}

### and

**Literaler Ausdruck**

```<expression1> and <expression2>```

Sowohl &lt;Ausdruck1> als auch &lt;Ausdruck2> müssen boolesch sein. Das Ergebnis ist boolesch.

**Beispiel**

```3.14 > 2 and 3.15 < 1```

### oder

**Literaler Ausdruck**

```<expression1> or <expression2>```

Sowohl &lt;Ausdruck1> als auch &lt;Ausdruck2> müssen boolesch sein. Das Ergebnis ist boolesch.

**Beispiel**

```3.14 > 2 or 3.15 < 1```

### not

**Literaler Ausdruck**

```not <expression>```

&lt;Ausdruck> muss boolesch sein. Das Ergebnis ist boolesch.

**Beispiel**

```not 3.15 < 1```

## Vergleich {#comparison}

### is null

**Literaler Ausdruck**

```<expression> is null```

Das Ergebnis ist boolesch.

Beachten Sie, dass null bedeutet, dass der Ausdruck keinen ausgewerteten Wert hat.

**Beispiel**

```@{BarBeacon.location} is null```

### is not null

**Literaler Ausdruck**

```<expression> is not null```

Das Ergebnis ist boolesch.

Beachten Sie, dass null bedeutet, dass der Ausdruck keinen ausgewerteten Wert hat.

**Beispiel**

```@ is not null```

### has null

**Literaler Ausdruck**

```<expression> has null```

&lt;Ausdruck> muss eine Liste sein. Das Ergebnis ist boolesch.

Nützlich, um zu ermitteln, dass eine Liste mindestens einen Nullwert enthält.

**Beispiel**

```["foo", "bar", null] has null``` gibt true zurück.

```["foo", "bar", ""] has null``` Gibt „false“ zurück, da &quot;&quot; nicht als null betrachtet wird.

### ==

**Literaler Ausdruck**

```<expression1> == <expression2>```

Sowohl &lt;Ausdruck1> als auch &lt;Ausdruck2> müssen denselben Datentyp aufweisen. Das Ergebnis ist boolesch.

**Beispiel**

```3.14 == 42```

```"foo" == "bar"```

### !=

**Literaler Ausdruck**

```<expression1> != <expression2>```

Sowohl &lt;Ausdruck1> als auch &lt;Ausdruck2> müssen denselben Datentyp aufweisen. Das Ergebnis ist boolesch.

**Beispiel**

```3.14 != 42```

```"foo" != "bar"```

### >

**Literaler Ausdruck**

```<expression1> > <expression2>```

Datum/Uhrzeit kann mit Datum/Uhrzeit verglichen werden.

Datum/Uhrzeit ohne Zeitzone kann mit Datum/Uhrzeit ohne Zeitzone verglichen werden.

Sowohl Ganzzahl als auch Dezimalzahl können mit Ganzzahl oder Dezimalzahl verglichen werden.

Jede andere Kombination ist unzulässig.

Das Ergebnis ist boolesch.

**Beispiel**

```3.14 > 42```

### >=

**Literaler Ausdruck**

```<expression1> >= <expression2>```

Datum/Uhrzeit kann mit Datum/Uhrzeit verglichen werden.

Datum/Uhrzeit ohne Zeitzone kann mit Datum/Uhrzeit ohne Zeitzone verglichen werden.

Sowohl Ganzzahl als auch Dezimalzahl können mit Ganzzahl oder Dezimalzahl verglichen werden.

Jede andere Kombination ist unzulässig.

Das Ergebnis ist boolesch.

**Beispiel**

```42 >= 3.14```

### &lt;

**Literaler Ausdruck**

```<expression1> < <expression2>```

Datum/Uhrzeit kann mit Datum/Uhrzeit verglichen werden.

Datum/Uhrzeit ohne Zeitzone kann mit Datum/Uhrzeit ohne Zeitzone verglichen werden.

Sowohl Ganzzahl als auch Dezimalzahl können mit Ganzzahl oder Dezimalzahl verglichen werden.

Jede andere Kombination ist unzulässig.

Das Ergebnis ist boolesch.

**Beispiel**

```42 < 3.14```

### &lt;=

**Literaler Ausdruck**

```<expression1> <= <expression2>```

Datum/Uhrzeit kann mit Datum/Uhrzeit verglichen werden.

Datum/Uhrzeit ohne Zeitzone kann mit Datum/Uhrzeit ohne Zeitzone verglichen werden.

Sowohl Ganzzahl als auch Dezimalzahl können mit Ganzzahl oder Dezimalzahl verglichen werden.

Jede andere Kombination ist unzulässig.

Das Ergebnis ist boolesch.

**Beispiel**

```42 <= 3.14```

## Arithmetisch {#arithmetic}

### +

**Literaler Ausdruck**

```<expression1> + <expression2>```

Beide Ausdrücke müssen numerischer Art sein (Ganzzahl oder Dezimalzahl).

Das Ergebnis ist ebenfalls numerisch.

**Beispiel**

```1 + 2``` liefert 3

### -

**Literaler Ausdruck**

```<expression1> - <expression2>```

Beide Ausdrücke müssen numerischer Art sein (Ganzzahl oder Dezimalzahl).

Das Ergebnis ist ebenfalls numerisch.

**Beispiel**

```2 - 1``` gibt 1 zurück

### /

**Literaler Ausdruck**

```<expression1> / <expression2>```

Beide Ausdrücke müssen numerischer Art sein (Ganzzahl oder Dezimalzahl).

Das Ergebnis ist ebenfalls numerisch.

&lt;Ausdruck2> darf nicht gleich 0 sein (gibt 0 zurück).

**Beispiel**

```4 / 2``` liefert 2

### *

**Literaler Ausdruck**

```<expression1> * <expression2>```

Beide Ausdrücke müssen numerischer Art sein (Ganzzahl oder Dezimalzahl).

Das Ergebnis ist ebenfalls numerisch.

**Beispiel**

```3 * 4``` liefert 12

### %

**Literaler Ausdruck**

```<expression1> % <expression2>```

Beide Ausdrücke müssen numerischer Art sein (Ganzzahl oder Dezimalzahl).

Das Ergebnis ist ebenfalls numerisch.

**Beispiel**

```3 % 2``` gibt 1 zurück.

## Mathematisch {#math}

### is numeric

**Literaler Ausdruck**

```<expression> is numeric```

Der Typ des Ausdrucks ist Ganzzahl oder Dezimalzahl.

**Beispiel**

```@ is numeric```

### is integer

**Literaler Ausdruck**

```<expression> is integer```

Der Typ des Ausdrucks ist Ganzzahl.

**Beispiel**

```@ is integer```

### is decimal

**Literaler Ausdruck**

```<expression> is decimal```

Der Typ des Ausdrucks ist Dezimalzahl.

**Beispiel**

```@ is decimal```

## Zeichenfolge {#string}

### +

**Literaler Ausdruck**

```<string> + <expression>```

```<expression> + <string>```

Damit werden zwei Ausdrücke verkettet.

Ein Ausdruck muss eine verkettete Zeichenfolge sein.

**Beispiel**

```"the current time is " + (now())``` gibt &quot;the current time is 2019-09-23T09:30:06.693Z&quot;zurück

```(now()) + " is the current time"``` gibt &quot;2019-09-23T09:30:06.693Z ist die aktuelle Zeit&quot;zurück

```"a" + "b" + "c" + 1234``` gibt &quot;abc1234&quot;zurück.

## Datum {#date}

### +

**Literaler Ausdruck**

```<expression + <duration>```

Anhängen einer Dauer an einen Datum/Uhrzeit-Wert, einen Datum/Uhrzeit-Wert ohne Zeitzone oder eine Dauer.

**Beispiel**

```toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M")``` gibt 2011-12-03T15:30:30Z zurück

```toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M")``` gibt 2011-12-03T15:30:30 zurück

```now() + toDuration("PT1H")``` gibt eine Stunde später eine dateTime (mit UTC-Zeitzone) zurück

```toDuration("PT1H") + toDuration("PT1H")``` gibt PT2H zurück
