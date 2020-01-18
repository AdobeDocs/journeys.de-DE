---
title: Datentypen
description: Informationen zu Datentypen in erweiterten Ausdrücken
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
source-git-commit: 4871550d1608f4ffdee3b56d38b08f808eb2281c

---


# Datentypen {#concept_gp3_rj5_dgb}

Technisch gesehen enthält eine Konstante immer einen Datentyp. Im Literalausdruck geben wir nur den Wert an. Der Datentyp kann aus dem Wert abgeleitet werden (z. B. Zeichenfolge, Ganzzahl, Dezimalzahl usw.). Für spezielle Fälle, wie z.B. die Datumszeit, verwenden wir spezielle Funktionen für die Darstellung.

So werden Datentypausdrücke dargestellt:

<table>
    <thead>
        <tr>
        <td>Datentyp</td>
        <td>Description</td>
        <td>Literale Darstellung</td>
        <td>Beispiel</td>
        </tr>
    </thead>
    <tbody>
    <tr>
        <td>string</td>
        <td><p>Allgemeine Zeichenfolge.</p><p>Es hat keine bestimmte Größe außer der impliziten, die aus der Umgebung stammt, wie z.B. die verfügbare Speichermenge.</p><p>JSON-Format: Zeichenfolge</p><p>Serialisierungsformat: UTF-8</p></td>
        <td><p>"&lt;value&gt;"</p><p>'&lt;value&gt;'</p></td>
        <td><p><pre>"hello world"</pre></p><p><pre>"hello world"</pre></p></td>
    </tr>
    <tr>
        <td>integer</td>
        <td><p>Ganzzahlwert von -2^63 bis 2^63-1.</p><p>JSON-Format: Nummer</p></td>
        <td>&lt;integer value&gt;</td>
        <td><p><pre>42</pre></p></td>
    </tr>
    <tr>
        <td>decimal</td>
        <td><p>Dezimalzahl.</p><p>Es stellt einen schwebenden Wert dar:</p>
        <p>- größter positiver Endwert des Typs Double, (2-2^-52)x2^1023</p>
        <p> - kleinster positiver Normalwert des Typs Double, 2-1022</p>
        <p> - kleinster positiver Wert ungleich null vom Typ Double, 2 p-1074</p><p>JSON-Format: Nummer</p><p>Serialisierungsformat: mit '.' als Dezimaltrenner.</p></td>
        <td>&lt;integer value&gt;.&lt;integer value&gt;</td>
        <td><p><pre>3.14</pre></p></td>
    </tr>
    <tr>
        <td>boolean</td>
        <td><p>Boolescher Wert, Kleinbuchstabe geschrieben: true oder false</p><p>JSON-Format: Boolesch</p></td>
        <td><p>wahr</p><p>false</p></td>
        <td><p><pre>wahr</pre></p></td>
    </tr>
    <tr>
        <td>dateTimeOnly</td>
        <td><p>Stellt eine Datumseingabe ohne Zeitzone dar, die als einminütige Millisekunde pro Jahr angesehen wird.</p><p>Es wird keine Zeitzone gespeichert oder dargestellt.</p><p>Stattdessen ist es eine Beschreibung des Datums, wie es zum Geburtstag verwendet wird, kombiniert mit der Ortszeit, wie sie auf einer Wanduhr zu sehen ist.</p><p>Es kann kein Instant on der Zeitleiste ohne zusätzliche Informationen wie Offset oder Zeitzone dargestellt werden.</p><p>Serialisierungsformat: ISO-8601 erweitertes Offset-Datumsformat.</p><p>Es verwendet DateTimeFormatter.</p><p>ISO_LOCAL_DATE_TIME, um den Wert zu deserialisieren und zu serialisieren.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME">Mehr dazu</a>.</td>
        <td><p>toDateTimeOnly("&lt;dateTimeOnly im ISO-8601-Format&gt;")</p></td>
        <td></td>
    </tr>
    <tr>
        <td>dateTime</td>
        <td><p>Zeitkonstante des Datums, die auch die Zeitzone berücksichtigt.</p><p>Es stellt eine Datums-/Uhrzeitangabe mit einem Offset von UTC dar. Es kann als ein sofortiger Zeitpunkt mit den zusätzlichen Informationen des Offsets betrachtet werden. </p><p>Es ist eine Möglichkeit, einen bestimmten "Moment"an einem bestimmten Ort der Welt zu repräsentieren.</p><p>JSON-Format: Zeichenfolge.</p><p> Sie muss in eine toDateTime-Funktion eingekapselt sein.</p><p>
        Serialisierungsformat: ISO-8601 erweitertes Offset-Datumsformat.</p><p> Es verwendet DateTimeFormatter.ISO_OFFSET_DATE_TIME, um den Wert zu deserialisieren und zu serialisieren.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME">Mehr dazu</a>. 
        <p>Sie können auch eine Ganzzahl übergeben, die einen Epochenwert übergibt.</p> <a href="https://www.epochconverter.com/">mehr dazu</a></p>
        <p>Die Zeitzone kann durch einen Offset- oder Zeitzonencode angegeben werden (Beispiel: Europa/Paris, Z - bedeutet UTC).</p></td>
        <td><p>toDateTime("&lt;dateTime im ISO-8601-Format&gt;")</p>
        <p>toDateTime(&lt;ganzzahliger Wert einer Epoche in Millisekunden&gt;)</p></td>
        <td><p><pre>toDateTime("1977-04-22T06:00:00Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123+02:00")</pre></p>
        <p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123-00:20")</pre></p><p><pre>toDateTime(1560762190189)</pre></p></td>
    </tr>
    <tr>
        <td>duration</td>
        <td><p>Es stellt einen zeitbasierten Zeitraum dar, z. B. "34,5 Sekunden".</p><p> Es modelliert eine Menge oder einen Zeitraum in Millisekunden.</p><p>Folgende Zeiteinheiten werden unterstützt: Millisekunden, Sekunden, Minuten, Stunden, Tage, bei denen ein Tag 24 Stunden entspricht.</p><p> Jahre und Monate werden nicht unterstützt, da sie keine feste Zeit sind.</p><p>JSON-Format: Zeichenfolge. Es muss in eine toDuration-Funktion eingekapselt werden.</p><p>Serialisierungsformat: Zur Deserialisierung einer Zeitzone-ID wird die Java-Funktion java.time verwendet.</p><p>Duration.parse: Die Formate basieren auf dem ISO-8601-Format für die Dauer PnDTnHnMn.nS, wobei die Tage genau 24 Stunden betragen.</p><a href="https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-">Mehr dazu</a>.</td>
        <td><p>toDuration("&lt;Dauer im ISO-8601-Format&gt;")</p><p>toDuration(&lt;Dauer in Millisekunden&gt;)</p></td>
        <td><p><pre>toDuration("PT5S") // 5 Sekunden</pre></p>
        <p><pre>toDuration(500) // </pre></p>
        <p><pre>500ms</pre></p>
        <p><pre>toDuration("PT20.345S") </pre></p>
        <p><pre>— parses as "20.345 seconds"</pre></p>
        <p><pre>toDuration("PT15M") </pre></p>
        <p><pre> — Parsen als "15 Minuten"</pre></p>
        <p><pre>(wobei eine Minute 60 Sekunden beträgt)</pre></p>
        <p><pre>toDuration("PT10H") </pre></p>
        <p><pre>— Parsen als "10 Stunden"</pre></p>
        <p><pre>(bei einer Stunde von 3600 Sekunden)</pre></p>
        <p><pre>toDuration("P2D") </pre></p>
        <p><pre>— Parsen als "2 Tage"</pre></p>
        <p><pre>(bei einem Tag </pre></p>
        <p><pre>24 Stunden oder 86400 Sekunden)</pre></p>
        <p><pre>toDuration("P2DT3H4M") </pre></p>
        <p><pre>— Parsen als</pre></p>
        <p><pre>"2 Tage, 3 Stunden und 4 Minuten"</pre></p>
        <p><pre>toDuration("P-6H3M") </pre></p>
        <p><pre>— Parsen als</pre></p>
        <p><pre>"-6 Stunden und +3 Minuten"</pre></p>
        <p><pre>toDuration("-P6H3M") </pre></p>
        <p><pre>— Parsen als</pre></p>
        <p><pre>"-6 Stunden und -3 Minuten"</pre></p>
        <p><pre>toDuration("-P-6H+3M") </pre></p>
        <p><pre>— Parsen als</pre></p>
        <p><pre>"+6 Stunden und -3 Minuten"</pre></p></td>
    </tr>
    <tr>
        <td>Liste</td>
        <td>Kommagetrennte Liste von Ausdrücken mit eckigen Klammern als Trennzeichen. Polymorphismus wird nicht unterstützt. Daher sollten alle in der Liste enthaltenen Ausdrücke denselben Typ haben.</td>
        <td>[&lt;Ausdruck&gt;, &lt;Ausdruck&gt;, ... ]</td>
        <td><p><pre>["value1","value2"]</pre></p><p><pre>[3,5]</pre></p><p><pre>[toDuration(500),toDuration(800)]</pre></p></td>
    </tr>
    </tbody>
</table>
