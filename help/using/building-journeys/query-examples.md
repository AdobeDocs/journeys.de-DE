---
title: Beispiele für Abfragen
description: Beispiele für Abfragen
topic: Content Management
role: User
level: Intermediate
exl-id: 07d25f8e-0065-4410-9895-ffa15d6447bb
source-git-commit: e758d4430bb28c109633c96e330b56ad08a61c02
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 2%

---

# Beispiele für Abfragen{#query-examples}

In diesem Abschnitt finden Sie einige häufig verwendete Beispiele für die Abfrage von Journey Step Events im Data Lake.

## Nachrichten-/Aktionsfehler

### Liste aller in Journey aufgetretenen Fehler

Mithilfe dieser Abfrage können Sie jeden in Journey aufgetretenen Fehler beim Ausführen einer Nachricht/Aktion auflisten.

_Data Lake-Abfrage_

```
SELECT _experience.journeyOrchestration.stepEvents.actionExecutionError, count(distinct _id) FROM journey_step_events
WHERE _experience.journeyOrchestration.stepEvents.nodeName=<'message-name'>
AND _experience.journeyOrchestration.stepEvents.actionExecutionError IS NOT NULL
AND _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>'
GROUP BY _experience.journeyOrchestration.stepEvents.actionExecutionError
```

_Beispiel_

```
SELECT _experience.journeyOrchestration.stepEvents.actionExecutionError, count(distinct _id) FROM journey_step_events
WHERE _experience.journeyOrchestration.stepEvents.nodeName='Message - 100KB Email with Gateway and Kafkav2'
AND _experience.journeyOrchestration.stepEvents.actionExecutionError IS NOT NULL
AND _experience.journeyOrchestration.stepEvents.journeyVersionID = '67b14482-143e-4f83-9cf5-cfec0fca3d26'
GROUP BY _experience.journeyOrchestration.stepEvents.actionExecutionError
```

Diese Abfrage gibt alle verschiedenen Fehler zurück, die beim Ausführen einer Journey aufgetreten sind, zusammen mit der Anzahl der aufgetretenen Fehler.

## Profilbasierte Abfragen

### Finden Sie heraus, ob ein Profil eine bestimmte Journey eingegeben hat.

_Data Lake-Abfrage_

```
SELECT count(distinct _id) FROM journey_step_events
where
_experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>' AND
_experience.journeyOrchestration.stepEvents.profileID = '<profileID corresponding to the namespace used>'
```

_Beispiel_

```
SELECT count(distinct _id) FROM journey_step_events
where
_experience.journeyOrchestration.stepEvents.journeyVersionID = 'ec9efdd0-8a7c-4d7a-a765-b2cad659fa4e' AND
_experience.journeyOrchestration.stepEvents.profileID = 'saurgarg@adobe.com'
```

Das Ergebnis sollte größer als 0 sein. Diese Abfrage gibt die genaue Anzahl der Eingaben eines Profils in eine Journey zurück.

### Ermitteln, ob ein Profil eine bestimmte Nachricht gesendet wurde

**Methode 1:** , wenn der Name Ihrer Nachricht in der Journey nicht eindeutig ist (er wird an mehreren Stellen verwendet).

_Data Lake-Abfrage_

```
SELECT count(distinct _id) FROM journey_step_events WHERE
_experience.journeyOrchestration.stepEvents.nodeID='<NodeId in the UI corresponding to the message>' AND
_experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
_experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>' AND
_experience.journeyOrchestration.stepEvents.profileID = '<profileID corresponding to the namespace used>'
```

_Beispiel_

```
SELECT count(distinct _id) FROM journey_step_events WHERE
_experience.journeyOrchestration.stepEvents.nodeID='17ae65a1-02dd-439d-b54e-b56a78520eba' AND
_experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
_experience.journeyOrchestration.stepEvents.journeyVersionID = '67b14482-143e-4f83-9cf5-cfec0fca3d26' AND
_experience.journeyOrchestration.stepEvents.profileID = 'saurgarg@adobe.com'
```

Das Ergebnis sollte größer als 0 sein. Diese Abfrage zeigt nur an, ob die Nachrichtenaktion auf der Journey-Seite erfolgreich ausgeführt wurde.

**Methode 2:** , wenn der Name Ihrer Nachricht in der Journey eindeutig ist.

_Data Lake-Abfrage_

```
SELECT count(distinct _id) FROM journey_step_events WHERE
_experience.journeyOrchestration.stepEvents.nodeName='<NodeName in the UI corresponding to the message>' AND
_experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
_experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>' AND
_experience.journeyOrchestration.stepEvents.profileID = '<profileID corresponding to the namespace used>'
```

_Beispiel_

```
SELECT count(distinct _id) FROM journey_step_events WHERE
_experience.journeyOrchestration.stepEvents.nodeID='Message- 100KB Email' AND
_experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
_experience.journeyOrchestration.stepEvents.journeyVersionID = '67b14482-143e-4f83-9cf5-cfec0fca3d26' AND
_experience.journeyOrchestration.stepEvents.profileID = 'saurgarg@adobe.com'
```

