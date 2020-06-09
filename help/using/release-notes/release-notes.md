---
title: Versionshinweise
description: Versionshinweise
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
source-git-commit: 4e850db61aa55c9bff448a0280f79810928cb6ec
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 70%

---


# Versionshinweise {#release-notes}

Auf dieser Seite werden alle neuen Funktionen und Verbesserungen bei Journey Orchestration aufgelistet.
Sie können auch den Abschnitt [Aktualisierungen der Dokumentation](../release-notes/documentation-updates.md) lesen.

## Q2-Version - Juni 2020 {#q2-release---june-2020}

<table>
<thead>
<tr>
<th><strong>Verbesserungen der Adobe Experience Platform-Integration</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Die folgenden Plattformintegrationsverbesserungen wurden vorgenommen:</p>
<ul>
<li><p>Eine neue Aktivität ermöglicht das Listening von Eingängen/Ausstiegen in Plattformsegmenten, um Menschen dazu zu bewegen, in eine Reise einzusteigen oder sich vorwärts zu bewegen. <a href="../building-journeys/event-activities.md#segment-qualification">mehr dazu</a></p>
<img src="../assets/rn-segment7.png"/>
</li>
<li><p>Plattformsegmente können jetzt erstellt und bearbeitet werden, ohne die Benutzeroberfläche für die Journey-Orchestrierung zu verlassen, dank einer neuen Registerkarte " <strong>Segmente</strong> ".<a href="../segment/about-segments.md">mehr dazu</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>Im einfachen Ausdruck-Editor werden Plattformsegmente jetzt direkt in der Navigationsstruktur aufgeführt, um eine einfache Einrichtung von Bedingungen wie "Gehört diese Person zu Segment A?"zu ermöglichen.<a href="../segment/using-a-segment.md">mehr dazu</a></p>
<img src="../assets/rn-segment4.png"/>
</li>
<li><p>Die Journey Orchestration leitet nun automatisch die Schritte, die auf Reisen ausgeführt werden, an die Adobe-Datenplattform weiter. Dazu gehören potenzielle Fehler. Diese Informationen können für die Erzielung von Berichte und Fehlerbehebung verwendet werden, indem Abfragen auf den Ereignissen für Reiseschritte für eine bestimmte Reise oder für alle Reisen ausgeführt werden. <a href="../building-journeys/sharing-overview.md">mehr dazu</a></p>
<img src="../assets/rn-journeystepevent.png"/>
</li>
</li>
<li><p>Die Journey Orchestration kann nun an die Plattform-Sandboxen für Produktion und Nicht-Produktion angeschlossen werden. Beachten Sie, dass Sandboxen eine Beta-Funktion sind. Wirksame Verfügbarkeit: 30. Juni 2020. <a href="../about/access-management.md#sandboxes">mehr dazu</a></p>
</li>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Verbesserungen beim Reisedesigner und Testmodus</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Die folgenden Verbesserungen wurden beim Reisedesigner und im Testmodus vorgenommen:</p>
<ul>
<li><p>Sie können jetzt Aktivitäten aus dem Einfügen von einer Reise in eine andere kopieren und eine oder N-Reise-Aktivität auswählen. <a href="../building-journeys/using-the-journey-designer.md#copy-paste">mehr dazu</a></p>
<img src="../assets/rn-copy-paste1.png"/>
</li>
<li><p>Nachdem Sie ein Ereignis ausgelöst haben, um ein Profil auf eine Reise zu bringen, können Sie nun anhand eines farbigen Sichtablaufs den Verlauf der Reise sehen. Bei Fehlern auf der Reise werden auch Details zu Fehlern angezeigt. <a href="../building-journeys/testing-the-journey.md#firing_events">mehr dazu</a></p>
<img src="../assets/rn-journeytest6.png"/>
</li>
<li>Der Status " <strong>Fertig</strong> "wurde in " <strong>geschlossen (kein Eingang)</strong> "umbenannt, um besser widerzuspiegeln, was dieser Status bedeutet.</li>
</ul>
</td>
</tr>
</tbody>
</table>

**Sonstige Verbesserungen**

Um zu viele API-Aufrufe an Drittanbietersysteme zu vermeiden, führen wir eine neue öffentliche API ein, um &quot;Capping&quot;-Regeln einzurichten. Durch die Begrenzung können Sie eine maximale Anzahl von Aufrufen an einen API-Endpunkt pro Millisekunden definieren. [mehr dazu](../api/capping.md)

