---
title: Zugriffsverwaltung
description: Weitere Informationen zur Zugangsverwaltung
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# Zugriffsverwaltung{#concept_rfj_wpt_52b}

## Über die Zugriffsverwaltung {#about-access-management}

Produktprofile werden einer Reihe von Benutzern zugewiesen, die innerhalb Ihres Unternehmens dieselben Rechte haben.

In der Admin-Konsole können Sie Ihren Benutzern eines der folgenden vordefinierten Produktprofile zuweisen:

* **[!UICONTROL Benutzer]**mit eingeschränktem Zugriff: Benutzer mit schreibgeschütztem Zugriff auf Reisen und Berichte. Dieses Produktprofil umfasst die folgenden Rechte:
   * Fahrten lesen
   * Berichte lesen

* **[!UICONTROL Administratoren]**: Benutzer mit Zugriff auf die Verwaltungsmenüs mit der Möglichkeit, Fahrten, Ereignisse und Berichte zu verwalten. Dieses Produktprofil umfasst die folgenden Rechte:
   * Verwalten und Ausführen von Fahrten
   * Ereignisse, Datenquellen und Aktionen verwalten
   * Berichte verwalten
   >[!NOTE]
   >
   >**[!UICONTROL Administratoren]**sind das einzige Produktprofil, das die Erstellung, Ausgabe und Veröffentlichung von Transaktionsnachrichten (oder Nachrichtenvorlagen) in Adobe Campaign Standard ermöglicht. Dieses Produktprofil ist erforderlich, wenn Sie mit Adobe Campaign Standard Nachrichten auf Ihren Reisen senden.

* **[!UICONTROL Standardbenutzer]**: Benutzer mit Basiszugriff, wie z. B. Reisemanagement. Dieses Produktprofil umfasst die folgenden Rechte:
   * Verwalten und Ausführen von Fahrten
   * Berichte verwalten

Sie können [hier](../assets/do-not-localize/acs_rights_journeys.pdf) die Kompatibilität zwischen Rechten und den verschiedenen Funktionen des Journey Orchesters finden.

## Zuweisen eines Produktprofils {#assigning-product-profile}

Produktprofile werden in der Admin-Konsole verwaltet. For more on this, refer to the [Admin Console documentation](https://helpx.adobe.com/enterprise/managing/user-guide.html).

So weisen Sie einem Benutzer ein Produktprofil für den Zugriff auf die Reisebegleitung zu:

1. Wählen Sie in der Admin-Konsole &quot; **[!UICONTROL Reiseorchestrierung&quot;]**.

   ![](../assets/user_management.png)

1. Wählen Sie das Produktprofil aus, mit dem der neue Benutzer verknüpft werden soll.

   ![](../assets/user_management_2.png)

1. Click **[!UICONTROL Add user]**.

   Sie können Ihren neuen Benutzer auch einer Benutzergruppe hinzufügen, um den freigegebenen Berechtigungssatz genauer einzustellen. Weiterführende Informationen hierzu finden Sie auf dieser [Seite](https://helpx.adobe.com/enterprise/using/user-groups.html).

   ![](../assets/user_management_3.png)

1. Geben Sie die E-Mail-Adresse Ihres neuen Benutzers ein und klicken Sie auf **[!UICONTROL Speichern]**.

   ![](../assets/user_management_4.png)

Ihr Benutzer sollte dann eine E-Mail-Umleitung zu Ihrer Journey-Orchestrierung erhalten.