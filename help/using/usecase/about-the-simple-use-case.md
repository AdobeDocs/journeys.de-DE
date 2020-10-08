---
title: Informationen zum einfachen Anwendungsfall
description: Mehr über die Journey mit dem einfachen Anwendungsfall
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 100%

---


# Informationen zum einfachen Anwendungsfall{#concept_grh_vby_w2b}

## Zweck {#purpose}

Nehmen wir als Beispiel eine Hotelmarke namens Marlton. In den Hotels der Kette wurden Beacon-Geräte in der Nähe aller strategischen Punkte angebracht: Lobby, Etagen, Restaurant, Fitness-Raum, Pool usw.

In diesem Anwendungsfall sehen wir, wie sich in Echtzeit eine personalisierte Nachricht an eine Person senden lässt, die einen Beacon nahe des Spa passiert.

Wir wollen nur dann eine Nachricht senden, wenn die Person weiblich ist. Die Nachricht muss innerhalb von Sekunden empfangen werden.

![](../assets/journeyuc1_16.png)

## Voraussetzungen:     {#prerequisites}

Für unseren Anwendungsfall haben wir in Adobe Campaign Standard eine Transaktionsnachrichtenvorlage in Form einer E-Mail entwickelt. Wir verwenden eine Transaktionsnachrichtenvorlage für Ereignisse. Mehr dazu erfahren Sie auf [dieser Seite](https://docs.adobe.com/content/help/de-DE/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign Standard ist so konfiguriert, dass E-Mails gesendet werden.

Ereignisse werden vom Mobiltelefon des Kunden gesendet, sobald es in der Nähe eines Beacons erkannt wird. Sie müssen eine App einrichten, damit Ereignisse vom Mobiltelefon des Kunden an das Mobile SDK gesendet werden.