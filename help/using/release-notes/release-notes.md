---
product: adobe campaign
title: Versionshinweise
description: Versionshinweise
feature: Journeys
role: User
level: Beginner
exl-id: b923f7e3-997b-483b-b6ac-eef62fc81a84
source-git-commit: 4f6c5f9326b4d1cc4a1a02a036b51e4ad1ae68c4
workflow-type: ht
source-wordcount: '4458'
ht-degree: 100%

---

# Versionshinweise {#release-notes}

>[!CAUTION]
>
>**Sie möchten mehr über Adobe Journey Optimizer erfahren**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um auf die Journey Optimizer-Dokumentation zuzugreifen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Accountteam, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._

Auf dieser Seite werden alle neuen Funktionen und Verbesserungen in Journey Orchestration aufgelistet. Informationen zu Funktionen von Experience Platform finden Sie in den folgenden [Versionshinweisen](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=de).

Für die nach 2022 veröffentlichten Funktionen verweisen die Links auf die [Dokumentation zu Adobe Journey Optimizer](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}.

## Version März 2024 {#mar-rn-2024}

### Verbesserungen {#mar-2024-improvements}

Dem Journey-Authoring-Lebenszyklus wurden neue Zwischenstatus hinzugefügt:

* der Status **Wird veröffentlicht** zwischen dem Status **Entwurf** und dem Status **Live**
* der Status **Wird gestoppt** zwischen dem Status **Live** und dem Status **Gestoppt**
* der Status **Testmodus wird aktiviert** oder **Testmodus wird deaktiviert** zwischen dem Status **Entwurf** und dem Status **Entwurf (Test)**

