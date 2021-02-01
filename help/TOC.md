---
product: adobe campaign
solution: Journey Orchestration
user-guide-title: Journey Orchestration
title: Handbuch zur Journey Orchestration
user-guide-description: Enthält Anleitungen zum Implementieren und Erstellen von Journeys.
index: true
translation-type: tm+mt
source-git-commit: c18670b32e0e56cf5621fde965b19aa24da8045b
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 100%

---


# Handbuch zur [!DNL Journey Orchestration] {#using}

+ [Produktdokumentation](journey-orchestration-home.md)
+ Neue Funktionen {#release-notes}
   + [Versionshinweise](using/release-notes/release-notes.md)
   + [Aktualisierungen der Dokumentation](using/release-notes/documentation-updates.md)
+ Einstieg in [!DNL Journey Orchestration] {#starting-with-journeys}
   + [Versionsinformationen [!DNL Journey Orchestration]](using/about/about-journey-orchestration.md)
   + [Einschränkungen](using/about/limitations.md)
   + [Erste Schritte](using/about/get-started.md)
   + [Benutzeroberfläche](using/about/user-interface.md)
   + [Zugriffsverwaltung](using/about/access-management.md)
   + [Fehlerbehebung](using/about/troubleshooting.md)
+ Konfigurieren eines Ereignisses {#events-journeys}
   + Informationen zu Ereignissen {#about-events}
      + [Allgemeine Funktionsweise](using/event/about-events.md)
      + [Datenzyklus](using/event/about-data-cycle.md)
      + [Ereignis erstellen](using/event/about-creating.md)
      + [Nutzung von Adobe Analytics](using/event/about-analytics.md)
      + [Informationen zu ExperienceEvent-Schemata](using/event/experience-event-schema.md)
      + [Zusätzliche Schritte zum Senden von Ereignissen](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
   + [Definieren der Payload-Felder](using/event/defining-the-payload-fields.md)
   + [Auswählen des Namespace](using/event/selecting-the-namespace.md)
   + [Definieren des Ereignisschlüssels](using/event/defining-the-event-key.md)
   + [Hinzufügen einer Bedingung](using/event/adding-a-condition.md)
   + [Anzeigen der Payload-Vorschau](using/event/previewing-the-payload.md)
+ Konfigurieren der Datenquelle {#data-source-journeys}
   + [Informationen zu Datenquellen](using/datasource/about-data-sources.md)
   + [Feldergruppen](using/datasource/field-groups.md)
   + [Datenquelle von Adobe Experience Platform](using/datasource/adobe-experience-platform-data-source.md)
   + [Externe Datenquellen](using/datasource/external-data-sources.md)
+ Konfigurieren einer Aktion {#action-journeys}
   + [Informationen zu Aktionen](using/action/action.md)
   + [Arbeiten mit Adobe Campaign](using/action/working-with-adobe-campaign.md)
   + Verwenden eines Drittanbietersystems {#action-third-party}
      + [Informationen zur Konfiguration einer benutzerdefinierten Aktion](using/action/about-custom-action-configuration.md)
      + [URL-Konfiguration](using/action/url-configuration.md)
      + [Definieren der Nachrichtenparameter](using/action/defining-the-message-parameters.md)
+ Verwenden von Platform-Segmenten {#configuring-segment}
   + [Informationen zu Platform-Segmenten](using/segment/about-segments.md)
   + [Erstellen eines Segments](using/segment/creating-a-segment.md)
   + [Verwenden von Segmenten in Bedingungen](using/segment/using-a-segment.md)
+ Erstellen der Journey {#building-journeys}
   + Informationen zum Erstellen von Journeys {#about-journey-building}
      + [Erstellen einer Journey ](using/building-journeys/journey.md)
      + [Verwenden des Journey-Designers](using/building-journeys/using-the-journey-designer.md)
      + [Ändern von Eigenschaften](using/building-journeys/changing-properties.md)
      + [Journey-Versionen](using/building-journeys/journey-versions.md)
      + [Abbrechen einer Journey](using/building-journeys/terminating-a-journey.md)
      + [Zeitzonen-Management](using/building-journeys/timezone-management.md)
   + Aktivitäten {#about-journey-building}
      + Ereignisaktivitäten {#events-activities}
         + [Über Ereignisaktivitäten](using/building-journeys/event-activities.md)
         + [Allgemeine Ereignisse](using/building-journeys/general-events.md)
         + [Reaktionsereignisse](using/building-journeys/reaction-events.md)
         + [Segmentqualifizierungsereignisse](using/building-journeys/segment-qualification-events.md)
      + Orchestrierungsaktivitäten {#orchestration-activities}
         + [Informationen zu Orchestrierungsaktivitäten](using/building-journeys/about-orchestration-activities.md)
         + [Bedingungsaktivität](using/building-journeys/condition-activity.md)
         + [Endaktivität](using/building-journeys/end-activity.md)
         + [Warteaktivität](using/building-journeys/wait-activity.md)
      + Aktionsaktivitäten {#action-activities}
         + [Informationen zu Aktionsaktivitäten](using/building-journeys/about-action-activities.md)
         + [Verwenden von Adobe Campaign-Aktionen](using/building-journeys/using-adobe-campaign-actions.md)
         + [Verwenden benutzerdefinierter Aktionen](using/building-journeys/using-custom-actions.md)
         + [Springen zwischen Journeys](using/building-journeys/jump.md)
   + [Testen der Journey](using/building-journeys/testing-the-journey.md)
   + [Veröffentlichen der Journey](using/building-journeys/publishing-the-journey.md)
   + Freigabe von Journey-Schritten mit Adobe Experience Platform {#sharing-journey-steps}
      + [Übersicht über die Freigabe von Journey-Schritten](using/building-journeys/sharing-overview.md)
      + [Gemeinsame Felder für journeyStep-Ereignisse](using/building-journeys/sharing-common-fields.md)
      + [Aktionsausführungsfelder für journeyStep-Ereignisse](using/building-journeys/sharing-execution-fields.md)
      + [Datenabruffelder für journeyStep-Ereignisse](using/building-journeys/sharing-fetch-fields.md)
      + [Identitätsfelder für journeyStep-Ereignisse](using/building-journeys/sharing-identity-fields.md)
      + [Journey-Felder](using/building-journeys/sharing-journey-fields.md)
+ Verwenden des erweiterten Ausdruckseditors {#building-advanced-conditions-journeys}
   + [Informationen zum erweiterten Ausdruckseditor](using/expression/expressionadvanced.md)
   + Syntax {#syntax}
      + [Allgemeines](using/expression/generalities.md)
      + [Bedingte Anweisung](using/expression/conditional-instruction.md)
      + [Datentypen](using/expression/data-types.md)
      + [Feldverweise](using/expression/field-references.md)
      + [Funktionen zur Verwaltung von Sammlungen](using/expression/collection-management-functions.md)
      + [Operatoren](using/expression/operators.md)
      + [Journey-Eigenschaften](using/expression/journey-properties.md)
      + [Beispiele](using/expression/advanced-editor-use-cases.md)
   + Funktionen {#main-functions-journey}
      + [Hauptfunktionen](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [inSegment](using/functions/functioninsegment.md)
      + Aggregation {#aggregation}
         + [avg](using/functions/functionavg.md)
         + [count](using/functions/functioncount.md)
         + [countOnlyNull](using/functions/functioncountonlynull.md)
         + [countWithNull](using/functions/functioncountwithnull.md)
         + [distinctCount](using/functions/functiondistinctcount.md)
         + [distinctCountWithNull](using/functions/functiondistinctcountwithnull.md)
         + [max](using/functions/functionmax.md)
         + [min](using/functions/functionmin.md)
         + [sum](using/functions/functionsum.md)
      + Konversion {#conversion}
         + [toBool](using/functions/functiontobool.md)
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + Datum {#date}
         + [currentTime&#x200B;InMillis](using/functions/functioncurrenttimeinmillis.md)
         + [inLastDays](using/functions/functioninlastdays.md)
         + [inLastHours](using/functions/functioninlasthours.md)
         + [inLastMonths](using/functions/functioninlastmonths.md)
         + [inLastYears](using/functions/functioninlastyears.md)
         + [inNextDays](using/functions/functioninnextdays.md)
         + [inNextHours](using/functions/functioninnexthours.md)
         + [inNextMonths](using/functions/functioninnextmonths.md)
         + [inNextYears](using/functions/functioninnextyears.md)
         + [now](using/functions/functionnow.md)
         + [nowWithDelta](using/functions/functionnowwithdelta.md)
         + [setHours](using/functions/functionsethours.md)
         + [setDays](using/functions/functionsetdays.md)
      + Liste {#list}
         + [distinct](using/functions/functiondistinct.md)
         + [distinctWithNull](using/functions/functiondistinctwithnull.md)
         + [getListItem](using/functions/functiongetlistitem.md)
         + [in](using/functions/functionin.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [sort](using/functions/functionsort.md)
      + Mathematisch {#math}
         + [random](using/functions/functionrandom.md)
         + [round](using/functions/functionround.md)
      + Zeichenfolge {#string}
         + [concat](using/functions/functionconcat.md)
         + [contain](using/functions/functioncontain.md)
         + [containWithIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [equalWithIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [length](using/functions/functionlength.md)
         + [lower](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notEqualWithIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [replace](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [split](using/functions/functionsplit.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [substr](using/functions/functionsubstr.md)
         + [trim](using/functions/functiontrim.md)
         + [upper](using/functions/functionupper.md)
         + [uuid](using/functions/functionuuid.md)
+ Erstellen von Berichten{#journey-reports}
   + [Informationen zu Journey-Berichten](using/reporting/about-journey-reports.md)
   + [Erstellen von Journey-Berichten](using/reporting/creating-your-journey-reports.md)
   + [Metriken und Dimensionen](using/reporting/metrics-and-dimensions.md)
+ Integrieren mit Intelligent Services{#use-case-advanced}
   + [Informationen zur KI-Integration](using/ai-services/ai-services-overview.md)
   + [Verwenden von Kunden-KI-Werten](using/ai-services/leveraging-customer-ai.md)
+ Anwendungsbeispiele{#use-cases-journeys}
   + Senden einer personalisierten E-Mail{#use-case-simple}
      + [Informationen zum einfachen Anwendungsfall](using/usecase/about-the-simple-use-case.md)
      + [Konfigurieren des Ereignisses](using/usecase/configuring-the-event.md)
      + [Konfigurieren der Datenquelle](using/usecase/configuring-the-data-source.md)
      + [Erstellen der Journey](using/usecase/simple-uc-building-the-journey.md)
   + Erstellen einer Cross-Channel-Journey{#use-case-advanced}
      + [Informationen zum erweiterten Anwendungsfall](using/usecase/about-the-advanced-use-case.md)
      + [Konfigurieren der Ereignisse](using/usecase/configuring-the-events.md)
      + [Konfigurieren von Datenquellen](using/usecase/configuring-the-data-sources.md)
      + [Erstellen der Journey](using/usecase/building-the-journey.md)
+ Arbeiten mit APIs{#working-with-apis}
   + [Begrenzen von APIs](using/api/capping.md)
+ Alpha-Funktionen {#alpha}
   + [Übersicht über die Alpha-Funktionen](using/alpha/alpha-overview.md)
   + [Benutzeroberfläche](using/alpha/alpha-interface.md)
   + [Aktivität „Segment lesen“](using/alpha/alpha-segment-trigger.md)

