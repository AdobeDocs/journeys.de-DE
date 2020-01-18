---
title: Problembehebung
description: Weitere Informationen zur Fehlerbehebung
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# Problembehebung{#concept_nlv_bcv_2fb}

In diesem Abschnitt erfahren Sie, wie Sie Reisen vor dem Testen oder Veröffentlichen beheben können. Alle unten aufgeführten Prüfungen können durchgeführt werden, wenn die Fahrt im Prüfmodus ist oder die Fahrt live ist. Die Empfehlung besteht darin, alle unten aufgeführten Prüfungen im Testmodus durchzuführen und dann mit der Veröffentlichung fortzufahren. Näheres wird im Abschnitt [](../building-journeys/testing-the-journey.md) beschrieben.

## Fehlersuche vor dem Testen{#section_h3q_kqk_fhb}

Überprüfen Sie vor dem Testen und Veröffentlichen Ihrer Reise, ob alle Aktivitäten ordnungsgemäß konfiguriert sind. Sie können keine Tests oder Veröffentlichungen durchführen, wenn das System weiterhin Fehler erkennt.

Fehler werden mit einem Warnsymbol angezeigt, das auf den Aktivitäten selbst auf der Arbeitsfläche angezeigt wird. Platzieren Sie den Cursor auf das Ausrufezeichen, um die Fehlermeldung anzuzeigen. Wenn Sie auf die Aktivität klicken, wird die Zeile mit einer Warnung angezeigt. Wenn beispielsweise ein Pflichtfeld leer ist, wird ein Fehler angezeigt.

![](../assets/journey63.png)

Neben dem Umschalter &quot; **[!UICONTROL Test]**&quot;und der Schaltfläche &quot;**[!UICONTROL  Veröffentlichen]** &quot;kann ein Warnzeichen angezeigt werden. Dieses Warnzeichen zeigt Fehler an, die vom System erkannt wurden, und verhindert die Aktivierung des Testmodus oder die Veröffentlichung der Fahrten. In den meisten Fällen werden vom System erkannte Fehler mit Fehlern in Verbindung gebracht, die bei den Aktivitäten sichtbar sind, gelegentlich aber mit anderen Problemen. In diesem Fall können Sie sie anzeigen und versuchen, das Problem anhand der Fehlerbeschreibung zu identifizieren. Wenn Sie das Problem nicht identifizieren können, können Sie die Details kopieren und an den Administrator oder den Support senden. Beachten Sie, dass Fehler, die den Test blockieren, und Fehler, die die Veröffentlichung blockieren, ähnlich sind.

Das System erkennt zwei Arten von Problemen: Fehler und Warnungen. Fehler blockieren die Veröffentlichung und Testaktivierung. Warnungen weisen auf potenzielle Probleme hin, die die Testaktivierung oder Veröffentlichung nicht blockieren. Daraufhin werden eine Beschreibung des Problems und eine Ausgabe-Protokoll-ID des Typs ERR_XXX_XXX angezeigt. Dadurch kann der technische Support das Problem identifizieren.

Neben dem Umschalter &quot; **[!UICONTROL Test]**&quot;und der Schaltfläche &quot;**[!UICONTROL  Veröffentlichen]** &quot;können zwei verschiedene Farben angezeigt werden. Das Zeichen wird bei Fehlern rot angezeigt. Es wird bei Warnungen orange angezeigt.

![](../assets/journey75.png)

Fehler und Warnungen, die für die Reise global sind, werden zuerst in der Liste angezeigt. Fehler und Warnungen in Bezug auf bestimmte Aktivitäten werden nach, nach der Reihenfolge oder nach dem Erscheinungsbild der Aktivität auf der Reise von links nach rechts aufgeführt. Mit der Schaltfläche &quot;Details **[!UICONTROL kopieren]**&quot;werden technische Informationen zur Reise kopiert, die das Supportteam zur Fehlerbehebung verwenden kann.

## Überprüfen, ob Ereignisse ordnungsgemäß gesendet werden{#section_rqz_11t_dgb}

Der Ausgangspunkt einer Reise ist immer ein Ereignis. Sie können Tests mit Tools wie Postman durchführen.

Sie können überprüfen, ob der API-Aufruf, den Sie über diese Tools senden, korrekt gesendet wurde. Wenn Sie einen Fehler zurückerhalten, bedeutet dies, dass Ihr Aufruf ein Problem hat. Überprüfen Sie erneut die Nutzlast, den Header (und insbesondere die Organisations-ID) und die Ziel-URL. Sie können Ihren Administrator fragen, welche URL Sie treffen sollten.