Wenn sich eine Journey in einem Zwischenzustand befindet, ist sie schreibgeschützt. [Weitere Informationen](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs#filter){target="_blank"}

## Version Februar 2024 {#feb-rn-2024}

### Verbesserungen {#feb-2024-improvements}

* **Filtern von Journeys**: Sie können jetzt zusätzlich zu den vorhandenen vordefinierten Datumsfiltern **eigene Daten zum Filtern des Inventars von Journeys** verwenden. Sie können die Liste verfeinern, indem Sie sich Journeys anzeigen lassen, die an einem bestimmten Datum, in einem bestimmten Monat, in einem ganzen Jahr oder in bestimmten Zeiträumen erstellt oder veröffentlicht wurden. [Weitere Informationen](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html?lang=de#filter){target="_blank"}
* **Benutzerdefinierte Aktionen**: Sie können jetzt den **Content-Typ**-Header aktualisieren. Dieser neue **Content-Typ** sollte auf JSON-Inhalte verweisen. [Weitere Informationen](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/action-journeys/about-custom-action-configuration.html?lang=de#url-configuration){target="_blank"}
* **Konfiguration**: Das Attribut „identityMap“ in „stepEvents“ ist jetzt vorausgefüllt. Die primäre Identität wird als „primary = true“ definiert. [Weitere Informationen](https://experienceleague.adobe.com/docs/journey-optimizer/using/reporting/reports/sharing-field-list.html?lang=de){target="_blank"}
* **Benutzeroberfläche**: Die obere Leiste in den Journey-Bildschirmen wurde für ein besseres Erlebnis umgestaltet. Unter den verschiedenen Updates sehen Sie, dass das Stiftsymbol, das Ihnen den Zugriff auf die Journey-Eigenschaften ermöglicht, nun links in der oberen Leiste neben dem Journey-Namen angezeigt wird. [Weitere Informationen](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html?lang=de#change-properties){target="_blank"}

## Version Januar 2024 {#jan-rn-2024}

### Verbesserungen {#jan-2024-improvements}

* **Dauer von Reaktionsereignissen** – Die maximale Dauer, die Sie in den **Reaktionsereignissen** definieren können, beträgt jetzt 29 Tage statt 30 Tage. [Weitere Informationen](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/about-journey-building/reaction-events.html?lang=de){target="_blank"}
* **Feldergruppen** – Mit dieser Version wird ein Problem behoben, das die Speicherung von Feldergruppen in bestimmten Fällen verhinderte.
* Die Unterstützung für `<listObject>` wurde in mehreren Funktionen geändert.

## Version August 2023 {#aug-rn-2023}

### Verbesserungen {#aug-2023-improvements}

* Sie können jetzt API-Aufrufantworten in benutzerdefinierten Aktionen nutzen und Ihre Journey basierend auf diesen Antworten koordinieren. Diese Funktion ist als private Betaversion verfügbar. Weitere Informationen finden Sie in der [Dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/action-journeys/action-response.html?lang=de){target="_blank"} zu Journey Optimizer.

## Version April 2023 {#apr-rn-2023}

### Verbesserungen {#april-2023-improvements}

* Das Layout des Konfigurationsbereichs, der in Aktionen, Datenquellen, Ereignissen und Journeys angezeigt wird, wurde verbessert.
* Sie können jetzt in Ihren benutzerdefinierten Aktionen statische oder dynamische Abfrageparameter definieren. Weitere Informationen finden Sie in der [Dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/action-journeys/about-custom-action-configuration.html?lang=de#url-configuration){target="_blank"} zu Journey Optimizer.
* Neue Limits zur Steuerung des Wachstums von Erlebnissen, die von Journeys bereitgestellt werden:
   * Es wird empfohlen, die Anzahl der Knoten auf maximal 50 zu begrenzen, um die Leistung, Lesbarkeit, Qualitätssicherung und Fehlerbehebung ihrer Journeys zu verbessern. Die Anzahl der Aktivitäten wird im linken oberen Bereich der Journey-Arbeitsfläche angezeigt. Weitere Informationen finden Sie in der [Dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html?lang=de#journeys-guardrails-journeys){target="_blank"} zu Journey Optimizer
   * Wenn Sie Journeys entwickeln und starten, benachrichtigen wir Sie, sobald Sie sich dem Meilenstein von 100 Live-Journeys nähern. Sollten Sie mehr als 100 Journeys benötigen, erstellen Sie bitte ein Support-Ticket, nachdem Sie die Benachrichtigung erhalten haben. Wir helfen Ihnen gerne weiter. Weitere Informationen finden Sie in der [Dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html?lang=de#journeys-guardrails-journeys){target="_blank"} zu Journey Optimizer

## Version März 2023 {#mar-2023}

### Verbesserungen {#mar-2023-improvements}

* Die neue **Einschränkungs-API** ermöglicht es Ihnen, ein Limit für die Anzahl der pro Sekunde gesendeten Ereignisse festzulegen, wodurch überlastende Traffic-Spitzen auf Ihren externen Systemen oder in Ihrer API verhindert werden. Wenn das festgelegte Limit erreicht ist, werden alle nachfolgenden API-Aufrufe in der Reihenfolge, in der sie empfangen wurden, in die Warteschlange gestellt und so bald wie möglich verarbeitet. Beachten Sie, dass diese Funktion nur eine Einschränkungskonfiguration für alle Sandboxes unterstützt. [Weitere Informationen](../api/throttling.md)
* Die Journey-Arbeitsfläche wurde verbessert, um das Benutzererlebnis zu vereinfachen und zu verbessern. Am Ende jedes Pfads auf der Arbeitsfläche wurden die leeren Platzhalter entfernt. Sie können Ihre Aktivitäten jetzt einfach hinzufügen, indem Sie sie an das Ende eines Pfads ziehen.
* Auf der Journey-Arbeitsfläche ist der Namen der vorherigen Aktivität nicht mehr automatisch als Titel des **Ende**-Tags festgelegt. Benutzerinnen und Benutzer können bei Bedarf manuell eine benutzerdefinierte Bezeichnung hinzufügen.
* Die standardmäßige Zeitüberschreitungs- und Fehlerdauer in den Journey-Eigenschaften wurde von 5 auf 30 Sekunden geändert. Weitere Informationen finden Sie in der [Dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/external-systems/external-systems.html?lang=de#timeout){target="_blank"} zu Journey Optimizer.
* Dem Testmodus wurde ein Schutzmechanismus hinzugefügt, der nur Ereignisse überwacht, die über die Oberfläche gesendet werden. Ereignisse, die über ein externes Tool gesendet werden, werden nicht berücksichtigt. Weitere Informationen finden Sie in der [Dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/testing-the-journey.html?lang=de){target="_blank"} zu Journey Optimizer.

## Version Februar 2023 {#feb-2023}

### Verbesserungen {#feb-2023-improvements}

* Das Feld **Wartezeit bis zum erneuten Eintritt** wurde zu den Journey-Eigenschaften hinzugefügt. In diesem Feld kann die Wartezeit definiert werden, bevor es einem Profil erlaubt wird, in unitären Journeys erneut in die Journey einzutreten (beginnend mit einem Ereignis oder einer Segmentqualifikation). Dadurch wird verhindert, dass Journeys fälschlicherweise mehrmals für dasselbe Ereignis ausgelöst werden. Standardmäßig ist das Feld auf 5 Minuten eingestellt. Weitere Informationen finden Sie in der [Dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html?lang=de#entrance){target="_blank"} zu Journey Optimizer.
* Es wurden Verbesserungen in Bezug auf die **Start- und Enddaten einer Journey** vorgenommen. Wenn kein Startdatum angegeben wurde, wird es jetzt automatisch zum Veröffentlichungszeitpunkt hinzugefügt. Dadurch können Profile beim Erreichen des Datums automatisch die Journey verlassen. Weitere Informationen finden Sie in der [Dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html?lang=de#dates){target="_blank"} zu Journey Optimizer.

## Version Januar 2023 {#jan-2023-release}

### Verbesserungen {#jan-2023-improvements}

* Beim Hinzufügen einer **Segmentqualifikation** in einer Journey ist der Namespace jetzt standardmäßig mit dem zuletzt verwendeten Namespace vorausgefüllt. Weitere Informationen finden Sie in der [Dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/about-journey-building/segment-qualification-events.html?lang=de#about-segment-qualification){target="_blank"} zu Journey Optimizer.
* Auf der Journey-Arbeitsfläche ist eine neue Schaltfläche in der Symbolleiste verfügbar, mit der Sie einen Screenshot Ihrer Journey herunterladen können.

## Version September 2022{#sept-2022-release}

### Neue Funktionen{#sept-2022-features}


<table>
<thead>
<tr>
<th><strong>Data Governance und Datenschutz</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Mit dem Governance-Framework Data Usage Labeling and Enforcement (DULE) kann Journey Orchestration jetzt Governance-Richtlinien von Adobe Experience Platform nutzen, um zu verhindern, dass sensible Felder durch benutzerdefinierte Aktionen in Drittanbieter-Systeme exportiert werden. Wenn das System in den benutzerdefinierten Aktionsparametern ein eingeschränktes Feld identifiziert, wird ein Fehler angezeigt, der die Veröffentlichung der Journey verhindert.</p>
<p>Die Verwendung von Data Usage Labeling and Enforcement (DULE) ist derzeit auf ausgewählte Kundinnen und Kunden beschränkt und wird in einer zukünftigen Version für alle Umgebungen bereitgestellt.</p>
<p>Weitere Informationen finden Sie in der <a href="https://experienceleague.adobe.com/docs/journey-optimizer/using/privacy/action-privacy.html?lang=de">Dokumentation</a> zu Journey Optimizer.
</td>
</tr>
</tbody>
</table>

### Verbesserungen{#sept-2022-improvements}

* Eine neue Sschutzmaßnahme wurde zu unitären Journeys hinzugefügt (beginnend mit einem Ereignis oder einer Segmentqualifikation), um zu verhindern, dass Journeys fälschlicherweise mehrfach für dasselbe Ereignis ausgelöst werden. Der erneute Profileintritt wird jetzt standardmäßig fünf Minuten lang vorübergehend blockiert. Weitere Informationen finden Sie in der [Dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html?lang=de#events-g){target="_blank"} zu Journey Optimizer.

### Weitere Änderungen{#sept-2022-other}

* Zur Performance-Verbesserung können Feldergruppen für Erlebnisereignisse nicht mehr in Journeys verwendet werden, die mit einer Segmentqualifikationsaktivität beginnen. Diese Änderung gilt nur für neue Journeys. Bestehende Journeys behalten das aktuelle Verhalten bei. Weitere Informationen finden Sie in der [Dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html?lang=de#expression-editor){target="_blank"} zu Journey Optimizer.

### Verbesserungen

* **Beenden einer Journey**: Auf der Journey-Arbeitsfläche wurde die Aktivität **Ende** aus der Palette entfernt. End-Tags werden jetzt standardmäßig am Ende jedes Pfades hinzugefügt und können nicht entfernt werden. Diese Verbesserung ermöglicht eine bessere Berichterstellung darüber, wo ein Kunde aus der Journey ausgestiegen ist, ohne dass die Person, die die Journey anwendet, Maßnahmen ergreifen muss. Weitere Informationen finden Sie in der [Dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/manage-journey/end-journey.html?lang=de){target="_blank"} zu Journey Optimizer.

* Die Option **Zeitzone des Profils** ist jetzt in den Journey-Eigenschaften standardmäßig deaktiviert. [Weitere Informationen](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/manage-journey/timezone-management.html?lang=de#timezone-from-profiles){target="_blank"}.

## Version Mai 2022 {#may-2022-release}

### Verbesserungen

* **Ausdruckseditor**: Die Funktion [Limit](../functions/functionlimit.md) wurde hinzugefügt, um die Anzahl der Elemente einer Liste zu begrenzen. Mit der Funktion [Sortierung](../functions/functionsort.md) können Sie jetzt ein Listenobjekt sortieren. Die Unterstützung von listObject wurde auch den Funktionen [distinct](../functions/functiondistinct.md) und [distinctWithNull](../functions/functiondistinctwithnull.md) hinzugefügt.

## Version März 2022 {#feb-2022-release}

### Verbesserungen

* Um im einheitlichen Profilschema unnötige Felder zu vermeiden, ist das Schema „Journey-Schrittereignisse“ nicht mehr standardmäßig für Profile aktiviert. Bei Bedarf können Sie es aktivieren. [Weitere Informationen](../building-journeys/sharing-overview.md)
* Neue Schrittereignisse im Zusammenhang mit Exportvorgängen werden jetzt von Journey Optimizer an Adobe Experience Platform gesendet. Beispiele für Abfragen wurden der Dokumentation hinzugefügt. [Weitere Informationen](../building-journeys/query-examples.md)

## Version Februar 2022 {#february-2022-release}

### Verbesserungen

* Um die Performance zu optimieren und unnötige Ressourcennutzung zu verhindern, wechseln alle Journeys im Testmodus, die seit einer Woche nicht ausgelöst wurden, wieder in den Entwurfsstatus. [Weitere Informationen](../building-journeys/testing-the-journey.md#important_notes)

## Version Januar 2022 {#january-2022-release}

### Verbesserungen

* Schrittereignisse von Journey Orchestration können jetzt mit anderen Datensätzen in [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=de){target="_blank"} verknüpft werden. Das Feld **profileID** im integrierten Schrittereignisschema einer Journey ist jetzt als Identitätsfeld definiert. [Weitere Informationen](../building-journeys/sharing-overview.md#integration-cja)
* Die Begrenzungsregel für Adobe Campaign Standard-Aktionen wurde in 4.000 Aufrufe/5 Minuten geändert. [Weitere Informationen](../action/working-with-adobe-campaign.md)

## Version Oktober 2021 {#october-2021-release}

### Verbesserungen

* **Ausdruckseditor** – Als Power-User stehen Ihnen jetzt Funktionen zur Verfügung, um mit Karten zu arbeiten. [Weitere Informationen](../expression/field-references.md)
* **Barrierefreiheit** – Es wurden Verbesserungen an der Barrierefreiheit vorgenommen. Die Barrierefreiheit von Journey Orchestration ist jetzt vollständig gewährleistet.
* **Sammlungen** – Arrays von Objekten, die Unterobjekte enthalten, werden nun unterstützt. [Weitere Informationen](../usecase/collections.md)
* **Monitoring** – Step-Ereignisse für Live-Journeys und den Testmodus wurden verbessert. Es wurden [neue Felder](../building-journeys/sharing-field-list.md#serviceevents) im Zusammenhang mit Profilexportvorgängen hinzugefügt. Um ein besseres Benutzererlebnis zu bieten, sind im Journey-Schrittereignisschema für Journey Orchestration die Schrittereignisfelder nun in verschiedene Kategorien unterteilt. Alle Felder für vorhergehende Schrittereignisse sind weiterhin in der Kategorie [stepEvents](../building-journeys/sharing-legacy-fields.md) verfügbar.

## Version September 2021 {#september-2021-release}

<table>
<thead>
<tr>
<th><strong>Dynamisches Übergeben von Datenlisten mithilfe benutzerdefinierter Aktionen</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Sie können jetzt Sammlungen oder eine Liste von Daten in Ihren benutzerdefinierten Aktionsparametern übergeben, die zur Laufzeit dynamisch gefüllt werden. Es werden zwei Arten von Sammlungen unterstützt: einfache Sammlungen und Objektsammlungen. Zuvor erstellte benutzerdefinierte Aktionen funktionieren weiterhin. </p>
<p>Weitere Informationen zu Sammlungen finden Sie in der <a href="../usecase/collections.md">entsprechenden Dokumentation</a>. </p>
<p>Der Filter und die Überschneidungsfunktionen wurden der Liste der im erweiterten Ausdruckseditor verfügbaren Funktionen hinzugefügt. Dies bietet mehr Möglichkeiten zum Filtern und Vergleichen von Sammlungen.</p>
<p>Lesen Sie die Dokumentation zu den Funktionen <a href="../functions/functionfilter.md">Filtern</a> und <a href="../functions/functionintersect.md">Überschneidung</a>.</p>
</td>
</tr>
</tbody>
</table>

### Verbesserungen

* Systemgenerierte Schemata und Datensätze, die während der Bereitstellung von Schrittereignissen erstellt wurden, befinden sich jetzt im schreibgeschützten Modus, um versehentliche Änderungen an kritischen Schemata zu verhindern. [Weitere Informationen](../building-journeys/sharing-overview.md)
* Sie können die Aktivität **Warten** eindeutig mit einer Bezeichnung benennen, die auf der Arbeitsfläche angezeigt wird. Die Bezeichnung wird auch in Reporting- und Testmodusprotokollen verwendet, um eindeutig zu identifizieren, was Sie tun. [Weitere Informationen](../building-journeys/using-the-journey-designer.md)
* Ihre Ereignisse und Aktionen sind jetzt schneller auffindbar, indem Sie Elemente in den Kategorien **Ereignisse** und **Aktion** mithilfe der Suche filtern. Orchestrierungsaktivitäten werden nicht mehr gefiltert. [Weitere Informationen](../building-journeys/using-the-journey-designer.md)
* Beim Definieren einer Ereignis-ID-Bedingung in einem regelbasierten Ereignis ist jetzt der Operator „enthält“ für Felder vom Typ Zeichenfolge verfügbar. [Weitere Informationen](../event/about-creating.md)

## Version August 2021 {#august-2021-release}

### Verbesserungen

**Journeys**

* **Dynamische Header** – Sie können jetzt dynamische Daten in HTTP-Header-Parametern übergeben. Diese Parameter können von den Integrationssystemen verwendet werden, die die HTTP-Aufrufe der Journey-Aktion empfangen, z. B. Zeitstempel oder Tracking-ID. [Mehr dazu](../action/url-configuration.md)
* **Dynamische URL-Pfade** – Sie können jetzt dynamische URL-Pfade für benutzerdefinierte Aktionen einrichten. [Mehr dazu](../action/url-configuration.md)

## Version Juli 2021 {#july-2021-release}

<table>
<thead>
<tr>
<th><strong>Nutzen von Schemabeziehungen</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Mit Adobe Experience Platform können Sie Beziehungen zwischen Schemata definieren, um einen Datensatz als Lookup-Tabelle für einen anderen zu verwenden. Journey Orchestration kann jetzt Daten aus einem verknüpften Schema nutzen.</p>
<p>Diese Felder sind bei der Konfiguration von unitären Ereignissen, in Journey-Bedingungen und bei der Personalisierung benutzerdefinierter Aktionen verfügbar.
<p>Weitere Informationen finden Sie in der <a href="../event/experience-event-schema.md#leverage_schema_relationships">ausführlichen Dokumentation</a>.</p>
</td>
</tr>
</tbody>
</table>

### Verbesserungen

* Das Feld **Aufbewahrungsfrist im Cache** wurde aus dem Konfigurationsbereich der Datenquelle entfernt. [Mehr dazu](../datasource/about-data-sources.md)

## Version Juni 2021 {#june-2021-release}

<table>
<thead>
<tr>
<th><strong> Adobe Campaign Classic-Integration</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Die Integration mit Adobe Campaign Classic ist jetzt allgemein verfügbar. Sie ermöglicht den Versand von E-Mails, Push-Benachrichtigungen und SMS unter Verwendung der Transaktionsnachrichten-Funktionen von Adobe Campaign v7 oder v8.</p>
<p>Die Verbindung zwischen der Journey Orchestration- und der Campaign-Instanz wird bei der Bereitstellung von Adobe eingerichtet.</p>
<p>Weitere Informationen finden Sie in der <a href="../action/acc-action.md">entsprechenden Dokumentation</a>.</p>
</td>
</tr>
</tbody>
</table>

### Verbesserungen

* Für externe Datenquellen wird jetzt automatisch eine Begrenzungsregel von 15 Aufrufen pro Sekunde festgelegt. [Mehr dazu](../about/external-systems.md#capping)
* Die einfachen und erweiterten Ausdruckseditoren unterstützen jetzt das XDM-Datumsformat.
* Im Journey-Listenbildschirm wurde ein neuer Filter hinzugefügt. Sie können jetzt nach Journey-Typ filtern: **[!UICONTROL Unitäres Ereignis]** oder **[!UICONTROL Segmentqualifikation]**. [Mehr dazu](../about/user-interface.md#section_lgm_hpz_pgb)
* Bei Live-Journeys zeigt der Journey-Eigenschaftenbildschirm jetzt das Veröffentlichungsdatum und den Namen des Benutzers an, der die Journey veröffentlicht hat. Diese Informationen sind auch verfügbar, wenn Sie die technischen Details der Journey kopieren. [Mehr dazu](../building-journeys/changing-properties.md#section_lgm_hpz_pgb)

## Version April 2021 {#april-2021-release}

### Verbesserungen

* Im Bildschirm **Ereigniskonfiguration** des Testmodus wird nun eine Dropdown-Liste für Felder angezeigt, bei denen eine Auflistung erwartet wird. Wählen Sie einfach einen der verfügbaren Werte aus. Dadurch werden Fehler beim Auslösen des Ereignisses vermieden, die auftreten können, wenn ein falscher Wert definiert ist. [Mehr dazu](../building-journeys/testing-the-journey.md#firing_events)

## Version März 2021 {#march-2021-release}

### Verbesserungen

* Es wurde ein neuer Status zu Journeys hinzugefügt. Wenn eine Journey beendet oder manuell geschlossen wird, wechselt ihr Status 30 Tage nach dem Schließen von **Geschlossen** zu **Beendet**. Dadurch können Sie inaktive Journeys leichter identifizieren und gleichzeitig sicherstellen, dass alle noch anwesenden Personen Zeit haben, die Journey zu beenden. [Mehr dazu](../building-journeys/journey.md#ending_a_journey)
* In den rechten Aktivitätsbereichen von Entwurfs-Journeys sind schreibgeschützte Felder jetzt standardmäßig ausgeblendet. Diese Vereinfachung der Oberfläche hilft Ihnen, Ihre Aktivitäten einfacher zu konfigurieren. Um sie anzuzeigen, klicken Sie auf das Symbol **Schreibgeschützte Felder anzeigen**, das in der oberen linken Ecke des Konfigurationsbereichs für die Aktivitäten verfügbar ist. [Mehr dazu](../building-journeys/using-the-journey-designer.md#configuration_pane)
* Im Testmodus wurde im Bildschirm **Ereigniskonfiguration** das Feld **Schlüssel**, das zur Definition der ID des Testprofils verwendet wird, in **Profilkennung** umbenannt, um das Benutzererlebnis zu verbessern. [Mehr dazu](../building-journeys/testing-the-journey.md).
* Bei Reaktionsereignissen kann die Dauer der maximalen Wartezeit jetzt nur mehr zwischen 40 Sekunden und 30 Tagen eingestellt werden. Beim Testen einer Journey, die ein Reaktionsereignis verwendet, beträgt der Standard- und Mindestwert der **[!UICONTROL Wartezeit]** für den Testmodus jetzt 40 Sekunden. [Mehr dazu](../building-journeys/reaction-events.md).

## Version Februar 2021 {#february-2021-release}

<table>
<thead>
<tr>
<th><strong>Profilaktivität aktualisieren</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Mit dieser neuen Aktivität können Sie ein vorhandenes Adobe Experience Platform-Profil mit Informationen aus dem Ereignis, aus einer Datenquelle oder mit einem bestimmten Wert aktualisieren.</p>
<p>Weitere Informationen finden Sie in der <a href="../building-journeys/update-profiles.md">entsprechenden Dokumentation</a>.</p>
</td>
</tr>
</tbody>
</table>

### Sonstige Verbesserungen 

* Beim Konfigurieren eines Ereignisses werden jetzt standardmäßig nur die für die XDM-Validierung erforderlichen Felder vorausgewählt. Die Auswahl dieser Felder kann nicht aufgehoben werden.
* In der Journey-Palette wurde ein neuer Filter hinzugefügt. Sie können damit neben den nativen nur die letzten fünf verwendeten Ereignisse und Aktionen anzeigen. Dies ist benutzerspezifisch. Standardmäßig werden alle Elemente angezeigt. [Mehr dazu](../building-journeys/using-the-journey-designer.md#palette)
* Beim Erstellen einer neuen Journey werden jetzt Elemente, die nicht als erster Schritt auf der Arbeitsfläche abgelegt werden können, ausgeblendet. Dies betrifft alle Aktionen, die Bedingungsaktivität, die Wartezeit und die Reaktion.
* Im linken Bereich des erweiterten Ausdruckseditors werden Funktionen nun am Ende der Liste unter dem Abschnitt **Funktionen** gruppiert dargestellt.

## Version Januar 2021 {#january-2021-release}

Bei der Auswahl eines Schemas in der Ereigniskonfiguration werden nur die Felder ausgewählt, die zwingend erforderlich sind, damit das Ereignis von Journey Orchestration korrekt empfangen werden kann. [Mehr dazu](../event/defining-the-payload-fields.md)

Attribute der Journey-Eigenschaften sind jetzt im einfachen Ausdruckseditor verfügbar. [Mehr dazu](../expression/journey-properties.md)

Es wurden zwei neue Attribute für Journey-Eigenschaften hinzugefügt (sandboxName und organizationId). [Mehr dazu](../expression/journey-properties.md)

Zur Anpassung an die SLAs von Adobe Campaign Standard wird jetzt automatisch eine Begrenzungsregel von 13 Aufrufen pro Sekunde für Adobe Campaign Standard-Aktionen definiert, sobald die Integration von Adobe Campaign Standard eingerichtet ist. [Mehr dazu](../action/working-with-adobe-campaign.md)

Die maximale Wartezeit des Ereignisses wird jetzt im Zeitüberschreitungspfad genauer angegeben. [Mehr dazu](../building-journeys/event-activities.md#listening-to-events-during-a-specific-time)

Die Funktionen [getListItem](../functions/functiongetlistitem.md) und [split](../functions/functionsplit.md) wurden der Liste der im erweiterten Ausdruckseditor verfügbaren Funktionen hinzugefügt. Dies bietet mehr Möglichkeiten in Ihren Anwendungsfällen zur Zeichenfolgenberechnung.

## Version November 2020 {#november-release}

<table>
<thead>
<tr>
<th><strong>Springen zwischen Journeys</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Mit einer neuen Aktionsaktivität können Sie Kontakte von einer Journey in eine andere bewegen. Die <strong>Sprungaktivität</strong> ermöglicht Ihnen Folgendes:
</p>
<ul>
<li>Vereinfachung der Gestaltung sehr komplexer Journeys durch Aufteilung in mehrere Journeys </li>
<li>Erstellung von Journeys anhand allgemeiner und wiederverwendbarer Journey-Muster</li>
</ul>
<p>Weitere Informationen finden Sie in der <a href="../building-journeys/jump.md">ausführlichen Dokumentation</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Verwenden der Journey-Eigenschaften im Ausdruckseditor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Im erweiterten Ausdruckseditor haben wir der Liste der Felder und Funktionen eine neue Kategorie hinzugefügt. Dabei handelt es sich um die Informationen, die das System von Live-Journeys abruft, wie z. B. die Journey-ID oder die aufgetretenen Fehler. Dadurch erhalten Sie beim Erstellen Ihrer Journeys mehr Möglichkeiten. Beispielsweise können Sie Systeme von Drittanbietern auf Fehler aufmerksam machen, die in einer Bedingung oder Aktion auftreten.
</p>
<p>Weitere Informationen finden Sie in der <a href="../expression/journey-properties.md">entsprechenden Dokumentation</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Regelbasierte Ereignisse (Beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Es gibt jetzt eine neue Methode, um Ihre Ereignisse einfacher einzurichten, ohne eine EventID zu verwenden: Regelbasierte Ereignisse werten aus, ob ein Ereignis gemäß einer Bedingung ausgelöst werden soll. Sie können weiterhin die vorhandene Methode verwenden, die jetzt als „systemgeneriert“ bezeichnet wird. Diese Funktion, die über das Alpha-Programm bei einer begrenzten Anzahl von Kunden getestet wurde, ist jetzt für alle Kunden in der Betaversion verfügbar.
</p>
</td>
</tr>
</tbody>
</table>

### Sonstige Verbesserungen 

Beim Erstellen neuer Versionen einer Journey wurden Einschränkungen hinzugefügt. Diese Einschränkungen vermeiden zu drastische Änderungen an der Journey, um eine gewisse Konsistenz zwischen den Versionen zu erhalten. [Mehr dazu](../about/limitations.md#journey-versions-limitations)

Die Aktivität **Segmentqualifikation** kann nicht mehr in einer Journey verwendet werden, die Nachrichtenaktivitäten in Campaign Standard enthält. Diese Einschränkung schützt die Integrität von Adobe Campaign Standard-Instanzen. In der Tat kann die Verwendung der Segmentqualifikation zu täglichen Spitzenwerten beim Nachrichtenversand führen, die die Transaktionsnachrichtenübermittlung in Campaign Standard überlasten würden. [Mehr dazu](../about/limitations.md#segment-qualification)

## Version Oktober 2020 {#october-release}

<table>
<thead>
<tr>
<th><strong>Maximale Wartezeit für Ereignisse</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Sie können jetzt eine maximale Wartezeit für ein Ereignis konfigurieren, damit eine Journey ein Ereignis nur während einer bestimmten Zeit überwacht. Dazu müssen Sie nicht mehr parallel zum Ereignispfad eine Warteaktivität hinzufügen.
</p>
<p>Weitere Informationen finden Sie in der <a href="../building-journeys/event-activities.md#listening-to-events-during-a-specific-time">entsprechenden Dokumentation</a>.</p>
</td>
</tr>
</tbody>
</table>

### Sonstige Verbesserungen 

* Wenn Sie eine neue Version einer Journey veröffentlichen, endet die vorherige Version automatisch und wechselt in den Status „Geschlossen“. [Mehr dazu](../building-journeys/journey-versions.md)

## Version September 2020 {#september-release}

### Allgemein verfügbare Updates{#september-ga-update}

<table>
<thead>
<tr>
<th><strong>Verbesserungen bei der Bedingungsaktivität</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Wenn Sie Bedingungen zu Ihrer Journey hinzufügen, können Sie jetzt einen Titel definieren. Wenn Sie mehrere Bedingungen in einer Journey verwenden, können Sie diese so leichter identifizieren.
</p>
<p>Weitere Informationen finden Sie in der <a href="../building-journeys/condition-activity.md#about_condition">entsprechenden Dokumentation</a>.</p>
</td>
</tr>
</tbody>
</table>

### Alpha-Updates{#september-alpha-update}

<table>
<thead>
<tr>
<th><strong>Verbesserungen bei der Segment-Lese-Aktivität</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Folgende Verbesserungen wurden an der Aktivität <strong>Segment lesen</strong> vorgenommen:
</p>
<ul>
<li><p>Segmentbasierte Journeys zeigen nun über der Arbeitsfläche eine Erinnerung an den Zeitplantyp der Journey an. Sie können auf diese Erinnerung klicken, um das Menü für die Konfiguration des Zeitplans aufzurufen.</p>
</li>
<li><p>Die Granularität der Testmodusprotokolle wurde verbessert, um den Fortschrittsstatus des Segmentexports anzuzeigen.</p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

## Version August 2020 {#august-release}

### Allgemein verfügbare Updates{#august-ga-update}

Die Payload von Segmentqualifkationsereignissen enthält jetzt die folgenden in Bedingungen und Aktionen verwendbaren Kontextinformationen: Verhalten (Eintreten, Verlassen), Zeitstempel der Qualifikation und Segmentkennung. [Mehr dazu](../building-journeys/segment-qualification-events.md)

### Alpha-Updates{#august-alpha-update}

<table>
<thead>
<tr>
<th><strong>Segmentauslöser-Aktivität</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Folgende Verbesserungen wurden an der Segmentauslöser-Aktivität vorgenommen:
</p>
<ul>
<li><p>Der Name der Aktivität wurde in „Segment lesen“ geändert. </p>
</li>
<li><p>Die Konfiguration der Journey-Planung wurde aus den Eigenschaften der Aktivität entfernt. Sie ist jetzt direkt über die Eigenschaften der Journey in einem eigenen Bereich aufrufbar, der angezeigt wird, wenn eine „Segment lesen“-Aktivität auf der Arbeitsfläche abgelegt wurde. </p>
</li>
<li><p>Sie können die Journey jetzt auf einem unitären Profil testen und den Fortschritt der Journey über den visuellen Verlauf verfolgen.</p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Regelbasierte Ereignisse</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Die folgenden Verbesserungen wurden an regelbasierten Ereignissen vorgenommen:
</p>
<ul>
<li><p>Sie können jetzt alle verhaltensbezogenen Ereignisdaten, die Sie in Adobe Analytics bereits erfassen und an Platform streamen, zum Auslösen von Journeys und zur Automatisierung von Erlebnissen für Ihre Kunden nutzen. <a href="../event/about-analytics.md">Mehr dazu</a></p>
</li>
<li><p>Beim Auslösen eines regelbasierten Ereignisses im Testmodus können Sie jetzt die Ereignis-ID-Bedingung direkt anzeigen. Außerdem ist jetzt neben jedem Feld, das Teil der Regelauswertung ist, eine QuickInfo verfügbar. <a href="../building-journeys/testing-the-journey.md#test-rule-based">Mehr dazu</a></p>
</li>
<li><p>Der Bildschirm zur Definition regelbasierter Ereignisse wurde zur Optimierung der Benutzerumgebung neu organisiert. <a href="../event/about-creating.md">Mehr dazu</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

## Alpha-Version – Juli 2020 {#alpha-release---july-2020}

Das Alpha-Programm bietet Funktionen, die derzeit von einer begrenzten Anzahl von Kunden getestet werden. Dies ermöglicht es uns, unser Produkt basierend auf dem erhaltenen Feedback zu verbessern. Diese Funktionen stehen nicht allen Kunden von Journey Orchestration zur Verfügung.

<table>
<thead>
<tr>
<th><strong>Verbesserte Benutzeroberfläche</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Die Navigation innerhalb der Menüs von Journey Orchestration wurde dahingehend verbessert, dass sie an die Benutzeroberfläche von Adobe Experience Platform angeglichen wurde:
</p>
<ul>
<li><p>Die Menüs wurden von der oberen zur linken Seite der Benutzeroberfläche verschoben. </p>
</li>
<li><p>Gruppierung der Admin-Funktionen in einem einzigen Dashboard.</p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Segmentauslöser-Aktivität</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Mit der Segmentauslöser-Aktivität können Sie alle Kontakte, die zu einem Adobe Experience Platform-Segment gehören, in eine Journey eintreten lassen. Der Eintritt in eine Journey kann entweder einmalig oder regelmäßig erfolgen. 
</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Regelbasierte Ereignisse</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Die Einrichtung von Erlebnisereignissen wurde vereinfacht. Bei der neuen Methode muss keine eventID verwendet werden. Wenn Sie Ihr Ereignis in Journey Orchestration einrichten, können Sie jetzt ein regelbasiertes Ereignis definieren. <a href="../event/about-events.md">Mehr dazu</a>
</p>
</td>
</tr>
</tbody>
</table>


## Version 2. Quartal – Juni 2020 {#q2-release---june-2020}

<table>
<thead>
<tr>
<th><strong>Verbesserungen bei der Adobe Experience Platform-Integration</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>An der Adobe Experience Platform-Integration wurden folgende Verbesserungen vorgenommen:</p>
<ul>
<li><p>Eine neue Aktivität ermöglicht das Überwachen von Eintritten/Austritten in Adobe Experience Platform-Segmenten, um Personen dazu zu bringen, in eine Journey einzutreten oder in einer Journey fortzufahren. <a href="../building-journeys/segment-qualification-events.md">Mehr dazu</a></p>
<img src="../assets/rn-segment7.png"/>
</li>
<li><p>Adobe Experience Platform-Segmente können jetzt erstellt und bearbeitet werden, ohne dass Sie die Benutzeroberfläche von Journey Orchestration verlassen müssen. Dafür sorgt ein neuer <strong>Segmente</strong>-Tab. <a href="../segment/about-segments.md">Mehr dazu</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>Im einfachen Ausdruckseditor werden Adobe Experience Platform-Segmente jetzt direkt in der Navigationsstruktur aufgeführt, um eine einfache Einrichtung von Bedingungen wie „Gehört diese Person zu Segment A?“ zu ermöglichen. <a href="../segment/using-a-segment.md">Mehr dazu</a></p>
<img src="../assets/rn-segment4.png"/>
</li>
<li><p>Journey Orchestration leitet nun die bei den Journeys ausgeführten Schritte automatisch an Adobe Experience Platform weiter. Dazu gehören potenziell auch Fehler. Diese Informationen können für die Berichterstellung und Fehlerbehebung verwendet werden, indem Abfragen zu den Journey-Schrittereignissen für eine bestimmte Journey oder für alle Journeys ausgeführt werden. <a href="../building-journeys/sharing-overview.md">Mehr dazu</a></p>
<img src="../assets/rn-journeystepevent.png"/>
</li>
<li><p>Journey Orchestration kann jetzt mit der Adobe Experience Platform-Sandbox für Produktion und Nicht-Produktion verbunden werden. Beachten Sie, dass Sandboxes eine Funktion der Betaversion sind. <a href="../about/access-management.md#sandboxes">Mehr dazu</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Verbesserungen beim Journey-Designer und Testmodus</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Am Journey-Designer und Testmodus wurden folgende Verbesserungen vorgenommen:</p>
<ul>
<li><p>Sie können jetzt Aktivitäten aus einer Journey kopieren und in eine andere einfügen, indem Sie eine oder N Journey-Aktivitäten auswählen. <a href="../building-journeys/using-the-journey-designer.md#copy-paste">Mehr dazu</a></p>
<img src="../assets/rn-copy-paste1.png"/>
</li>
<li><p>Nach Auslösung eines Ereignisses, damit ein Testprofil in eine Journey eintritt, können Sie nun anhand eines farbigen Verlaufs den Fortschritt der Journey anzeigen. Bei Fehlern in der Journey werden auch Fehlerdetails angezeigt. <a href="../building-journeys/testing-the-journey.md#firing_events">Mehr dazu</a></p>
<img src="../assets/rn-journeytest6.png"/>
</li>
<li>Der Journey-Status <strong>Beendet</strong> wurde in <strong>Geschlossen (kein Eintritt)</strong>umbenannt, um besser zu kennzeichnen, was dieser Status bedeutet.</li>
</ul>
</td>
</tr>
</tbody>
</table>

**Sonstige Verbesserungen**

Um ein Senden zu vieler API-Aufrufe an Drittanbietersysteme zu vermeiden, führen wir eine neue öffentliche API für die Einrichtung von Begrenzungsregeln ein. Mit Begrenzungsregeln können Sie eine maximale Anzahl von Aufrufen an einen API-Endpunkt pro Millisekunde festlegen. [Mehr dazu](../api/capping.md)

Die Zugriffskontrolle ermöglicht nun eine größere Granularität bei der Verwaltung des Benutzerzugriffs. Tatsächliche Verfügbarkeit: 30. Juni 2020. [Mehr dazu](../about/access-management.md#create-product-profile)

Journey Orchestration ist jetzt im Raum APAC verfügbar (australisches Rechenzentrum). Tatsächliche Verfügbarkeit: 30. Juni 2020

Die Benutzeroberfläche von Journey Orchestration ist auf Japanisch verfügbar.

## Version 1. Quartal – März 2020 {#q1-release---march-2020}

<table>
<thead>
<tr>
<th><strong>Verbesserungen am Testmodus</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Die folgenden Verbesserungen wurden am Testmodus vorgenommen:</p>
<ul>
<li>Wenn in einer Journey mehrere Ereignisse verwendet werden, können diese jetzt einzeln ausgelöst werden, indem Sie sie im Testmodus im Bildschirm <strong>Ereigniskonfiguration</strong> aus einer Dropdown-Liste auswählen. <a href="../building-journeys/testing-the-journey.md#firing_events">Mehr dazu</a></p></li>
<li><p>Wenn in einer Journey eine oder mehrere <strong>Warteaktivitäten</strong> verwendet werden, können Sie jetzt festlegen, wie lange diese Aktivitäten im Testmodus dauern sollen. Der Standardwert ist 10 Sekunden. Sie können diese mithilfe des Parameters <strong>Wartezeit im Test</strong> unten links ändern. <a href="../building-journeys/testing-the-journey.md">Mehr dazu</a></p><img src="../assets/rn-test.png"/>
</li>
<li>In den <strong>Testprotokollen</strong> werden bei einem Fehler beim Aufrufen eines Drittanbietersystems (Datenquelle oder Aktion) der Fehlercode und die Fehlerantwort angezeigt. <a href="../building-journeys/testing-the-journey.md#viewing_logs">Mehr dazu</a>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Zentrales Zeitzonen-Management</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>Das Zeitzonen-Management ist jetzt gebündelt im Panel der Journey-Eigenschaften verfügbar. In den Eigenschaften der Journey wurden zwei Parameter hinzugefügt:</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li>In der Dropdown-Liste <strong>Zeitzone</strong> können Sie eine bestimmte Zeitzone auswählen. Standardmäßig wird die Zeitzone des Browsers verwendet. </li>
<li>Sofern verfügbar, können Sie mit dem Kontrollkästchen <strong>Zeitzone des Profils</strong> die Zeitzone des Adobe Experience Platform-Profils der Person verwenden, die in die Journey eintritt. Andernfalls wird die in der Dropdown-Liste definierte Zeitzone verwendet. Diese Funktion ist nicht mit Journeys kompatibel, die Ereignisse ohne Namespace verwenden.</li>
</ul>
<p>Weitere Informationen finden Sie in den Abschnitten <a href="../building-journeys/changing-properties.md#timezone">Ändern von Eigenschaften</a> und <a href="../building-journeys/timezone-management.md">Zeitzonen-Management</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Verbesserungen am Journey-Designer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>Die <strong>Palette</strong> „Journey“ auf der linken Seite im Journey-Designer wurde erweitert:</p>
<ul>
<li>Mit einem neuen Symbol neben der <strong>Suchleiste</strong> können Sie nicht verfügbare Elemente in der Palette ein- oder ausblenden (z. B. Ereignisse, die einen anderen Namespace als den in Ihrer Journey verwenden). Standardmäßig werden nicht verfügbare Elemente ausgeblendet.</li>
<li>Wenn Sie das Feld <strong>Suchen</strong> verwenden, wird jetzt die Anzahl der Ergebnisse für jede Aktivitätskategorie der Arbeitsfläche angezeigt.</li>
<li>Die Navigation zwischen den verschiedenen Aktivitätskategorien wurde verbessert.</li>
</ul>
<p>Im Journey-Designer können Sie jetzt feststellen, ob Sie auf die aktuelle Version der Journey zugreifen. Diese Information wird neben der Versionsnummer angezeigt.</p>
<p>Wenn zwei Aktivitäten auf der <strong>Arbeitsfläche</strong> einer Journey getrennt werden, wird jetzt eine Warnmeldung angezeigt.</p>
<img src="../assets/rn-canvas.png"/>
<p>Weitere Informationen finden Sie in der <a href="../building-journeys/using-the-journey-designer.md">entsprechenden Dokumentation</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Kontextuelle Hilfe</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>In den verschiedenen Listenbildschirmen (Journeys, Ereignisse, Aktionen und Datenquellen) von Journey Orchestration ist jetzt eine kontextuelle Hilfe verfügbar. Auf diese Weise können Sie eine kurze Beschreibung der aktuellen Funktion anzeigen und auf zugehörige Artikel und Videos zugreifen.</p>
<p>Durch Anklicken des <img src="../assets/icon-context.png"/>-Symbols oben rechts im Bildschirm können Sie die kontextuelle Hilfe anzeigen. </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**Sonstige Verbesserungen**

* Zusätzlich zu den USA ist Journey Orchestration jetzt in der Region **EMEA** verfügbar. Die Anwendung und die Dokumentation sind in Französisch und Deutsch verfügbar.

* Experience League ist jetzt in das Produkt integriert. Dies vereinfacht den Zugriff auf verwandte Inhalte und hilft Ihnen, Experience Cloud optimal zu nutzen. Unten im Tab „Hilfe“ können Sie direkt auf die Dokumentation für Journey Orchestration zugreifen. Zusätzlich können Sie unter Hilfe > Feedback Probleme melden oder Ihre Ideen mit Adobe teilen.

* Der Tastaturbefehl **C**, mit dem Sie ein neues Element erstellen können, ist jetzt in allen Listenbildschirmen verfügbar: Journeys, Datenquellen, Aktionen und Ereignisse. [Mehr dazu](../about/user-interface.md#section_ksq_zr1_ffb)

* Sie können jetzt gestoppte Journeys **löschen**. Berichte für diese gelöschten Journeys werden nicht mehr verfügbar sein.

* Beim Durchsuchen von **Adobe Experience Platform-Feldern** (XDM-Format) wird nun neben dem Feldnamen der Anzeigename angezeigt. Diese Informationen werden aus der Schemadefinition im Experience-Datenmodell abgerufen. Wenn verfügbar, wird der alternative Anzeigename angezeigt. Mit dieser benutzerfreundlichen Beschreibung, die insbesondere bei eVar-Feldern nützlich ist, können Sie Ihre Felder leichter wiedererkennen. [Mehr dazu](../about/user-interface.md#friendly-names-display)

## Allgemein verfügbare Version – Dezember 2019 {#ga-release---december-2019}

Journey Orchestration ist jetzt allgemein verfügbar.

Journey Orchestration ermöglicht die Erstellung von Anwendungsfällen für die Echtzeit-Orchestrierung mithilfe von kontextuellen Daten aus Ereignissen oder Datenquellen.

Journey Orchestration erlaubt eine Echtzeit-Orchestrierung auf Basis von kontextuellen Daten aus Ereignissen, Informationen aus Adobe Experience Platform oder Daten aus API-Diensten von Drittanbietern. Die Anwendung bestimmt in mehrstufigen Flüssen, die Journeys genannt werden, je nach Profil und Verhalten des Benutzers die nächsten für den Kunden optimalen Aktionen. Dies umfasst sowohl den besten Zeitpunkt als auch die Art der Aktion, z. B. das Senden einer Push-Benachrichtigung über die Transaktionsnachrichtenfunktion von Adobe Campaign Standard (Adobe Campaign Standard erforderlich) oder das Benachrichtigen eines Drittanbietersystems. Diese Entscheidungen werden auf Grundlage von Regeln und Sensei-Werten getroffen.

[Weitere Informationen](../action/working-with-adobe-campaign.md) zu Journey Orchestration.
