---
product: adobe campaign
solution: Journey Orchestration
title: Senden von Nachrichten mit Campaign v7/v8
description: Senden von Nachrichten mit Campaign v7/v8
source-git-commit: 2195ee3863b38ead504eb6785ceb3c37735fade9
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Senden von Nachrichten mit Campaign v7/v8 {#campaign-classic-use-case}

In diesem Anwendungsbeispiel werden alle Schritte vorgestellt, die zum Senden einer E-Mail mithilfe der Integration mit Adobe Campaign Classic v7 und Adobe Campaign v8 erforderlich sind.

Zunächst wird in Campaign eine Transaktions-E-Mail-Vorlage erstellt. Dann erstellen wir in Journey Orchestration das Ereignis und die Aktion und entwerfen die Journey.

Weiterführende Informationen zur Campaign-Integration finden Sie auf diesen Seiten:

* [Erstellen einer Campaign-Aktion](../action/acc-action.md)
* [Verwenden der Aktion in einer Journey](../building-journeys/using-adobe-campaign-classic.md).

**Adobe Campaign**

Ihre Campaign-Instanz muss für diese Integration bereitgestellt werden. Die Funktion für Transaktionsnachrichten muss konfiguriert sein.

1. Melden Sie sich bei Ihrer Campaign-Kontrollinstanz an.

1. Wählen Sie unter **Administration** > **Platform** > **Auflistungen** die Auflistung **Ereignistyp** (eventType) aus. Erstellen Sie einen neuen Ereignistyp (in unserem Beispiel „Journey-Ereignis“). Beim späteren Schreiben der JSON-Datei müssen Sie den internen Namen des Ereignistyps verwenden.

   ![](../assets/accintegration-uc-1.png)

1. Trennen Sie die Verbindung zur Instanz und verbinden Sie sie erneut, damit die Erstellung wirksam wird.

1. Erstellen Sie unter **Message Center** > **Transaktionsnachrichten-Vorlagen** eine neue E-Mail-Vorlage basierend auf dem zuvor erstellten Ereignistyp.

   ![](../assets/accintegration-uc-2.png)

1. Gestalten Sie Ihre Vorlage. In diesem Beispiel verwenden wir eine Personalisierung mit dem Vornamen und der Bestellnummer des Profils. Der Vorname befindet sich in der Adobe Experience Platform-Datenquelle und die Bestellnummer ist ein Feld von unserem Journey Orchestration-Ereignis. Stellen Sie sicher, dass Sie die richtigen Feldnamen in Campaign verwenden.

   ![](../assets/accintegration-uc-3.png)

1. Veröffentlichen Sie Ihre Transaktionsnachrichtenvorlage.

   ![](../assets/accintegration-uc-4.png)

1. Jetzt müssen Sie die JSON-Payload schreiben, die der Vorlage entspricht.

```
{
     "channel": "email",
     "eventType": "journey-event",
     "email": "Email address",
     "ctx": {
          "firstName": "First name", "purchaseOrderNumber": "Purchase order number"
     }
}
```

* Beim Kanal geben Sie „E-Mail“ ein.
* Verwenden Sie für eventType den internen Namen des zuvor erstellten Ereignistyps.
* Die E-Mail-Adresse ist eine Variable, sodass Sie einen beliebigen Titel eingeben können.
* Unter ctx sind die Personalisierungsfelder auch Variablen.

**Journey Orchestration**

1. Zunächst müssen Sie ein Ereignis erstellen. Stellen Sie sicher, dass Sie das Feld „purchaseOrderNumber“ einschließen.

   ![](../assets/accintegration-uc-5.png)

1. Erstellen Sie dann in Journey Orchestration eine Ihrer Campaign-Vorlage entsprechende Aktion. Wählen Sie aus der Dropdown-Liste **Aktionstyp** die Option **Adobe Campaign Classic** aus.

   ![](../assets/accintegration-uc-6.png)

1. Klicken Sie auf das Feld **Payload** und fügen Sie die zuvor erstellte JSON-Datei ein.

   ![](../assets/accintegration-uc-7.png)

1. Ändern Sie für die E-Mail-Adresse und die beiden Personalisierungsfelder **Konstante** in **Variable**.

   ![](../assets/accintegration-uc-8.png)

1. Erstellen Sie nun eine neue Journey und beginnen Sie mit dem zuvor erstellten Ereignis.

   ![](../assets/accintegration-uc-9.png)

1. Fügen Sie die Aktion hinzu und ordnen Sie jedes Feld dem richtigen Feld in Journey Orchestration zu.

   ![](../assets/accintegration-uc-10.png)

1. Fügen Sie die Aktivität **Ende** hinzu und testen Sie Ihre Journey.

   ![](../assets/accintegration-uc-11.png)

1. Sie können Ihre Journey jetzt veröffentlichen.
