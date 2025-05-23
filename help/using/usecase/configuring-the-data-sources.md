---
product: adobe campaign
title: Konfigurieren der Datenquellen
description: Erfahren Sie, wie Sie die Datenquelle für eine Journey in einem erweiterten Anwendungsfall konfigurieren
feature: Journeys
role: User
level: Intermediate
exl-id: 2cfa4397-fe8f-44b3-b219-2fd5d3bdd156
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '520'
ht-degree: 100%

---

# Konfigurieren der Datenquellen {#concept_vml_hdy_w2b}


>[!CAUTION]
>
>**Sie möchten mehr über Adobe Journey Optimizer erfahren**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um auf die Journey Optimizer-Dokumentation zuzugreifen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Accountteam, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._


In unserem Anwendungsfall möchten wir für unsere Nachrichten Personalisierungsdaten verwenden. Außerdem müssen wir überprüfen, ob die Person Mitglied des Treueprogramms ist und in den letzten 24 Stunden nicht kontaktiert wurde. Diese Informationen sind in der Echtzeit-Kundenprofildatenbank gespeichert. Der **technische Anwender** muss die Adobe Experience Platform-Datenquelle konfigurieren, damit sich diese Felder abrufen lassen.

Weitere Informationen zur Datenquellenkonfiguration finden Sie auf [dieser Seite](../datasource/about-data-sources.md).

1. Wählen Sie im Menübereich **[!UICONTROL Admin]** aus. Klicken Sie im Abschnitt **[!UICONTROL Datenquellen]** auf **[!UICONTROL Verwalten]**.
1. Wählen Sie die integrierte Adobe Experience Platform-Datenquelle aus.

   ![](../assets/journey23.png)

1. Überprüfen Sie in den vorkonfigurierten Gruppenfeldern, ob die folgenden Felder ausgewählt sind:

   * _person > name > firstName_
   * _person > name > lastName_
   * _personalEmail > address_

1. Klicken Sie auf **[!UICONTROL Neue Feldergruppe hinzufügen]**, wählen Sie ein **[!UICONTROL Profilschema]** aus und fügen Sie das Feld **Mitglied des Treueprogramms** unserer Bedingung hinzu. Das Feld **Mitglied des Treueprogramms** ist ein benutzerdefiniertes Feld und wurde in XDM hinzugefügt: _customer > marlton > loyaltyMember

   ![](../assets/journeyuc2_6.png)

1. Klicken Sie auf **[!UICONTROL Neue Feldergruppe hinzufügen]**, wählen Sie ein **[!UICONTROL ExperienceEvent]**-Schema und wählen Sie die für unsere Bedingung erforderlichen Felder für die Anzahl der in einem bestimmten Zeitraum gesendeten Nachrichten aus: _timestamp_ für das Datum und _directMarketing > sends > value_ für die Zahl der gesendeten Nachrichten.

   ![](../assets/journeyuc2_7.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

Zudem muss geprüft werden, ob die Person im Hotelreservierungssystem über eine Buchung verfügt. Der **technische Anwender** muss eine zweite Datenquelle konfigurieren, damit sich dieses Feld abrufen lässt.

1. Klicken Sie in der Liste der Datenquellen auf **[!UICONTROL Hinzufügen]**, um eine neue externe Datenquelle hinzuzufügen und die Verbindung zum Hotelreservierungssystem zu definieren.

   ![](../assets/journeyuc2_9.png)

1. Geben Sie einen Namen für die Datenquelle und die URL des externen Dienstes ein, z. B.: _https://marlton.com/reservation_.

   >[!CAUTION]
   >
   >Aus Sicherheitsgründen wird die Verwendung von HTTPS dringend empfohlen.

1. Konfigurieren Sie die Authentifizierung je nach Konfiguration des externen Dienstes: **[!UICONTROL Keine Authentifizierung]**, **[!UICONTROL Einfach]**, **[!UICONTROL Benutzerdefiniert]** oder **[!UICONTROL API-Schlüssel]**. In unserem Beispiel wählen wir als Typ „Einfach“ und geben den Benutzernamen und das Passwort für den API-Aufruf an.

   ![](../assets/journeyuc2_10.png)

1. Klicken Sie auf **[!UICONTROL Neue Feldergruppe hinzufügen]**, um die abzurufenden Informationen und die API-Parameter zu definieren. In unserem Beispiel gibt es nur einen Parameter (die ID). Daher müssen wir eine Feldergruppe mit den folgenden Informationen erstellen:

   * **[!UICONTROL Methode]**: Wählen Sie die POST- oder GET-Methode aus. In unserem Beispiel wählen wir die GET-Methode aus.
   * **[!UICONTROL Antwort-Payload]**: Klicken Sie in das Feld **[!UICONTROL Payload]** und fügen Sie ein Beispiel der Payload ein. Überprüfen Sie, ob die Feldtypen korrekt sind. Jedes Mal, wenn die API aufgerufen wird, ruft das System alle im Payload-Beispiel enthaltenen Felder ab. In unserem Beispiel enthält die Payload nur den Buchungsstatus:

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamische Werte]**: Geben Sie den Parameter ein, der dem Schlüssel entspricht, der zur Identifizierung der einzelnen Kunden dient (in unserem Beispiel „id“). Der Wert dieses Parameters wird in der Journey definiert.

   ![](../assets/journeyuc2_11.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   Die Datenquellen sind nun konfiguriert und können in Ihrer Journey verwendet werden.
