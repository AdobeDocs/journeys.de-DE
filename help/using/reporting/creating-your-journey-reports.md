---
title: Erstellen von Reiseberichten
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
source-git-commit: b87de729f48c4624554eb19b6d418cb3cf70b805

---


# Erstellen von Reiseberichten {#concept_rfj_wpt_52b}

## Zugriff auf und Erstellung von Berichten {#accessing-reports}

>[!NOTE]
>
>Nach dem Löschen einer Reise stehen nicht mehr alle zugehörigen Berichte zur Verfügung.

In diesem Abschnitt erfahren Sie, wie Sie vordefinierte Berichte erstellen oder verwenden. Kombinieren Sie Bereiche, Komponenten und Visualisierungen, um den Erfolg Ihrer Reisen besser zu verfolgen.

So greifen Sie auf Ihre Berichte zu Reisen zu und beginnen, den Erfolg Ihrer Auslieferungen zu verfolgen:

1. Klicken Sie im oberen Menü auf die Registerkarte **[!UICONTROL Start]**.

1. Wählen Sie die Reise aus, über die Sie Bericht erstatten möchten.

   Beachten Sie, dass Sie auch auf Ihre Berichte zugreifen können, indem Sie auf **Bericht** klicken, während Sie den Mauszeiger über eine Reise in der Liste der Reisen halten.

   ![](../assets/dynamic_report_journey.png)

1. Klicken Sie oben rechts auf dem Bildschirm auf das Symbol **[!UICONTROL Bericht]**.

   ![](../assets/dynamic_report_journey_2.png)

1. Der Bericht zur **[!UICONTROL Reisezusammenfassung]**wird auf dem Bildschirm angezeigt. Klicken Sie auf die Schaltfläche**[!UICONTROL  Schließen]** , um auf benutzerdefinierte Berichte zuzugreifen.

   ![](../assets/dynamic_report_journey_12.png)

1. Klicken Sie auf das **[!UICONTROL Projekt]**neu erstellen, um Ihren Bericht von Grund auf neu zu erstellen.

   ![](../assets/dynamic_report_journey_3.png)

