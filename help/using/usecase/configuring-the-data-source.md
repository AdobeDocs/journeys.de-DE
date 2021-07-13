---
product: adobe campaign
title: 'Konfigurieren der Datenquelle '
description: Erfahren Sie, wie Sie die Datenquelle für die Journey mit dem einfachen Anwendungsfall konfigurieren können
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 100%

---

# Konfigurieren der Datenquelle{#concept_ax3_bcy_w2b}

In unserem Anwendungsfall möchten wir für unsere Nachrichten Personalisierungsdaten verwenden. Außerdem wollen wir überprüfen, ob die Person weiblich ist. Diese Informationen sind in der Echtzeit-Kundenprofildatenbank gespeichert. Der **technische Anwender** muss prüfen, ob diese Felder in der integrierten Adobe Experience Platform-Datenquelle definiert sind.

Weitere Informationen zur Datenquellenkonfiguration finden Sie auf [dieser Seite](../datasource/about-data-sources.md).

1. Klicken Sie im oberen Menü auf den Tab **[!UICONTROL Datenquellen]** und wählen Sie die integrierte Adobe Experience Platform-Datenquelle aus.

   ![](../assets/journey23.png)

1. Überprüfen Sie, ob in den Feldgruppen die folgenden Felder ausgewählt sind:

   * _person > name > firstName_
   * _person > name > lastName_
   * _person > gender_
   * _personalEmail > address_

1. Klicken Sie auf **[!UICONTROL Speichern]**.

Die Datenquelle ist jetzt konfiguriert und kann in Ihrer Journey verwendet werden.