Zugriffskontrolle ermöglicht nun eine größere Granularität bei der Verwaltung des Benutzerzugriffs. Wirksame Verfügbarkeit: 30. Juni 2020. [mehr dazu](../about/access-management.md#create-product-profile)

Journey Orchestration ist jetzt in APAC (Australisches Rechenzentrum) erhältlich. Wirksame Verfügbarkeit: 30. Juni 2020

Die Benutzeroberfläche für die Journey-Orchestrierung ist auf Japanisch verfügbar.

## Version 1. Quartal – März 2020 {#q1-release---march-2020}

**Neue Funktionen**

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
<p>Das Zeitzonen-Management ist jetzt im Eigenschaften-Bereich der Journey gebündelt. In den Eigenschaften der Journey wurden zwei Parameter hinzugefügt:</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li>In der Dropdown-Liste <strong>Zeitzone</strong> können Sie eine bestimmte Zeitzone auswählen. Standardmäßig wird die Zeitzone des Browsers verwendet. </li>
<li>Sofern verfügbar, können Sie mit dem Kontrollkästchen <strong>Zeitzone des Profils</strong> die Zeitzone des Experience Platform-Profils der Person verwenden, die in die Journey eintritt. Andernfalls wird die in der Dropdown-Liste definierte Zeitzone verwendet. Diese Funktion ist nicht mit Journeys kompatibel, die Ereignisse ohne Namespace verwenden.</li>
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
<p>Im Journey-Designer können Sie jetzt feststellen, ob Sie auf die neueste Version der Journey zugreifen. Diese Information wird neben der Versionsnummer angezeigt.</p>
<p>Wenn zwei Aktivitäten auf der <strong>Arbeitsfläche</strong> einer Journey getrennt werden, wird jetzt eine Warnmeldung angezeigt.</p>
<img src="../assets/rn-canvas.png"/>
<p>Weitere Informationen finden Sie im <a href="../building-journeys/using-the-journey-designer.md">entsprechenden Handbuch</a>.</p>
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

* Journeys Orchestration ist jetzt neben den USA auch in der Region **EMEA** verfügbar. Die Anwendung und die Dokumentation sind in Französisch und Deutsch verfügbar.

* Experience League ist jetzt in das Produkt integriert. Dies vereinfacht den Zugriff auf verwandte Inhalte und hilft Ihnen, Experience Cloud optimal zu nutzen. Unten im Tab „Hilfe“ können Sie direkt auf die Dokumentation für Journey Orchestration zugreifen. Sie können auch auf „Hilfe > Feedback“ klicken, um Adobe Probleme oder Anregungen mitzuteilen.

* Der Tastaturbefehl **C**, mit dem Sie ein neues Element erstellen können, ist jetzt in allen Listenbildschirmen verfügbar: Journeys, Datenquellen, Aktionen und Ereignisse. [Mehr dazu](../about/user-interface.md#section_ksq_zr1_ffb)

* Sie können jetzt gestoppte Journeys **löschen**. Berichte für diese gelöschten Journeys werden nicht mehr verfügbar sein.

* Beim Durchsuchen von **Datenplattformfeldern** (XDM-Format) wird nun neben dem Feldnamen der Anzeigename angezeigt. Diese Informationen werden aus der Schemadefinition im Experience-Datenmodell abgerufen. Wenn verfügbar, wird der alternative Anzeigename angezeigt. Mit dieser benutzerfreundlichen Beschreibung, die insbesondere bei eVar-Feldern nützlich ist, können Sie Ihre Felder leichter wiedererkennen. [Mehr dazu](../about/user-interface.md#friendly-names-display)

## GA-Version - Dezember 2019 {#ga-release---december-2019}

Journey Orchestration ist jetzt allgemein verfügbar.

Erstellen Sie Anwendungsfälle für Echtzeit-Orchestrierung mithilfe von Kontextdaten, die in Ereignissen oder Datenquellen gespeichert sind.

Journey Orchestration erlaubt eine Echtzeit-Orchestrierung auf Basis von Kontextdaten aus Ereignissen, Informationen aus Adobe Experience Platform oder Daten aus API-Diensten von Drittanbietern. Die Anwendung bestimmt in mehrstufigen Flüssen, die Journeys genannt werden, je nach Profil und Verhalten des Benutzers die nächsten für den Kunden optimalen Aktionen. Dies umfasst sowohl den besten Zeitpunkt als auch die Art der Aktion, z. B. das Senden einer Push-Benachrichtigung über die Transaktionsnachrichtenfunktion von Adobe Campaign Standard (Adobe Campaign Standard erforderlich) oder das Benachrichtigen eines Drittanbietersystems. Diese Entscheidungen werden auf Grundlage von Regeln und Sensei-Werten getroffen.

[Weitere Informationen](../action/working-with-adobe-campaign.md) zu Journey Orchestration.

Zusätzliche Ressourcen:

* [Tutorials](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [Community](https://www.adobe.com/go/journeyorchestrationcommunity_de)
