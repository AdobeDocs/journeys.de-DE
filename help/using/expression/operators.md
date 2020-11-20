---
product: adobe campaign
solution: Journey Orchestration
title: Operatoren
description: Erfahren Sie mehr über Operatoren in erweiterten Ausdrücken
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '618'
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

## Logisch

<table>
<thead>
<tr><th>Operator</th><th>Literaler Ausdruck</th><th>Beispiel</th></tr>
</thead>
<tbody>
<tr><td>and</td><td><p><pre>&lt;Ausdruck1&gt; and &lt;Ausdruck2&gt;</pre></p>Sowohl &lt;Ausdruck1&gt; als auch &lt;Ausdruck2&gt; müssen boolesch sein. Das Ergebnis ist boolesch.</td><td><pre>3.14 &gt; 2 and 3.15 &lt; 1</pre></td></tr>
<tr><td>or</td><td><p><pre>&lt;Ausdruck1&gt; or &lt;Ausdruck2&gt;</pre></p><p>Sowohl &lt;Ausdruck1&gt; als auch &lt;Ausdruck2&gt; müssen boolesch sein.</p><p> Das Ergebnis ist boolesch.</p></td><td><p><pre>3.14 &gt; 2 or 3.15 &lt; 1</pre></p></td></tr>
<tr><td>not</td><td><p><pre>not &lt;Ausdruck&gt;</pre></p><p>&lt;Ausdruck&gt; muss boolesch sein.</p><p> Das Ergebnis ist boolesch.</p></td><td><pre>not 3.15 &lt; 1</pre></td></tr>
</tbody>
</table>

## Vergleich

