---
title: Benutzer
description: Informationen zu Operatoren in erweiterten Ausdrücken
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



# Benutzer {#concept_wd5_pj5_dgb}

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
<tr ><th  >Operator</th><th  >Literaler Ausdruck</th><th  >Beispiel</th></tr>
</thead>
<tbody>
<tr >&gt;<td>und</td><td><p><pre>&lt;expression1&gt; und &lt;expression2&gt;</pre></p>Sowohl &lt;expression1&gt; als auch &lt;expression2&gt; müssen boolean sein. Das Ergebnis ist boolesch.</td><td><pre>3.14 &gt; 2 und 3.15 &lt; 1</pre></td></tr>
<tr ><td>oder</td><td><p><pre>&lt;expression1&gt; oder &lt;expression2&gt;</pre></p><p>Sowohl &lt;expression1&gt; als auch &lt;expression2&gt; müssen boolean sein.</p><p> Das Ergebnis ist boolesch.</p></td><td><p><pre>3.14 &gt; 2 oder 3.15 &lt; 1</pre></p></td></tr>
<tr ><td>not</td><td><p><pre>not &lt;expression&gt;</pre></p><p>&lt;expression&gt; muss boolean sein.</p><p> Das Ergebnis ist boolesch.</p></td><td><pre>nicht 3.15 &lt; 1</pre></td></tr>
</tbody>
  </table>

## Vergleich

<table>
<thead>
<tr ><th  >Operator</th><th  >Literaler Ausdruck </th><th  >Beispiel</th></tr>
</thead>
<tbody><tr ><td>ist null</td><td><p><pre>&lt;expression&gt; ist null</pre></p><p>Das Ergebnis ist boolesch.</p><p>Beachten Sie, dass null bedeutet, dass der Ausdruck keinen ausgewerteten Wert hat.</p></td><td><pre>@{BarBeacon.location} ist null</pre></td></tr>
<tr ><td>ist nicht null</td><td><p><pre>&lt;expression&gt; ist nicht null</pre></p><p>Das Ergebnis ist boolesch.</p><p>Beachten Sie, dass null bedeutet, dass der Ausdruck keinen ausgewerteten Wert hat.</p></td><td><pre>@ ist nicht null</pre></td></tr>
<tr ><td>hat null</td><td><p><pre>&lt;expression&gt; hat null</pre>muss eine Liste sein.</p><p>Das Ergebnis ist boolesch.</p><p>Nützlich zur Identifizierung, dass eine Liste mindestens einen Nullwert enthält.</p></td><td><p><pre>["foo", "bar", null] hat null</pre></p>return true<p><pre>["foo", "bar", ""] hat null</pre></p> gibt false zurück, da ""nicht als null betrachtet wird.</td></tr>
<tr ><td>==</td><td><p><pre>&lt;expression1&gt; == &lt;expression2&gt;</pre></p><p>Sowohl &lt;expression1&gt; als auch &lt;expression2&gt; müssen denselben Datentyp haben.</p><p> Das Ergebnis ist boolesch.</p></td><td><pre>3.14 == 42</pre><br /><pre>"foo" == "bar"</pre></td></tr>
<tr ><td>!=</td><td><p><pre>&lt;expression1&gt; != &lt;expression2&gt;</pre></p><p> Sowohl &lt;expression1&gt; als auch &lt;expression2&gt; müssen denselben Datentyp haben.</p><p> Das Ergebnis ist boolesch.</p></td><td><pre>3.14 != 42</pre><br /><pre>"foo" != "bar"</pre></td></tr>
<tr ><td>&gt;</td><td><p><pre>&lt;expression1&gt; &gt; &lt;expression2&gt;</pre></p><p>Die Zeit kann mit der Zeit verglichen werden.</p><p>Datetimeonly kann mit Datetimeonly verglichen werden.</p><p>Sowohl Ganzzahl als auch Dezimalzahl können mit Ganzzahl oder Dezimalzahl verglichen werden.</p><p>Jede andere Kombination ist verboten.</p><p>Das Ergebnis ist boolesch.</p></td><td><pre>3.14 &gt; 42</pre></td></tr>
<tr ><td>&gt;=</td><td><p><pre>&lt;expression1&gt; &gt;= &lt;expression2&gt;</pre></p><p>Die Zeit kann mit der Zeit verglichen werden.</p><p>Datetimeonly kann mit Datetimeonly verglichen werden.</p><p>Sowohl Ganzzahl als auch Dezimalzahl können mit Ganzzahl oder Dezimalzahl verglichen werden.</p><p>Jede andere Kombination ist verboten.</p><p>Das Ergebnis ist boolesch.</p></td><td><pre>42 &gt;= 3.14</pre></td></tr>
<tr ><td>&lt;</td><td><p><pre>&lt;expression1&gt; &lt; &lt;expression2&gt;</pre></p><p>Die Zeit kann mit der Zeit verglichen werden.</p><p>Datetimeonly kann mit Datetimeonly verglichen werden.</p><p>Sowohl Ganzzahl als auch Dezimalzahl können mit Ganzzahl oder Dezimalzahl verglichen werden.</p><p>Jede andere Kombination ist verboten.</p><p>Das Ergebnis ist boolesch.</p></td><td><pre>42 &lt; 3.14</pre></td></tr>
<tr ><td>&lt;=</td><td><p><pre>&lt;expression1&gt; &lt;= &lt;expression2&gt;</pre></p><p>Die Zeit kann mit der Zeit verglichen werden.</p><p>Datetimeonly kann mit Datetimeonly verglichen werden.</p><p>Sowohl Ganzzahl als auch Dezimalzahl können mit Ganzzahl oder Dezimalzahl verglichen werden.</p><p>Jede andere Kombination ist verboten.</p><p>Das Ergebnis ist boolesch.</p></td><td><pre>42 &lt;= 3.14</pre></td></tr>
</tbody>
</table>

