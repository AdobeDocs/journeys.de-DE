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
source-git-commit: d331454b0ad351a1967ec57d0b3f24a675f10f2a

---


# Versionshinweise {#release-notes}

Auf dieser Seite werden alle neuen Funktionen und Verbesserungen bei Journey Orchestration aufgelistet.
Sie können auch den Abschnitt [Aktualisierungen der Dokumentation](../release-notes/documentation-updates.md) lesen.

## Q1 Version - März 2020 {#q1-release---march-2020}

**Neue Funktionen?**

<table>
<thead>
<tr>
<th><strong>Verbesserungen im Testmodus</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Folgende Verbesserungen wurden am Testmodus vorgenommen:</p>
<ul>
<li>Wenn eine Reise mehrere Ereignisse verwendet, können Sie jetzt jede einzelne von ihnen aus einer Dropdown-Liste im Testmodus im Bildschirm <strong>Ereigniskonfiguration</strong> auslösen. <a href="../building-journeys/testing-the-journey.md#firing_events">Mehr dazu</a></p></li>
<li><p>Wenn eine oder mehrere Aktivitäten zum <strong>Warten</strong> auf einer Reise verwendet werden, können Sie jetzt festlegen, wie lange diese Aktivitäten im Testmodus dauern sollen. Die Standardzeit beträgt 10 Sekunden. Sie können dies mithilfe des Parameters <strong>Wartezeit im Test</strong> unten links ändern. <a href="../building-journeys/testing-the-journey.md">Mehr dazu</a></p><img src="../assets/rn-test.png"/>
</li>
<li>In den <strong>Testprotokollen</strong>werden bei einem Fehler beim Aufruf eines Drittanbietersystems (Datenquelle oder Aktion) nun der Fehlercode und die Fehlerantwort angezeigt. <a href="../building-journeys/testing-the-journey.md#viewing_logs">Mehr dazu</a>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Zentrales Zeitzonenmanagement</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>Das Zeitzonenmanagement ist jetzt im Bereich der Reiseeigenschaften zentralisiert. In den Reiseeigenschaften wurden zwei Parameter hinzugefügt:</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li>In der Dropdownliste <strong>Zeitzone</strong> können Sie eine bestimmte Zeitzone auswählen. Standardmäßig wird die Zeitzone des Browsers verwendet.</li>
<li>Mit dem Kontrollkästchen <strong>Profilzeitzone</strong> können Sie die Profilzeitzone der Erlebnisplattform der Person verwenden, die die Reise beginnt, sofern verfügbar. Andernfalls wird die in der Dropdownliste definierte Zeitzone verwendet. Diese Funktion ist nicht mit Reisen kompatibel, die Ereignisse ohne Namespace verwenden.</li>
</ul>
<p>Weitere Informationen finden Sie in den Abschnitten <a href="../building-journeys/changing-properties.md#timezone">Eigenschaften</a> ändern und <a href="../building-journeys/timezone-management.md">Zeitzonenverwaltung</a> .</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Verbesserungen beim Journey-Designer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>Die <strong>Palette</strong>"Reise"auf der linken Seite des Reisedesigners wurde erweitert:</p>
<ul>
<li>Mit einem neuen Symbol neben der <strong>Suchleiste</strong> können Sie nicht verfügbare Elemente in der Palette ein- oder ausblenden, z. B. Ereignisse, die einen anderen Namespace verwenden als die während der Reise verwendeten. Standardmäßig werden nicht verfügbare Elemente ausgeblendet.</li>
<li>Wenn Sie das Feld <strong>Suchen</strong> verwenden, wird nun die Anzahl der Ergebnisse für jede Arbeitsflächenaktivitätskategorie angezeigt.</li>
<li>Die Navigation zwischen den verschiedenen Aktivitätskategorien wurde verbessert.</li>
</ul>
<p>Im Reisedesigner können Sie jetzt überprüfen, ob Sie auf die neueste Version der Reise zugreifen. Diese Informationen werden neben der Versionsnummer angezeigt.</p>
<p>Wenn auf der <strong>Arbeitsfläche</strong>der Reise zwei Aktivitäten getrennt sind, wird jetzt eine Warnmeldung angezeigt.</p>
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
<p>Eine kontextbezogene Hilfe steht nun über die verschiedenen Listenbildschirme für die Journey Orchestrierung (Reisen, Veranstaltungen, Aktionen und Datenquellen) zur Verfügung. Auf diese Weise können Sie eine kurze Beschreibung der aktuellen Funktion anzeigen und auf zugehörige Artikel und Videos zugreifen.</p>
<p>Um die kontextbezogene Hilfe anzuzeigen, klicken Sie auf das <img src="../assets/icon-context.png"/> Symbol in der oberen rechten Ecke des Bildschirms. </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**Sonstige Verbesserungen**

