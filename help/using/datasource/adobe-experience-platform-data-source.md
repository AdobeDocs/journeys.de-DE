---
title: 'Datenquelle von Adobe Experience Platform '
description: 'Erfahren Sie, wie Sie die Datenquelle von Adobe Experience Platform konfigurieren '
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
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1

---


# Datenquelle von Adobe Experience Platform {#concept_zrb_nqt_52b}

Die Datenquelle von Experience Platform definiert die Verbindung zum Echtzeit-Kundenprofildienst. Diese Datenquelle ist integriert und vorkonfiguriert. Sie kann nicht gelöscht werden. Diese Datenquelle dient zum Abrufen und Verwenden von Daten aus dem Echtzeit-Kundenprofildienst (überprüfen Sie beispielsweise, ob es sich bei der Person, die an einer Journey teilnimmt, um eine Frau handelt). Sie ermöglicht Ihnen die Verwendung von Profildaten und Erlebnisereignisdaten. Weitere Informationen zum Echtzeit-Kundenprofildienst finden Sie auf dieser [Seite](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html).

>[!NOTE]
>
>Sie können die 1.000 neuesten Erlebnisereignisse abrufen, die vor weniger als einem Jahr erstellt wurden.

Um die Verbindung zum Echtzeit-Kundenprofildienst zu ermöglichen, müssen wir einen Schlüssel zur Identifizierung einer Person und einen Namespace verwenden, der den Schlüssel kontextualisiert. Daher können Sie diese Datenquelle nur verwenden, wenn Ihre Journeys mit einem Ereignis beginnen, das einen Schlüssel und einen Namespace enthält. Siehe [](../building-journeys/journey.md).

Sie können die vorkonfigurierte Feldergruppe mit dem Namen „ProfileFieldGroup“ bearbeiten, neue hinzufügen und diejenigen entfernen, die nicht in Entwurfs- oder Live-Journeys verwendet werden. Siehe [](../datasource/field-groups.md).

Im Folgenden finden Sie die wichtigsten Schritte, um der integrierten Datenquelle Feldergruppen hinzuzufügen.

1. Wählen Sie in der Liste der Datenquellen die integrierte Datenquelle von Experience Platform aus.

   Dadurch wird der Konfigurationsbereich für die Datenquellen auf der rechten Seite des Bildschirms geöffnet.

   ![](../assets/journey23.png)

1. Klicken Sie auf **[!UICONTROL Add a New Field Group]** , um eine neue Reihe von Feldern zum Abrufen zu definieren. Siehe [](../datasource/field-groups.md).

   ![](../assets/journey24.png)

1. Wählen Sie ein aus der Dropdown-Liste **[!UICONTROL Schema]** Schema aus. In diesem Feld werden die in der Plattform verfügbaren Profil- und Erlebnisereignisschemata aufgelistet. Die Schemaerstellung wird nicht in Journey Orchestration durchgeführt. Sie wird in der Datenplattform durchgeführt.
1. Wählen Sie die Felder aus, die Sie verwenden möchten.
1. Definieren Sie die Aufbewahrungsfrist im Cache.
1. Klicken Sie auf **[!UICONTROL Save]**.

Wenn Sie den Cursor auf dem Namen einer Feldergruppe platzieren, werden rechts zwei Symbole angezeigt. Damit können Sie die Feldergruppe löschen und duplizieren. Note that the **[!UICONTROL Delete]** icon is only available if the field group is not used in any live or draft journey (information displayed in the **[!UICONTROL Used in]** field).
