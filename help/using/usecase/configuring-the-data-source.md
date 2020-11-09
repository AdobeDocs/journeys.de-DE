---
title: 'Konfigurieren der Datenquelle '
description: Erfahren Sie, wie Sie die Datenquelle für die Journey mit dem einfachen Anwendungsfall konfigurieren können
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: bcb8a71a27e2b9e37af7d0260cec04ed0fda24ee
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 92%

---


# Konfigurieren der Datenquelle{#concept_ax3_bcy_w2b}

In unserem Anwendungsfall möchten wir für unsere Nachrichten Personalisierungsdaten verwenden. Außerdem wollen wir überprüfen, ob die Person weiblich ist. Diese Informationen sind in der Echtzeit-Kundenprofildatenbank gespeichert. Der **technische Anwender** muss prüfen, ob diese Felder in der integrierten Adobe Experience Platform-Datenquelle definiert sind.

For additional information on data source configuration, refer to [this page](../datasource/about-data-sources.md).

1. Klicken Sie im oberen Menü auf den Tab **[!UICONTROL Datenquellen]** und wählen Sie die integrierte Adobe Experience Platform-Datenquelle.

   ![](../assets/journey23.png)

1. Überprüfen Sie, ob in den Feldgruppen die folgenden Felder ausgewählt sind:

   * _person > name > firstName_
   * _person > name > lastName_
   * _person > gender_
   * _personalEmail > address_

1. Klicken Sie auf **[!UICONTROL Speichern]**.

Die Datenquelle ist jetzt konfiguriert und kann in Ihrer Journey verwendet werden.