Die Abfrage gibt die Liste aller Nachrichten zusammen mit der Anzahl der für das ausgewählte Profil aufgerufenen Nachrichten zurück.

## Suchen Sie alle Nachrichten, die ein Profil in den letzten 30 Tagen erhalten hat.

_Data Lake-Abfrage_

```
SELECT _experience.journeyOrchestration.stepEvents.nodeName, count(distinct _id) FROM journey_step_events
WHERE  _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
_experience.journeyOrchestration.stepEvents.nodeType = 'action' AND
_experience.journeyOrchestration.stepEvents.profileID = '<profileID corresponding to the namespace used>' AND
timestamp > (now() - interval '30' day)
GROUP BY _experience.journeyOrchestration.stepEvents.nodeName
```

_Beispiel_

```
SELECT _experience.journeyOrchestration.stepEvents.nodeName, count(distinct _id) FROM journey_step_events
WHERE  _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
_experience.journeyOrchestration.stepEvents.nodeType = 'action' AND
_experience.journeyOrchestration.stepEvents.profileID = 'saurgarg@adobe.com' AND
timestamp > (now() - interval '30' day)
GROUP BY _experience.journeyOrchestration.stepEvents.nodeName
```

Die Abfrage gibt die Liste aller Nachrichten zusammen mit der Anzahl der für das ausgewählte Profil aufgerufenen Nachrichten zurück.

### Suchen Sie alle Journey, die in den letzten 30 Tagen ein Profil eingegeben hat.

_Data Lake-Abfrage_

```
SELECT _experience.journeyOrchestration.stepEvents.journeyVersionName, count(distinct _id) FROM journey_step_events
WHERE  _experience.journeyOrchestration.stepEvents.nodeType = 'start' AND
_experience.journeyOrchestration.stepEvents.profileID = '<profileID corresponding to the namespace used>' AND
timestamp > (now() - interval '30' day)
GROUP BY _experience.journeyOrchestration.stepEvents.journeyVersionName
```

_Beispiel_

```
SELECT _experience.journeyOrchestration.stepEvents.journeyVersionName, count(distinct _id) FROM journey_step_events
WHERE  _experience.journeyOrchestration.stepEvents.nodeType = 'start' AND
_experience.journeyOrchestration.stepEvents.profileID = 'saurgarg@adobe.com' AND
timestamp > (now() - interval '30' day)
GROUP BY _experience.journeyOrchestration.stepEvents.journeyVersionName
```

Die Abfrage gibt die Liste aller Journey-Namen sowie die Anzahl der Eingaben des abgefragten Profils in die Journey zurück.

### Anzahl der Profile, die sich für eine Journey täglich qualifiziert haben

_Data Lake-Abfrage_

```
SELECT DATE(timestamp), count(distinct _experience.journeyOrchestration.stepEvents.profileID) FROM journey_step_events
WHERE DATE(timestamp) > (now() - interval '<last x days>' day)
AND _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>'
GROUP BY DATE(timestamp)
ORDER BY DATE(timestamp) desc
```

_Beispiel_

```
SELECT DATE(timestamp), count(distinct _experience.journeyOrchestration.stepEvents.profileID) FROM journey_step_events
WHERE DATE(timestamp) > (now() - interval '100' day)
AND _experience.journeyOrchestration.stepEvents.journeyVersionID = '180ad071-d42d-42bb-8724-2a6ff0a109f1'
GROUP BY DATE(timestamp)
ORDER BY DATE(timestamp) desc
```

Die Abfrage gibt für den definierten Zeitraum die Anzahl der Profile zurück, die täglich in die Journey eingestiegen sind. Wenn ein Profil über mehrere Identitäten eingegeben wird, wird es zweimal gezählt. Wenn der erneute Eintritt aktiviert ist, kann die Anzahl der Profile über verschiedene Tage hinweg dupliziert werden, wenn sie an einem anderen Tag erneut in die Journey eingegeben wird.

## Journey-basierte Abfragen

### Anzahl der aktiven Journey täglich

_Data Lake-Abfrage_

```
SELECT DATE(timestamp), count(distinct _experience.journeyOrchestration.stepEvents.journeyVersionID) FROM journey_step_events
WHERE DATE(timestamp) > (now() - interval '<last x days>' day)
GROUP BY DATE(timestamp)
ORDER BY DATE(timestamp) desc
```

_Beispiel_

```
SELECT DATE(timestamp), count(distinct _experience.journeyOrchestration.stepEvents.journeyVersionID) FROM journey_step_events
WHERE DATE(timestamp) > (now() - interval '100' day)
GROUP BY DATE(timestamp)
ORDER BY DATE(timestamp) desc
```

Die Abfrage gibt für den definierten Zeitraum die Anzahl der eindeutigen Journey zurück, die jeden Tag ausgelöst werden. Eine einzelne Journey, die mehrere Tage lang ausgelöst wird, wird einmal pro Tag gezählt.