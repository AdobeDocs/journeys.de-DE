---
title: Veranstaltungen
description: Informationen zu Veranstaltungen
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# Veranstaltungen {#concept_rws_1rt_52b}

Die vom technischen Benutzer konfigurierten Ereignisse (siehe [](../event/about-events.md) werden alle in der ersten Kategorie der Palette auf der linken Seite des Bildschirms angezeigt.

![](../assets/journey43.png)

Beginnen Sie Ihre Reise immer mit Drag &amp; Drop einer Ereignisaktivität. Sie können auch darauf doppelklicken.

![](../assets/journey44.png)

Wenn Sie auf die Ereignisaktivität auf der Arbeitsfläche klicken, wird der Bereich für die Aktivitätskonfiguration angezeigt. Wenn Sie dasselbe Ereignis mehrmals verwenden, wird dem Ereignisnamen standardmäßig eine inkrementierte Zahl auf der Arbeitsfläche hinzugefügt. Darüber hinaus können Sie mit dem Feld **[!UICONTROL Bezeichnung]**dem Ereignisnamen ein Suffix hinzufügen, das unter Ihrer Aktivität auf der Arbeitsfläche angezeigt wird. Dies ist nützlich, um Ihre Ereignisse auf der Arbeitsfläche zu identifizieren, insbesondere wenn Sie dasselbe Ereignis mehrmals verwenden. Außerdem wird das Debugging bei Fehlern erleichtert und das Lesen von Berichten erleichtert.

![](../assets/journey33.png)

## Allgemeine Veranstaltungen {#section_ofg_jss_dgb}

Für diesen Ereignistyp können Sie nur eine Bezeichnung und eine Beschreibung hinzufügen. Der Rest der Konfiguration kann nicht bearbeitet werden. Es wurde vom technischen Benutzer durchgeführt. Näheres wird im Abschnitt [](../event/about-events.md) beschrieben.

## Reaktionsereignisse {#section_dhx_gss_dgb}

Unter den verschiedenen Ereignisaktivitäten, die in der Palette verfügbar sind, finden Sie das integrierte **Reaktionsereignis** . Mit dieser Aktivität können Sie auf Verfolgungsdaten reagieren, die sich auf eine mit E-Mail-, SMS- oder Push-Aktivitäten gesendete Nachricht innerhalb derselben Reise beziehen. Diese Informationen stammen aus Transaktionsnachrichten in Adobe Campaign Standard. Wir erfassen diese Informationen in Echtzeit, sobald sie für die Datenplattform freigegeben werden. Bei Push-Benachrichtigungen können Sie auf angeklickte, gesendete oder fehlgeschlagene Nachrichten reagieren. Bei SMS-Nachrichten können Sie auf gesendete oder fehlgeschlagene Nachrichten reagieren. Bei E-Mails können Sie auf angeklickte, gesendete, geöffnete oder fehlgeschlagene Nachrichten reagieren.

Sie können diesen Mechanismus auch verwenden, um eine Aktion auszuführen, wenn keine Reaktion auf Ihre Nachrichten erfolgt. Erstellen Sie dazu einen zweiten Pfad parallel zur Reaktionsaktivität und fügen Sie eine Warteaktivität hinzu. Wenn während des in der Warteaktivität definierten Zeitraums keine Reaktion erfolgt, wird der zweite Pfad gewählt. Sie können beispielsweise eine Folgemeldung senden.

Beachten Sie, dass Sie eine Reaktionsaktivität auf der Arbeitsfläche nur verwenden können, wenn zuvor eine E-Mail-, Push- oder SMS-Aktivität stattgefunden hat.

Näheres wird im Abschnitt [](../building-journeys/about-action-activities.md) beschrieben.

![](../assets/journey45.png)

Im Folgenden werden die verschiedenen Schritte zum Konfigurieren der Reaktionsereignisse beschrieben:

1. Fügen Sie der Reaktion eine **[!UICONTROL Beschriftung]**hinzu. Dieser Schritt ist optional.
1. Wählen Sie aus der Dropdownliste die Aktionsaktivität aus, auf die Sie reagieren möchten. Sie können jede Aktionsaktivität auswählen, die in den vorherigen Schritten des Pfades platziert wurde.
1. Wählen Sie je nach ausgewählter Aktion (E-Mail, SMS oder Push-Benachrichtigung) aus, worauf Sie reagieren möchten.
1. Sie können eine Bedingung als optionalen Schritt definieren. Beispielsweise können Sie nach einer E-Mail-Aktion zwei Pfade erstellen: einen mit einem Reaktionsereignis, um Klicks nur für VIP-Kunden zu verfolgen, und einen mit einem Reaktionsereignis, um Klicks von Frauen zu verfolgen.

>[!NOTE]
>
>Reaktionsereignisse können keine E-Mail-, SMS- oder Push-Aktionen verfolgen, die auf einer anderen Reise stattfinden.
>
>Reaktionsereignisse verfolgen Klicks auf Links des Typs &quot;verfolgt&quot;(siehe diese [Seite](https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/links.html#about-tracked-urls)). Die Links zum Abbestellen und Spiegeln von Seiten werden nicht berücksichtigt.

>[!CAUTION]
>
>E-Mail-Clients wie Gmail erlauben die Blockierung von Bildern. E-Mails, die geöffnet werden, werden mit einem Bild von 0 Pixel verfolgt, das in der E-Mail enthalten ist. Wenn Bilder blockiert werden, wird das Öffnen von E-Mails nicht berücksichtigt.

## Erweiterte Verwendung: Ereignisse mit paralleler Wartezeit{#section_vxv_h25_pgb}

**Wie können Sie eine Veranstaltung nur während einer bestimmten Zeit abhören?**

Eine auf der Reise positionierte Ereignisaktivität überwacht Ereignisse unbegrenzt. Damit ein Ereignis nur während einer bestimmten Zeit überwacht werden kann, müssen Sie parallel zum Ereignispfad eine Warteaktivität hinzufügen. Die Reise überwacht dann das Ereignis während der in der Warteaktivität angegebenen Zeit. Wenn ein Ereignis während dieses Zeitraums empfangen wird, fließt die Person in den Ereignispfad. Andernfalls fließt der Kunde in den Wartepfad.

Sie haben beispielsweise einen Willkommens-Push an einen Kunden geschickt und möchten nur dann einen Push mit einem Rabatt senden, wenn der Kunde innerhalb der nächsten 6 Stunden ins Restaurant kommt. Dazu erstellen Sie einen zweiten Pfad (parallel zum Restaurantereignis) mit einer 6-stündigen Wartezeit. Wenn das Restaurantereignis weniger als 6 Stunden nach dem Begrüßungs-Push empfangen wird, wird die Push-Aktivität für das Essen gesendet. Wenn innerhalb der nächsten 6 Stunden kein Restaurantereignis eingeht, fließt die Person durch den Warteweg.

![](../assets/journeyuc2_31.png)
