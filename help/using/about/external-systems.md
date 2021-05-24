---
product: adobe campaign
solution: Journey Orchestration
title: Integration mit externen Systemen
description: Best Practices bei der Integration externer Systeme
feature: Journeys
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: a25ff95e0b74d3a0693310179670c7fe7b0de51c
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---

# Integration mit externen Systemen {#external-systems}

Auf dieser Seite finden Sie die verschiedenen Limits, die die Journey Orchestration bei der Integration eines externen Systems bietet, sowie Best Practices: wie Sie den Schutz Ihres externen Systems mit der Begrenzungs-API optimieren können, wie Journey-Timeout konfiguriert wird und wie Neuversuche funktionieren.

Mit Journey Orchestration können Sie Verbindungen zu externen Systemen über benutzerdefinierte Datenquellen und benutzerdefinierte Aktionen konfigurieren. Auf diese Weise können Sie beispielsweise Ihre Journey mit Daten aus einem externen Reservierungssystem anreichern oder Nachrichten mit Drittanbietersystemen wie Epsilon oder Facebook versenden.

Bei der Integration eines externen Systems können mehrere Probleme auftreten, das System kann langsam sein, nicht mehr reagieren oder es kann möglicherweise nicht in der Lage sein, große Mengen zu verarbeiten. Journey Orchestration bietet verschiedene Schutzmechanismen, um Ihr System vor Überlastung zu schützen.

Alle externen Systeme unterscheiden sich hinsichtlich der Leistung. Sie müssen die Konfiguration an jeden Anwendungsfall anpassen.

Wenn Journey Orchestration einen Aufruf an eine externe API ausführt, werden die technischen Limits wie folgt ausgeführt:

1. Begrenzung: Begrenzungsregeln angewendet
2. Zeitüberschreitung und erneuter Versuch:

## Obergrenze

Die integrierte Capping-API bietet eine vorgelagerte technische Limits, die zum Schutz Ihres externen Systems beitragen. Zuvor müssen Sie die Kapazität Ihrer externen API evaluieren. Wenn beispielsweise Journey Orchestration 1.000 Aufrufe pro Sekunde sendet und Ihr System nur 100 Aufrufe pro Sekunde unterstützen kann, müssen Sie eine Begrenzungsregel definieren, damit Ihr System nicht überfordert wird.

Begrenzungsregeln werden auf Sandbox-Ebene für einen bestimmten Endpunkt (URL genannt) definiert. Zur Laufzeit überprüft Journey Orchestration, ob eine Begrenzungsregel definiert ist, und wendet die definierte Rate während der Aufrufe auf diesen Endpunkt an. Wenn die Anzahl der Aufrufe die definierte Rate überschreitet, werden die verbleibenden Aufrufe verworfen.

Eine Begrenzungsregel ist für einen Endpunkt spezifisch, aber global für alle Journey einer Sandbox. Das bedeutet, dass Aufruffenster für alle Journey einer Sandbox freigegeben werden. Nehmen wir beispielsweise an, dass Ihr externes System über eine definierte Begrenzung von 100 Aufrufen pro Sekunde verfügt und durch eine benutzerdefinierte Aktion in 10 verschiedenen Journey aufgerufen wird. Wenn eine Journey 200 Aufrufe pro Sekunde erhält, bleiben die 100 Slots verfügbar und die 100 verbleibenden Slots werden verworfen. Da die Höchstrate bereits überschritten ist, werden die anderen 9 Journey keine Steckplätze zur Verfügung stehen. Diese Granularität trägt dazu bei, das externe System vor Überlastung und Abstürzen zu schützen.

Ein Aufruf, der aufgrund von Begrenzungen verworfen wurde, wird bei der Berichterstellung als Fehler gezählt.

Informationen zum Konfigurieren von Begrenzungsregeln finden Sie auf [dieser Seite](../api/timezone-management.md).

## Zeitüberschreitung und Wiederholungen

Ensuite -> Zeitüberschreitungsdefinition, et qui definir le temps maximum qu&#39;on aloue a lappel au sys. Pendant ce temps là, on essaie de faire des appels. Auf der fait un appel, si l&#39;appel dure moinre longtemps que le timeout ca marche, si plus longtemps on voit kann eine Zeitüberschreitungsfehler kommen, und coté Reporting compabilisé comme une erreur. si l&#39;appel echoue, (planter sur 500 ou autre), Wiederholen. 3 Wiederholungsmax, kann konfiguriert werden. SI kann die Zeitüberschreitung global (z. B. 2 Essais, mais depasse le timeout) überschreiten. plsu de temps que notwendigen. Timeout durée max qu&#39;on lassen eine Apfel und aux Wiederholungen sind erreurs.

