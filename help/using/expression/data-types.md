---
title: Datentypen
description: Erfahren Sie mehr über die Datentypen in erweiterten Ausdrücken
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: 4871550d1608f4ffdee3b56d38b08f808eb2281c
workflow-type: ht
source-wordcount: '675'
ht-degree: 100%

---


# Datentypen {#concept_gp3_rj5_dgb}

Technisch gesehen enthält eine Konstante immer einen Datentyp. Wörtlich genommen geben wir nur den Wert an. Der Datentyp kann aus dem Wert abgeleitet werden (z. B. Zeichenfolge, Ganzzahl, Dezimalzahl usw.). Für bestimmte Fälle wie Datum und Uhrzeit verwenden wir spezielle Funktionen für die Darstellung.

So werden Datentypausdrücke dargestellt:

<table>
    <thead>
        <tr>
        <td>Datentyp</td>
        <td>Beschreibung</td>
        <td>Wörtliche Darstellung</td>
        <td>Beispiel</td>
        </tr>
    </thead>
    <tbody>
    <tr>
        <td>string</td>
        <td><p>Allgemeine Zeichenfolge.</p><p>Er hat keine bestimmte Größe außer der impliziten Größe, die aus der Umgebung stammt, z. B. die verfügbare Speicherkapazität.</p><p>JSON-Format: Zeichenfolge</p><p>Serialisierungsformat: UTF-8</p></td>
        <td><p>"&lt;Wert&gt;"</p><p>'&lt;Wert&gt;'</p></td>
        <td><p><pre>"Hello World"</pre></p><p><pre>'Hello World'</pre></p></td>
    </tr>
    <tr>
        <td>integer</td>
        <td><p>Ganzzahlwert von -2^63 bis 2^63-1.</p><p>JSON-Format: Zahl</p></td>
        <td>&lt;Ganzzahlwert&gt;</td>
        <td><p><pre>42</pre></p></td>
    </tr>
    <tr>
        <td>decimal</td>
        <td><p>Dezimalzahl.</p><p>Stellt einen Gleitkommawert dar:</p>
        <p>- größter positiver endlicher Wert des Typs „double“, (2-2^-52)x2^1023</p>
        <p> - kleinster positiver Normalwert des Typs „double“, 2-1022</p>
        <p> - kleinster positiver Wert ungleich null vom Typ „double“, 2 p-1074</p><p>JSON-Format: Zahl</p><p>Serialisierungsformat: mit '.' als Dezimaltrennzeichen.</p></td>
        <td>&lt;Ganzzahlwert&gt;.&lt;Ganzzahlwert&gt;</td>
        <td><p><pre>3.14</pre></p></td>
    </tr>
    <tr>
        <td>boolean</td>
        <td><p>Boolescher Wert in Kleinbuchstaben: true (wahr) oder false (falsch)</p><p>JSON-Format: Boolesch</p></td>
        <td><p>true</p><p>false</p></td>
        <td><p><pre>true</pre></p></td>
    </tr>
    <tr>
        <td>dateTimeOnly</td>
        <td><p>Stellt Datum und Uhrzeit ohne Zeitzone dar, die als Jahr-Monat-Tag-Stunde-Minute-Sekunde-Millisekunde interpretiert wird.</p><p>Es wird keine Zeitzone gespeichert oder dargestellt.</p><p>Stattdessen handelt es sich um eine Beschreibung des Datums, wie es für Geburtstage verwendet wird, kombiniert mit der Ortszeit, wie sie auf einer Wanduhr angezeigt wird.</p><p>Ohne zusätzliche Informationen wie Versatz oder Zeitzone kann kein Zeitpunkt auf der Zeitachse dargestellt werden.</p><p>Serialisierungsformat: ISO-8601, erweitertes Versatz-Datums-/Uhrzeitformat.</p><p>DateTimeFormatter wird verwendet.</p><p>ISO_LOCAL_DATE_TIME zur Deserialisierung und Serialisierung des Wertes.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME">Mehr dazu</a>.</td>
        <td><p>toDateTimeOnly("&lt;dateTimeOnly im ISO-8601-Format&gt;")</p></td>
        <td></td>
    </tr>
    <tr>
        <td>dateTime</td>
        <td><p>Datums-/Zeitkonstante, die auch die Zeitzone berücksichtigt.</p><p>Es wird Datum + Uhrzeit mit einem Versatz relativ zur UTC dargestellt. Mit den zusätzlichen Informationen zum Versatz kann ein bestimmter Zeitpunkt dargestellt werden. </p><p>Bietet eine Möglichkeit, einen bestimmten Zeitpunkt an einem bestimmten Ort der Welt darzustellen.</p><p>JSON-Format: Zeichenfolge.</p><p> Muss in einer toDateTime-Funktion gekapselt sein.</p><p>
        Serialisierungsformat: ISO-8601, erweitertes Versatz-Datums-/Uhrzeitformat.</p><p> Verwendet DateTimeFormatter.ISO_OFFSET_DATE_TIME zur Deserialisierung und Serialisierung des Wertes.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME">Mehr dazu</a>. 
        <p>Sie können auch eine Ganzzahl übergeben, die einen Epochenwert übergibt.</p> <a href="https://www.epochconverter.com/">Mehr dazu</a>.</p>
        <p>Die Zeitzone kann durch einen Versatz oder einen Zeitzonen-Code angegeben werden (Beispiel: Europa/Paris, Z – bedeutet UTC).</p></td>
        <td><p>toDateTime("&lt;dateTime im ISO-8601-Format&gt;")</p>
        <p>toDateTime(&lt;ganzzahliger Wert einer Epoche in Millisekunden&gt;)</p></td>
        <td><p><pre>toDateTime("1977-04-22T06:00:00Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123+02:00")</pre></p>
        <p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123-00:20")</pre></p><p><pre>toDateTime(1560762190189)</pre></p></td>
    </tr>
    <tr>
        <td>duration</td>
        <td><p>Stellt eine zeitbasierte Dauer dar, z. B. „34,5 Sekunden“.</p><p> Modelliert eine Menge oder Dauer in Millisekunden.</p><p>Folgende Zeiteinheiten werden unterstützt: Millisekunden, Sekunden, Minuten, Stunden, Tage, wobei ein Tag 24 Stunden entspricht.</p><p> Jahre und Monate werden nicht unterstützt, da sie keine feste Dauer haben.</p><p>JSON-Format: Zeichenfolge. Muss in einer toDuration-Funktion gekapselt sein.</p><p>Serialisierungsformat: Zur Deserialisierung einer Zeitzonen-ID wird die Java-Funktion java.time verwendet.</p><p>Duration.parse: Die akzeptierten Formate basieren auf dem ISO-8601-Dauerformat „PnDTnHnMn.nS“, wobei Tage als genau 24 Stunden angesehen werden.</p><a href="https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-">Mehr dazu</a>.</td>
        <td><p>toDuration("&lt;Dauer im ISO-8601-Format&gt;")</p><p>toDuration(&lt;Dauer in Millisekunden&gt;)</p></td>
        <td><p><pre>toDuration("PT5S") // 5 Sekunden</pre></p>
        <p><pre>toDuration(500) // </pre></p>
        <p><pre>500ms</pre></p>
        <p><pre>toDuration("PT20.345S") </pre></p>
        <p><pre>- wird als „20,345 Sekunden“ gedeutet</pre></p>
        <p><pre>toDuration("PT15M") </pre></p>
        <p><pre> - wird als „15 Minuten“ gedeutet</pre></p>
        <p><pre>(wobei eine Minute 60 Sekunden hat)</pre></p>
        <p><pre>toDuration("PT10H") </pre></p>
        <p><pre>- wird als „10 Stunden“ gedeutet</pre></p>
        <p><pre>(wobei eine Stunde 3600 Sekunden hat)</pre></p>
        <p><pre>toDuration("P2D") </pre></p>
        <p><pre>- wird als „2 Tage“ gedeutet</pre></p>
        <p><pre>(wobei ein Tag </pre></p>
        <p><pre>24 Stunden oder 86400 Sekunden hat)</pre></p>
        <p><pre>toDuration("P2DT3H4M") </pre></p>
        <p><pre>- wird als</pre></p>
        <p><pre>„2 Tage, 3 Stunden und 4 Minuten“ gedeutet</pre></p>
        <p><pre>toDuration("P-6H3M") </pre></p>
        <p><pre>- wird als</pre></p>
        <p><pre>„-6 Stunden und +3 Minuten“ gedeutet</pre></p>
        <p><pre>toDuration("-P6H3M") </pre></p>
        <p><pre>- wird als</pre></p>
        <p><pre>„-6 Stunden und -3 Minuten“ gedeutet</pre></p>
        <p><pre>toDuration("-P-6H+3M") </pre></p>
        <p><pre>- wird als</pre></p>
        <p><pre>„+6 Stunden und -3 Minuten“ gedeutet</pre></p></td>
    </tr>
    <tr>
        <td>list</td>
        <td>Kommagetrennte Liste von Ausdrücken mit eckigen Klammern als Trennzeichen. Polymorphismus wird nicht unterstützt. Daher sollten alle in der Liste enthaltenen Ausdrücke denselben Typ haben.</td>
        <td>[&lt;Ausdruck&gt;, &lt;Ausdruck&gt;, ... ]</td>
        <td><p><pre>["Wert1","Wert2"]</pre></p><p><pre>[3,5]</pre></p><p><pre>[toDuration(500),toDuration(800)]</pre></p></td>
    </tr>
    </tbody>
</table>
