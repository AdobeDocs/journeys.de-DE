---
product: adobe campaign
title: Übersicht über die Freigabe von Journey-Schritten
description: Übersicht über die Freigabe von Journey-Schritten
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '519'
ht-degree: 100%

---

# Übersicht über die Freigabe von Journey-Schritten{#sharing-overview}


>[!CAUTION]
>
>**Sie möchten mehr über Adobe Journey Optimizer erfahren**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um auf die Journey Optimizer-Dokumentation zuzugreifen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Accountteam, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._


[!DNL Journey Orchestration] sendet automatisch Journey-Performance-Daten an Adobe Experience Platform, damit sie zu Analysezwecken mit anderen Daten kombiniert werden können.

>[!NOTE]
>
>Diese Funktion ist standardmäßig auf allen Instanzen für Journey-Schrittereignisse aktiviert. Sie können die Schemata und Datensätze, die bei der Bereitstellung für Schrittereignisse erstellt wurden, nicht ändern oder aktualisieren. Standardmäßig sind diese Schemata und Datensätze schreibgeschützt.

Sie haben beispielsweise eine Journey eingerichtet, die mehrere E-Mails sendet. Mit dieser Funktion können Sie [!DNL Journey Orchestration]-Daten mit nachgelagerten Ereignisdaten kombinieren (z. B. der Anzahl der Konversionen, der Interaktionen auf der Website oder der Transaktionen im Store). Die Journey-Daten können entweder über andere digitale Eigenschaften oder über Offline-Eigenschaften mit Daten aus Adobe Experience Platform kombiniert werden, um eine genauere Ansicht der Performance zu ermöglichen.

[!DNL Journey Orchestration] erstellt für jeden Schritt, den ein Kontakt bei einer Journey unternimmt, automatisch die erforderlichen Schemata und streamt die Daten in Datensätze zu Adobe Experience Platform. Ein Schrittereignis entspricht einem Kontakt, der bei einer Journey von einem Knoten zu einem anderen wechselt. Beispielsweise werden bei einer Journey, die über ein Ereignis, eine Bedingung und eine Aktion verfügt, drei Schrittereignisse an Adobe Experience Platform gesendet.

Die Liste der weitergeleiteten XDM-Felder ist umfassend. Einige enthalten systemgenerierte Codes, andere haben lesbare Anzeigenamen. Beispiele sind die Bezeichnung der Journey-Aktivität und der Schrittstatus: wie oft eine Aktion die Zeit überschritten hat oder fehlerhaft endete.

>[!CAUTION]
>
>Für den Echtzeit-Profildienst können keine Datensätze aktiviert werden. Stellen Sie sicher, dass der Umschalter **[!UICONTROL Profil]** deaktiviert ist.

Journeys sendet Daten direkt im Streaming-Modus. Sie können diese Daten mit dem Query Service abfragen. Sie können eine Verbindung zu Customer Journey Analytics oder anderen BI-Tools herstellen, um Daten anzuzeigen, die mit diesen Schritten in Verbindung stehen.

Die folgenden Schemata werden erstellt:

* Journey Step Event-Schema für [!DNL Journey Orchestration] – Journey-Schrittereignis, das mit Journey-Metadaten verknüpft ist.
* Journey-Schema mit Journey-Feldern für [!DNL Journey Orchestration] – Journey-Metadaten zur Beschreibung von Journeys.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

Die folgenden Datensätze werden übergeben:

* Journey-Schrittereignisse
* Journeys

![](../assets/sharing3.png)

Die Listen der XDM-Felder, die an Adobe Experience Platform übergeben werden, werden hier beschrieben:

* [Liste für Schrittereignisfelder](../building-journeys/sharing-field-list.md)
* [Veraltete Felder für Step-Ereignisse](../building-journeys/sharing-legacy-fields.md)


## Integration mit Customer Journey Analytics{#integration-cja}

Schrittereignisse von Journey Orchestration können mit anderen Datensätzen in [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=de) verknüpft werden. So sieht der allgemeine Workflow aus:

* Customer Journey Analytics nimmt den Datensatz „Step-Ereignis der Journey“ auf.
* Das Feld **profileID** im zugehörigen „Step-Ereignisschema der Journey für Journey Orchestration“ wird als Identitätsfeld definiert. In Customer Journey Analytics können Sie diesen Datensatz dann mit jedem anderen Datensatz verknüpfen, der denselben Wert wie die personenbasierte Kennung hat.
* Wenn Sie diesen Datensatz in Customer Journey Analytics für eine kanalübergreifende Journey-Analyse verwenden möchten, lesen Sie diese [Dokumentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/cross-channel.html?lang=de).