1. Ziehen Sie auf der Registerkarte &quot; **[!UICONTROL Bedienfelder]**&quot;so viele Bedienfelder oder Freiformtabellen wie nötig per Drag &amp; Drop. For more information, refer to this[section](#adding-panels).

   ![](../assets/dynamic_report_journey_4.png)

1. Anschließend können Sie Ihre Daten filtern, indem Sie Dimensionen und Metriken aus der Registerkarte &quot; **[!UICONTROL Komponenten]**&quot;in Ihre Freiform-Tabelle ziehen und dort ablegen. For more information, refer to this[section](#adding-components).

   ![](../assets/dynamic_report_journey_5.png)

1. Um eine klarere Ansicht Ihrer Daten zu erhalten, können Sie Visualisierungen auf der Registerkarte &quot; **[!UICONTROL Visualisierungen]**&quot;hinzufügen. For more information, refer to this[section](#adding-visualizations).

## Bedienfelder hinzufügen{#adding-panels}

### Leeres Bedienfeld hinzufügen {#adding-a-blank-panel}

Um Ihren Bericht zu starten, können Sie einem vordefinierten oder benutzerspezifischen Bericht eine Reihe von Bereichen hinzufügen. Jedes Bedienfeld enthält unterschiedliche Datensätze und besteht aus Freiformtabellen und Visualisierungen.

In diesen Bedienfeldern können Sie nach Bedarf Ihre Berichte erstellen. Sie können beliebig viele Bedienfelder in Ihre Berichte einfügen, um Ihre Daten nach unterschiedlichen Zeiträumen zu filtern.

1. Klicken Sie auf das **[!UICONTROL Bedienfeldsymbol.]**Sie können auch ein Bedienfeld hinzufügen, indem Sie das**[!UICONTROL  Einfügen-Tab]** und **[!UICONTROL Neues leeres Bedienfeld]**auswählen.

   ![](../assets/dynamic_report_panel_1.png)

1. Ziehen Sie das **[!UICONTROL leere Bedienfeld]**in Ihr Dashboard.

   ![](../assets/dynamic_report_panel.png)

Dann können Sie eine Freiformtabelle in Ihr Bedienfeld einfügen, um mit der Datensuche zu beginnen.

### Freiformtabelle hinzufügen {#adding-a-freeform-table}

Mit Freiformtabellen kann eine Tabelle erstellt werden, in der Daten unter Verwendung der unterschiedlichen Messwerte und Dimensionen im Bereich **[!UICONTROL Komponente]**analysiert werden.

Die Größe jeder Tabelle und Grafik kann entsprechend Ihrem Bericht geändert und verschoben werden.

1. Klicken Sie auf das **[!UICONTROL Bedienfeldsymbol]**.

   ![](../assets/dynamic_report_panel_1.png)

1. Ziehen Sie das **[!UICONTROL Freiformfeld]**in Ihr Dashboard.

   Sie können auch eine Tabelle hinzufügen, indem Sie in einem leeren Bedienfeld den Tab **[!UICONTROL Einfügen]**und anschließend**[!UICONTROL  Neue Freiform]** oder **[!UICONTROL Neue Freiform-Tabelle]**auswählen.

   ![](../assets/dynamic_report_panel_2.png)

1. Ziehen Sie Elemente aus dem Tab **[!UICONTROL Komponenten]**in die Spalten und Zeilen, um Ihre Tabelle zu erstellen.

   ![](../assets/dynamic_report_freeform_3.png)

1. Klicken Sie auf das Symbol **[!UICONTROL Einstellungen]**, um die Darstellung der Daten in den Spalten zu ändern.

   ![](../assets/dynamic_report_freeform_4.png)

   Die **[!UICONTROL Spalteneinstellungen]**beinhalten folgende Optionen:

   * **[!UICONTROL Anzahl]**: Ermöglicht das Anzeigen oder Verbergen der Anzahl der Zusammenfassungen in der Spalte
   * **[!UICONTROL Prozent]**: können Sie Prozentwerte in der Spalte ein- oder ausblenden.
   * **[!UICONTROL Null als keinen Wert auffassen]**: Ermöglicht es, den Wert Null anzuzeigen oder zu verbergen.
   * **[!UICONTROL Hintergrund]**: Ermöglicht das Anzeigen oder Verbergen des Fortschrittsbalkens in Zellen
   * **[!UICONTROL Wiederholungsversuche einbeziehen]**: Ermöglicht das Einbeziehen von weiteren Zustellversuchen in das Ergebnis. Dies ist nur für**[!UICONTROL  Gesendet]** und **[!UICONTROL Bounces + Fehler]**verfügbar.

1. Wählen Sie eine oder mehrere Zeilen aus und danach das Symbol **[!UICONTROL Visualisieren]**. Die ausgewählten Zeilen werden daraufhin grafisch dargestellt.

   ![](../assets/dynamic_report_freeform_5.png)

Jetzt können Sie beliebig viele Komponenten und Visualisierungen hinzufügen, um Ihre Daten grafisch darzustellen.

## Komponenten hinzufügen{#adding-components}

Mit Komponenten können Sie Ihren Berichten unterschiedliche Dimensionen, Messwerte und Zeiträume hinzufügen.

1. Klicken Sie auf den Tab **[!UICONTROL Komponenten]**, um auf die Liste mit Komponenten zuzugreifen.

   ![](../assets/dynamic_report_components.png)

1. Jede im Tab **[!UICONTROL Komponenten]**angezeigt Kategorie enthält die fünf am häufigsten verwendeten Elemente. Klicken Sie auf den Namen einer Kategorie, um die gesamte Liste mit Komponenten zu öffnen.

   Die Tabelle &quot;Komponenten&quot;ist in drei Kategorien unterteilt:

   * **[!UICONTROL Dimensionen]**: Hier erhalten Sie Informationen vom Versandlog, wie Details zum Browser oder zur Domain des Benutzers oder darüber, wie erfolgreich ein Versand war.
   * **[!UICONTROL Metriken]**: Hier erhalten Sie Details zum Status einer Nachricht, Wenn beispielsweise eine Nachricht gesendet und der Benutzer sie geöffnet hat.
   * **[!UICONTROL Zeitraum]**: Hier können Sie für Ihre Tabelle einen Zeitraum festlegen.

1. Verschieben Sie Komponenten per Drag &amp; Drop in ein Bedienfeld, um Ihre Daten zu filtern.

Sie können beliebig viele Komponenten verschieben und miteinander vergleichen.

## Visualisierungen hinzufügen{#adding-visualizations}

Im Tab **[!UICONTROL Visualisierungen]**können Sie per Drag &amp; Drop Visualisierungselemente wie Bereich, Kreis und Diagramm auswählen. Durch diese Elemente können Sie Ihre Daten unterschiedlich grafisch darstellen.

1. Ziehen Sie im Tab **[!UICONTROL Visualisierungen]**ein Visualisierungselement in ein Bedienfeld.

   ![](../assets/dynamic_report_visualization_1.png)

1. Nachdem Sie eine Visualisierung zu Ihrem Bedienfeld hinzugefügt haben, werden die Daten in Ihrer Freiformtabelle automatisch von Ihren Berichten erkannt. Wählen Sie die Visualisierungseinstellungen aus.
1. Wenn mehr als eine Freiformtabelle vorhanden ist, wählen Sie im Fenster **[!UICONTROL Datenquelleneinstellungen]**die verfügbare Datenquelle, die Ihrem Diagramm hinzugefügt werden soll. Dieses Fenster können Sie auch öffnen, indem Sie den Farbpunkt neben dem Darstellungstitel auswählen.

   ![](../assets/dynamic_report_visualization_2.png)

1. Mit der Schaltfläche für die **[!UICONTROL Darstellungseinstellungen]**können Sie die Art des Diagramms oder dessen Inhalt ändern, z. B.:

   * **[!UICONTROL Prozentsatz]**: Zeigt die Werte in Prozenten an.
   * **[!UICONTROL Y-Achse bei null verankern]**: Erzwingt für die y-Achse den Wert null, selbst wenn deren Werte über null liegen.
   * **[!UICONTROL Legende eingeblendet]**: Ermöglicht das Verbergen der Legende.
   * **[!UICONTROL Normalisierung]**: Erzwingt die Übereinstimmung von Werten.
   * **[!UICONTROL Zwei Achsen anzeigen]**: Fügt Ihrem Diagramm eine weitere Achse hinzu.
   * **[!UICONTROL Grenzwert für max. Anzahl Elemente]**: Beschränkt die Anzahl der dargestellten Diagramme.
   * **[!UICONTROL Schwellenwert]**: Hiermit können Sie einen Schwellenwert für das Diagramm festlegen. Sie wird als schwarz gepunktete Linie dargestellt.
   ![](../assets/dynamic_report_visualization_3.png)

Mit dieser Visualisierung können die Daten in Ihren Berichte übersichtlicher dargestellt werden.