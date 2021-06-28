---
product: adobe campaign
solution: Journey Orchestration
title: Integration mit externen Systemen
description: Informationen zu Best Practices bei der Integration externer Systeme
feature: Journeys
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: 5d2e82c10dd22b5b4bac15a78a2f6f592aedd371
workflow-type: ht
source-wordcount: '957'
ht-degree: 100%

---

# Integration mit externen Systemen {#external-systems}

Auf dieser Seite finden Sie die verschiedenen Schutzmechanismen, die Journey Orchestration bei der Integration eines externen Systems bietet, sowie Best Practices: wie Sie den Schutz Ihres externen Systems unter Verwendung der Begrenzungs-API optimieren können, wie die maximale Wartezeit bei Journeys konfiguriert wird und wie erneute Versuche funktionieren.

Mit Journey Orchestration können Sie über benutzerdefinierte Datenquellen und Aktionen Verbindungen zu externen Systemen konfigurieren. Auf diese Weise können Sie beispielsweise Ihre Journey mit Daten aus einem externen Reservierungssystem anreichern oder Nachrichten mithilfe eines Drittanbietersystems wie Epsilon oder Facebook versenden.

Bei der Integration eines externen Systems können mehrere Probleme auftreten. Das System kann langsam sein, nicht mehr reagieren oder es ist möglicherweise nicht in der Lage, große Mengen zu verarbeiten. Journey Orchestration bietet verschiedene Schutzmechanismen, um Ihr System vor Überlastung zu schützen.

Alle externen Systeme unterscheiden sich hinsichtlich der Leistung. Sie müssen die Konfiguration an Ihre Anwendungsfälle anpassen.

Wenn Journey Orchestration einen Aufruf an eine externe API ausführt, werden die technischen Schutzmaßnahmen wie folgt ausgeführt:

1. Begrenzungsregeln werden angewendet: Wenn die maximale Rate erreicht wird, werden die verbleibenden Aufrufe verworfen.

2. Maximale Wartezeit und erneuter Versuch: Wenn die Begrenzungsregel erfüllt ist, versucht Journey Orchestration, den Aufruf durchzuführen, bis das Ende der maximalen Wartezeit erreicht ist.

## Begrenzung{#capping}

Die integrierte Begrenzungs-API bietet eine vorgeschaltete technische Schutzmaßnahme, die zum Schutz Ihres externen Systems beiträgt. Zuvor müssen Sie die Kapazität Ihrer externen API abschätzen. Wenn beispielsweise Journey Orchestration 1.000 Aufrufe pro Sekunde sendet und Ihr System nur 100 Aufrufe pro Sekunde unterstützen kann, müssen Sie eine Begrenzungsregel definieren, damit Ihr System nicht überfordert wird.

Begrenzungsregeln werden auf Sandbox-Ebene für einen bestimmten Endpunkt (die aufgerufene URL) definiert. Zur Laufzeit überprüft Journey Orchestration, ob eine Begrenzungsregel definiert ist, und wendet die definierte Rate während der Aufrufe auf diesen Endpunkt an. Wenn die Anzahl der Aufrufe die definierte Rate überschreitet, werden die verbleibenden Aufrufe verworfen und im Reporting als Fehler gezählt.

Eine Begrenzungsregel gilt zwar für einen spezifischen Endpunkt, wird aber global auf alle Journeys einer Sandbox angewendet. Dies bedeutet, dass es für alle Journeys einer Sandbox gemeinsame Begrenzungs-Slots gibt.

Nehmen wir beispielsweise an, Sie haben für das externe System eine Begrenzungsregel von 100 Aufrufen pro Sekunde definiert. Das System wird durch eine benutzerdefinierte Aktion in 10 verschiedenen Journeys aufgerufen. Wenn eine Journey 200 Aufrufe pro Sekunde erhält, verwendet sie die 100 verfügbaren Slots und verwirft die 100 verbleibenden Slots. Da die Höchstrate überschritten wurde, werden die anderen 9 Journeys keinen Slot mehr bekommen. Diese Granularität hilft, das externe System vor Überlastung und Abstürzen zu schützen.

Weitere Informationen zur Begrenzungs-API und zum Konfigurieren von Begrenzungsregeln finden Sie auf [dieser Seite](../api/capping.md).

## Maximale Wartezeit und erneute Versuche{#timeout}

Wenn die Begrenzungsregel erfüllt ist, wird die Regel für die maximale Wartezeit angewendet.