## Arithmetik

<table>
<thead>
<tr ><th  >Operator</th><th>Literaler Ausdruck </th><th  >Beispiel</th></tr>
</thead>
<tbody><tr ><td>+</td><td><p><pre>&lt;expression1&gt; + &lt;expression2&gt;</pre></p><p>Beide Ausdrücke müssen numerisch (Ganzzahl oder Dezimalzahl) sein. </p><p>Das Ergebnis ist auch numerisch.</p></td><td><p><p><pre>1 + 2</pre></p></p><br /><p>Gibt 3 zurück</p></td></tr>
<tr ><td>-</td><td><p><pre>&lt;expression1&gt; - &lt;expression2&gt;</pre></p><p> Beide Ausdrücke müssen numerisch (Ganzzahl oder Dezimalzahl) sein.</p><p> Das Ergebnis ist auch numerisch.</p></td><td><p><pre>2 - 1</pre></p>Gibt 1 zurück</td></tr>
<tr ><td>/</td><td><p><pre>&lt;expression1&gt; / &lt;expression2&gt;</pre></p><p>Beide Ausdrücke müssen numerisch (Ganzzahl oder Dezimalzahl) sein. </p><p>Das Ergebnis ist auch numerisch.</p><p>&lt;expression2&gt; darf nicht gleich 0 sein (gibt 0 zurück).</p></td><td><p><pre>4 / 2</pre></p>Gibt 2 zurück</td></tr>
<tr ><td>*</td><td><p><pre>&lt;expression1&gt; * &lt;expression2&gt;</pre></p><p> Beide Ausdrücke müssen numerisch (Ganzzahl oder Dezimalzahl) sein. </p><p>Das Ergebnis ist auch numerisch.</p></td><td><p><pre>3 * 4</pre></p>Gibt 12 zurück</td></tr>
<tr ><td>%</td><td><p><pre>&lt;expression1&gt; % &lt;expression2&gt;</pre></p><p>Beide Ausdrücke müssen numerisch (Ganzzahl oder Dezimalzahl) sein.</p><p> Das Ergebnis ist auch numerisch.</p></td><td><p><pre>3 % 2</pre></p>Gibt 1 zurück.</td></tr>
</tbody>
</table>

## Mathematik

<table>
<thead>
<tr ><th  >Operator</th><th  >Literaler Ausdruck </th><th  >Beispiel</th></tr>
</thead>
<tbody><tr ><td>ist numerisch</td><td><p><pre>&lt;Ausdruck&gt; ist numerisch</pre></p><p>Der Ausdruckstyp ist Ganzzahl oder Dezimalzahl.</p></td><td><pre>@ ist numerisch</pre></td></tr>
<tr ><td>is integer</td><td><p><pre>&lt;expression&gt; ist integer</pre></p><p>Der Typ des Ausdrucks ist integer.</p></td><td><pre>@ ist integer</pre></td></tr>
<tr ><td>ist dezimal</td><td><p><pre>&lt;expression&gt; ist decimal</pre></p><p>Der Typ des Ausdrucks ist dezimal.</p></td><td><pre>@ ist dezimal</pre></td></tr>

## String

<table>
<thead>
<tr ><th  >Operator</th><th  >Literaler Ausdruck </th><th  >Beispiel</th></tr>
</thead>
<tbody><tr ><td>+</td><td><p><pre>&lt;string&gt; + &lt;expression&gt;</pre></p><p><pre>&lt;expression&gt; + &lt;string&gt;</pre></p><p>Es verkettet zwei Ausdrücke. </p><p>Ein Ausdruck muss eine verkettete Zeichenfolge sein.</p></td><td><p><pre>"Die aktuelle Zeit ist " + (now())</pre></p> Gibt "the current time is 2019-09-23T09:30:06.693Z"zurück<p><pre>(now()) + " ist die aktuelle Zeit"</pre></p>Gibt "2019-09-23T09:30:06.693Z ist die aktuelle Uhrzeit"zurück<p><pre>"a" + "b" + "c" + 1234</pre></p> Gibt "abc1234"zurück.</td></tr>
</tbody>
</table>

## Date

<table>
<thead>
<tr ><th  >Operator</th><th  >Literaler Ausdruck </th><th  >Beispiel</th></tr>
</thead>
<tbody>
<tr ><td>+</td><td><p><pre>&lt;Ausdruck + &lt;Dauer&gt;</pre></p><p>Hängen Sie eine Dauer an eine dateTime, eine dateTimeOnly oder eine Dauer an.</p></td><td><p><pre>toDateTime("2011-12-03T15:15:30Z")</pre></p><p><pre> + toDuration("PT15M")</pre></p><p>Gibt 2011-12-03T15:30:30Z zurück</p><p><pre>toDateTimeOnly("2011-12-03T15:15:30")</pre></p><p><pre> + toDuration("PT15M")</pre></p>Gibt 2011-12-03T15:30:30 zurück<p><pre>now() + toDuration("PT1H")</pre></p><p>Gibt eine Stunde später eine dateTime (mit UTC-Zeitzone) zurück</p><p><pre>toDuration("PT1H") + toDuration("PT1H")</pre></p><p>Gibt PT2H zurück</p></td></tr>
</tbody>
</table>