<table>
<thead>
<tr><th>Operator</th><th>Literaler Ausdruck </th><th>Beispiel</th></tr>
</thead>
<tbody><tr><td>is null</td><td><p><pre>&lt;Ausdruck&gt; is null</pre></p><p>Das Ergebnis ist boolesch.</p><p>Beachten Sie, dass null bedeutet, dass der Ausdruck keinen ausgewerteten Wert hat.</p></td><td><pre>@{BarBeacon.location} is null</pre></td></tr>
<tr><td>is not null</td><td><p><pre>&lt;Ausdruck&gt; is not null</pre></p><p>Das Ergebnis ist boolesch.</p><p>Beachten Sie, dass null bedeutet, dass der Ausdruck keinen ausgewerteten Wert hat.</p></td><td><pre>@ is not null</pre></td></tr>
<tr><td>has null</td><td><p><pre>&lt;Ausdruck&gt; has null</pre>&lt;Ausdruck&gt; muss eine Liste sein.</p><p>Das Ergebnis ist boolesch.</p><p>Nützlich, um zu ermitteln, dass eine Liste mindestens einen Nullwert enthält.</p></td><td><p><pre>["foo", "bar", null] has null</pre></p>Gibt „true“ zurück.<p><pre>["foo", "bar", ""] has null</pre></p> Gibt „false“ zurück, da "" nicht als null betrachtet wird.</td></tr>
<tr><td>==</td><td><p><pre>&lt;Ausdruck1&gt; == &lt;Ausdruck2&gt;</pre></p><p>Sowohl &lt;Ausdruck1&gt; als auch &lt;Ausdruck2&gt; müssen denselben Datentyp aufweisen.</p><p> Das Ergebnis ist boolesch.</p></td><td><pre>3.14 == 42</pre><br /><pre>"foo" == "bar"</pre></td></tr>
<tr><td>!=</td><td><p><pre>&lt;Ausdruck1&gt; != &lt;Ausdruck2&gt;</pre></p><p> Sowohl &lt;Ausdruck1&gt; als auch &lt;Ausdruck2&gt; müssen denselben Datentyp aufweisen.</p><p> Das Ergebnis ist boolesch.</p></td><td><pre>3.14 != 42</pre><br /><pre>"foo" != "bar"</pre></td></tr>
<tr><td>&gt;</td><td><p><pre>&lt;Ausdruck1&gt; &gt; &lt;Ausdruck2&gt;</pre></p><p>Datum/Uhrzeit kann mit Datum/Uhrzeit verglichen werden.</p><p>Datum/Uhrzeit ohne Zeitzone kann mit Datum/Uhrzeit ohne Zeitzone verglichen werden.</p><p>Sowohl Ganzzahl als auch Dezimalzahl können mit Ganzzahl oder Dezimalzahl verglichen werden.</p><p>Jede andere Kombination ist unzulässig.</p><p>Das Ergebnis ist boolesch.</p></td><td><pre>3.14 &gt; 42</pre></td></tr>
<tr><td>&gt;=</td><td><p><pre>&lt;Ausdruck1&gt; &gt;= &lt;Ausdruck2&gt;</pre></p><p>Datum/Uhrzeit kann mit Datum/Uhrzeit verglichen werden.</p><p>Datum/Uhrzeit ohne Zeitzone kann mit Datum/Uhrzeit ohne Zeitzone verglichen werden.</p><p>Sowohl Ganzzahl als auch Dezimalzahl können mit Ganzzahl oder Dezimalzahl verglichen werden.</p><p>Jede andere Kombination ist unzulässig.</p><p>Das Ergebnis ist boolesch.</p></td><td><pre>42 &gt;= 3.14</pre></td></tr>
<tr><td>&lt;</td><td><p><pre>&lt;Ausdruck1&gt; &lt; &lt;Ausdruck2&gt;</pre></p><p>Datum/Uhrzeit kann mit Datum/Uhrzeit verglichen werden.</p><p>Datum/Uhrzeit ohne Zeitzone kann mit Datum/Uhrzeit ohne Zeitzone verglichen werden.</p><p>Sowohl Ganzzahl als auch Dezimalzahl können mit Ganzzahl oder Dezimalzahl verglichen werden.</p><p>Jede andere Kombination ist unzulässig.</p><p>Das Ergebnis ist boolesch.</p></td><td><pre>42 &lt; 3.14</pre></td></tr>
<tr><td>&lt;=</td><td><p><pre>&lt;Ausdruck1&gt; &lt;= &lt;Ausdruck2&gt;</pre></p><p>Datum/Uhrzeit kann mit Datum/Uhrzeit verglichen werden.</p><p>Datum/Uhrzeit ohne Zeitzone kann mit Datum/Uhrzeit ohne Zeitzone verglichen werden.</p><p>Sowohl Ganzzahl als auch Dezimalzahl können mit Ganzzahl oder Dezimalzahl verglichen werden.</p><p>Jede andere Kombination ist unzulässig.</p><p>Das Ergebnis ist boolesch.</p></td><td><pre>42 &lt;= 3.14</pre></td></tr>
</tbody>
</table>

## Arithmetisch

<table>
<thead>
<tr><th>Operator</th><th>Literaler Ausdruck </th><th>Beispiel</th></tr>
</thead>
<tbody><tr><td>+</td><td><p><pre>&lt;Ausdruck1&gt; + &lt;Ausdruck2&gt;</pre></p><p>Beide Ausdrücke müssen numerischer Art sein (Ganzzahl oder Dezimalzahl). </p><p>Das Ergebnis ist ebenfalls numerisch.</p></td><td><p><p><pre>1 + 2</pre></p></p><br /><p>Gibt 3 zurück.</p></td></tr>
<tr><td>-</td><td><p><pre>&lt;Ausdruck1&gt; - &lt;Ausdruck2&gt;</pre></p><p> Beide Ausdrücke müssen numerischer Art sein (Ganzzahl oder Dezimalzahl).</p><p> Das Ergebnis ist ebenfalls numerisch.</p></td><td><p><pre>2 - 1</pre></p>Gibt 1 zurück.</td></tr>
<tr><td>/</td><td><p><pre>&lt;Ausdruck1&gt; / &lt;Ausdruck2&gt;</pre></p><p>Beide Ausdrücke müssen numerischer Art sein (Ganzzahl oder Dezimalzahl). </p><p>Das Ergebnis ist ebenfalls numerisch.</p><p>&lt;Ausdruck2&gt; darf nicht gleich 0 sein (gibt 0 zurück).</p></td><td><p><pre>4 / 2</pre></p>Gibt 2 zurück.</td></tr>
<tr><td>*</td><td><p><pre>&lt;Ausdruck1&gt; * &lt;Ausdruck2&gt;</pre></p><p> Beide Ausdrücke müssen numerischer Art sein (Ganzzahl oder Dezimalzahl). </p><p>Das Ergebnis ist ebenfalls numerisch.</p></td><td><p><pre>3 * 4</pre></p>Gibt 12 zurück.</td></tr>
<tr><td>%</td><td><p><pre>&lt;Ausdruck1&gt; % &lt;Ausdruck2&gt;</pre></p><p>Beide Ausdrücke müssen numerischer Art sein (Ganzzahl oder Dezimalzahl).</p><p> Das Ergebnis ist ebenfalls numerisch.</p></td><td><p><pre>3 % 2</pre></p>Gibt 1 zurück.</td></tr>
</tbody>
</table>