In jeder Journey können Sie eine maximale Wartezeit festlegen. Auf diese Weise können Sie beim Aufruf eines externen Systems eine Höchstdauer festlegen. Die maximale Wartezeit wird in den Eigenschaften einer Journey konfiguriert. Mehr dazu erfahren Sie auf [dieser Seite](../building-journeys/changing-properties.md#timeout_and_error).

Diese maximale Wartezeit gilt für alle externen Aufrufe (externe API-Aufrufe in benutzerdefinierten Aktionen und Datenquellen). Standardmäßig ist dieser Zeitraum mit 5 Sekunden festgelegt.

Während der definierten maximalen Wartezeit versucht Journey Orchestration, das externe System aufzurufen. Nach dem ersten Aufruf können bis zum Ende der maximalen Wartezeit maximal drei weitere Versuche durchgeführt werden. Die Anzahl erneuter Versuche kann nicht geändert werden.

Bei jedem erneuten Versuch wird ein Slot verwendet. Wenn Sie eine Begrenzung von 100 Aufrufen pro Sekunde haben und jeder Ihrer Aufrufe zwei erneute Versuche erfordert, sinkt die Rate auf 30 Aufrufe pro Sekunde (jeder Aufruf verwendet 3 Slots: den ersten Aufruf und zwei erneute Versuche).

Der Wert für die maximale Wartezeit hängt vom Anwendungsfall ab. Wenn Sie Ihre Nachricht schnell senden möchten, z. B. wenn der Kunde das Geschäft betritt, sollten Sie keine lange Wartezeit einrichten. Je länger die maximale Wartezeit ist, desto mehr Elemente werden in die Warteschlange gestellt. Dies kann die Leistung erheblich beeinträchtigen. Wenn Journey Orchestration 1.000 Aufrufe pro Sekunde ausführt, kann die Speicherung von 5 oder 15 Sekunden Daten das System schnell überfordern.

Nehmen wir als Beispiel eine maximale Wartezeit von 5 Sekunden.

* Der erste Aufruf dauert weniger als 5 Sekunden: Der Aufruf ist erfolgreich und es wird kein erneuter Versuch unternommen.
* Der erste Aufruf dauert länger als 5 Sekunden: Der Aufruf wird abgebrochen und es wird kein erneuter Versuch unternommen. Er wird im Reporting als Zeitüberschreitungsfehler gezählt.
* Der erste Aufruf schlägt nach 2 Sekunden fehl (das externe System gibt einen Fehler zurück): 3 Sekunden bleiben für erneute Versuche, wenn Begrenzungs-Slots verfügbar sind.
   * Wenn einer der drei erneuten Versuche vor Ablauf der 5 Sekunden erfolgreich ist, wird der Aufruf durchgeführt und es wird kein Fehler ausgegeben.
   * Wenn das Ende der maximalen Wartezeit während der erneuten Versuche erreicht wird, wird der Aufruf abgebrochen und im Reporting als Zeitüberschreitungsfehler gezählt.

## Häufig gestellte Fragen{#faq}

**Wie kann ich eine Begrenzungsregel konfigurieren? Gibt es eine standardmäßige Begrenzungsregel?**

Standardmäßig gibt es keine Begrenzungsregel. Begrenzungsregeln werden auf Sandbox-Ebene für einen bestimmten Endpunkt (die aufgerufene URL) unter Verwendung der Begrenzungs-API definiert. Weitere Informationen finden Sie in [diesem Abschnitt](../about/external-systems.md#capping) und auf [dieser Seite](../api/capping.md).

**Wie viele erneute Versuche werden unternommen? Kann ich die Anzahl der erneuten Versuche ändern oder eine Mindestwartezeit zwischen den erneuten Versuchen definieren?**

Für einen gegebenen Aufruf können nach dem ersten Aufruf maximal drei erneute Versuche durchgeführt werden, bis das Ende der maximalen Wartezeit erreicht ist. Die Anzahl erneuter Versuche und die Zeit zwischen den einzelnen erneuten Versuchen können nicht geändert werden. Weitere Informationen finden Sie in [diesem Abschnitt](../about/external-systems.md#timeout).

**Wo kann ich die maximale Wartezeit konfigurieren? Gibt es einen Höchstwert?**

In jeder Journey können Sie eine maximale Wartezeit festlegen. Die maximale Wartezeit wird in den Eigenschaften einer Journey konfiguriert. Die maximale Wartezeit muss zwischen 1 Sekunde und 30 Sekunden liegen. Weitere Informationen finden Sie in [diesem Abschnitt](../about/external-systems.md#timeout) und auf [dieser Seite](../building-journeys/changing-properties.md#timeout_and_error).