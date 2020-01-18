---
product: Journeys
audience: end-user
user-guide-title: Journey Orchestration Help
index: true
translation-type: tm+mt
source-git-commit: 22569d66acb1637efc346f77864302b9e2cb6070

---


# Hilfe zur Reiseorganisation {#using}

+ [Produktdokumentation](journey-orchestration-home.md)
+ Neue Funktionen {#release-notes}
   + [Versionshinweise](using/release-notes/release-notes.md)
   + [Aktualisierungen der Dokumentation](using/release-notes/documentation-updates.md)
+ Start mit Reisebegleitung {#starting-with-journeys}
   + [Informationen zur Reiseorganisation](using/about/about-journey-orchestration.md)
   + [Jetzt loslegen](using/about/get-started.md)
   + [Benutzeroberfläche](using/about/user-interface.md)
   + [Zugriffsverwaltung](using/about/access-management.md)
   + [Problembehebung](using/about/troubleshooting.md)
+ Konfigurieren eines Ereignisses {#events-journeys}
   + [Ereignisse](using/event/about-events.md)
   + [Definieren der Payload-Felder](using/event/defining-the-payload-fields.md)
   + [Auswählen des Namespace](using/event/selecting-the-namespace.md)
   + [Definieren des Ereignisschlüssels](using/event/defining-the-event-key.md)
   + [Hinzufügen einer Bedingung](using/event/adding-a-condition.md)
   + [Vorschau der Nutzlast](using/event/previewing-the-payload.md)
   + [Zusätzliche Schritte zum Senden von Ereignissen](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
+ Datenquelle konfigurieren {#data-source-journeys}
   + [Datenquellen](using/datasource/about-data-sources.md)
   + [Feldgruppen](using/datasource/field-groups.md)
   + [Adobe Experience Platform-Datenquelle](using/datasource/adobe-experience-platform-data-source.md)
   + [Externe Datenquellen](using/datasource/external-data-sources.md)
+ Konfigurieren einer Aktion {#action-journeys}
   + [Aktionen](using/action/action.md)
   + [Arbeiten mit Adobe Campaign](using/action/working-with-adobe-campaign.md)
   + Verwenden eines Drittanbietersystems {#action-third-party}
      + [Konfiguration benutzerdefinierter Aktionen](using/action/about-custom-action-configuration.md)
      + [Benutzerdefinierte Aktionsbeschränkungen](using/action/custom-action-limitations.md)
      + [URL-Konfiguration](using/action/url-configuration.md)
      + [Definieren der Nachrichtenparameter](using/action/defining-the-message-parameters.md)
+ Eine Reise bauen {#building-journeys}
   + Informationen zum Reiseaufbau {#about-journey-building}
      + [Eine Reise erstellen](using/building-journeys/journey.md)
      + [Verwendung des Reisedesigners](using/building-journeys/using-the-journey-designer.md)
      + [Eigenschaften ändern](using/building-journeys/changing-properties.md)
      + [Reiseversionen](using/building-journeys/journey-versions.md)
      + [Beendigung einer Reise](using/building-journeys/terminating-a-journey.md)
      + [Zeitzonen](using/building-journeys/timezone-management.md)
   + Activities {#about-journey-building}
      + [Veranstaltungen](using/building-journeys/event-activities.md)
      + Orchestrierung {#orchestration-activities}
         + [Informationen zu Orchestrierung](using/building-journeys/about-orchestration-activities.md)
         + [Bedingungsaktivität](using/building-journeys/condition-activity.md)
         + [Aktivität beenden](using/building-journeys/end-activity.md)
         + [Aktivität warten](using/building-journeys/wait-activity.md)
      + Aktionsaktivitäten {#action-activities}
         + [Informationen zu Aktivitäten](using/building-journeys/about-action-activities.md)
         + [Adobe Campaign-Aktionen verwenden](using/building-journeys/using-adobe-campaign-actions.md)
         + [Verwenden benutzerdefinierter Aktionen](using/building-journeys/using-custom-actions.md)
   + [Testen der Reise](using/building-journeys/testing-the-journey.md)
   + [Veröffentlichen der Reise](using/building-journeys/publishing-the-journey.md)
+ Verwenden des erweiterten Ausdruckseditors {#building-advanced-conditions-journeys}
   + [Informationen zum erweiterten Ausdruckseditor](using/expression/expressionadvanced.md)
   + Syntax {#syntax}
      + [Allgemein](using/expression/generalities.md)
      + [Bedingte Anweisung](using/expression/conditional-instruction.md)
      + [Datentypen](using/expression/data-types.md)
      + [Feldverweise](using/expression/field-references.md)
      + [Sammlungsverwaltungsfunktionen](using/expression/collection-management-functions.md)
      + [Benutzer](using/expression/operators.md)
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
         + [differentCount](using/functions/functiondistinctcount.md)
         + [differentCountWithNull](using/functions/functiondistinctcountwithnull.md)
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
         + [currentTime &#x200B; InMillis](using/functions/functioncurrenttimeinmillis.md)
         + [inLastDays](using/functions/functioninlastdays.md)
         + [inLastHours](using/functions/functioninlasthours.md)
         + [inLastMonths](using/functions/functioninlastmonths.md)
         + [inLastYears](using/functions/functioninlastyears.md)
         + [inNextDays](using/functions/functioninnextdays.md)
         + [inNextHours](using/functions/functioninnexthours.md)
         + [inNextMonths](using/functions/functioninnextmonths.md)
         + [inNextYears](using/functions/functioninnextyears.md)
         + [jetzt](using/functions/functionnow.md)
         + [nowWithDelta](using/functions/functionnowwithdelta.md)
         + [setHours](using/functions/functionsethours.md)
         + [setDays](using/functions/functionsetdays.md)
      + Liste {#list}
         + [unterscheide](using/functions/functiondistinct.md)
         + [differentWithNull](using/functions/functiondistinctwithnull.md)
         + [in](using/functions/functionin.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [Sortierung](using/functions/functionsort.md)
      + Mathematik {#math}
         + [random](using/functions/functionrandom.md)
         + [round](using/functions/functionround.md)
      + String {#string}
         + [concat](using/functions/functionconcat.md)
         + [contains](using/functions/functioncontain.md)
         + [containsWithIgnoreCase](using/functions/functioncontainwithignorecase.md)
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
         + [ersetzen](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [substr](using/functions/functionsubstr.md)
         + [trim](using/functions/functiontrim.md)
         + [top](using/functions/functionupper.md)
         + [uuid](using/functions/functionuuid.md)
+ Erstellen von Berichten{#journey-reports}
   + [Info zu Reiseberichten](using/reporting/about-journey-reports.md)
   + [Erstellen von Reiseberichten](using/reporting/creating-your-journey-reports.md)
   + [Metriken und Dimensionen](using/reporting/metrics-and-dimensions.md)
+ Anwendungsbeispiele{#use-cases-journeys}
   + Einfacher Verwendungsfall{#use-case-simple}
      + [Über den einfachen Verwendungsfall](using/usecase/about-the-simple-use-case.md)
      + [Konfigurieren des Ereignisses](using/usecase/configuring-the-event.md)
      + [Datenquelle konfigurieren](using/usecase/configuring-the-data-source.md)
      + [Aufbau der Reise](using/usecase/simple-uc-building-the-journey.md)
   + Erweiterte Anwendungsfälle{#use-case-advanced}
      + [Informationen zum erweiterten Verwendungsfall](using/usecase/about-the-advanced-use-case.md)
      + [Konfigurieren der Ereignisse](using/usecase/configuring-the-events.md)
      + [Datenquellen konfigurieren](using/usecase/configuring-the-data-sources.md)
      + [Aufbau der Reise](using/usecase/building-the-journey.md)
   + [Nutzen von Ermüdungswerten](using/usecase/leveraging-fatigue-scores.md)

