---
product: adobe campaign
title: Versionshinweise
description: Versionshinweise
feature: Journeys
role: User
level: Beginner
exl-id: b923f7e3-997b-483b-b6ac-eef62fc81a84
source-git-commit: a60640f91e80becd2769d647b762ca2225f9e9b2
workflow-type: ht
source-wordcount: '2971'
ht-degree: 100%

---

# Versionshinweise {#release-notes}

Auf dieser Seite werden alle neuen Funktionen und Verbesserungen bei Journey Orchestration aufgelistet.
Sie können auch die neusten [Aktualisierungen der Dokumentation](../release-notes/documentation-updates.md) einsehen.

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
<p>Sie können jetzt Kollektionen oder eine Liste von Daten in Ihren benutzerdefinierten Aktionsparametern übergeben, die zur Laufzeit dynamisch gefüllt werden. Es werden zwei Arten von Kollektionen unterstützt: einfache Kollektionen und Objektkollektionen. Zuvor erstellte benutzerdefinierte Aktionen funktionieren weiterhin. </p>
<p>Weitere Informationen zu Kollektionen finden Sie in der <a href="../usecase/collections.md">entsprechenden Dokumentation</a>. </p>
<p>Der Filter und die Überschneidungsfunktionen wurden der Liste der im erweiterten Ausdruckseditor verfügbaren Funktionen hinzugefügt. Dies bietet mehr Möglichkeiten zum Filtern und Vergleichen von Kollektionen.</p>
<p>Lesen Sie die Dokumentation zu den Funktionen <a href="../functions/functionfilter.md">Filtern</a> und <a href="../functions/functionintersect.md">Überschneidung</a>.</p>
</td>
</tr>
</tbody>
</table>

### Verbesserungen

* Systemgenerierte Schemas und Datensätze, die während der Bereitstellung von Schrittereignissen erstellt wurden, befinden sich jetzt im schreibgeschützten Modus, um unbeabsichtigte Änderungen an kritischen Schemas zu verhindern. [Weitere Informationen](../building-journeys/sharing-overview.md)
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
<p>Mit Adobe Experience Platform können Sie Beziehungen zwischen Schemas definieren, um einen Datensatz als Lookup-Tabelle für einen anderen zu verwenden. Journey Orchestration kann jetzt Daten aus einem verknüpften Schema nutzen.</p>
<p>Diese Felder sind bei der Konfiguration von unitären Ereignissen, in Journey-Bedingungen und bei der Personalisierung benutzerdefinierter Aktionen verfügbar.
<p>Weitere Informationen finden Sie in der <a href="../event/experience-event-schema.md#leverage_schema_relationships">entsprechenden Dokumentation</a>.</p>
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
<p>Weiterführende Informationen finden Sie im <a href="../building-journeys/jump.md">entsprechenden Handbuch</a> und im <a href="https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html?lang=de">Anleitungsvideo</a>.</p>
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
<p>Im erweiterten Ausdruckseditor haben wir der Liste der Felder und Funktionen eine neue Kategorie hinzugefügt. Dabei handelt es sich um die Informationen, die das System von Live-Journeys abruft, wie z. B. die Journey-ID oder die spezifischen aufgetretenen Fehler. Dadurch erhalten Sie beim Erstellen Ihrer Journeys mehr Möglichkeiten. Beispielsweise können Sie Systeme von Drittanbietern auf Fehler aufmerksam machen, die in einer Bedingung oder Aktion auftreten.
</p>
<p>Weitere Informationen finden Sie in der <a href="../expression/journey-properties.md">entsprechenden Dokumentation</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Regelbasierte Ereignisse           (Betaversion)</strong><br/></th>
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
<li><p>Wenn in einer Journey eine oder mehrere <strong>Warteaktivitäten</strong> verwendet werden, können Sie jetzt festlegen, wie lange diese Aktivitäten im Testmodus dauern sollen. Die standardmäßige Dauer beträgt 10 Sekunden. Sie können diese mithilfe des Parameters <strong>Wartezeit im Test</strong> unten links ändern. <a href="../building-journeys/testing-the-journey.md">Mehr dazu</a></p><img src="../assets/rn-test.png"/>
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
<th><strong>Kontexthilfe</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>In den verschiedenen Listenbildschirmen (Journeys, Ereignisse, Aktionen und Datenquellen) von Journey Orchestration ist jetzt eine Kontexthilfe verfügbar. Auf diese Weise können Sie eine kurze Beschreibung der aktuellen Funktion anzeigen und auf zugehörige Artikel und Videos zugreifen.</p>
<p>Durch Anklicken des <img src="../assets/icon-context.png"/>-Symbols oben rechts im Bildschirm können Sie die Kontexthilfe anzeigen. </p>
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

Journey Orchestration ermöglicht die Erstellung von Anwendungsfällen für die Echtzeit-Orchestrierung mithilfe von Kontextdaten aus Ereignissen oder Datenquellen.

Journey Orchestration erlaubt eine Echtzeit-Orchestrierung auf Basis von Kontextdaten aus Ereignissen, Informationen aus Adobe Experience Platform oder Daten aus API-Diensten von Drittanbietern. Die Anwendung bestimmt in mehrstufigen Flüssen, die Journeys genannt werden, je nach Profil und Verhalten des Benutzers die nächsten für den Kunden optimalen Aktionen. Dies umfasst sowohl den besten Zeitpunkt als auch die Art der Aktion, z. B. das Senden einer Push-Benachrichtigung über die Transaktionsnachrichtenfunktion von Adobe Campaign Standard (Adobe Campaign Standard erforderlich) oder das Benachrichtigen eines Drittanbietersystems. Diese Entscheidungen werden auf Grundlage von Regeln und Sensei-Werten getroffen.

[Weitere Informationen](../action/working-with-adobe-campaign.md) zu Journey Orchestration.

Zusätzliche Ressourcen:

* [Tutorials](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/introduction.html?lang=de)
* [Community](https://www.adobe.com/go/journeyorchestrationcommunity_de)
