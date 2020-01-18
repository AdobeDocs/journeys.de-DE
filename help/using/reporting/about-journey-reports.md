---
title: Info zu Reiseberichten
description: Erfahren Sie, wie Sie Ihre Reiseberichte erstellen
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
source-git-commit: b5b3c8b6adafaedbdd80db3091300e7a26249a3e

---


# Info zu Reiseberichten {#concept_rfj_wpt_52b}

>[!NOTE]
>
>Die Komponente &quot;Bereitstellungsdaten und Segmente&quot;wird nur ausgefüllt, wenn Sie über Adobe Campaign Standard verfügen.

In diesem Abschnitt erfahren Sie, wie Sie auf Berichte zugreifen und diese verwenden können, um die Effektivität Ihrer Reise zu messen.

## Benutzeroberfläche für die Berichterstellung {#reporting-interface}

Über die am oberen Seitenrand befindliche Symbolleiste können Sie beispielsweise einen Bericht ändern, speichern oder ausdrucken.

![](../assets/dynamic_report_toolbar.png)

Im Tab **[!UICONTROL Projekt]**haben Sie folgende Möglichkeiten:

* **[!UICONTROL Öffnen]**: öffnet einen zuvor erstellten Bericht oder eine Vorlage.
* **[!UICONTROL Speichern unter]**: dupliziert Vorlagen, um sie ändern zu können.
* **[!UICONTROL Projekt]**aktualisieren: aktualisiert Ihren Bericht auf der Grundlage neuer Daten und Änderungen an Filtern.
* **[!UICONTROL CSV]**herunterladen: exportiert Ihre Berichte in eine CSV-Datei.
* **[!UICONTROL Drucken]**: druckt Ihren Bericht.

Im Tab **[!UICONTROL Bearbeiten]**haben Sie folgende Möglichkeiten:

* **[!UICONTROL Rückgängig]**: bricht Ihre letzte Aktion im Dashboard ab.
* **[!UICONTROL Wiederholen]**: bricht Ihre letzte Aktion**[!UICONTROL  Rückgängig]** im Dashboard ab.
* **[!UICONTROL Alle]**löschen: löscht alle Bereiche im Dashboard.

Im Tab **[!UICONTROL Einfügen]**können Sie Ihre Berichte anpassen, indem Sie Diagramme und Tabellen zu Ihrem Dashboard hinzufügen:

* **[!UICONTROL Neues leeres Bedienfeld]**: fügt Ihrem Dashboard ein neues leeres Bedienfeld hinzu.
* **[!UICONTROL Neue Freiform]**: fügt Ihrem Dashboard eine neue Freiformtabelle hinzu.
* **[!UICONTROL Neue Zeile]**: fügt Ihrem Dashboard ein neues Liniendiagramm hinzu.
* **[!UICONTROL Neue Leiste]**: fügt Ihrem Dashboard ein neues Balkendiagramm hinzu.

In den linken Tabs können Sie nach Bedarf Berichte erstellen und Daten filtern.

![](../assets/dynamic_report_interface.png)

Über diese Tabs haben Sie Zugriff auf folgende Elemente:

