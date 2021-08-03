---
product: adobe campaign
solution: Journey Orchestration
title: Integration mit externen Systemen
description: Best Practices bei der Integration externer Systeme
feature: Journeys
role: User
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: ht
source-wordcount: '1012'
ht-degree: 100%

---

# Integration mit externen Systemen {#external-systems}

Auf dieser Seite finden Sie die verschiedenen Schutzmechanismen, die Journey Orchestration bei der Integration eines externen Systems bietet, sowie Best Practices: wie Sie den Schutz Ihres externen Systems unter Verwendung der Begrenzungs-API optimieren können, wie die maximale Wartezeit bei Journeys konfiguriert wird und wie erneute Versuche funktionieren.

Mit Journey Orchestration können Sie über benutzerdefinierte Datenquellen und Aktionen Verbindungen zu externen Systemen konfigurieren. Auf diese Weise können Sie beispielsweise Ihre Journeys mit Daten aus einem externen Reservierungssystem anreichern oder Nachrichten mithilfe eines Drittanbietersystems wie Epsilon oder Facebook versenden.

Bei der Integration eines externen Systems können mehrere Probleme auftreten: Das System kann langsam sein, nicht mehr reagieren oder es kann möglicherweise nicht in der Lage sein, große Datenmengen zu verarbeiten. Journey Orchestration bietet verschiedene Schutzmechanismen, um Ihr System vor Überlastung zu schützen.

Alle externen Systeme unterscheiden sich hinsichtlich ihrer Leistung. Sie müssen die Konfiguration deshalb an Ihre Anwendungsfälle anpassen.

Wenn Journey Orchestration einen Aufruf an eine externe API ausführt, werden die technischen Schutzmaßnahmen wie folgt ausgeführt:

1. Begrenzungsregeln werden angewendet: Wenn die maximale Anzahl erreicht wurde, werden die verbleibenden Aufrufe verworfen.

2. Maximale Wartezeit und erneuter Versuch: Wenn die Begrenzungsregel erfüllt ist, versucht Journey Orchestration, den Aufruf durchzuführen, bis das Ende der maximalen Wartezeit erreicht ist.

## Begrenzung{#capping}

Die integrierte Begrenzungs-API bietet einen vorgelagerten technischen Schutzmechanismus für Ihr externes System.

Bei externen Datenquellen wird die maximale Anzahl von Aufrufen pro Sekunde auf 15 festgelegt. Wenn die Anzahl der Aufrufe 15 pro Sekunde überschreitet, werden die verbleibenden Aufrufe verworfen. Sie können diese Beschränkung für private externe Datenquellen erhöhen. Wenden Sie sich an Adobe, um den Endpunkt auf die Zulassungsliste zu setzen. Dies ist für öffentliche externe Datenquellen nicht möglich.

Für benutzerdefinierte Aktionen müssen Sie die Kapazität Ihrer externen API ermitteln. Wenn Journey Optimizer beispielsweise 1.000 Aufrufe pro Sekunde sendet und Ihr System nur 100 Aufrufe pro Sekunde unterstützt, müssen Sie eine Begrenzungsregel definieren, damit Ihr System nicht überlastet wird.

Begrenzungsregeln werden auf Sandbox-Ebene für einen bestimmten Endpunkt (die aufgerufene URL) definiert. Zur Laufzeit überprüft Journey Orchestration, ob eine Begrenzungsregel definiert ist, und wendet die definierte Rate während der Aufrufe auf diesen Endpunkt an. Wenn die Anzahl der Aufrufe die definierte Rate überschreitet, werden die verbleibenden Aufrufe verworfen und in Berichten als Fehler gezählt.

Eine Begrenzungsregel gilt spezifisch für einen Endpunkt, aber global für alle Journeys einer Sandbox. Dies bedeutet, dass Begrenzungs-Slots an alle Journeys einer Sandbox weitergegeben werden.

Nehmen wir beispielsweise an, Sie haben eine Begrenzungsregel von 100 Aufrufen pro Sekunde für Ihr externes System definiert. Eine benutzerdefinierte Aktion führt in 10 verschiedenen Journeys Aufrufe an Ihr System aus. Wenn eine Journey 200 Aufrufe pro Sekunde erhält, verwendet sie die 100 verfügbaren Slots und verwirft die 100 übrigen Slots. Da die Höchstrate überschritten wurde, sind für die anderen 9 Journeys keine Slots mehr übrig. Durch diese Granularität ist das externe System vor Überlastung und Abstürzen geschützt.

Weitere Informationen zur Begrenzungs-API und zum Konfigurieren von Begrenzungsregeln finden Sie auf [dieser Seite](../api/capping.md).

## Zeitüberschreitung und erneute Versuche{#timeout}

Wenn die Begrenzungsregel erfüllt ist, wird die Zeitüberschreitungsregel angewendet.

