---
product: adobe campaign
solution: Journey Orchestration
title: Integration mit externen Systemen
description: Best Practices bei der Integration externer Systeme
feature: Journeys
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: 5d2e82c10dd22b5b4bac15a78a2f6f592aedd371
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 1%

---

# Integration mit externen Systemen {#external-systems}

Auf dieser Seite finden Sie die verschiedenen Limits, die die Journey Orchestration bei der Integration eines externen Systems bietet, sowie Best Practices: wie Sie den Schutz Ihres externen Systems mithilfe der Begrenzungs-API optimieren können, wie Journey-Timeout konfiguriert wird und wie Neuversuche funktionieren.

Mit Journey Orchestration können Sie Verbindungen zu externen Systemen über benutzerdefinierte Datenquellen und benutzerdefinierte Aktionen konfigurieren. Auf diese Weise können Sie beispielsweise Ihre Journey mit Daten aus einem externen Reservierungssystem anreichern oder Nachrichten mithilfe eines Drittanbietersystems wie Epsilon oder Facebook versenden.

Bei der Integration eines externen Systems können mehrere Probleme auftreten, das System kann langsam sein, nicht mehr reagieren oder es kann möglicherweise nicht in der Lage sein, große Mengen zu verarbeiten. Journey Orchestration bietet verschiedene Schutzmechanismen, um Ihr System vor Überlastung zu schützen.

Alle externen Systeme unterscheiden sich hinsichtlich der Leistung. Sie müssen die Konfiguration an Ihre Anwendungsfälle anpassen.

Wenn Journey Orchestration einen Aufruf an eine externe API ausführt, werden die technischen Limits wie folgt ausgeführt:

1. Begrenzungsregeln werden angewendet: Wenn die maximale Rate erreicht wird, werden die verbleibenden Aufrufe verworfen.

2. Zeitüberschreitung und erneuter Versuch: Wenn die Begrenzungsregel erfüllt ist, versucht Journey Orchestration, den Aufruf durchzuführen, bis das Ende der Timeout-Dauer erreicht ist.

## Obergrenze{#capping}

Die integrierte Capping-API bietet eine vorgelagerte technische Limits, die zum Schutz Ihres externen Systems beitragen. Zuvor müssen Sie die Kapazität Ihrer externen API evaluieren. Wenn beispielsweise Journey Orchestration 1.000 Aufrufe pro Sekunde sendet und Ihr System nur 100 Aufrufe pro Sekunde unterstützen kann, müssen Sie eine Begrenzungsregel definieren, damit Ihr System nicht überfordert wird.

Begrenzungsregeln werden auf Sandbox-Ebene für einen bestimmten Endpunkt (die URL genannt) definiert. Zur Laufzeit überprüft Journey Orchestration, ob eine Begrenzungsregel definiert ist, und wendet die definierte Rate während der Aufrufe auf diesen Endpunkt an. Wenn die Anzahl der Aufrufe die definierte Rate überschreitet, werden die verbleibenden Aufrufe verworfen und in der Berichterstellung als Fehler gezählt.

Eine Begrenzungsregel ist für einen Endpunkt spezifisch, aber global für alle Journey einer Sandbox. Dies bedeutet, dass Begrenzungsfenster für alle Journey einer Sandbox freigegeben werden.

Nehmen wir beispielsweise an, Sie haben eine Begrenzungsregel von 100 Aufrufen pro Sekunde für Ihr externes System definiert. Ihr System wird durch eine benutzerdefinierte Aktion in 10 verschiedenen Journey aufgerufen. Wenn eine Journey 200 Aufrufe pro Sekunde erhält, verwendet sie die 100 verfügbaren Slots und verwirft die 100 verbleibenden Slots. Da die Höchstrate überschritten wurde, werden die anderen 9 Journey keine Zeitnischen mehr haben. Diese Granularität trägt dazu bei, das externe System vor Überlastung und Abstürzen zu schützen.

Weitere Informationen zur Begrenzungs-API und zum Konfigurieren von Begrenzungsregeln finden Sie auf [dieser Seite](../api/capping.md).

## Zeitüberschreitung und Wiederholungen{#timeout}

Wenn die Begrenzungsregel erfüllt ist, wird die Timeout-Regel angewendet.

