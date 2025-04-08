---
product: adobe campaign
title: Die Benutzeroberfläche
description: Erfahren Sie mehr über die Benutzeroberfläche
feature: Journeys
role: User
level: Intermediate
exl-id: 0d0e74c7-6cb0-4068-a69a-3c01f8b3552d
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '998'
ht-degree: 92%

---

# Benutzeroberfläche{#concept_rcq_lqt_52b}


>[!CAUTION]
>
>**Suche nach Adobe Journey Optimizer**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um die Dokumentation zu Journey Optimizer anzuzeigen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Account-Team, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._


## Zugreifen auf [!DNL Journey Orchestration]{#accessing_journey_orchestration}

Um die Benutzeroberfläche von [!DNL Journey Orchestration] aufzurufen, klicken Sie oben rechts auf das Symbol **[!UICONTROL App Selector]**. Klicken Sie dann auf **[!UICONTROL Journey Orchestration]**.

![](../assets/journey1.png)

Alternativ können Sie auf [!DNL Journey Orchestration] über die Experience Cloud-Startseite im Bereich **[!UICONTROL Schnellzugriff]** zugreifen.

![](../assets/journey1bis.png)

## Vorstellung der Benutzeroberfläche{#section_jsq_zr1_ffb}

>[!CONTEXTUALHELP]
>id="jo_home"
>title="Informationen zur Liste der Journeys"
>abstract="Die Liste der Journeys ermöglicht es Ihnen, alle Ihre Journeys gleichzeitig anzuzeigen, deren Status zu sehen und Standardaktionen durchzuführen."
>additional-url="https://images-tv.adobe.com/mpcv3/38af62cb-9390-4bc0-a576-d336849adb97_1574809570.1920x1080at3000_h264.mp4" text="Demovideo ansehen"

Die Menüs am oberen Seitenrand bieten Zugriff auf die verschiedenen Funktionen von [!DNL Journey Orchestration]: **[!UICONTROL Startseite]** (die Journeys), **[!UICONTROL Datenquellen]**, **[!UICONTROL Ereignisse]**, **[!UICONTROL Aktionen]**.

![](../assets/journey2.png)

Klicken Sie auf das ![](../assets/icon-context.png)-Symbol oben rechts im Bildschirm, um die kontextuelle Hilfe anzuzeigen. Sie ist jetzt in allen Listenbildschirmen (Journeys, Ereignisse, Aktionen und Datenquellen) von [!DNL Journey Orchestration] verfügbar. Auf diese Weise können Sie eine kurze Beschreibung der aktuellen Funktion anzeigen und auf zugehörige Artikel und Videos zugreifen.

![](../assets/journey2bis.png)

## Suchen und Filtern{#section_lgm_hpz_pgb}

In den Listen **[!UICONTROL Startseite]**, **[!UICONTROL Datenquellen]**, **[!UICONTROL Ereignisse]** und **[!UICONTROL Aktionen]** können Sie über eine Suchleiste nach einem Element suchen.

Sie können auf die **[!UICONTROL Filter]** zugreifen, indem Sie auf das Filtersymbol links oben in der Liste klicken. Mit dem Filtermenü können Sie die angezeigten Elemente anhand unterschiedlicher Kriterien filtern. Sie können festlegen, dass nur die Elemente eines bestimmten Typs oder Status, die von Ihnen erstellten Elemente oder die in den letzten 30 Tagen geänderten Elemente angezeigt werden sollen.

Verwenden Sie in den Listen **[!UICONTROL Datenquellen]**, **[!UICONTROL Ereignisse]** und **[!UICONTROL Aktionen]** die **[!UICONTROL Erstellungsfilter]**, um nach dem Erstellungsdatum und Anwender zu filtern. Sie können beispielsweise festlegen, dass nur die Ereignisse angezeigt werden sollen, die Sie in den letzten 30 Tagen erstellt haben.

In der Journey-Liste (unter **[!UICONTROL Startseite]**) können Sie die angezeigten Journeys zusätzlich zu den **[!UICONTROL Erstellungsfiltern]** auch nach Status, Typ und Version filtern (**[!UICONTROL Status- und Versionsfilter]**). Der Typ kann **[!UICONTROL Unitäres Ereignis]** oder **[!UICONTROL Segmentqualifikation]** sein. Sie können auch festlegen, dass nur die Journeys angezeigt werden, die ein bestimmtes Ereignis, eine bestimmte Feldergruppe oder eine bestimmte Aktion verwenden (**[!UICONTROL Aktivitätsfilter]** und **[!UICONTROL Datenfilter]**). Mit den **[!UICONTROL Veröffentlichungsfiltern]** können Sie ein Veröffentlichungsdatum oder einen bestimmten Benutzer auswählen. Sie können beispielsweise entscheiden, dass nur die aktuellen Versionen von Live-Journeys, die am Vortag veröffentlicht wurden, angezeigt werden sollen. Weitere Informationen finden Sie auf [dieser Seite](../building-journeys/using-the-journey-designer.md).

