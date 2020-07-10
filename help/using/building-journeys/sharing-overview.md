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
source-git-commit: c4335cf1f94172fabed1099d3772bc539adb02ef
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 100%

---


# Übersicht über die Freigabe von Journey-Schritten{#sharing-overview}

[!DNL Journey Orchestration] sendet automatisch Daten zur Journey-Performance an Adobe Experience Platform, damit sie zu Analysezwecken mit anderen Daten kombiniert werden können.

Sie haben beispielsweise eine Journey eingerichtet, die mehrere E-Mails sendet. Mit dieser Funktion können Sie [!DNL Journey Orchestration]-Daten mit nachgelagerten Ereignisdaten kombinieren (z. B. der Anzahl der Konversionen, der Interaktionen auf der Website oder der Transaktionen im Store). Die Journey-Daten können mit Daten aus Platform kombiniert werden, entweder über andere digitale Eigenschaften oder über Offline-Eigenschaften, um eine genauere Ansicht der Leistung zu ermöglichen.

[!DNL Journey Orchestration] erstellt für jeden Schritt, den ein Kontakt bei einer Journey unternimmt, automatisch die erforderlichen Schemata und streamt die Daten in Datensätze zu Platform. Ein Schrittereignis entspricht einem Kontakt, die bei einer Journey von einem Knoten zu einem anderen wechselt. Beispielsweise werden bei einer Journey, die über ein Ereignis, eine Bedingung und eine Aktion verfügt, drei Schrittereignisse an Platform gesendet.

Die Liste der weitergeleiteten XDM-Felder ist umfassend. Einige enthalten systemgenerierte Codes, andere haben lesbare Anzeigenamen. Beispiele sind die Bezeichnung der Journey-Aktivität und der Schrittstatus: wie oft eine Aktion die Zeit überschritten hat oder fehlerhaft endete.

>[!CAUTION]
>
>Für den Echtzeit-Profildienst können keine Datensätze aktiviert werden. Stellen Sie sicher, dass der Umschalter **Profil** deaktiviert ist.

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

Die Listen der XDM-Felder, die an Platform übergeben werden, werden hier beschrieben:

* [Gemeinsame Felder für journeyStep-Ereignisse](../building-journeys/sharing-common-fields.md)
* [Aktionsausführungsfelder für journeyStep-Ereignisse](../building-journeys/sharing-execution-fields.md)
* [Datenabruffelder für journeyStep-Ereignisse](../building-journeys/sharing-fetch-fields.md)
* [Identitätsfelder für journeyStep-Ereignisse](../building-journeys/sharing-identity-fields.md)
* [Journey-Felder](../building-journeys/sharing-journey-fields.md)

