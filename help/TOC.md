---
product: Journeys
audience: end-user
user-guide-title: Hilfe für Journey Orchestration
index: true
translation-type: ht
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: ht
source-wordcount: '348'
ht-degree: 100%

---


# [!DNL Journey Orchestration] Hilfe {#using}

+ [Produktdokumentation](journey-orchestration-home.md)
+ Neue Funktionen {#release-notes}
   + [Versionshinweise](using/release-notes/release-notes.md)
   + [Aktualisierungen der Dokumentation](using/release-notes/documentation-updates.md)
+ Einstieg in [!DNL Journey Orchestration] {#starting-with-journeys}
   + [Info [!DNL Journey Orchestration]](using/about/about-journey-orchestration.md)
   + [Erste Schritte](using/about/get-started.md)
   + [Benutzeroberfläche](using/about/user-interface.md)
   + [Zugriffsverwaltung](using/about/access-management.md)
   + [Problembehebung](using/about/troubleshooting.md)
+ Konfigurieren eines Ereignisses {#events-journeys}
   + [Informationen zu Ereignissen](using/event/about-events.md)
   + [Informationen zu ExperienceEvent-Schemata](using/event/experience-event-schema.md)
   + [Definieren der Payload-Felder](using/event/defining-the-payload-fields.md)
   + [Auswählen des Namespace](using/event/selecting-the-namespace.md)
   + [Definieren des Ereignisschlüssels](using/event/defining-the-event-key.md)
   + [Hinzufügen einer Bedingung](using/event/adding-a-condition.md)
   + [Anzeigen der Payload-Vorschau](using/event/previewing-the-payload.md)
   + [Zusätzliche Schritte zum Senden von Ereignissen](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
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
      + [Einschränkungen für benutzerdefinierte Aktionen](using/action/custom-action-limitations.md)
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
      + [Ereignisaktivitäten](using/building-journeys/event-activities.md)
      + Orchestrierungsaktivitäten {#orchestration-activities}
         + [Informationen zu Orchestrierungsaktivitäten](using/building-journeys/about-orchestration-activities.md)
         + [Bedingungsaktivität](using/building-journeys/condition-activity.md)
         + [Endaktivität](using/building-journeys/end-activity.md)
         + [Warteaktivität](using/building-journeys/wait-activity.md)
      + Aktionsaktivitäten {#action-activities}
         + [Informationen zu Aktionsaktivitäten](using/building-journeys/about-action-activities.md)
         + [Verwenden von Adobe Campaign-Aktionen](using/building-journeys/using-adobe-campaign-actions.md)
         + [Verwenden benutzerdefinierter Aktionen](using/building-journeys/using-custom-actions.md)
   + [Testen der Journey](using/building-journeys/testing-the-journey.md)
   + [Veröffentlichen der Journey](using/building-journeys/publishing-the-journey.md)
   + Freigeben von Journey-Schritten für Platform {#sharing-journey-steps}
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
      + [Beispiele](using/expression/advanced-editor-use-cases.md)
   + Funktionen {#main-functions-journey}
      + [Hauptfunktionen](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [getBestSendTime](using/functions/functiongetbestsendtime.md)
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
+ Anwendungsfälle{#use-cases-journeys}
   + Einfacher Anwendungsfall{#use-case-simple}
      + [Informationen zum einfachen Anwendungsfall](using/usecase/about-the-simple-use-case.md)
      + [Konfigurieren des Ereignisses](using/usecase/configuring-the-event.md)
      + [Konfigurieren der Datenquelle](using/usecase/configuring-the-data-source.md)
      + [Erstellen der Journey](using/usecase/simple-uc-building-the-journey.md)
   + Erweiterter Anwendungsfall{#use-case-advanced}
      + [Informationen zum erweiterten Anwendungsfall](using/usecase/about-the-advanced-use-case.md)
      + [Konfigurieren der Ereignisse](using/usecase/configuring-the-events.md)
      + [Konfigurieren von Datenquellen](using/usecase/configuring-the-data-sources.md)
      + [Erstellen der Journey](using/usecase/building-the-journey.md)
   + [Nutzen von Ermüdungswerten](using/usecase/leveraging-fatigue-scores.md)
+ Arbeiten mit APIs{#working-with-apis}
   + [Begrenzen von APIs](using/api/capping.md)

