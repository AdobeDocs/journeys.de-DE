---
title: Aktualisierungen der Dokumentation
description: Erfahren Sie mehr über die Aktualisierungen der Dokumentation
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
source-git-commit: 10d4fd57e9a801dab2310b2b511bf99cf1d9170a
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 94%

---


# Aktualisierungen der Dokumentation

Auf dieser Seite werden alle Aktualisierungen der Dokumentation für [!DNL Journey Orchestration] aufgelistet.
Lesen Sie auch die [!DNL Journey Orchestration]-[Versionshinweise](../release-notes/release-notes.md).

## August 2020 {#august-2020}

* Es wurden Informationen zum Sortieren und Auswählen der Spalten hinzugefügt, die in der Segmentspalten-Liste angezeigt werden sollen. [mehr dazu](../building-journeys/segment-qualification-events.md)
* Es wurden Informationen zum Kopieren des Segmentnamens und der Segmentkennung nach Auswahl hinzugefügt. [mehr dazu](../building-journeys/segment-qualification-events.md)
* Die Vorkommen von Experience Platformen wurden auf den verschiedenen Seiten harmonisiert.

## Juli 2020 {#july-2020}

* Es wurde ein Link zu einem neuen Anleitungsvideo für Schrittereignis-Berichte zu Adobe Experience Platform hinzugefügt. [Mehr dazu](../building-journeys/sharing-overview.md)
* Der Bereich „Ereignisaktivitäten“ wurde für jede Art von Ereignis in spezifische Unterbereiche umstrukturiert. [Mehr dazu](../building-journeys/event-activities.md)
* Es wurden Best Practices hinzugefügt, um eine Überlastung durch Segmentqualifikation zu vermeiden. [Mehr dazu](../building-journeys/segment-qualification-events.md#speed-segment-qualification)
* Es wurde ein Hinweis hinzugefügt, der erklärt, wie eine Journey nach einem Fehler in einer Aktion oder Bedingung fortgesetzt werden kann. [Mehr dazu](../about/troubleshooting.md#section_h3q_kqk_fhb)
* Es wurde ein neuer Abschnitt zu den Alpha-Funktionen hinzugefügt, die von einer begrenzten Anzahl von Kunden getestet werden. [Mehr dazu](../alpha/alpha-overview.md)
* Es wurde ein neuer Abschnitt zur Integration mit Intelligent Services hinzugefügt. [Mehr dazu](../ai-services/ai-services-overview.md)
* Es wurde ein neuer Abschnitt zur Erstellung von Testprofilen hinzugefügt. [Mehr dazu](../building-journeys/testing-the-journey.md#create-test-profile)
* Es wurden Informationen zur Verwendung des Knotens **[!UICONTROL SegmentQualification]** in einer Journey-Bedingung oder Aktion hinzugefügt. [Mehr dazu](../building-journeys/segment-qualification-events.md)
* In der Transaktionsnachricht und Ereignisveröffentlichung in Campaign wurde ein Hinweis hinzugefügt. Siehe [Arbeiten mit Adobe Campaign](../action/working-with-adobe-campaign.md) und [Verwenden von Adobe Campaign-Aktionen](../building-journeys/using-adobe-campaign-actions.md).
* Es wurden Informationen zu den Prüfungen hinzugefügt, die beim Testen der URL der Campaign Standard-Instanz durchgeführt werden. [Mehr dazu](../action/working-with-adobe-campaign.md)
* Es wurden Informationen zur Kompatibilität von Reaktionsereignissen mit den auf AWS- oder Azure-Servern gehosteten Campaign Standard-Instanzen hinzugefügt. [Mehr dazu](../building-journeys/reaction-events.md)
* Es wurde ein Hinweis hinzugefügt, dass eine Begrenzungsregel eingerichtet werden muss, wenn mit Transaktionsnachrichten von Campaign Standard gearbeitet wird. [Mehr dazu](../action/working-with-adobe-campaign.md)
* Es wurde ein Hinweis zur Generierung echter Ereignisse hinzugefügt, wenn Ereignisse im Testmodus ausgelöst werden. [Mehr dazu](../building-journeys/testing-the-journey.md#firing_events)

## Juni 2020{#june-2020}

* Es wurden Informationen darüber hinzugefügt, wie die Aufbewahrungsfrist im Cache des Tokens für eine benutzerdefinierte Authentifizierungsdatenquelle geändert werden kann. [mehr dazu](../datasource/external-data-sources.md#section_wjp_nl5_nhb)
* Screenshots und Text wurden aktualisiert, um der Umbenennung des Journey-Status **[!UICONTROL Beendet]** Rechnung zu tragen, der nun **[!UICONTROL Geschlossen (kein Eintritt)]** heißt.
* Es wurden Informationen zur Definition der Sprache der Benutzeroberfläche hinzugefügt. [mehr dazu](../about/user-interface.md)
* Die Liste der Status der Journey eines Kontakts wurde in den Bereich [Testmodusprotokolle](../building-journeys/testing-the-journey.md#viewing_logs) verschoben.

## April 2020 {#april-2020}

* Es wurde ein neuer Abschnitt zur Schemadefinition für Erlebnisereignisse hinzugefügt, der Benutzern bei der Konfiguration ihres ersten Ereignisses hilft. [mehr dazu](../event/experience-event-schema.md)
* Die Startseite für die [!DNL Journey Orchestration]-Dokumentation wurde um weitere nützliche Links ergänzt. [Mehr dazu](../../journey-orchestration-home.md)

## März 2020 {#march-2020}

* Parameterbeschreibungen für _actionExecutionErrors_ und _fetchErrors_ wurden im Abschnitt über Testprotokolle hinzugefügt – [mehr dazu](../building-journeys/testing-the-journey.md#viewing_logs)
* Die Beschränkungen für in Journeys verwendete benutzerdefinierte Aktionen wurden aktualisiert. Sie können auch das **[!UICONTROL URL-Feld]** und die **[!UICONTROL Authentifizierungsparameter]** ändern – [mehr dazu](../action/about-custom-action-configuration.md)
* Es wurden neue Einträge für die kontextuelle Hilfe hinzugefügt. Der Payload-Bereich für die benutzerdefinierte Authentifizierung (in Aktionen und Datenquellen) enthält jetzt ein Hilfesymbol, das auf diesen [Abschnitt](../datasource/external-data-sources.md#section_wjp_nl5_nhb) verweist.
* Geschlossene Journeys können jetzt gestoppt werden. [mehr dazu](../building-journeys/using-the-journey-designer.md)
* Der Abschnitt zur Beschreibung der Benutzeroberfläche wurde neu angeordnet. [mehr dazu](../about/user-interface.md)
* Die Auslösung mehrerer Ereignisse wurde dem Abschnitt „Testmodus“ hinzugefügt. [Mehr dazu](../building-journeys/testing-the-journey.md#firing_events)
* Der Abschnitt „Testmodus“ wurde hinsichtlich des neuen Parameters **[!UICONTROL Wartezeit im Test]** aktualisiert. [Mehr dazu](../building-journeys/testing-the-journey.md)
* Der Abschnitt „Testprotokoll“ wurde mit Fehlercodes und Antworten für externe Aufrufe aktualisiert. [Mehr dazu](../building-journeys/testing-the-journey.md#viewing_logs)
* Das Zeitzonen-Management ist jetzt gebündelt im Fenster der Journey-Eigenschaften verfügbar. Mehr dazu [hier](../building-journeys/changing-properties.md#timezone) und [hier](../building-journeys/timezone-management.md)
* Der Abschnitt „Journey-Designer“ wurde aktualisiert, um die jüngsten Verbesserungen widerzuspiegeln. [Mehr dazu](../building-journeys/using-the-journey-designer.md)
* Die Beschreibung der Benutzeroberfläche wurde mit Informationen zur Kontexthilfe aktualisiert. [Mehr dazu](../about/user-interface.md#section_ksq_zr1_ffb)
* Beim Durchsuchen von **XDM-Feldern** wird jetzt der Benutzername angezeigt. Die entsprechenden Abschnitte wurden aktualisiert. [Mehr dazu](../about/user-interface.md#friendly-names-display)

## Februar 2020 {#february-2020}

* Der Abschnitt mit den Tastaturbefehlen wurde aktualisiert. Mit dem Tastaturbefehl **C** können Sie in allen Listenbildschirmen ein neues Element erstellen. [Mehr dazu](../about/user-interface.md#section_ksq_zr1_ffb)
* Die Übersichtsseiten für [Datenquellen](../datasource/about-data-sources.md) und [Aktionen](../action/action.md) wurden verbessert.

## Januar 2020 {#january-2020}

* Für [Erlebnisereignisse](../datasource/adobe-experience-platform-data-source.md) und [Segmente](../functions/functioninsegment.md) wurden Abrufeinschränkungen hinzugefügt.

<!--* The [getBestSendTime documentation](../functions/functiongetbestsendtime.md) has been updated.-->

## Dezember 2019 {#december-2019}

* Alle Screenshots wurden entsprechend den Änderungen der Benutzeroberfläche aktualisiert.
* Der Abschnitt „Testmodus“ wurde aktualisiert. [Mehr dazu](../building-journeys/testing-the-journey.md)
<!--* A warning has been added in the [email send time optimization](../building-journeys/wait-activity.md) and [predictive fatigue scores](../ai-services/leveraging-fatigue-scores.md) sections. These capabilities are only available to customers who use the [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).-->
* Gestoppte Journeys können nun gelöscht werden. Die entsprechenden Seiten in der Dokumentation wurden aktualisiert.
* Wenn in einer Journey Probleme erkannt werden, werden nun zwei Farben angezeigt. Rot steht für Fehler und orange für Warnungen. [Mehr dazu](../about/troubleshooting.md)
* Der Abschnitt zum erweiterten Ausdruckseditor wurde aktualisiert. [Mehr dazu](../expression/expressionadvanced.md).
* Die Abschnitte [Bedingte Anweisung](../expression/conditional-instruction.md) und [Verwaltung von Sammlungen](../expression/collection-management-functions.md) wurden verschoben und aktualisiert.
* Der Abschnitt [Funktionen](../expression/functions.md) wurde um neue Beispiele ergänzt.
* Die Dokumentation für die Funktion [toDateTime](../functions/functiontodatetime.md) wurde aktualisiert, um Änderungen an der Zeitzonensyntax widerzuspiegeln.
