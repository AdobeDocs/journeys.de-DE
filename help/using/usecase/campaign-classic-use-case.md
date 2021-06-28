---
product: adobe campaign
solution: Journey Orchestration
title: Senden einer Nachricht mit Campaign v7/v8
description: Senden einer Nachricht mit Campaign v7/v8
source-git-commit: 8d10739381b4f5b09ad7070498d5f1566961c221
workflow-type: ht
source-wordcount: '394'
ht-degree: 100%

---


# Senden einer Nachricht mit Campaign v7/v8 {#campaign-classic-use-case}

In diesem Anwendungsbeispiel werden alle Schritte vorgestellt, die zum Senden einer E-Mail mithilfe der Integration mit Adobe Campaign Classic v7 und Adobe Campaign v8 erforderlich sind.

Zunächst wird in Campaign eine Transaktions-E-Mail-Vorlage erstellt. Dann erstellen wir in Journey Orchestration das Ereignis und die Aktion und entwerfen die Journey.

Weiterführende Informationen zur Campaign-Integration finden Sie auf diesen Seiten:

* [Erstellen einer Campaign-Aktion](../action/acc-action.md)
* [Verwenden der Aktion in einer Journey](../building-journeys/using-adobe-campaign-classic.md).

**Adobe Campaign**

Ihre Campaign-Instanz muss für diese Integration bereitgestellt werden. Die Transaktionsnachrichten-Funktion muss konfiguriert werden.

1. Melden Sie sich bei Ihrer Campaign-Kontrollinstanz an.

1. Wählen Sie unter **Administration** > **Plattform** > **Auflistungen** die Auflistung **Ereignistyp** (eventType). Erstellen Sie einen neuen Ereignistyp (in unserem Beispiel „Journey-Ereignis“). Beim späteren Schreiben der JSON-Datei müssen Sie den internen Namen des Ereignistyps verwenden.

   ![](../assets/accintegration-uc-1.png)

1. Trennen Sie die Verbindung zur Instanz und stellen Sie erneut eine Verbindung her, damit die Erstellung wirksam wird.

1. Erstellen Sie unter **Message Center** > **Transaktionsnachrichten-Vorlagen** eine neue E-Mail-Vorlage basierend auf dem zuvor erstellten Ereignistyp.

   ![](../assets/accintegration-uc-2.png)

1. Gestalten Sie Ihre Vorlage. In diesem Beispiel verwenden wir eine Personalisierung für den Vornamen des Profils und die Bestellnummer. Der Vorname befindet sich in der Adobe Experience Platform-Datenquelle und die Bestellnummer ist ein Feld von unserem Journey Orchestration-Ereignis. Verwenden Sie in Campaign unbedingt die richtigen Feldnamen.

   ![](../assets/accintegration-uc-3.png)

1. Veröffentlichen Sie Ihre Transaktionsvorlage.

   ![](../assets/accintegration-uc-4.png)

1. Jetzt müssen Sie die der Vorlage entsprechende JSON-Payload schreiben.

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

* Geben Sie für den Kanal „E-Mail“ ein.
* Verwenden Sie für eventType den internen Namen des zuvor erstellten Ereignistyps.
* Die E-Mail-Adresse ist eine Variable, sodass Sie eine beliebige Bezeichnung eingeben können.
* Unter ctx sind die Personalisierungsfelder auch Variablen.

**Journey Orchestration**

1. Zunächst müssen Sie ein Ereignis erstellen. Schließen Sie unbedingt das Feld „purchaseOrderNumber“ ein.

   ![](../assets/accintegration-uc-5.png)

1. Erstellen Sie dann in Journey Orchestration eine Ihrer Campaign-Vorlage entsprechende Aktion. Wählen Sie in der Dropdown-Liste **Aktionstyp** **Adobe Campaign Classic** aus.

   ![](../assets/accintegration-uc-6.png)

1. Klicken Sie auf das Feld **Payload** und fügen Sie den zuvor erstellten JSON-Code ein.

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