Sie können in jeder Journey eine Zeitüberschreitungsdauer festlegen. Auf diese Weise können Sie für den Aufruf eines externen Systems eine maximale Dauer festlegen. Die Zeitüberschreitungsdauer wird in den Eigenschaften einer Journey konfiguriert. Mehr dazu erfahren Sie auf [dieser Seite](../building-journeys/changing-properties.md#timeout_and_error).

Diese Zeitüberschreitung gilt für alle externen Aufrufe (externe API-Aufrufe in benutzerdefinierten Aktionen und Datenquellen). Standardmäßig ist dieser Zeitraum mit fünf Sekunden festgelegt.

Während der definierten maximalen Wartezeit versucht Journey Orchestration, das externe System aufzurufen. Nach dem ersten Aufruf können bis zum Ende der Zeitüberschreitungsdauer maximal drei weitere Versuche unternommen werden. Die Anzahl weiterer Versuche kann nicht geändert werden.

Bei jedem erneuten Versuch wird ein Slot verwendet. Wenn Sie eine Begrenzung von 100 Aufrufen pro Sekunde haben und jeder Ihrer Aufrufe zwei weitere Versuche erfordert, sinkt die Rate auf 30 Aufrufe pro Sekunde (jeder Aufruf verwendet drei Slots: den ersten Aufruf und zwei weitere Versuche).

Der Wert für die Zeitüberschreitungsdauer hängt vom Anwendungsfall ab. Wenn Sie Ihre Nachricht schnell senden möchten, z. B. wenn ein Kunde das Geschäft betritt, ist es nicht sinnvoll, eine lange Zeitüberschreitung einzurichten. Je länger die Zeitüberschreitung ist, desto mehr Elemente werden in die Warteschlange gestellt. Dies kann die Leistung erheblich beeinträchtigen. Wenn Journey Orchestration 1.000 Aufrufe pro Sekunde ausführt, kann die Speicherung von 5 oder 15 Sekunden Daten das System schnell überfordern.

Sehen wir uns ein Beispiel einer Zeitüberschreitung von fünf Sekunden an.

* Der erste Aufruf dauert weniger als fünf Sekunden: Der Aufruf ist erfolgreich und es wird kein erneuter Versuch unternommen.
* Der erste Aufruf dauert länger als fünf Sekunden: Der Aufruf wird abgebrochen und es wird kein erneuter Versuch unternommen. In Berichten wird dies als Zeitüberschreitungsfehler gezählt.
* Der erste Aufruf schlägt nach zwei Sekunden fehl (das externe System gibt einen Fehler zurück): drei Sekunden bleiben für weitere Versuche, wenn Begrenzungs-Slots verfügbar sind.
   * Wenn einer der drei weiteren Versuche vor Ablauf der fünf Sekunden erfolgreich ist, wird der Aufruf durchgeführt und es wird kein Fehler ausgegeben.
   * Wenn während der erneuten Versuche das Ende der maximalen Wartezeit erreicht wird, wird der Aufruf abgebrochen und in Berichten als Zeitüberschreitungsfehler gezählt.

## Häufig gestellte Fragen{#faq}

**Wie kann ich eine Begrenzungsregel konfigurieren? Gibt es eine standardmäßige Begrenzungsregel?**

Standardmäßig gibt es keine Begrenzungsregel. Begrenzungsregeln werden auf Sandbox-Ebene mithilfe der Begrenzungs-API für einen bestimmten Endpunkt (die aufgerufene URL) definiert. Weitere Informationen finden Sie in [diesem Abschnitt](../about/external-systems.md#capping) und auf [dieser Seite](../api/capping.md).

**Wie viele weitere Versuche werden unternommen? Kann ich die Anzahl der weiteren Versuche ändern oder eine Mindestwartezeit zwischen den Versuchen definieren?**

Pro Aufruf können nach dem ersten Aufruf maximal drei weitere Versuche durchgeführt werden, bis das Ende der Zeitüberschreitungsdauer erreicht ist. Die Anzahl weiterer Versuche und die Zeit zwischen den einzelnen Versuchen können nicht geändert werden. Weitere Informationen finden Sie in [diesem Abschnitt](../about/external-systems.md#timeout).

**Wo kann ich die Zeitüberschreitung konfigurieren? Gibt es einen Maximalwert?**

Sie können in jeder Journey eine Zeitüberschreitungsdauer festlegen. Die Zeitüberschreitungsdauer wird in den Eigenschaften einer Journey konfiguriert. Die Zeitüberschreitungsdauer muss zwischen 1 Sekunde und 30 Sekunden liegen. Weitere Informationen finden Sie in [diesem Abschnitt](../about/external-systems.md#timeout) und auf [dieser Seite](../building-journeys/changing-properties.md#timeout_and_error).