Veranstaltungen werden nicht direkt von der Quelle an das Journey Orchestration weitergeleitet. Die Journey Orchestration setzt auf die Streaming-APIs der Experience Platform. Daher können Sie bei Problemen mit Ereignissen auf dieser [Seite](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingestion_FAQ.md) die Fehlerbehebung für Streaming-APIs aufrufen.

## Überprüfen, ob Personen auf die Reise gelangen{#section_x4v_zzs_dgb}

Die Berichterstattung über die Reiseorchestrierung misst die Eingänge der Menschen zu einer Reise in Echtzeit.

Wenn Sie die Veranstaltung erfolgreich versenden, aber keinen Eingang auf die Reise sehen, bedeutet das, dass etwas zwischen dem Senden der Veranstaltung und dem Empfang der Veranstaltung während der Reise schiefgeht.

Im Folgenden finden Sie einige Punkte, die der Administrator überprüfen sollte:

* Sind Sie sicher, dass die Reise, auf der das eingehende Ereignis erwartet wird, im Testmodus oder live verläuft?
* Haben Sie das Ereignis gespeichert, bevor Sie die Nutzlast aus der Nutzdatenvorschau kopiert haben?
* Enthält Ihre Ereignisnutzlast eine Ereignis-ID?
* Haben Sie die richtige URL erreicht?
* Haben Sie die Payload-Struktur der Streaming Ingestion APIs mithilfe der Payload-Strukturvorschau im Ereigniskonfigurationsbereich befolgt? Näheres wird im Abschnitt [](../event/previewing-the-payload.md) beschrieben.
* Haben Sie die richtigen Schlüssel/Wert-Paare in der Kopfzeile Ihres Ereignisses verwendet?

   ```
   X-gw-ims-org-id - your ORGID
   Content-type - application/json
   ```

## Überprüfen, wie Menschen durch die Reise navigieren{#section_l5y_yzs_dgb}

Die Berichterstattung über die Reisebegleitung misst den Fortschritt von Personen innerhalb einer Reise. Es ist einfach herauszufinden, wo und warum eine Person angehalten wurde.

Im Folgenden sind einige Punkte zu prüfen:

* Ist das auf eine Bedingung zurückzuführen, die die Person ausschließt? Zum Beispiel ist die Krankheit &quot;Geschlecht = männlich&quot;und die Person eine Frau. Diese Prüfung kann von einem Geschäftsbenutzer durchgeführt werden, wenn die Bedingung nicht zu komplex ist.
* Ist dies auf einen Aufruf an eine Datenquelle zurückzuführen, die nicht reagiert? Wenn die Reise getestet wird, können diese Informationen in Testmodusprotokollen angezeigt werden. Wenn die Reise live ist, kann ein Administrator Direktaufrufe an die Datenquelle testen und die erhaltene Antwort überprüfen. Ein Administrator kann die Reise auch duplizieren und testen.

## Überprüfen, ob Nachrichten erfolgreich gesendet wurden{#section_qb1_yzs_dgb}

Wenn Einzelpersonen den richtigen Weg entlang der Reise gehen, aber keine Nachrichten erhalten, die sie erhalten sollten, können Sie prüfen, ob:

* Bei der Transaktionsnachrichten wurde die Anfrage zum Senden der Nachricht korrekt berücksichtigt. Ein Geschäftsbenutzer kann auf die Transaktionsnachricht zugreifen, die gesendet werden soll, und prüfen, ob der Zeitpunkt der letzten Ausführung der Ausführungszeit Ihrer Reise entspricht. Er kann auch die neuesten API-Aufrufe/Ereignisse überprüfen, die von Transaktionsnachrichten empfangen wurden.
* Die Nachricht wurde erfolgreich von Transaktionsnachrichten gesendet. In den Versandprotokollen der Transaktionsnachricht können Sie den Status jeder Ausführung sehen. Sie können sehen, ob es grün, rot ist und was das Problem war. Ein Geschäftsbenutzer kann auf diesen Bildschirm zugreifen und die Protokolle zur weiteren Prüfung an einen Administrator senden.

Bei einer Nachricht, die über eine benutzerdefinierte Aktion gesendet wird, kann nur geprüft werden, ob der Aufruf des Systems der benutzerdefinierten Aktion zu einem Fehler führt oder nicht. Wenn der Aufruf an das externe System, das mit der benutzerdefinierten Aktion verknüpft ist, nicht zu einem Fehler führt, sondern nicht zum Senden einer Nachricht führt, sollten einige Untersuchungen auf der Seite des externen Systems durchgeführt werden.

