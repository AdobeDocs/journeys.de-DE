---
product: adobe campaign
solution: Journey Orchestration
title: Reiseeigenschaften
description: Informationen zu Reiseeigenschaften
translation-type: tm+mt
source-git-commit: 1fd02fcc2a535046cfbcdb5d1c52850ee93370af
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---


# Journey properties {#journey-properties}

Im erweiterten Ausdruck-Editor finden Sie die Kategorie **Reiseeigenschaften** unter den Kategorien Ereignis und Datenquelle. Diese Kategorie enthält technische Bereiche, die sich auf die Reise eines bestimmten Profils beziehen. Dies sind die Informationen, die das System von Live-Reisen abruft, wie z. B. die Reise-ID oder die spezifischen aufgetretenen Fehler.

![](../assets/journey-properties.png)

Sie finden hier beispielsweise Informationen zu folgenden Themen:

* Reiseversion: Reise-UID, Reiseversion-UID, Instanz-UID usw.
* Fehler: Datenabruf, Aktionsausführung usw.
* aktueller Schritt, letzter aktueller Schritt usw.
* verworfene Profil

Sie können diese Felder zum Aufbau von Ausdrücken verwenden. Während der Ausführung der Reise werden die Werte direkt von der Reise abgerufen.

Im Folgenden finden Sie einige Beispiele für Verwendungsfälle:

* **Verworfene Profil**: Sie können alle Profil, die von einer Nachricht ausgeschlossen sind, mit einer Sperrregel zu Protokollierungszwecken an ein Drittanbietersystem senden. Dazu richten Sie im Fall von Timeout und Fehler einen Pfad ein und fügen eine Bedingung hinzu, um nach einem bestimmten Fehlertyp zu filtern, z. B.: &quot;Verwerfen von Personen durch Deckelung der Regel&quot;. Anschließend können Sie die verworfenen Profil über eine benutzerdefinierte Aktion an ein Drittanbietersystem senden.

* **Gesendete Push-Benachrichtigungen bei Fehlern**: Sie können eine Benachrichtigung an ein Drittanbietersystem senden, sobald ein Fehler in einer Nachricht auftritt. Dazu richten Sie im Fehlerfall einen Pfad ein, fügen eine Bedingung und eine benutzerdefinierte Aktion hinzu. Sie können beispielsweise eine Benachrichtigung an einen Slack-Kanal mit der Fehlerbeschreibung senden.

* **Fehler in Berichte** verfeinern: Statt nur einen Pfad für Fehlermeldungen zu haben, können Sie eine Bedingung pro Fehlertyp definieren. Auf diese Weise können Sie den Berichte und die Ansicht aller Fehlertypen verfeinern.

## Feldliste {#journey-properties-fields}

|Kategorie|Feldname|Bezeichnung|Beschreibung|
|-|-|-|—|
|Version der Reise|Reise-UID|Reisekennung| |
| |travelVersionUID|Journey-Versionskennung| |
| |travelVersionName|Versionsname der Reiseversion| |
| |travelVersionDescription|Journey-Version-Beschreibung| |
| |travelVersion|Journey-Version| |
|Journey Instance|instanceUID|Kennung der Reiseinstanz|ID der Instanz|
| |externalKey|External Key|Individuelle Kennung, die die Reise auslöst|
|Identity|profileId|Profil Identifier|Bezeichner des Profils auf der Reise|
| |Namensraum|Profil Identity Namensraum|Namensraum des Profils auf der Reise (Beispiel: ECID)|
|Current Node|currentNodeId|Current Node Identifier|Identifier der aktuellen Aktivität (Node)|
| |currentNodeName|Current Node Name|Name der aktuellen Aktivität (node)|
|Previous Node|previousNodeId|Previous Node Identifier|Identifier der vorherigen Aktivität (Node)|
| |previousNodeName|Previous Node Name|Name der vorherigen Aktivität (node)|
|Fehler|lastNodeUIDInError|Letzte Node-ID in Error|Bezeichner der neuesten Aktivität (Node) in error|
| |lastNodeNameInError|Last Node Name in Error|Name der neuesten Aktivität (Node) in error|
| |lastNodeTypeInError|Last Node Type in Error|Error type of the last Aktivität (node) in error. Mögliche Typen:<ul><li>Ereignisse: Ereignis, Reaktionen, SQ (Beispiel: Segmentqualifikation)</li><li>Flusssteuerung: Ende, Bedingung, warten</li><li>Aktionen: ACS-Aktionen, Sprung, benutzerdefinierte Aktion</li></ul>|
| |lastErrorCode|Letzter Fehlercode|Fehlercode der neuesten Aktivität (Node) in error. Mögliche Fehler: <ul><li>HTTP-Fehlercodes</li><li>gezählt</li><li>timedOut</li><li>error (Beispiel: Standard bei unerwartetem Fehler. Sollte nicht/extrem selten vorkommen)</li></ul>|
| |lastExecuteActionErrorCode|Letzter Aktionsfehlercode der ausgeführten Aktion|Fehlercode der letzten Aktion in Fehler |
| |lastDataFetchErrorCode|Last Data Fetch Error Code|Fehlercode des neuesten Datenabrufs aus Datenquellen|
|Time|lastActionExecutionElapsedTime|Die letzte Aktionsausführungszeit ist abgelaufen|Die Zeit, die zum Ausführen der letzten Aktion verbracht wurde|
| |lastDataFetchElapsedTime|Letzter Datenabruf abgelaufen|Zeit, die zum Ausführen des neuesten Datenabrufs aus Datenquellen verbracht wurde|
