---
product: adobe campaign
title: Konfigurieren der Datenquelle
description: Erfahren Sie, wie Sie die Datenquelle für die Journey mit dem einfachen Anwendungsfall konfigurieren können
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '188'
ht-degree: 100%

---

# Konfigurieren der Datenquelle{#concept_ax3_bcy_w2b}


>[!CAUTION]
>
>**Sie möchten mehr über Adobe Journey Optimizer erfahren**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um auf die Journey Optimizer-Dokumentation zuzugreifen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Accountteam, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._


In unserem Anwendungsfall möchten wir für unsere Nachrichten Personalisierungsdaten verwenden. Außerdem wollen wir überprüfen, ob die Person weiblich ist. Diese Informationen sind in der Echtzeit-Kundenprofildatenbank gespeichert. Der **technische Anwender** muss prüfen, ob diese Felder in der integrierten Adobe Experience Platform-Datenquelle definiert sind.

Weitere Informationen zur Datenquellenkonfiguration finden Sie auf [dieser Seite](../datasource/about-data-sources.md).

1. Wählen Sie im Menübereich **[!UICONTROL Admin]** aus. Klicken Sie im Abschnitt **[!UICONTROL Datenquellen]** auf **[!UICONTROL Verwalten]**.
1. Wählen Sie die integrierte Adobe Experience Platform-Datenquelle aus.

   ![](../assets/journey23.png)

1. Überprüfen Sie, ob in den Feldgruppen die folgenden Felder ausgewählt sind:

   * _person > name > firstName_
   * _person > name > lastName_
   * _person > gender_
   * _personalEmail > address_

1. Klicken Sie auf **[!UICONTROL Speichern]**.

Die Datenquelle ist jetzt konfiguriert und kann in Ihrer Journey verwendet werden.
