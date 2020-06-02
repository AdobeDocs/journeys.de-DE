---
title: Ereignisaktivitäten
description: Erfahren Sie mehr über Ereignisaktivitäten
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
source-git-commit: 957e72de7feccb33684523e26b2bdccb2074e4ca
workflow-type: tm+mt
source-wordcount: '971'
ht-degree: 77%

---


# Ereignisaktivitäten {#concept_rws_1rt_52b}

Die vom technischen Anwender konfigurierten Ereignisse (siehe [](../event/about-events.md)) werden alle in der ersten Kategorie der Palette auf der linken Seite des Bildschirms angezeigt.

![](../assets/journey43.png)

Beginnen Sie Ihre Journey immer mit Drag-and-Drop einer Ereignisaktivität. Sie können auf diese auch doppelklicken.

![](../assets/journey44.png)

Wenn Sie auf die Ereignisaktivität auf der Arbeitsfläche klicken, wird der Konfigurationsbereich für die Aktivität angezeigt. Wenn Sie dasselbe Ereignis mehrmals verwenden, wird dem Ereignisnamen auf der Arbeitsfläche standardmäßig eine fortlaufende Nummer hinzugefügt. Darüber hinaus können Sie mit dem Feld **[!UICONTROL Titel]** dem Ereignisnamen ein Suffix hinzufügen, das unter Ihrer Aktivität auf der Arbeitsfläche angezeigt wird. Dies ist nützlich, um Ihre Ereignisse auf der Arbeitsfläche zu identifizieren, insbesondere wenn Sie dasselbe Ereignis mehrmals verwenden. Außerdem wird die Problembehebung bei Fehlern und das Lesen von Berichten erleichtert.

![](../assets/journey33.png)

## Allgemeine Ereignisse {#section_ofg_jss_dgb}

Für diesen Ereignistyp können Sie nur einen Titel und eine Beschreibung hinzufügen. Der Rest der Konfiguration kann nicht bearbeitet werden. Dies wurde vom technischen Anwender durchgeführt. Siehe [](../event/about-events.md).

## Reaktionsereignisse {#section_dhx_gss_dgb}

Unter den verschiedenen Ereignisaktivitäten, die in der Palette verfügbar sind, finden Sie das integrierte **Reaktionsereignis**. Mit dieser Aktivität können Sie auf Tracking-Daten reagieren, die sich auf eine mit E-Mail-, SMS- oder Push-Aktivitäten gesendete Nachricht innerhalb derselben Journey beziehen. Diese Informationen stammen aus Transaktionsnachrichten in Adobe Campaign Standard. Wir erfassen diese Informationen in Echtzeit, sobald sie für die Datenplattform freigegeben werden. Bei Push-Benachrichtigungen können Sie auf angeklickte, gesendete oder fehlgeschlagene Nachrichten reagieren. Bei SMS-Nachrichten können Sie auf gesendete oder fehlgeschlagene Nachrichten reagieren. Bei E-Mails können Sie auf angeklickte, gesendete, geöffnete oder fehlgeschlagene Nachrichten reagieren.

Sie können diesen Mechanismus auch verwenden, um eine Aktion auszuführen, wenn keine Reaktion auf Ihre Nachrichten erfolgt. Erstellen Sie dazu einen zweiten Pfad parallel zur Reaktionsaktivität und fügen Sie eine Warteaktivität hinzu. Wenn während des in der Warteaktivität definierten Zeitraums keine Reaktion erfolgt, wird der zweite Pfad ausgewählt. Sie können beispielsweise eine Folgenachricht senden.

Beachten Sie, dass Sie eine Reaktionsaktivität auf der Arbeitsfläche nur verwenden können, wenn zuvor eine E-Mail-, Push- oder SMS-Aktivität stattgefunden hat.

