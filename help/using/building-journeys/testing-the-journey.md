---
title: Testen der Journey
description: 'Erfahren Sie mehr über das Testen von Journeys '
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
source-git-commit: 6274426ec04315149fb430b847498c0e20164bae

---


# Testen der Journey{#testing_the_journey}

Bevor Sie Ihre Journey testen können, müssen Sie alle eventuellen Fehler beheben. Siehe [](../about/troubleshooting.md#section_h3q_kqk_fhb).

Sie können Ihre Journey vor der Veröffentlichung mit Testprofilen testen. Auf diese Weise können Sie analysieren, wie sich Kontakte in der Journey bewegen, und Fehler vor der Veröffentlichung beheben.

>[!NOTE]
>
>Im Testmodus werden alle Warteaktivitäten automatisch auf 5 Sekunden eingestellt. So können Sie schnell auf die Testergebnisse zugreifen.

Gehen Sie wie folgt vor, um den Testmodus zu verwenden:

1. Bevor Sie Ihre Journey testen, überprüfen Sie, ob sie gültig ist und keine Fehler vorliegen. Fehlerbehaftete Journeys können nicht getestet werden. Siehe [](../about/troubleshooting.md#section_h3q_kqk_fhb). Bei Fehlern wird ein Warnsymbol angezeigt.

1. Um den Testmodus zu aktivieren, klicken Sie in der rechten oberen Ecke auf den Umschalter **[!UICONTROL Test]**.

   ![](../assets/journeytest1.png)

1. Klicken Sie auf , **[!UICONTROL Trigger an event]** um Ereignisse zu konfigurieren und an die Reise zu senden. Vergewissern Sie sich, dass Ereignisse im Zusammenhang mit Testprofilen gesendet werden. Siehe [Auslösen Ihrer Ereignisse](#firing_events).

   ![](../assets/journeyuctest1.png)

1. After the events are received, click the **[!UICONTROL Show log]** button to view the test result and verify them. Siehe [Anzeigen der Protokolle](#viewing_logs).

   ![](../assets/journeyuctest2.png)

1. Wenn ein Fehler auftritt, deaktivieren Sie den Testmodus, ändern Sie Ihre Journey und testen Sie sie erneut. Wenn der Test abgeschlossen ist, können Sie Ihre Journey veröffentlichen. Siehe [](../building-journeys/publishing-the-journey.md).

## Wichtige Hinweise  {#important_notes}

* Es wird eine Schnittstelle bereitgestellt, über die Ereignisse für die getestete Journey ausgelöst werden können. Ereignisse können aber auch von Drittanbietersystemen wie Postman gesendet werden.
* Nur Kontakte, die im Echtzeit-Kundenprofil als „Testprofile“ gekennzeichnet sind, dürfen an der getesteten Journey teilnehmen. Der Prozess zum Erstellen eines Testprofils entspricht dem Vorgang zum Erstellen eines Profils in der Datenplattform. Sie müssen nur sicherstellen, dass die Testprofilmarkierung aktiviert ist. Sie können den Abschnitt „Segmente“ in der Benutzeroberfläche der Datenplattform verwenden, um ein Segment mit Testprofilen in Ihrer Datenplattform zu erstellen und eine nicht vollständige Liste anzuzeigen. Die vollständige Liste kann derzeit nicht angezeigt werden.
* Der Testmodus ist nur in Entwurfs-Journeys verfügbar, die einen Namespace verwenden. Der Testmodus muss tatsächlich prüfen, ob eine Person, die die Journey betritt, ein Testprofil ist oder nicht, und muss daher in der Lage sein, die Datenplattform zu erreichen.
* Die maximale Anzahl von Testprofilen, die während einer Testsitzung auf eine Journey zugreifen können, beträgt 100.
* Wenn Sie den Testmodus deaktivieren, werden alle Personen, die in der Vergangenheit an der Journey teilgenommen haben oder sich derzeit darin befinden, aus der Journey entfernt.
* Sie können den Testmodus beliebig oft aktivieren/deaktivieren.
* Sie können Ihre Journey nicht ändern, wenn der Testmodus aktiviert ist. Im Testmodus können Sie die Journey direkt veröffentlichen, ohne den Testmodus zuvor deaktivieren zu müssen.

## Auslösen Ihrer Ereignisse {#firing_events}

The **[!UICONTROL Trigger an event]** button allows you to configure an event that will make a person enter the journey.

Als Voraussetzung müssen Sie wissen, welche Profile in der Datenplattform als Testprofile gekennzeichnet sind. Der Testmodus lässt nur diese Profile in der Journey zu und das Ereignis muss eine ID enthalten. Die erwartete ID hängt von der Ereigniskonfiguration ab. Sie kann beispielsweise eine ECID sein.

In diesem Bildschirm können Sie die im Ereignis übergebenen Felder und die Ausführung des Ereignisversands konfigurieren. Die Oberfläche hilft Ihnen, die richtigen Informationen in der Ereignis-Payload weiterzugeben und sicherzustellen, dass der Informationstyp korrekt ist. Der Testmodus speichert die zuletzt in einer Testsitzung verwendeten Parameter zur späteren Verwendung.

![](../assets/journeytest4.png)

Über die Oberfläche können Sie einfache Ereignisparameter übergeben. If you want to pass collections or other advanced objects in the event, you can click on **[!UICONTROL Code View]** to see the entire code of the payload and modify it. Beispielsweise können Sie die von einem technischen Anwender erstellten Ereignisinformationen kopieren und einfügen.

![](../assets/journeytest5.png)

Ein technischer Anwender kann diese Oberfläche auch verwenden, um Payloads für Ereignisse zu erstellen und Ereignisse auszulösen, ohne ein Tool eines Drittanbieters verwenden zu müssen.

## Anzeigen der Protokolle {#viewing_logs}

The **[!UICONTROL Show log]** button allows you to view the test results. Auf dieser Seite werden die aktuellen Informationen der Journey im JSON-Format angezeigt. Mit einer Schaltfläche können Sie ganze Knoten kopieren. Sie müssen die Seite manuell aktualisieren, um die Testergebnisse der Journey zu aktualisieren.

![](../assets/journeytest3.png)

Die Anzahl der Kontakte (technisch gesehen handelt es sich um Instanzen), die sich derzeit innerhalb der Journey befinden, wird angezeigt. Hier finden Sie nützliche Informationen, die für jeden Kontakt angezeigt werden:

* _ID_: die interne ID des Kontakts in der Journey. Diese kann zum Debugging verwendet werden.
* _currentstep_: der Schritt, in dem sich der Kontakt in der Journey befindet. Es wird empfohlen, Ihren Aktivitäten Titel hinzuzufügen, damit Sie sie leichter identifizieren können.
* _currentstep > phase_: der Status der Journey des Kontakts (Läuft, Abgeschlossen, Fehler, Zeitüberschreitung). Weitere Informationen finden Sie unten.
* _currentstep_ > _extraInfo_: Beschreibung des Fehlers und andere kontextbezogene Informationen.
* _externalKeys_: der Wert für die im Ereignis definierte Schlüsselformel.
* _enrichedData_: die Daten, die die Journey abgerufen hat, wenn die Journey Datenquellen verwendet.
* _transitionHistory_: die Liste der Schritte, denen der betreffende Kontakt folgte. Bei Ereignissen wird die Payload angezeigt.

