---
product: adobe campaign
title: Informationen zu Ereignisaktivitäten
description: Erfahren Sie mehr über Ereignisaktivitäten
feature: Journeys
role: User
level: Intermediate
exl-id: 3a4ff8b1-bbe7-47c8-9fba-defe4b1d5299
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '578'
ht-degree: 100%

---

# Informationen zu Ereignisaktivitäten {#concept_rws_1rt_52b}


>[!CAUTION]
>
>**Sie möchten mehr über Adobe Journey Optimizer erfahren**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um auf die Journey Optimizer-Dokumentation zuzugreifen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Accountteam, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._


Die vom technischen Anwender konfigurierten Ereignisse (siehe [diese Seite](../event/about-events.md)) werden alle in der ersten Kategorie der Palette auf der linken Seite des Bildschirms angezeigt.

![](../assets/journey43.png)

Beginnen Sie Ihre Journey immer mit Drag-and-Drop einer Ereignisaktivität. Sie können auf diese auch doppelklicken.

![](../assets/journey44.png)

Wenn Sie auf die Ereignisaktivität auf der Arbeitsfläche klicken, wird der Konfigurationsbereich für die Aktivität angezeigt. Wenn Sie dasselbe Ereignis mehrmals verwenden, wird dem Ereignisnamen auf der Arbeitsfläche standardmäßig eine fortlaufende Nummer hinzugefügt. Darüber hinaus können Sie mit dem Feld **[!UICONTROL Titel]** dem Ereignisnamen ein Suffix hinzufügen, das unter Ihrer Aktivität auf der Arbeitsfläche angezeigt wird. Dies ist nützlich, um Ihre Ereignisse auf der Arbeitsfläche zu identifizieren, insbesondere wenn Sie dasselbe Ereignis mehrmals verwenden. Außerdem wird die Problembehebung bei Fehlern und das Lesen von Berichten erleichtert.

![](../assets/journey33.png)

## Überwachen von Ereignissen während eines bestimmten {#listening}

Eine in der Journey positionierte Ereignisaktivität überwacht Ereignisse auf unbestimmte Zeit. Damit ein Ereignis nur während einer bestimmten Zeit überwacht wird, müssen Sie für das Ereignis eine maximale Wartezeit konfigurieren.

Die Journey überwacht dann das Ereignis während der in der maximalen Wartezeit angegebenen Zeit. Wenn ein Ereignis während dieses Zeitraums empfangen wird, wird die Person in den Ereignispfad geleitet. Andernfalls gelangt der Kunde bzw. die Kundin in den Pfad für die maximale Wartezeit, sofern er definiert ist, oder setzt die Journey fort. Wenn kein Pfad für die maximale Wartezeit definiert ist, fungiert die Einstellung für die maximale Wartezeit als Warteaktivität. Dadurch wartet das Profil für einen Zeitraum, der beendet werden kann, wenn ein Ereignis vor dem Ende dieser Wartezeit eintritt. Wenn Sie möchten, dass Profile nach einer maximalen Wartezeit von dieser Journey ausgeschlossen werden, müssen Sie einen Pfad für die maximale Wartezeit festlegen.

Gehen Sie wie folgt vor, um für ein Ereignis eine maximale Wartezeit zu konfigurieren:

1. Aktivieren Sie die Option **[!UICONTROL Zeitüberschreitung für das Ereignis definieren]** in den Eigenschaften des Ereignisses.

1. Legen Sie fest, wie lange die Journey auf das Ereignis warten soll.

1. Wenn Sie die Kontakte in einen Zeitüberschreitungspfad senden möchten, wenn innerhalb der angegebenen maximalen Wartezeit kein Ereignis empfangen wird, aktivieren Sie die Option **[!UICONTROL Pfad der Zeitüberschreitung festlegen]**. Wenn diese Option nicht aktiviert ist, wird die Journey für den betreffenden Kontakt fortgesetzt, sobald die maximale Wartezeit erreicht wird.

   ![](../assets/event-timeout.png)

In diesem Beispiel sendet die Journey einen ersten Willkommens-Push an einen Kunden. Es wird nur dann ein Essensrabatt-Push gesendet, wenn der Kunde das Restaurant innerhalb des nächsten Tages betritt. Deshalb wurde das Restaurantereignis mit einer maximalen Wartezeit von 1 Tag konfiguriert:

* Wenn das Restaurantereignis in weniger als 1 Tag nach der Begrüßungs-Push-Benachrichtigung eingeht, wird die Push-Aktivität für den Rabatt gesendet.
* Wenn innerhalb des nächsten Tages kein Restaurantereignis eingeht, wird die Person durch den Zeitüberschreitungspfad geleitet.

Wenn Sie eine maximale Wartezeit für mehrere Ereignisse konfigurieren möchten, die sich hinter einer **[!UICONTROL Warteaktivität]** befinden, müssen Sie die maximale Wartezeit nur für eines dieser Ereignisse konfigurieren.

Die maximale Wartezeit gilt für alle Ereignisse, die hinter der **[!UICONTROL Warteaktivität]** positioniert wurden. Wenn vor der angegebenen maximalen Wartezeit kein Ereignis empfangen wird, gelangen die Personen in einen einzigen Pfad für die maximale Wartezeit oder fahren mit der Journey über die Verzweigung fort, die die Aktivität verlässt, in der diese Einstellungen für die maximale Wartezeit definiert wurden.

![](../assets/event-timeout-group.png)
