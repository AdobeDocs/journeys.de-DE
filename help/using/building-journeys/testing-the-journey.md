---
product: adobe campaign
solution: Journey Orchestration
title: Testen der Journey
description: 'Erfahren Sie mehr über das Testen von Journeys '
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: ht
source-git-commit: 8c7c7d85d4e7835721b70faa7b3b6166796e79c4
workflow-type: ht
source-wordcount: '1640'
ht-degree: 100%

---


# Testen der Journey{#testing_the_journey}

Bevor Sie Ihre Journey testen können, müssen Sie alle eventuell vorhandenen Fehler beheben. Siehe [diesen Abschnitt](../about/troubleshooting.md#section_h3q_kqk_fhb).

Sie können Ihre Journey vor der Veröffentlichung mit Testprofilen testen. Auf diese Weise können Sie analysieren, wie sich Kontakte in der Journey bewegen, und Fehler vor der Veröffentlichung beheben.

Nur Testprofile können im Testmodus in eine Journey eintreten. Sie können entweder ein neues Testprofil erstellen oder ein vorhandenes Profil in ein Testprofil umwandeln. Siehe diesen [Abschnitt](../building-journeys/creating-test-profiles.md).

Gehen Sie wie folgt vor, um den Testmodus zu verwenden:

1. Bevor Sie Ihre Journey testen, überprüfen Sie, ob sie gültig ist und keine Fehler vorliegen. Fehlerbehaftete Journeys können nicht getestet werden. Siehe [diesen Abschnitt](../about/troubleshooting.md#section_h3q_kqk_fhb). Bei Fehlern wird ein Warnsymbol angezeigt.

1. Um den Testmodus zu aktivieren, klicken Sie in der rechten oberen Ecke auf den Umschalter **[!UICONTROL Test]**.

   ![](../assets/journeytest1.png)

1. Verwenden Sie den Parameter **[!UICONTROL Wartezeit]** unten links, um die Zeit für jede Warteaktivität und die maximale Wartezeit für ein Ereignis im Testmodus zu definieren. Die Standardzeit für Wartezeiten und die maximale Wartezeit für Ereignisse beträgt 10 Sekunden. Dadurch erhalten Sie die Testergebnisse schnell. Dieser Parameter wird nur angezeigt, wenn Sie Ihrer Journey mindestens eine Warteaktivität hinzugefügt haben.

   ![](../assets/journeytest_wait.png)

   >[!NOTE]
   >
   >Wenn in einer Journey ein Reaktionsereignis verwendet wird, beträgt der Standard- und Mindestwert für die Wartezeit 40 Sekunden. Weitere Informationen finden Sie in [diesem Abschnitt](../building-journeys/reaction-events.md).

1. Klicken Sie auf **[!UICONTROL Ereignis auslösen]**, um Ereignisse zu konfigurieren und an die Journey zu senden.

   ![](../assets/journeyuctest1.png)

1. Konfigurieren Sie die verschiedenen erwarteten Felder. Geben Sie im Feld **Profilkennung** den Wert des Felds ein, das zum Identifizieren des Testprofils verwendet wird. Das kann beispielsweise die E-Mail-Adresse sein. Vergewissern Sie sich, dass Ereignisse gesendet werden, die im Zusammenhang mit Testprofilen stehen. Siehe [Auslösen Ihrer Ereignisse](#firing_events).

   ![](../assets/journeyuctest1-bis.png)

1. Nachdem die Ereignisse eingegangen sind, klicken Sie auf die Schaltfläche **[!UICONTROL Protokoll anzeigen]**, um das Testergebnis anzuzeigen und zu überprüfen. Siehe [Anzeigen der Protokolle](#viewing_logs).

   ![](../assets/journeyuctest2.png)

1. Wenn ein Fehler auftritt, deaktivieren Sie den Testmodus, ändern Sie Ihre Journey und testen Sie sie erneut. Wenn der Test abgeschlossen ist, können Sie Ihre Journey veröffentlichen. Weitere Informationen finden Sie auf [dieser Seite](../building-journeys/publishing-the-journey.md).

## Wichtige Hinweise {#important_notes}

* Es wird eine Benutzeroberfläche bereitgestellt, über die Ereignisse für die getestete Journey ausgelöst werden können. Ereignisse können aber auch von Drittanbietersystemen wie Postman gesendet werden.
* Nur Kontakte, die im Echtzeit-Kundenprofil als „Testprofile“ gekennzeichnet sind, dürfen an der getesteten Journey teilnehmen. Siehe diesen [Abschnitt](../building-journeys/creating-test-profiles.md).
* Der Testmodus ist nur in Entwurfs-Journeys verfügbar, die einen Namespace verwenden. Der Testmodus muss prüfen, ob eine Person, die die Journey betritt, ein Testprofil ist oder nicht, und muss daher in der Lage sein, Adobe Experience Platform zu erreichen.
* Die maximale Anzahl von Testprofilen, die während einer Testsitzung auf eine Journey zugreifen können, beträgt 100.
* Wenn Sie den Testmodus deaktivieren, werden alle Personen, die in der Vergangenheit an der Journey teilgenommen haben oder sich derzeit darin befinden, aus der Journey entfernt. Dabei werden auch die Berichte gelöscht.
* Sie können den Testmodus beliebig oft aktivieren/deaktivieren.
* Sie können Ihre Journey nicht ändern, wenn der Testmodus aktiviert ist. Im Testmodus können Sie die Journey direkt veröffentlichen, ohne den Testmodus zuvor deaktivieren zu müssen.

## Umwandeln eines Profils in ein Testprofil{#turning-profile-into-test}

Sie können ein vorhandenes Profil in ein Testprofil umwandeln. In Adobe Experience Platform können Sie die Attribute von Profilen über API-Aufrufe aktualisieren, jedoch nicht über die Oberfläche.

Am einfachsten geht dies, wenn Sie die Aktionsaktivität **Profil aktualisieren** verwenden und das boolesche Feld des Testprofils von „false“ auf „true“ ändern. Siehe [diesen Abschnitt](../building-journeys/update-profiles.md#using-the-test-mode).

## Erstellen eines Testprofils{#create-test-profile}

Der Prozess zum Erstellen eines neuen Testprofils entspricht dem Vorgang zum Erstellen eines Profils in Adobe Experience Platform. Er wird über API-Aufrufe ausgeführt. Weitere Informationen finden Sie auf dieser [Seite](https://docs.adobe.com/content/help/de-DE/experience-platform/profile/home.html)

Sie müssen ein Profilschema verwenden, das das Mixin für Profiltestdetails enthält. Die Markierung „testProfile“ ist Teil dieses Mixins.

Achten Sie beim Erstellen eines Profils darauf, diesen Wert zu übergeben: testProfile = true.

Beachten Sie, dass Sie auch ein vorhandenes Profil aktualisieren können, um die Markierung „testProfile“ in „true“ zu ändern.

Hier sehen Sie ein Beispiel für einen API-Aufruf zum Erstellen eines Testprofils:

```
curl -X POST \
'https://dcs.adobedc.net/collection/xxxxxxxxxxxxxx' \
-H 'Cache-Control: no-cache' \
-H 'Content-Type: application/json' \
-H 'Postman-Token: xxxxx' \
-H 'cache-control: no-cache' \
-H 'x-api-key: xxxxx' \
-H 'x-gw-ims-org-id: xxxxx' \
-d '{
"header": {
"msgType": "xdmEntityCreate",
"msgId": "xxxxx",
"msgVersion": "xxxxx",
"xactionid":"xxxxx",
"datasetId": "xxxxx",
"imsOrgId": "xxxxx",
"source": {
"name": "Postman"
},
"schemaRef": {
"id": "https://example.adobe.com/mobile/schemas/xxxxx",
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"body": {
"xdmMeta": {
"schemaRef": {
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"xdmEntity": {
"_id": "xxxxx",
"_mobile":{
"ECID": "xxxxx"
},
"testProfile":true
}
}
}'
```

## Auslösen Ihrer Ereignisse {#firing_events}

Mit der Schaltfläche **[!UICONTROL Ereignis auslösen]** können Sie ein Ereignis konfigurieren, das eine Person zum Zutritt zur Journey veranlasst.

>[!NOTE]
>
>Wenn Sie ein Ereignis im Testmodus auslösen, wird ein reales Ereignis generiert, d. h. es beeinflusst auch andere Journeys, die dieses Ereignis überwachen.

Als Voraussetzung müssen Sie wissen, welche Profile in Adobe Experience Platform als Testprofile gekennzeichnet sind. Der Testmodus lässt nur diese Profile in der Journey zu und das Ereignis muss eine ID enthalten. Die erwartete ID hängt von der Ereigniskonfiguration ab. Es kann sich beispielsweise um eine ECID oder eine E-Mail-Adresse handeln. Der Wert dieses Schlüssels muss im Feld **Profilkennung** hinzugefügt werden.

Wenn Ihre Journey mehrere Ereignisse enthält, wählen Sie ein Ereignis aus der Dropdown-Liste aus. Konfigurieren Sie dann für jedes Ereignis die weitergeleiteten Felder und die Ausführung des Ereignisversands. Über die Benutzeroberfläche können Sie die richtigen Informationen in der Ereignis-Payload angeben und prüfen, ob der Informationstyp korrekt ist. Der Testmodus speichert die zuletzt in einer Testsitzung verwendeten Parameter zur späteren Verwendung.

![](../assets/journeytest4.png)

Über die Benutzeroberfläche können Sie einfache Ereignisparameter übergeben. Wenn Sie Sammlungen oder andere erweiterte Objekte in dem Ereignis verwenden möchten, können Sie auf **[!UICONTROL Codeansicht]** klicken, um den gesamten Code der Payload anzuzeigen und zu ändern. Beispielsweise können Sie die von einem technischen Anwender erstellten Ereignisinformationen kopieren und einfügen.

![](../assets/journeytest5.png)

Ein technischer Anwender kann diese Benutzeroberfläche auch verwenden, um Payloads für Ereignisse zu erstellen und Ereignisse auszulösen, ohne ein Tool eines Drittanbieters verwenden zu müssen.

Wenn Sie auf die Schaltfläche **[!UICONTROL Senden]** klicken, beginnt der Test. Der Fortschritt des Kontakts in der Journey wird durch einen visuellen Verlauf dargestellt. Der Pfad wird immer grüner, je weiter sich der Kontakt in der Journey bewegt. Tritt ein Fehler auf, wird auf dem entsprechenden Schritt ein Warnsymbol angezeigt. Sie können den Cursor darauf platzieren, um weitere Informationen zum Fehler anzuzeigen und genaue Details aufzurufen (sofern verfügbar).

![](../assets/journeytest6.png)

Wenn Sie im Bildschirm für die Ereigniskonfiguration ein anderes Profil auswählen und den Test erneut ausführen, wird der visuelle Verlauf geleert und stattdessen der Pfad des neuen Kontakts angezeigt.

Beim Öffnen einer Journey im Test ist der angezeigte Pfad der des zuletzt durchgeführten Tests

Der visuelle Fluss funktioniert unabhängig davon, ob das Ereignis über die Benutzeroberfläche oder extern ausgelöst wird (z. B. mit Postman).

## Testmodus für regelbasierte Journeys {#test-rule-based}

Der Testmodus ist für Journeys, bei denen ein regelbasiertes Ereignis verwendet wird, ebenfalls verfügbar. Weitere Informationen zu regelbasierten Ereignissen finden Sie auf [dieser Seite](../event/about-events.md).

Beim Auslösen eines Ereignisses können Sie im Bildschirm **Ereigniskonfiguration** die Ereignisparameter definieren, nach denen der Test als bestanden gilt. Durch Klicken auf das QuickInfo-Symbol oben rechts können Sie die Ereignis-ID-Bedingung anzeigen. Außerdem ist neben jedem Feld, das Teil der Regelauswertung ist, ebenfalls eine QuickInfo verfügbar.

![](../assets/alpha-event8.png)

Weitere Informationen zur Verwendung des Testmodus finden Sie auf [dieser Seite](../building-journeys/testing-the-journey.md).

## Anzeigen der Protokolle {#viewing_logs}

Mit der Schaltfläche **[!UICONTROL Protokoll anzeigen]** können Sie die Testergebnisse anzeigen. Auf dieser Seite werden die aktuellen Informationen der Journey im JSON-Format angezeigt. Mit einer Schaltfläche können Sie ganze Knoten kopieren. Sie müssen die Seite manuell aktualisieren, um die Testergebnisse der Journey zu aktualisieren.

![](../assets/journeytest3.png)

>[!NOTE]
>
>In den Testprotokollen werden bei einem fehlerhaften Aufruf eines Drittanbietersystems (Datenquelle oder Aktion) der Fehlercode und die Fehlerantwort angezeigt.

Die Anzahl der Kontakte (technisch gesehen handelt es sich um Instanzen), die sich derzeit innerhalb der Journey befinden, wird angezeigt. Außerdem finden Sie hier nützliche Informationen zu jedem Kontakt:

* _ID_: die interne ID des Kontakts in der Journey. Diese kann zum Debugging verwendet werden.
* _currentstep_: der Schritt, in dem sich der Kontakt in der Journey befindet. Es wird empfohlen, Ihren Aktivitäten Titel zu geben, damit Sie sie leichter identifizieren können.
* _currentstep > phase_: der Status der Journey des Kontakts (Läuft, Beendet, Fehler, Zeitüberschreitung). Weitere Informationen finden Sie unten.
* _currentstep_ > _extraInfo_: Beschreibung des Fehlers und andere kontextbezogene Informationen.
* _currentstep_ > _fetchErrors_: Informationen zu Datenfehlern beim Abrufen, die während dieses Schritts aufgetreten sind.
* _externalKeys_: der Wert für die im Ereignis definierte Schlüsselformel.
* _enrichedData_: die Daten, die die Journey abgerufen hat, falls sie Datenquellen verwendet hat.
* _transitionHistory_: die Schritte, denen der betreffende Kontakt folgte. Bei Ereignissen wird die Payload angezeigt.
* _actionExecutionErrors_: Informationen zu den aufgetretenen Fehlern.

Hier eine Liste der verschiedenen Status der Journey eines Kontakts:

* _Läuft_: der Kontakt befindet sich derzeit in der Journey.
* _Beendet_: der Kontakt befindet sich am Ende der Journey.
* _Fehler_: der Kontakt wird aufgrund eines Fehlers in der Journey gestoppt.
* _Zeitüberschreitung_: der Kontakt wird aufgrund eines Schritts, der zu viel Zeit in Anspruch genommen hat, in der Journey gestoppt.

Wenn ein Ereignis im Testmodus ausgelöst wird, wird automatisch ein Datensatz mit dem Namen der Quelle generiert.

Wenn ein Ereignis im Testmodus ausgelöst wird, wird automatisch ein Datensatz mit dem Namen der Quelle generiert.

Der Testmodus erstellt automatisch ein Erlebnis-Ereignis und sendet es an Adobe Experience Platform. Der Name der Quelle für dieses Erlebnis-Ereignis lautet „Journey Orchestration Test-Ereignisse“.

Wenn mehrere Ereignisse von mehreren Journeys ausgelöst werden

Es gibt ein Szenario, bei dem mehrere Ereignisse von mehreren Journeys gesendet werden, die unterschiedliche Schemas haben. Können n Schemas zu 1 Datensatz zugeordnet werden? Wenn nicht, werden mehrere Datensätze benötigt.

Wenn ein Zieldatensatz nicht in dem Erlebnis-Ereignis enthalten ist, werden diese Datensätze automatisch erstellt und benannt. Deshalb sehen wir heute den „Automatisch erstellten Datensatz für Journey“.

Die Benennung unserer Quelle führt zur automatischen Erstellung. Wenn wir mehrere Ereignisse haben, sollten wir verketten und es „Journey Orchestration Test-Ereignis – NAME DES SCHEMAS“ nennen. Dies wird sich automatisch in „Automatisch generierter Datensatz für Journey Orchestration Test-Ereignis – NAME DES SCHEMAS“ ändern.

