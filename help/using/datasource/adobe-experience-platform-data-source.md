---
product: adobe campaign
solution: Journey Orchestration
title: 'Datenquelle von Adobe Experience Platform '
description: 'Erfahren Sie, wie Sie die Datenquelle von Adobe Experience Platform konfigurieren '
translation-type: ht
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: ht
source-wordcount: '366'
ht-degree: 100%

---


# Datenquelle von Adobe Experience Platform {#concept_zrb_nqt_52b}

Die Datenquelle von Adobe Experience Platform definiert die Verbindung zum Echtzeit-Kundenprofildienst. Diese Datenquelle ist integriert und vorkonfiguriert. Sie kann nicht gelöscht werden. Diese Datenquelle dient zum Abrufen und Verwenden von Daten aus dem Echtzeit-Kundenprofildienst (überprüfen Sie beispielsweise, ob es sich bei der Person, die an einer Journey teilnimmt, um eine Frau handelt). Sie ermöglicht Ihnen die Verwendung von Profildaten und Erlebnisereignisdaten. Weitere Informationen zum Echtzeit-Kundenprofildienst finden Sie auf dieser [Seite](https://docs.adobe.com/content/help/de-DE/experience-platform/profile/home.html).

>[!NOTE]
>
>Sie können die 1.000 neuesten Erlebnisereignisse abrufen, die vor weniger als einem Jahr erstellt wurden.

Um die Verbindung zum Echtzeit-Kundenprofildienst zu ermöglichen, müssen wir einen Schlüssel zur Identifizierung einer Person und einen Namespace verwenden, der den Schlüssel kontextualisiert. Daher können Sie diese Datenquelle nur verwenden, wenn Ihre Journeys mit einem Ereignis beginnen, das einen Schlüssel und einen Namespace enthält. Weitere Informationen finden Sie auf [dieser Seite](../building-journeys/journey.md).

Sie können die vorkonfigurierte Feldergruppe mit dem Namen „ProfileFieldGroup“ bearbeiten, neue hinzufügen und diejenigen entfernen, die nicht in Entwurfs- oder Live-Journeys verwendet werden. Weitere Informationen finden Sie auf [dieser Seite](../datasource/field-groups.md).

Im Folgenden finden Sie die wichtigsten Schritte, um der integrierten Datenquelle Feldergruppen hinzuzufügen.

1. Wählen Sie in der Liste der Datenquellen die integrierte Datenquelle von Adobe Experience Platform aus.

   Dadurch wird der Konfigurationsbereich für die Datenquellen auf der rechten Seite des Bildschirms geöffnet.

   ![](../assets/journey23.png)

1. Klicken Sie auf **[!UICONTROL Neue Feldergruppe hinzufügen]**, um eine neue Reihe von Feldern zum Abrufen zu definieren. Weitere Informationen finden Sie auf [dieser Seite](../datasource/field-groups.md).

   ![](../assets/journey24.png)

1. Wählen Sie ein Schema aus der Dropdown-Liste **[!UICONTROL Schema]** aus. In diesem Feld werden die in Adobe Experience Platform verfügbaren Profil- und Erlebnisereignisschemata aufgelistet. Die Schemaerstellung wird nicht in [!DNL Journey Orchestration] durchgeführt. Sie wird in Adobe Experience Platform ausgeführt.
1. Wählen Sie die Felder aus, die Sie verwenden möchten.
1. Definieren Sie die Aufbewahrungsfrist im Cache.
1. Klicken Sie auf **[!UICONTROL Speichern]**.

Wenn Sie den Cursor auf dem Namen einer Feldergruppe platzieren, werden rechts zwei Symbole angezeigt. Damit können Sie die Feldergruppe löschen und duplizieren. Beachten Sie, dass das Symbol **[!UICONTROL Löschen]** nur verfügbar ist, wenn die Feldergruppe in keiner Live- oder Entwurfs-Journey verwendet wird (die Information wird im Feld **[!UICONTROL Verwendet in]** angezeigt).