* **[!UICONTROL Bedienfelder]**: Fügen Sie Ihrem Bericht ein leeres Bedienfeld oder Freiformelement hinzu, um Ihre Daten zu filtern. For more on this, refer to the[Adding panels](../reporting/creating-your-journey-reports.md#adding-panels)section
* **[!UICONTROL Visualisierungen]**: Ziehen Sie die gewünschten Visualisierungselemente in den Bereich, um Ihren Bericht grafisch aufzubereiten. For more on this, refer to the[Adding visualizations](../reporting/creating-your-journey-reports.md#adding-visualizations)section.
* **[!UICONTROL Komponenten]**: Passen Sie Ihren Bericht mit unterschiedlichen Dimensionen, Metriken, Segmenten und Zeiträumen an. For more on this, refer to the[Adding components](../reporting/creating-your-journey-reports.md#adding-components)section.

## Kurzvorlage für die Reise {#ootb-template}

Berichte sind in zwei Kategorien unterteilt: eine vordefinierte Vorlage und benutzerdefinierte Berichte.
Die vordefinierte Vorlage, **[!UICONTROL Reisezusammenfassung]**, bietet einen klaren Überblick über die wichtigsten Verfolgungsdaten.

![](../assets/dynamic_report_journey_8.png)

Für jede Tabelle werden Zusammenfassungen und Grafiken erstellt. Die Darstellung dieser Details können Sie in deren Einstellungen ändern.

Die folgenden KPIs stehen oben in Ihrem Bericht zur Verfügung:

* **[!UICONTROL Fahrt - Einfahrt]**: Gesamtzahl der Personen, die das Einstiegsereignis der Reise erreicht haben.
* **[!UICONTROL Reise - Abschlussrate]**: Gesamtzahl der Personen, die das Ende der Reise erreicht haben (oder bei Personen, die keiner Bedingung entsprechen), im Vergleich zur Gesamtzahl der Personen, die die Reise betreten haben.
* **[!UICONTROL Reise - aktuell]**: Gesamtzahl der Personen, die sich derzeit auf der Reise befinden.
* **[!UICONTROL Reise - Fehlgeschlagene Rate]**: Gesamtzahl der Fahrten, die im Vergleich zur Anzahl der Fahrten nicht erfolgreich durchgeführt wurden.
* **[!UICONTROL Auslieferung - gesendete]**Nachrichten: Gesamtzahl der gesendeten Nachrichten.
* **[!UICONTROL Auslieferungsrate]**: Gesamtzahl der erfolgreich ausgelieferten Nachrichten im Vergleich zu den gesendeten Nachrichten.
* **[!UICONTROL Auslieferung - Absprungrate]**: Gesamtzahl der Nachrichten, die im Vergleich zu den gesendeten Nachrichten abgeschnitten haben.
* **[!UICONTROL Auslieferung - Abmeldung]**: Gesamtzahl der Abmeldeabbrüche nach Empfänger im Vergleich zu den bereitgestellten Nachrichten.
* **[!UICONTROL Auslieferung - Offene Preise]**: Gesamtzahl der geöffneten Nachrichten im Vergleich zur Anzahl der ausgelieferten Nachrichten.
* **[!UICONTROL Auslieferung - Klickrate]**: Gesamtanzahl der Klicks in einer Auslieferung im Vergleich zur Anzahl der ausgelieferten Nachrichten.

Mit der Visualisierung des Reiseflusses können Sie den Pfad Ihrer Zielprofile Schritt für Schritt durch Ihre Reise sehen. Dies ist nur verfügbar, wenn Sie eine Reise als Ziel auswählen. Es wird automatisch generiert und kann nicht geändert werden.

![](../assets/dynamic_report_journey_10.png)

Die **[!UICONTROL Tabelle &quot;Reisezusammenfassung]**&quot;enthält die für Ihre Reise verfügbaren Daten, z. B.:

* **[!UICONTROL Eingegeben]**: Gesamtzahl der Personen, die das Einstiegsereignis der Reise erreicht haben.
* **[!UICONTROL Abschlussrate]**: Gesamtzahl der Personen, die die Endflusskontrolle der Reise erreicht haben, im Vergleich zur Gesamtzahl der Personen, die die Reise betreten haben.
* **[!UICONTROL Aktuell]**: Gesamtzahl der Personen, die sich derzeit auf der Reise befinden.
* **[!UICONTROL Fehlgeschlagen]**: Gesamtzahl der Fahrten, die nicht erfolgreich durchgeführt wurden.
* **[!UICONTROL Fehlgeschlagene Rate]**: Gesamtzahl der Fahrten, die im Vergleich zur Anzahl der Fahrten nicht erfolgreich durchgeführt wurden.

Die Tabelle &quot; **[!UICONTROL Wichtigste Ereignisse]**&quot;zeigt die erfolgreichsten Ereignisse und die**[!UICONTROL  Top-Aktion]**an, die erfolgreichsten Aktionen auf Ihren Reisen.

![](../assets/dynamic_report_journey_11.png)

Die **[!UICONTROL Tabelle &quot;Auslieferung - Übersendung]**&quot;enthält die für die Auslieferungen Ihrer Reise verfügbaren Daten, z. B.:

* **[!UICONTROL Verarbeitet/gesendet]**: Gesamtzahl der gesendeten Nachrichten.
* **[!UICONTROL Ausgelieferte Rate]**: Gesamtzahl der erfolgreich ausgelieferten Nachrichten im Vergleich zu den gesendeten Nachrichten.
* **[!UICONTROL Ausgeliefert]**: Anzahl der erfolgreich gesendeten Nachrichten im Verhältnis zur Gesamtanzahl der gesendeten Nachrichten.
* **[!UICONTROL Absprung- und Fehlerquote]**: Gesamtzahl der Nachrichten, die im Vergleich zu den gesendeten Nachrichten abgeschnitten haben.
* **[!UICONTROL Absprünge + Fehler]**: die Gesamtzahl der während der Bereitstellung und der automatischen Verarbeitung der Rücksendung gesammelten Fehler im Verhältnis zur Gesamtzahl der gesendeten Nachrichten.

Die **[!UICONTROL Übersicht]**über die Auslieferung - Rückverfolgung enthält die Daten, die zur Verfolgung des Erfolgs Ihrer Auslieferungen verfügbar sind, z. B.:

* **[!UICONTROL Offene Rate]**: Prozentsatz der geöffneten Nachrichten.
* **[!UICONTROL Öffnen]**: Anzahl der Male, die eine Nachricht bei einer Bereitstellung geöffnet wurde.
* **[!UICONTROL Klicken Sie auf Trough Rate]**: Gesamtanzahl der Klicks in einer Auslieferung im Vergleich zur Anzahl der ausgelieferten Nachrichten.
* **[!UICONTROL Klicken Sie auf]**: Anzahl der Male, die bei einer Bereitstellung auf einen Inhalt geklickt wurde.
* **[!UICONTROL Abmelderate]**: Prozentsatz der Abmeldeabbrüche nach Empfänger im Vergleich zu den bereitgestellten Nachrichten.
* **[!UICONTROL Abmeldung]**: Gesamtzahl der Abmeldeabbrüche nach Empfänger im Vergleich zu den bereitgestellten Nachrichten.
