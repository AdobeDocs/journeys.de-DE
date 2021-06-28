---
product: adobe campaign
title: Informationen zur Integration von Campaign v7/v8
description: Informationen zur Integration von Campaign v7/v8
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 8d10739381b4f5b09ad7070498d5f1566961c221
workflow-type: ht
source-wordcount: '443'
ht-degree: 100%

---

# Verwenden von Adobe Campaign v7/v8 {#integrating-with-adobe-campaign-classic}

Diese Integration ist für Adobe Campaign Classic v7 ab Version 21.1 und Adobe Campaign v8 verfügbar. Sie ermöglicht Ihnen das Senden von E-Mails, Push-Benachrichtigungen und SMS mit der Transaktionsnachrichten-Funktion von Adobe Campaign.

Die Verbindung zwischen der Journey Orchestration- und der Campaign-Instanz wird bei der Bereitstellung durch Adobe eingerichtet.

In diesem [Abschnitt](../usecase/campaign-classic-use-case.md) wird ein Anwendungsfall vollständig beschrieben.

Für jede konfigurierte Aktion ist eine Aktionsaktivität in der Journey-Designer-Palette verfügbar. Siehe diesen [Abschnitt](../building-journeys/using-adobe-campaign-classic.md).

## Wichtige Hinweise     

* Es gibt keine Drosselung der Nachrichten. Wir begrenzen die Anzahl der Nachrichten, die versendet werden können, basierend auf unserem aktuellen Campaign SLA auf 50.000/Stunde. Aus diesem Grund sollte Journey Orchestration nur in unitären Anwendungsfällen (einzelne Ereignisse, nicht Segmente) verwendet werden.

* Sie müssen für jede Vorlage, die Sie verwenden möchten, eine Aktion auf der Arbeitsfläche konfigurieren. Sie müssen für jede Vorlage, die Sie in Adobe Campaign verwenden möchten, eine Aktion in Journey Orchestration konfigurieren.

* Es wird empfohlen, eine dedizierte Message Center-Instanz zu verwenden, die für diese Integration gehostet wird, um zu vermeiden, dass andere Campaign-Vorgänge, die Sie vielleicht gerade ausführen, beeinträchtigt werden. Der Marketing-Server kann gehostet oder On-Premise bereitgestellt werden. Der erforderliche Build ist Release Candidate 21.1 oder höher.

* Es wird nicht überprüft, ob die Payload oder Campaign-Nachricht korrekt ist.

* Sie können keine Campaign-Aktion mit einem Segmentqualifikationsereignis verwenden.

## Voraussetzungen

Sie müssen in Campaign eine Transaktionsnachricht und das zugehörige Ereignis erstellen und veröffentlichen. Weitere Informationen finden Sie in der [Dokumentation zu Adobe Campaign](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=de#transactional-messaging).

Sie können Ihre JSON-Payload entsprechend den folgenden Mustern für jede Nachricht erstellen. Sie fügen diese Payload dann beim Konfigurieren der Aktion in Journey Orchestration ein (siehe unten).

Hier ein Beispiel:

```
{
    "channel": "email",
    "eventType": "welcome",
    "email": "example@adobe.com",
    "ctx": {
        "firstName": "John"
    }
}
```

* **channel**: der Kanal, der für Ihre Campaign-Transaktionsvorlage definiert ist
* **eventType**: der interne Name Ihres Campaign-Ereignisses
* **ctx**: die Variable basierend auf der Personalisierung, die Sie in Ihrer Nachricht haben

## Konfigurieren der Aktion

In Journey Orchestration müssen Sie eine Aktion pro Transaktionsnachricht konfigurieren. Führen Sie folgende Schritte aus:

1. Erstellen Sie eine neue Aktion. Siehe diesen [Abschnitt](../action/action.md).
1. Geben Sie einen Namen und eine Beschreibung ein.
1. Wählen Sie im Feld **Aktionstyp** **Adobe Campaign Classic** aus.
1. Klicken Sie in das Feld **Payload** und fügen Sie ein Beispiel der JSON-Payload ein, die der Campaign-Nachricht entspricht. Wenden Sie sich an Adobe, um diese Payload zu erhalten.
1. Stellen Sie die verschiedenen Felder auf der Journey-Arbeitsfläche je nach gewünschter Zuordnung auf statisch oder variabel ein. Bestimmte Felder, wie z. B. Kanalparameter für E-Mail-Adressen- und Personalisierungsfelder (ctx), sollten als Variablen für die Zuordnung im Kontext der Journey definiert werden.
1. Klicken Sie auf **Speichern**.

![](../assets/accintegration1.png)


