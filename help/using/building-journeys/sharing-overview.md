---
title: Übersicht über die Freigabe von Journey-Schritten
description: Übersicht über die Freigabe von Journey-Schritten
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
source-git-commit: b8cfc9de56e879d8812cf3871067252937454e1d
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 71%

---


# Übersicht über die Freigabe von Journey-Schritten{#sharing-overview}

[!DNL Journey Orchestration] sendet automatisch Daten zur Journey-Performance an Adobe Experience Platform, damit sie zu Analysezwecken mit anderen Daten kombiniert werden können.

Sie haben beispielsweise eine Journey eingerichtet, die mehrere E-Mails sendet. Mit dieser Funktion können Sie [!DNL Journey Orchestration]-Daten mit nachgelagerten Ereignisdaten kombinieren (z. B. der Anzahl der Konversionen, der Interaktionen auf der Website oder der Transaktionen im Store). Die Fahrteninformationen können mit Daten auf dem Adobe Experience Platform kombiniert werden, entweder von anderen digitalen Eigenschaften oder von Offline-Eigenschaften, um eine umfassendere Ansicht der Leistung zu ermöglichen.

[!DNL Journey Orchestration] erstellt automatisch die erforderlichen Schema und streamt die Daten in die Adobe Experience Platform für jeden Schritt, den ein Einzelner auf einer Reise unternimmt. Ein Schrittereignis entspricht einem Kontakt, die bei einer Journey von einem Knoten zu einem anderen wechselt. So werden bei einer Reise mit Ereignis, Bedingung und Aktion drei Ereignis an die Adobe Experience Platform gesendet.

Die Liste der weitergeleiteten XDM-Felder ist umfassend. Einige enthalten systemgenerierte Codes, andere haben lesbare Anzeigenamen. Beispiele sind die Bezeichnung der Journey-Aktivität und der Schrittstatus: wie oft eine Aktion die Zeit überschritten hat oder fehlerhaft endete.

>[!CAUTION]
>
>Für den Echtzeit-Profildienst können keine Datensätze aktiviert werden. Stellen Sie sicher, dass der Umschalter **[!UICONTROL Profil]** deaktiviert ist.

Journeys sendet Daten direkt im Streaming-Modus. Sie können diese Daten mit dem Query Service abfragen. Sie können eine Verbindung zu Customer Journey Analytics oder anderen BI-Tools herstellen, um Daten anzuzeigen, die mit diesen Schritten in Verbindung stehen.

Die folgenden Schemata werden erstellt:

* Journey Step Profile Event-Schema für [!DNL Journey Orchestration] – Erlebnisereignisse für Schritte, die in einer Journey unternommen werden, zusammen mit einer Identitätszuordnung, die der Zuordnung zu einem einzelnen Journey-Teilnehmer dient.
* Journey Step Event-Schema für [!DNL Journey Orchestration] – Journey-Schrittereignis, das mit Journey-Metadaten verknüpft ist.
* Journey-Schema mit Journey-Feldern für [!DNL Journey Orchestration] – Journey-Metadaten zur Beschreibung von Journeys.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

Die folgenden Datensätze werden übergeben:

* Journey Step Profile Event-Schema für [!DNL Journey Orchestration]
* Journey-Schrittereignisse
* Journeys

![](../assets/sharing3.png)

Die Listen der XDM-Felder, die an das Adobe Experience Platform übergeben werden, sind hier aufgeführt:

* [Gemeinsame Felder für journeyStep-Ereignisse](../building-journeys/sharing-common-fields.md)
* [Aktionsausführungsfelder für journeyStep-Ereignisse](../building-journeys/sharing-execution-fields.md)
* [Datenabruffelder für journeyStep-Ereignisse](../building-journeys/sharing-fetch-fields.md)
* [Identitätsfelder für journeyStep-Ereignisse](../building-journeys/sharing-identity-fields.md)
* [Journey-Felder](../building-journeys/sharing-journey-fields.md)

Weitere Informationen zum Berichte mit Step-Ereignisse in Adobe Experience Platform finden Sie in diesem [Lernvideo](https://docs.adobe.com/content/help/en/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html).