>[!NOTE]
>
>Beachten Sie, dass angezeigte Spalten mithilfe der Konfigurationsschaltfläche oben rechts in den Listen personalisiert werden können. Die Personalisierung wird für jeden Benutzer individuell gespeichert.

Mit den Spalten **[!UICONTROL Letzte Aktualisierung]** und **[!UICONTROL Letzte Aktualisierung von]** können Sie anzeigen, wann und durch wen Ihre Journeys zuletzt aktualisiert wurden.

![](../assets/journey74.png)

In den Konfigurationsbereichen für Ereignis, Datenquelle und Aktion zeigt das Feld **[!UICONTROL Verwendet in]** die Zahl der Journeys an, die dieses bestimmte Ereignis, diese Feldergruppe oder diese Aktion verwenden. Sie können auf die Schaltfläche **[!UICONTROL Customer Journeys anzeigen]** klicken, um die Liste der entsprechenden Journeys zu öffnen.

![](../assets/journey3bis.png)

In den verschiedenen Listen können Sie grundlegende Aktionen für einzelne Elemente durchführen. Sie können Elemente beispielsweise duplizieren oder löschen.

![](../assets/journey4.png)

## Durchsuchen von Adobe Experience Platform-Feldern {#friendly-names-display}

Bei der Definition von [Ereignis-Payload](../event/defining-the-payload-fields.md), [Feldgruppen-Payload](../datasource/field-groups.md) und der Auswahl von Feldern im [Ausdruckseditor](../expression/expressionadvanced.md) wird der Anzeigename zusätzlich zum Feldnamen angezeigt. Diese Informationen werden aus der Schemadefinition im Experience-Datenmodell abgerufen.

Wenn beim Einrichten von Schemata Deskriptoren wie „xdm:alternateDisplayInfo“ angegeben werden, werden die Anzeigenamen durch benutzerfreundliche Namen ersetzt. Dies ist besonders bei der Arbeit mit „eVars“ und generischen Feldern nützlich. Sie können Deskriptoren für benutzerfreundliche Namen über einen API-Aufruf konfigurieren. Weitere Informationen finden Sie im [Entwicklerhandbuch zur Schema Registry](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=de).

![](../assets/xdm-from-descriptors.png)

Wenn ein benutzerfreundlicher Name verfügbar ist, wird das Feld als `<friendly-name>(<name>)` angezeigt. Ist kein benutzerfreundlicher Name verfügbar, wird der Anzeigename angezeigt, z. B. `<display-name>(<name>)`. Wenn keiner der Namen definiert ist, wird nur der technische Name des Felds `<name>` angezeigt.

>[!NOTE]
>
>Benutzerfreundliche Namen werden nicht abgerufen, wenn Sie Felder aus einer Vereinigungsmenge von Schemata auswählen.

## Barrierefreiheit{#accessibility}

Die Funktionen für Barrierefreiheit in Adobe Journey Optimizer werden von Adobe Experience Platform bereitgestellt:

* Tastaturzugriff
* Farbkontrast
* Validierung von Pflichtfeldern

