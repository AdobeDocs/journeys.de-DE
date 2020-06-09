---
title: Zugriffsverwaltung
description: Erfahren Sie mehr über die Zugriffsverwaltung
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: a3114ffe7c087645e97caf3a77e7649d922945eb
workflow-type: tm+mt
source-wordcount: '864'
ht-degree: 29%

---


# Zugriffsverwaltung{#concept_rfj_wpt_52b}

## Informationen zur Zugriffsverwaltung {#about-access-management}

[!DNL Journey Orchestration] ermöglicht es Ihnen, Ihren Benutzern eine Reihe von Rechten zuzuweisen, um zu definieren, auf welchen Teil der Oberfläche sie zugreifen können.

Sie können von Administratoren verwaltet werden, die Zugriff auf die Admin-Konsole haben. Weitere Informationen zur Admin Console finden Sie in [dieser Dokumentation](https://helpx.adobe.com/de/enterprise/managing/user-guide.html).

In der Admin Console können Sie Ihren Benutzern eines der folgenden vordefinierten Produktprofile zuweisen:

* **[!UICONTROL Benutzer mit eingeschränktem Zugriff]**: Benutzer mit schreibgeschütztem Zugriff auf Journeys und Berichte. Dieses Produktprofil umfasst folgende Berechtigungen:
   * Journeys lesen
   * Berichte lesen

* **[!UICONTROL Administratoren]**: Benutzer mit Zugriff auf die Verwaltungsmenüs und mit der Fähigkeit, Journeys, Ereignisse und Berichte zu verwalten. Dieses Produktprofil umfasst folgende Berechtigungen:
   * Verwalten von Reisen
   * Veröffentlichen von Reisen
   * Ereignisse, Datenquellen und Aktionen verwalten
   * Berichte verwalten

   >[!NOTE]
   >
   >**[!UICONTROL Administratoren]** ist das einzige Produktprofil, das in Adobe Campaign Standard eine Erstellung, Bearbeitung und Veröffentlichung von Transaktionsnachrichten (oder Nachrichtenvorlagen) ermöglicht. Dieses Produktprofil ist erforderlich, wenn Sie mit Adobe Campaign Standard in Journeys Nachrichten senden möchten.

* **[!UICONTROL Standardbenutzer]**: Benutzer mit Basiszugriff, wie z. B. Verwaltung von Journeys. Dieses Produktprofil umfasst folgende Berechtigungen:
   * Verwalten von Reisen
   * Veröffentlichen von Reisen
   * Berichte verwalten

Sie können auch eigene Profil erstellen, wenn die vordefinierten Profil nicht ausreichen, um Ihre Benutzer zu verwalten.
Benutzer müssen immer mit einem Produkt-Profil verknüpft sein, damit Sie ihnen spezifische integrierte Rechte zuweisen können, z. B.:

* **[!UICONTROL Journeys lesen]**
* **[!UICONTROL Berichte lesen]**
* **[!UICONTROL Ereignisse, Datenquellen und Aktionen verwalten]**
* **[!UICONTROL Ereignisse, Datenquellen und Aktionen lesen]**
* **[!UICONTROL Verwalten von Reisen]**
* **[!UICONTROL Veröffentlichen von Reisen]**
* **[!UICONTROL Berichte verwalten]**

You can find below the compatibility between rights and [!DNL Journey Orchestration]&#39;s different functionalities.

![](../assets/journey_permission.png)

## Creating a product profile {#create-product-profile}

[!DNL Journey Orchestration] ermöglicht es Ihnen, eigene Profil zu erstellen und Ihren Benutzern eine Reihe von Rechten und Sandboxen zuzuweisen. Mit Produkt-Profilen können Sie den Zugriff auf bestimmte Funktionen oder Objekte in der Benutzeroberfläche autorisieren oder verweigern.

Weitere Informationen zum Erstellen und Verwalten von Sandboxen finden Sie in der Dokumentation zu [Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/sandbox/ui/user-guide.html).

So erstellen Sie ein Produkt-Profil und weisen einen Satz von Rechten und Sandboxen zu:

1. In the Admin Console, select **[!UICONTROL Journey Orchestration]**. Klicken Sie auf der Registerkarte **[!UICONTROL Product Profil]** auf **[!UICONTROL New Profil]**.

1. Hinzufügen eines **[!UICONTROL Profils]** und einer **[!UICONTROL Beschreibung]** für Ihr neues Profil. Wenn Sie möchten, dass der **[!UICONTROL Anzeigename]** Ihres Profils unterschiedlich ist, deaktivieren Sie **[!UICONTROL Wie Profil]** und geben Sie Ihren **[!UICONTROL Anzeigenamen]** ein.

1. Wählen Sie in der Kategorie &quot; **[!UICONTROL Benutzerbenachrichtigungen]** &quot;aus, ob Benutzer per E-Mail benachrichtigt werden, wenn sie zu diesem Profil hinzugefügt oder daraus entfernt werden.

1. Klicken Sie abschließend auf **[!UICONTROL Fertig]**. Ihr neues Profil wurde erstellt.

1. Wählen Sie Ihr neues Profil aus, um die Berechtigungen des Beginns zu verwalten. Fügen Sie auf der Registerkarte &quot; **[!UICONTROL Benutzer]** &quot;Ihrem Profil Benutzer hinzu. Weiterführende Informationen hierzu finden Sie auf dieser [Seite](../about/access-management.md#assigning-product-profile).

1. Führen Sie dieselben Schritte wie oben beschrieben aus, um Ihrem Produkt-Profil **[!UICONTROL Admin]** hinzuzufügen.

1. Wählen Sie auf der Registerkarte **[!UICONTROL Berechtigungen]** eine der beiden Kategorien **[!UICONTROL Sandbox]** oder **[!UICONTROL Authoring]** aus, um die Seite &quot;Berechtigungen **[!UICONTROL bearbeiten]** &quot;zu öffnen und Berechtigungen für Ihr Produkt-Profil hinzuzufügen oder zu entfernen.

1. Wählen Sie in der Kategorie **[!UICONTROL Sandbox]** -Berechtigung die Sandbox(n) aus, die Sie Ihrem Produkt-Profil zuweisen möchten. Klicken Sie unter &quot; **[!UICONTROL Verfügbare Berechtigungselemente]**&quot;auf das Pluszeichen (+), um Ihrem Profil Sandboxen zuzuweisen.

   >[!NOTE]
   >
   >Plattform-Sandbox ist eine Beta-Funktion.
   <br>Weitere Informationen zu Sandboxen finden Sie in diesem [Abschnitt](../about/access-management.md#sandboxes).

1. Klicken Sie bei Bedarf unter **[!UICONTROL Einbezogene Berechtigungselemente]** auf das X-Symbol neben dem, um die Berechtigungen für Ihr Produkt-Profil zu entfernen.

1. Führen Sie in der Kategorie **[!UICONTROL Authoring]** -Berechtigung dieselben Schritte wie oben aus, um Ihrem Produkt-Profil Rechte hinzuzufügen.
   <br>Weitere Informationen zu Rechten und Kompatibilität zwischen Rechten und [!DNL Journey Orchestration]seinen verschiedenen Funktionen finden Sie in diesem [Abschnitt](../about/access-management.md#about-access-management).

1. Klicken Sie abschließend auf **[!UICONTROL Speichern]**.

Ihr Profil wurde jetzt erstellt und konfiguriert. Benutzer, die mit diesem Profil verknüpft sind, können jetzt eine Verbindung herstellen [!DNL Journey Orchestration].

## Zuweisen eines Produktprofils {#assigning-product-profile}

Produktprofile werden einer Reihe von Benutzern zugewiesen, die innerhalb Ihres Unternehmens dieselben Rechte haben.
Die Liste aller vordefinierten Profil mit zugewiesenen Rechten finden Sie in diesem Abschnitt.

To assign a product profile for a user to access [!DNL Journey Orchestration]:

1. In the Admin Console, select **[!UICONTROL Journey Orchestration]**.

   ![](../assets/user_management.png)

1. Wählen Sie das Produktprofil aus, mit dem der neue Benutzer verknüpft werden soll.

   ![](../assets/user_management_2.png)

1. Wählen Sie **[!UICONTROL Benutzer hinzufügen]** aus.

   Sie können Ihren neuen Benutzer auch einer Benutzergruppe hinzufügen, um den freigegebenen Berechtigungssatz genauer anzupassen. Weiterführende Informationen hierzu finden Sie auf dieser [Seite](https://helpx.adobe.com/de/enterprise/using/user-groups.html).

   ![](../assets/user_management_3.png)

1. Geben Sie die E-Mail-Adresse Ihres neuen Benutzers ein und klicken Sie auf **[!UICONTROL Speichern]**.

   ![](../assets/user_management_4.png)

Your user should then receive an email redirecting to your [!DNL Journey Orchestration] instance.

## Verwenden von Sandboxes {#sandboxes}

>[!NOTE]
>
>Plattform-Sandbox ist eine Beta-Funktion.

[!DNL Journey Orchestration] ermöglicht es Ihnen, Ihre Instanz in separate virtuelle Umgebung, so genannte Sandboxes, zu unterteilen.
Sandboxen werden über Produkt-Profil in der Admin-Konsole zugewiesen. For more information on how to assign sandboxes, refer to this [section](../about/access-management.md#create-product-profile).

[!DNL Journey Orchestration] spiegelt die Plattform-Sandboxes wider, die für eine bestimmte Organisation erstellt wurden.
Plattform-Sandboxes können von Ihrer Adobe Experience Platform-Instanz erstellt oder zurückgesetzt werden. Detaillierte Anweisungen finden Sie im [Sandbox-Benutzerhandbuch](https://docs.adobe.com/content/help/en/experience-platform/sandbox/ui/user-guide.html) .

Die Sandbox-Umschalter finden Sie oben links auf Ihrem Bildschirm. Um von einer Sandbox zu einer anderen zu wechseln, klicken Sie auf die derzeit aktive Sandbox im Umschalter und wählen Sie in der Dropdown-Liste eine andere Sandbox aus.
