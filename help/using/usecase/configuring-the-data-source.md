---
title: Datenquelle konfigurieren
description: Erfahren Sie, wie Sie die Datenquelle für den einfachen Anwendungsfall konfigurieren
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# Datenquelle konfigurieren{#concept_ax3_bcy_w2b}

In unserem Anwendungsfall möchten wir Personalisierungsdaten für unsere Nachrichten verwenden. Wir müssen auch überprüfen, ob die Person eine Frau ist. Diese Informationen werden in der Echtzeit-Kundenprofildatenbank gespeichert. Der **technische Benutzer** muss überprüfen, ob diese Felder in der integrierten Experience Platform-Datenquelle definiert sind.

Weitere Informationen zur Datenquellenkonfiguration finden Sie unter [](../datasource/about-data-sources.md).

1. Klicken Sie im oberen Menü auf die Registerkarte **[!UICONTROL Datenquellen]**und wählen Sie die integrierte Experience Platform-Datenquelle.

   ![](../assets/journey23.png)

1. Überprüfen Sie, ob in den Feldgruppen die folgenden Felder ausgewählt sind:

   * _person > name > firstName_
   * _person > name > lastName_
   * _person > gender_
   * _personalEmail > address_

1. Wählen Sie **[!UICONTROL Speichern]**aus.

Die Datenquelle ist jetzt konfiguriert und kann auf Ihrer Reise verwendet werden.