[Weitere Informationen](https://experienceleague.adobe.com/docs/experience-platform/accessibility/features.html?lang=de){target="_blank"} finden Sie in der Dokumentation zu Adobe Experience Platform.

Sie können die folgenden gängigen Tastaturbefehle in Adobe Journey Optimizer verwenden:

| Aktion | Tastenkombination |
| --- | --- |
| Wechseln zwischen Elementen, Abschnitten und Menügruppen der Benutzeroberfläche | Tabulatortaste |
| Rückwärts zwischen Elementen, Abschnitten und Menügruppen der Benutzeroberfläche wechseln | Umschalttaste + Tabulatortaste |
| Bewegen innerhalb von Abschnitten zum Setzen des Fokus auf einzelne Elemente | Pfeil |
| Auswählen oder Löschen eines Element, das sich im Fokus befindet | Eingabetaste oder Leertaste |
| Abbrechen einer Auswahl, Reduzieren eines Panels oder Schließen eines Dialogfelds | Esc |

[Weitere Informationen](https://experienceleague.adobe.com/docs/experience-platform/accessibility/custom.html?lang=de){target="_blank"} finden Sie in der Dokumentation zu Adobe Experience Platform.

Sie können diese Tastaturbefehle in bestimmten Teilen von Journey Optimizer verwenden:

<table>
  <thead>
    <tr>
      <th>Element der Benutzeroberfläche</th>
      <th>Aktion</th>
      <th>Tastenkombination</th>
    </tr>
  </thead>
  <tr>
    <td>Liste der Journeys, Aktionen, Datenquellen oder Ereignisse</td>
    <td>Erstellen einer Journey, Aktion, Datenquelle oder eines Ereignisses</td>
    <td>C</td>
  </tr>
  <tr>
    <td rowspan="3">Journey-Arbeitsfläche im Entwurfsstatus</td>
    <td>Hinzufügen einer Aktivität aus der linken Palette an der ersten verfügbaren Position von oben nach unten</td>
    <td>Doppelklick auf die Aktivität</td>
  </tr>
  <tr>
    <td>Auswahl aller Aktivitäten</td>
    <td>Strg + A (Windows)<br/>Befehl + A (Mac)</td>
  </tr>
  <tr>
    <td>Löschen von ausgewählten Aktivitäten</td>
    <td>Löschen oder Rücktaste und anschließend Eingabetaste zur Bestätigung des Löschvorgangs</td>
  </tr>
  <tr>
  <td rowspan="3">

Konfigurationsbereich dieser Elemente:

<ul>
  <li>Aktivität in einer Journey</li>
  <li>Ereignis</li>
  <li>Datenquelle</li>
  <li>Aktion</li>
</ul>

</td>
    <td>Wechseln zum nächsten zu konfigurierenden Feld</td>
    <td>Tabulatortaste</td>
  </tr>
  <tr>
    <td>Speichern der Änderungen und Schließen des Konfigurationsbereichs</td>
    <td>Eingabetaste</td>
  </tr>
  <tr>
    <td>Verwerfen von Änderungen und Schließen des Konfigurationsbereichs</td>
    <td>Esc</td>
  </tr>
  <tr>
    <td rowspan="4">Journey im Testmodus</td>
    <td>Aktivieren oder Deaktivieren des Testmodus</td>
    <td>T</td>
  </tr>
  <tr>
    <td>Auslösen eines Ereignisses in einer ereignisbasierten Journey</td>
    <td>E</td>
  </tr>
  <tr>
    <td>

Auslösen eines Ereignisses in einer segmentbasierten Journey, für die die Option **[!UICONTROL Jeweils ein Einzelprofil]** aktiviert ist

</td>
    <td>P</td>
  </tr>
  <tr>
    <td>Anzeigen der Testprotokolle</td>
    <td>L</td>
  </tr>
<!-- //Ajouter ce raccourci quand il marchera (actuellement, le raccourci Ctrl/Cmd+F du navigateur a priorité sur celui de AJO).//
  <tr>
    <td>Page with a search bar</td>
    <td>Select the search bar</td>
    <td>Ctrl/Command + F</td>
  </tr>
-->
  <tr>
    <td>Textfeld</td>
    <td>Auswahl des gesamten Texts im ausgewählten Feld</td>
    <td>Strg + A (Windows)<br/>Befehl + A (Mac)</td>
  </tr>
  <tr>
    <td rowspan="2">Popup-Fenster</td>
    <td>Änderungen speichern oder die Aktion bestätigen</td>
    <td>Eingabetaste</td>
  </tr>
  <tr>
    <td>Schließen des Fensters</td>
    <td>Esc</td>
  </tr>
  <tr>
    <td>Einfacher Ausdruckseditor</td>
    <td>Auswählen und Hinzufügen eines Feldes</td>
    <td>Doppelklick auf ein Feld</td>
  </tr>
  <tr>
    <td>Durchsuchen von XDM-Feldern</td>
    <td>Auswahl aller Felder eines Knotens</td>
    <td>Auswahl des übergeordneten Knotens</td>
  </tr>
  <tr>
    <td>Payload-Vorschau</td>
    <td>Auswahl der Payload</td>
    <td>Strg + A (Windows)<br/>Befehl + A (Mac)</td>
  </tr>
</table>