* Zusätzlich zu den USA ist das Journeys Orchestration jetzt auch in der **EMEA** erhältlich. Der Antrag und die Dokumentation sind in französischer und deutscher Sprache verfügbar.

* Experience League ist jetzt in das Produkt integriert. Dadurch wird der Zugriff auf verwandte Inhalte vereinfacht und Sie können die Vorteile der Experience Cloud optimal nutzen. Direkter Zugriff auf die Dokumentation für die Reisebegleitung finden Sie unten auf der Registerkarte Hilfe. Klicken Sie außerdem auf Hilfe > Feedback, um Probleme zu melden oder Ihre Ideen mit Adobe zu teilen.

* Der **C** -Tastaturbefehl, mit dem Sie ein neues Element erstellen können, ist jetzt in allen Listenbildschirmen verfügbar: Reisen, Datenquellen, Aktionen und Ereignisse. [Mehr dazu](../about/user-interface.md#section_ksq_zr1_ffb)

* Sie können jetzt gestoppte Fahrten **löschen** . Berichte zu diesen gelöschten Fahrten stehen nicht zur Verfügung.

* Beim Durchsuchen von **Datenplattformfeldern** (XDM-Format) wird nun neben dem Feldnamen der Anzeigename angezeigt. Diese Informationen werden aus der Schemadefinition im Erlebnisdatenmodell abgerufen. Wenn verfügbar, wird der alternative Anzeigename angezeigt. Diese benutzerfreundliche Beschreibung, besonders nützlich bei eVar-Feldern, ermöglicht Ihnen die leichtere Identifizierung Ihrer Felder. [Mehr dazu](../about/user-interface.md#friendly-names-display)

## GA-Version - Dezember 2019 {#ga-release---december-2019}

Journey Orchestration ist jetzt allgemein verfügbar.

Erstellen Sie Anwendungsfälle für Echtzeit-Orchestrierung mithilfe von Kontextdaten, die in Ereignissen oder Datenquellen gespeichert sind.

Journey Orchestration erlaubt eine Echtzeit-Orchestrierung auf Basis von Kontextdaten aus Ereignissen, Informationen aus Adobe Experience Platform oder Daten aus API-Diensten von Drittanbietern. Die Anwendung bestimmt in mehrstufigen Flüssen, die Journeys genannt werden, je nach Profil und Verhalten des Benutzers die nächsten für den Kunden optimalen Aktionen. Dies umfasst sowohl den besten Zeitpunkt als auch die Art der Aktion, z. B. das Senden einer Push-Benachrichtigung über die Transaktionsnachrichtenfunktion von Adobe Campaign Standard (Adobe Campaign Standard erforderlich) oder das Benachrichtigen eines Drittanbietersystems. Diese Entscheidungen werden auf Grundlage von Regeln und Sensei-Werten getroffen.

[Weitere Informationen](../action/working-with-adobe-campaign.md) zu Journey Orchestration.

Zusätzliche Ressourcen:

* [Tutorials](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [Community](https://www.adobe.com/go/journeyorchestrationcommunity)