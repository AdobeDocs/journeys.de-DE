---
title: Über Ereignisaktivitäten
description: Erfahren Sie mehr über Ereignisaktivitäten
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
source-wordcount: '334'
ht-degree: 100%

---


# Über Ereignisaktivitäten{#concept_rws_1rt_52b}

Die vom technischen Anwender konfigurierten Ereignisse (siehe [](../event/about-events.md)) werden alle in der ersten Kategorie der Palette auf der linken Seite des Bildschirms angezeigt.

![](../assets/journey43.png)

Beginnen Sie Ihre Journey immer mit Drag-and-Drop einer Ereignisaktivität. Sie können auf diese auch doppelklicken.

![](../assets/journey44.png)

Wenn Sie auf die Ereignisaktivität auf der Arbeitsfläche klicken, wird der Konfigurationsbereich für die Aktivität angezeigt. Wenn Sie dasselbe Ereignis mehrmals verwenden, wird dem Ereignisnamen auf der Arbeitsfläche standardmäßig eine fortlaufende Nummer hinzugefügt. Darüber hinaus können Sie mit dem Feld **[!UICONTROL Titel]** dem Ereignisnamen ein Suffix hinzufügen, das unter Ihrer Aktivität auf der Arbeitsfläche angezeigt wird. Dies ist nützlich, um Ihre Ereignisse auf der Arbeitsfläche zu identifizieren, insbesondere wenn Sie dasselbe Ereignis mehrmals verwenden. Außerdem wird die Problembehebung bei Fehlern und das Lesen von Berichten erleichtert.

![](../assets/journey33.png)

## Erweiterte Verwendung: Ereignisse mit paralleler Wartezeit{#section_vxv_h25_pgb}

**Wie können Sie ein Ereignis nur während einer bestimmten Zeit überwachen?**

Eine in der Journey positionierte Ereignisaktivität überwacht Ereignisse auf unbestimmte Zeit. Damit ein Ereignis nur während einer bestimmten Zeit überwacht wird, müssen Sie parallel zum Ereignispfad eine Warteaktivität hinzufügen. Die Journey überwacht dann das Ereignis während der in der Warteaktivität angegebenen Zeit. Wenn ein Ereignis während dieses Zeitraums empfangen wird, wird die Person in den Ereignispfad geleitet. Andernfalls wird der Kunde in den Wartepfad geleitet.

Sie haben beispielsweise eine erste Willkommens-Push-Benachrichtigung an einen Kunden gesendet und möchten nur dann eine Push-Benachrichtigung mit einem Rabatt senden, wenn der Kunde innerhalb der nächsten 6 Stunden ins Restaurant kommt. Dazu erstellen Sie einen zweiten Pfad (parallel zum Restaurantereignis) mit einer 6-stündigen Warteaktivität. Wenn das Restaurantereignis weniger als 6 Stunden nach der Begrüßungs-Push-Benachrichtigung eingeht, wird die Push-Aktivität für den Rabatt gesendet. Wenn innerhalb der nächsten 6 Stunden kein Restaurantereignis eingeht, wird die Person durch den Wartepfad geleitet.

![](../assets/journeyuc2_31.png)