In jeder Journey können Sie eine Zeitüberschreitungsdauer festlegen. Auf diese Weise können Sie beim Aufruf eines externen Systems eine maximale Dauer festlegen. Die Zeitüberschreitungsdauer wird in den Eigenschaften einer Journey konfiguriert. Mehr dazu erfahren Sie auf [dieser Seite](../building-journeys/changing-properties.md#timeout_and_error).

Diese Zeitüberschreitung gilt für alle externen Aufrufe (externe API-Aufrufe in benutzerdefinierten Aktionen und benutzerdefinierten Datenquellen). Standardmäßig ist er auf 5 Sekunden eingestellt.

Während der definierten Timeout-Dauer versucht Journey Orchestration, das externe System aufzurufen. Nach dem ersten Aufruf können bis zum Ende der Timeout-Dauer maximal drei weitere Versuche durchgeführt werden. Die Anzahl weiterer Versuche kann nicht geändert werden.

Bei jedem erneuten Versuch wird ein Steckplatz verwendet. Wenn Sie eine Begrenzung von 100 Aufrufen pro Sekunde haben und jeder Ihrer Aufrufe zwei weitere Zustellversuche erfordert, sinkt die Rate auf 30 Aufrufe pro Sekunde (jeder Aufruf verwendet 3 Slots: den ersten Aufruf und zwei weitere Versuche).

Der Wert für die Zeitüberschreitungsdauer hängt vom Anwendungsfall ab. Wenn Sie Ihre Nachricht schnell senden möchten, z. B. wenn der Client den Store betritt, möchten Sie keine lange Zeitüberschreitung einrichten. Je länger die Zeitüberschreitung ist, desto mehr Elemente werden in die Warteschlange gestellt. Dies kann die Leistung erheblich beeinträchtigen. Wenn Journey Orchestration 1.000 Aufrufe pro Sekunde ausführt, kann das System durch die Beibehaltung von Daten in 5 oder 15 Sekunden schnell überlastet werden.

Nehmen wir ein Beispiel für eine Zeitüberschreitung von 5 Sekunden.

* Der erste Aufruf dauert weniger als 5 Sekunden: Wenn der Aufruf erfolgreich war, wird kein Neuversuch unternommen.
* Der erste Aufruf dauert länger als 5 Sekunden: wird der Aufruf abgebrochen und es wird kein Neuversuch unternommen. Er wird in Berichten als Zeitüberschreitungsfehler gezählt.
* Der erste Aufruf schlägt nach 2 Sekunden fehl (das externe System gibt einen Fehler zurück): 3 Sekunden bleiben für weitere Versuche, wenn Begrenzungsfenster verfügbar sind.
   * Wenn einer der drei weiteren Versuche vor Ablauf der 5 Sekunden erfolgreich war, wird der Aufruf durchgeführt und es wird kein Fehler ausgegeben.
   * Wenn das Ende der Timeout-Dauer während der Wiederholungen erreicht wird, wird der Aufruf abgebrochen und in den Berichten als Timeout-Fehler gezählt.

## Häufig gestellte Fragen{#faq}

**Wie kann ich eine Begrenzungsregel konfigurieren? Gibt es eine standardmäßige Begrenzungsregel?**

Standardmäßig gibt es keine Begrenzungsregel. Begrenzungsregeln werden auf Sandbox-Ebene für einen bestimmten Endpunkt (die URL genannt) mithilfe der Begrenzungs-API definiert. Weitere Informationen finden Sie in [diesem Abschnitt](../about/external-systems.md#capping) und [dieser Seite](../api/capping.md).

**Wie viele weitere Zustellversuche werden unternommen? Kann ich die Anzahl der weiteren Zustellversuche ändern oder eine minimale Wartezeit zwischen den Zustellversuchen definieren?**

Für einen gegebenen Aufruf können nach dem ersten Aufruf maximal drei weitere Versuche durchgeführt werden, bis das Ende der Timeout-Dauer erreicht ist. Die Anzahl weiterer Versuche und die Zeit zwischen den einzelnen Wiederholungen können nicht geändert werden. Weitere Informationen finden Sie in [diesem Abschnitt](../about/external-systems.md#timeout).

**Wo kann ich die Zeitüberschreitung konfigurieren? Gibt es einen Maximalwert?**

In jeder Journey können Sie eine Zeitüberschreitungsdauer festlegen. Die Zeitüberschreitungsdauer wird in den Eigenschaften einer Journey konfiguriert. Die Zeitüberschreitungsdauer muss zwischen 1 Sekunde und 30 Sekunden liegen. Weitere Informationen finden Sie in [diesem Abschnitt](../about/external-systems.md#timeout) und [dieser Seite](../building-journeys/changing-properties.md#timeout_and_error).