## Mathematisch

<table>
<thead>
<tr><th>Operator</th><th>Literaler Ausdruck</th><th>Beispiel</th></tr>
</thead>
<tbody><tr><td>is numeric</td><td><p><pre>&lt;Ausdruck&gt; is numeric</pre></p><p>Der Typ des Ausdrucks ist Ganzzahl oder Dezimalzahl.</p></td><td><pre>@ is numeric</pre></td></tr>
<tr><td>is integer</td><td><p><pre>&lt;Ausdruck&gt; is integer</pre></p><p>Der Typ des Ausdrucks ist Ganzzahl.</p></td><td><pre>@ is integer</pre></td></tr>
<tr><td>is decimal</td><td><p><pre>&lt;Ausdruck&gt; is decimal</pre></p><p>Der Typ des Ausdrucks ist Dezimalzahl.</p></td><td><pre>@ is decimal</pre></td></tr>
</tbody>
</table>

## Zeichenfolge

<table>
<thead>
<tr><th>Operator</th><th>Literaler Ausdruck </th><th>Beispiel</th></tr>
</thead>
<tbody><tr><td>+</td><td><p><pre>&lt;Zeichenfolge&gt; + &lt;Ausdruck&gt;</pre></p><p><pre>&lt;Ausdruck&gt; + &lt;Zeichenfolge&gt;</pre></p><p>Damit werden zwei Ausdrücke verkettet. </p><p>Ein Ausdruck muss eine verkettete Zeichenfolge sein.</p></td><td><p><pre>"Die aktuelle Zeit lautet " + (now())</pre></p> Gibt „Die aktuelle Zeit lautet 2019-09-23T09:30:06.693Z“ zurück.<p><pre>(now()) + " lautet die aktuelle Zeit"</pre></p>Gibt „2019-09-23T09:30:06.693Z lautet die aktuelle Zeit“ zurück.<p><pre>"a" + "b" + "c" + 1234</pre></p> Gibt „abc1234“ zurück.</td></tr>
</tbody>
</table>

## Datum

<table>
<thead>
<tr><th>Operator</th><th>Literaler Ausdruck </th><th>Beispiel</th></tr>
</thead>
<tbody>
<tr><td>+</td><td><p><pre>&lt;Ausdruck&gt; + &lt;Dauer&gt;</pre></p><p>Anhängen einer Dauer an einen Datum/Uhrzeit-Wert, einen Datum/Uhrzeit-Wert ohne Zeitzone oder eine Dauer.</p></td><td><p><pre>toDateTime("2011-12-03T15:15:30Z")</pre></p><p><pre> + toDuration("PT15M")</pre></p><p>Gibt „2011-12-03T15:30:30Z“ zurück.</p><p><pre>toDateTimeOnly("2011-12-03T15:15:30")</pre></p><p><pre> + toDuration("PT15M")</pre></p>Gibt „2011-12-03T15:30:30“ zurück.<p><pre>now() + toDuration("PT1H")</pre></p><p>Gibt einen Datum/Uhrzeit-Wert (mit UTC-Zeitzone) eine Stunde nach der aktuellen Zeit zurück.</p><p><pre>toDuration("PT1H") + toDuration("PT1H")</pre></p><p>Gibt „PT2H“ zurück.</p></td></tr>
</tbody>
</table>