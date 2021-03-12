---
product: adobe campaign
solution: Journey Orchestration
title: Informationen über die Campaign Classic-Integration
description: Informationen zur Campaign Classic-Integration
hide: true
hidefromtoc: true
feature: Journeys
role: Geschäftspraktiker
level: Fortgeschr.
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 99%

---


# Integrieren von Adobe Campaign Classic {#integrating-with-adobe-campaign-classic}

Diese Integration ermöglicht Ihnen das Senden von E-Mails, Push-Benachrichtigungen und SMS mit der Transaktionsnachrichtenfunktion von Adobe Campaign Classic.

Die Verbindung zwischen der Journey Orchestration- und der Campaign Classic-Instanz wird bei der Bereitstellung von Adobe hergestellt.

>[!CAUTION]
>
> Diese Integration ist als private Betaversion verfügbar. Sie steht nicht allen Journey Orchestration-Kunden zur Verfügung.

## Wichtige Hinweise     

* Es gibt keine Drosselung der Nachrichten. Wir begrenzen die Anzahl der Nachrichten, die versendet werden können, basierend auf unserem aktuellen Campaign Classic SLA auf 50.000/Stunde. Aus diesem Grund sollte Journey Orchestration nur in unitären Anwendungsfällen (einzelne Ereignisse, nicht Segmente) verwendet werden.

* Sie müssen für jede Vorlage, die Sie verwenden möchten, eine Aktion auf der Arbeitsfläche konfigurieren.

* Es wird empfohlen, eine dedizierte Message Center-Instanz zu verwenden, die für diese Integration gehostet wird, um zu vermeiden, dass andere Campaign Classic-Vorgänge, die Sie vielleicht gerade ausführen, beeinträchtigt werden. Der Marketing-Server kann gehostet oder On-Premise bereitgestellt werden. Der erforderliche Build ist 21.1 Release Candidate.

* Es wird nicht überprüft, ob die Payload oder Campaign Classic-Nachricht korrekt ist.

* Sie können keine Campaign Classic-Aktion mit einer Segmentqualifikation verwenden.

## Voraussetzungen

Sie müssen in Campaign Classic eine Transaktionsnachricht und das zugehörige Ereignis erstellen und veröffentlichen. Weitere Informationen finden Sie in der [Adobe Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=de#transactional-messaging).

Wenden Sie sich an Adobe, um die JSON-Payload für jede Nachricht zu erhalten. Sie fügen diese Payload dann beim Konfigurieren der Aktion in Journey Orchestration ein (siehe unten).

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

## Konfigurieren der Aktion

In Journey Orchestration müssen Sie eine Aktion pro Transaktionsnachricht konfigurieren. Führen Sie folgende Schritte aus:

1. Erstellen Sie eine neue Aktion. Siehe diesen [Abschnitt](../action/action.md).
1. Geben Sie einen Namen und eine Beschreibung ein.
1. Wählen Sie im Feld **Aktionstyp** **Adobe Campaign Classic** aus.
1. Klicken Sie in das Feld **Payload** und fügen Sie ein Beispiel der JSON-Payload ein, die der Campaign Classic-Nachricht entspricht. Wenden Sie sich an Adobe, um diese Payload zu erhalten.
1. Passen Sie die verschiedenen Felder an. Bestimmte Felder, wie z. B. Kanalparameter und Personalisierungsfelder (ctx), müssen als Variablen definiert werden.
1. Wählen Sie **Speichern** aus.

![](../assets/accintegration1.png)

Für jede konfigurierte Aktion ist eine Aktionsaktivität in der Journey-Designer-Palette verfügbar.

## Hinzufügen einer Nachricht zu einer Journey

1. Beginnen Sie bei der Erstellung Ihrer Journey mit einem Ereignis. Siehe diesen [Abschnitt](../building-journeys/journey.md).
1. Wählen Sie im Abschnitt **Aktion** der Palette eine Campaign Classic-Aktion aus und fügen Sie sie zu Ihrer Journey hinzu.
1. Unter **Aktionsparameter** werden alle Felder angezeigt, die in der Nachrichten-Payload erwartet werden. Sie müssen jedes dieser Felder entweder im Ereignis oder der Datenquelle dem zu verwendenden Feld zuordnen. Dies ähnelt benutzerdefinierten Aktionen. Siehe diesen [Abschnitt](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)