Siehe [](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

Im Folgenden werden die verschiedenen Schritte zum Konfigurieren der Reaktionsereignisse beschrieben:

1. Fügen Sie der Reaktion einen **[!UICONTROL Titel]** hinzu. Dieser Schritt ist optional.
1. Wählen Sie aus der Dropdown-Liste die Aktionsaktivität aus, auf die Sie reagieren möchten. Sie können jede Aktionsaktivität auswählen, die in den vorherigen Schritten des Pfades platziert wurde.
1. Wählen Sie je nach ausgewählter Aktion (E-Mail, SMS oder Push-Benachrichtigung) aus, worauf Sie reagieren möchten.
1. Sie können eine Bedingung als optionalen Schritt definieren. Beispielsweise können Sie nach einer E-Mail-Aktion zwei Pfade erstellen, einen mit einem Reaktionsereignis zum Verfolgen von Klicks nur für VIP-Kunden und einen mit einem Reaktionsereignis zum Verfolgen von Klicks, die von Frauen ausgeführt wurden.

>[!NOTE]
>
>Reaktionsereignisse können keine E-Mail-, SMS- oder Push-Aktionen verfolgen, die in einer anderen Journey stattfinden.
>
>Reaktionsereignisse verfolgen Klicks auf Links des Typs „verfolgt“ (siehe diese [Seite](https://docs.adobe.com/content/help/de-DE/campaign-standard/using/designing-content/links.html#about-tracked-urls)). Abmeldungs- und Mirrorseiten-Links werden nicht berücksichtigt.

>[!CAUTION]
>
>E-Mail-Clients wie Gmail erlauben die Blockierung von Bildern. Das Öffnen von E-Mails wird anhand eines in der E-Mail enthaltenen 0-Pixel-Bildes nachverfolgt. Wenn Bilder blockiert werden, wird das Öffnen von E-Mails nicht berücksichtigt.

## Ereignisse zur Segmentqualifizierung {#segment-qualification}

Diese Aktivität ermöglicht es Ihnen, die Ein- und Ausgänge von Profilen in Plattformsegmenten anzuhören, um Einzelpersonen dazu zu bewegen, in eine Reise einzusteigen oder sich vorwärts zu bewegen. For more information on segment creation, refer to this [section](../segment/about-segments.md).

Nehmen wir einmal an, Sie haben ein Segment &quot;Silber-Kunde&quot;. Mit dieser Aktivität können Sie alle Neukunden auf eine Reise bringen und ihnen eine Reihe personalisierter Nachrichten senden.

Diese Art von Ereignis kann als erster Schritt oder später auf der Reise positioniert werden.

Wenn das Segment mit der Option &quot;Hochfrequente Audiencen&quot;der Plattform gestreamt wird, werden Einstiegs- und Ausstiege in Echtzeit überwacht. Wenn das Segment nicht gestreamt wird, werden Ein- und Ausstiege bei der Segmentberechnung berücksichtigt.

1. Entpacken Sie die Kategorie der **Ereignis** und legen Sie eine Aktivität für die **Segmentqualifizierung** auf Ihrer Arbeitsfläche ab.

   ![](../assets/segment5.png)

1. Add a **Label** to the activity. Dieser Schritt ist optional.

1. Klicken Sie in das Feld **Segment** und wählen Sie die Segmente aus, die Sie nutzen möchten.

   ![](../assets/segment6.png)

1. Wählen Sie im Feld &quot; **Verhalten** &quot;aus, ob Sie die Segmenteingänge, -ausstiege oder beides überwachen möchten.

1. Namensraum auswählen. Dies ist nur dann erforderlich, wenn das Ereignis als erster Reiseschritt positioniert ist.

   ![](../assets/segment7.png)

Die Payload enthält die folgenden Kontextinformationen, die Sie in Bedingungen und Aktionen verwenden können:

* Verhalten (Eingang, Ausgang)
* Zeitstempel der Qualifikation
* die Segment-ID

## Erweiterte Verwendung: Ereignisse mit paralleler Wartezeit{#section_vxv_h25_pgb}

**Wie können Sie ein Ereignis nur während einer bestimmten Zeit überwachen?**

Eine in der Journey positionierte Ereignisaktivität überwacht Ereignisse auf unbestimmte Zeit. Damit ein Ereignis nur während einer bestimmten Zeit überwacht wird, müssen Sie parallel zum Ereignispfad eine Warteaktivität hinzufügen. Die Journey überwacht dann das Ereignis während der in der Warteaktivität angegebenen Zeit. Wenn ein Ereignis während dieses Zeitraums empfangen wird, wird die Person in den Ereignispfad geleitet. Andernfalls wird der Kunde in den Wartepfad geleitet.

Sie haben beispielsweise eine erste Willkommens-Push-Benachrichtigung an einen Kunden gesendet und möchten nur dann eine Push-Benachrichtigung mit einem Rabatt senden, wenn der Kunde innerhalb der nächsten 6 Stunden ins Restaurant kommt. Dazu erstellen Sie einen zweiten Pfad (parallel zum Restaurantereignis) mit einer 6-stündigen Warteaktivität. Wenn das Restaurantereignis weniger als 6 Stunden nach der Begrüßungs-Push-Benachrichtigung eingeht, wird die Push-Aktivität für den Rabatt gesendet. Wenn innerhalb der nächsten 6 Stunden kein Restaurantereignis eingeht, wird die Person durch den Wartepfad geleitet.

![](../assets/journeyuc2_31.png)
