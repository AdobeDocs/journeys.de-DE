---
title: Testen der Reise
description: 'Informationen zu Reiseversuchen '
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
source-git-commit: a0ab3528b090e34867d54174421741c689e378e7

---


# Testen der Reise{#testing_the_journey}

Bevor Sie Ihre Reise testen können, müssen Sie alle Fehler gegebenenfalls beheben. Näheres wird im Abschnitt [](../about/troubleshooting.md#section_h3q_kqk_fhb) beschrieben.

Sie haben die Möglichkeit, Ihre Reise vor der Veröffentlichung mit Testprofilen zu testen. Auf diese Weise können Sie analysieren, wie sich Einzelpersonen auf der Reise bewegen, und eine Fehlerbehebung vor der Veröffentlichung durchführen.

>[!NOTE]
>
>Im Testmodus werden alle Warteaktivitäten automatisch auf 5 Sekunden eingestellt. So können Sie schnell auf die Testergebnisse zugreifen.

Gehen Sie wie folgt vor, um den Testmodus zu verwenden:

1. Bevor Sie Ihre Reise testen, überprüfen Sie, ob sie gültig ist und ob kein Fehler vorliegt. Sie können keinen Test einer Reise mit Fehlern starten. Näheres wird im Abschnitt [](../about/troubleshooting.md#section_h3q_kqk_fhb) beschrieben. Bei Fehlern wird ein Warnsymbol angezeigt.

1. Um den Testmodus zu aktivieren, klicken Sie auf den **[!UICONTROL Test]**-Umschalter in der oberen rechten Ecke.

   ![](../assets/journeytest1.png)

1. Klicken Sie auf Ereignis **[!UICONTROL auslösen]**, um Ereignisse zu konfigurieren und an die Reise zu senden. Vergewissern Sie sich, dass Ereignisse im Zusammenhang mit Testprofilen gesendet werden. Siehe[Veranstaltungen](#firing_events).

   ![](../assets/journeyuctest1.png)

1. Nachdem die Ereignisse eingegangen sind, klicken Sie auf die Schaltfläche Protokoll **[!UICONTROL anzeigen]**, um das Testergebnis anzuzeigen und zu überprüfen. Siehe[Anzeigen der Protokolle](#viewing_logs).

   ![](../assets/journeyuctest2.png)

1. Wenn ein Fehler auftritt, deaktivieren Sie den Testmodus, ändern Sie Ihre Reise und testen Sie sie erneut. Wenn der Test abgeschlossen ist, können Sie Ihre Reise veröffentlichen. Näheres wird im Abschnitt [](../building-journeys/publishing-the-journey.md) beschrieben.

## Wichtige Hinweise {#important_notes}

* Es wird eine Schnittstelle bereitgestellt, über die Ereignisse auf die getestete Reise ausgelöst werden können. Ereignisse können aber auch von Drittanbietersystemen wie Postman gesendet werden.
* Nur Personen, die im Kundenprofildienst in Echtzeit als &quot;Testprofile&quot;gekennzeichnet sind, dürfen an der getesteten Reise teilnehmen. Der Prozess zum Erstellen eines Testprofils entspricht dem Vorgang zum Erstellen eines Profils in der Datenplattform. Sie müssen nur sicherstellen, dass das Test-Profil-Flag wahr ist. Sie können den Abschnitt &quot;Segmente&quot;in der Benutzeroberfläche der Datenplattform verwenden, um ein Segment mit Testprofilen in Ihrer Datenplattform zu erstellen und eine nicht erschöpfende Liste anzuzeigen. Die vollständige Liste kann vorerst nicht angezeigt werden.
* Der Testmodus ist nur bei Reisen im Entwurf verfügbar, die einen Namespace verwenden. Tatsächlich muss der Testmodus prüfen, ob eine Person, die die Reise betritt, ein Testprofil ist oder nicht, und somit die Datenplattform erreichen können.
* Die maximale Anzahl von Testprofilen, die während einer Testsitzung auf eine Reise gelangen können, beträgt 100.
* Wenn Sie den Testmodus deaktivieren, entleert er die Reisen von allen Personen, die ihn in der Vergangenheit betreten haben oder sich derzeit darin befinden.
* Sie können den Testmodus beliebig oft aktivieren/deaktivieren.
* Sie können Ihre Reise nicht ändern, wenn der Testmodus aktiviert ist. Im Testmodus können Sie die Reise direkt veröffentlichen, ohne den Testmodus zuvor deaktivieren zu müssen.

## Veranstaltungen auslösen {#firing_events}

Mit der Schaltfläche &quot;Ereignis **[!UICONTROL auslösen]**&quot;können Sie ein Ereignis konfigurieren, das eine Person in die Reise einleitet.

Als Voraussetzung müssen Sie wissen, welche Profile in der Datenplattform als Testprofile gekennzeichnet werden. Der Testmodus erlaubt nur diese Profile während der Fahrt und das Ereignis muss eine ID enthalten. Die erwartete ID hängt von der Ereigniskonfiguration ab. Es kann beispielsweise eine ECID sein.

In diesem Bildschirm können Sie die Felder konfigurieren, die im Ereignis übergeben werden, und die Ausführung des Ereignisses senden. Die Oberfläche hilft Ihnen, die richtigen Informationen in der Ereignisauslastung weiterzugeben und sicherzustellen, dass der Informationstyp korrekt ist. Der Testmodus speichert die letzten Parameter, die in einer Testsitzung verwendet werden, zur späteren Verwendung.

![](../assets/journeytest4.png)

Über die Oberfläche können Sie einfache Ereignisparameter übergeben. Wenn Sie Sammlungen oder andere erweiterte Objekte in dem Ereignis weitergeben möchten, können Sie auf **[!UICONTROL Codeansicht]**klicken, um den gesamten Code der Payload anzuzeigen und ihn zu ändern. Beispielsweise können Sie die von einem technischen Benutzer erstellten Ereignisinformationen kopieren und einfügen.

![](../assets/journeytest5.png)

Ein technischer Benutzer kann diese Schnittstelle auch verwenden, um Nutzdaten für Ereignisse zu erstellen und Ereignisse auszulösen, ohne ein Tool eines Drittanbieters verwenden zu müssen.

## Protokolle anzeigen {#viewing_logs}

Mit der Schaltfläche Protokoll ****anzeigen können Sie die Testergebnisse anzeigen. Auf dieser Seite werden die aktuellen Informationen der Reise im JSON-Format angezeigt. Mit einer Schaltfläche können Sie ganze Knoten kopieren. Sie müssen die Seite manuell aktualisieren, um die Testergebnisse der Reise zu aktualisieren.

![](../assets/journeytest3.png)

Die Anzahl der Personen (technisch gesehen werden sie Instanzen genannt), die sich derzeit innerhalb der Reise befinden, wird angezeigt. Hier finden Sie nützliche Informationen, die für jede einzelne Person angezeigt werden:

* _ID_: die interne ID der Person während der Reise. Dies kann zum Debugging verwendet werden.
* _currentstep_: der Schritt, in dem sich der Einzelne auf der Reise befindet. Es wird empfohlen, Ihren Aktivitäten Beschriftungen hinzuzufügen, um sie leichter identifizieren zu können.
* _currentstep_ > phase: der Status der Reise des Einzelnen (laufend, fertig, fehlerbehaftet oder abgelaufen). Weitere Informationen finden Sie unten.
* _currentstep_ > _extraInfo_: Beschreibung des Fehlers und andere kontextbezogene Informationen.
* _externalKeys_: der Wert für die im Ereignis definierte Schlüsselformel.
* _angereicherteData_: die Daten, die die Reise abgerufen hat, wenn die Reise Datenquellen verwendet.
* _transiHistory_: die Liste der Schritte, denen die betreffende Person folgte. Bei Ereignissen wird die Nutzlast angezeigt.

