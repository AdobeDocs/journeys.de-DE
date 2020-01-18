---
title: Informationen zum erweiterten Verwendungsfall
description: Mehr über die Reise - fortgeschrittener Anwendungsfall
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
source-git-commit: 54b54a64ad2822eec96008ac4a2e16c208a4a3ab

---


# Informationen zum erweiterten Verwendungsfall{#concept_vzy_ncy_w2b}

## Zweck {#purpose}

Nehmen wir das Beispiel einer Hotelmarke namens Marlton. In ihren Hotels haben sie Beacon-Geräte in der Nähe aller strategischen Bereiche positioniert: Lobby, Fußböden, Restaurant, Fitnessraum, Pool, etc.

>[!NOTE]
>
>In diesem Fall verwenden wir Adobe Campaign Standard, um Nachrichten zu senden.

In diesem Fall werden wir sehen, wie personalisierte Nachrichten in Echtzeit an Kunden gesendet werden, wenn sie in der Nähe eines bestimmten Beacons gehen.

Zunächst möchten wir eine Nachricht senden, sobald eine Person in ein Marlton Hotel eintritt. Wir möchten eine Nachricht nur senden, wenn die Person innerhalb der letzten 24 Stunden keine Mitteilung von uns erhalten hat.

Anschließend prüfen wir zwei Bedingungen:

* Wenn diese Person kein Treuemitglied ist, senden wir ihm eine E-Mail, um dem Treueangebot beizutreten.
* Wenn diese Person bereits Treuemitglied ist, prüfen wir, ob sie über eine Zimmerreservierung verfügt:
   * Wenn er das nicht tut, senden wir ihm eine Push-Benachrichtigung mit Zimmerpreisen.
   * Wenn er das tut, senden wir ihm eine willkommene Push-Benachrichtigung. Und wenn er in den nächsten 6 Stunden ins Restaurant kommt, senden wir ihm eine Push-Benachrichtigung mit einem Rabatt auf eine Mahlzeit.

![](../assets/journeyuc2_29.png)

Für diesen Anwendungsfall müssen wir zwei Ereignisse erstellen (siehe [](../usecase/configuring-the-events.md)):

* Das Beacon-Ereignis der Lobby, das an das System gesendet wird, wenn ein Kunde das Hotel betritt.
* Das Restaurant-Beacon-Ereignis, das gestoßen wird, wenn ein Kunde das Restaurant betritt.

Es muss eine Verbindung zu zwei Datenquellen konfiguriert werden (siehe [](../usecase/configuring-the-data-sources.md)):

* Die integrierte Experience Platform-Datenquelle zum Abrufen der Informationen für unsere beiden Bedingungen (Treuemitgliedschaft und Datum des letzten Kontakts) sowie die Informationen zur Personalisierung der Nachricht.
* Das Hotelreservierungssystem, um die Informationen zum Reservierungsstatus abzurufen.

## Voraussetzungen: {#prerequisites}

Für unseren Verwendungsfall haben wir drei transaktionale Meldungsvorlagen von Adobe Campaign Standard entwickelt. Wir verwenden Vorlagen für Ereignistransaktionen. Refer to this [page](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign Standard ist so konfiguriert, dass E-Mails und Push-Benachrichtigungen gesendet werden.

Die Experience Cloud ID wird als Schlüssel zur Identifizierung des Kunden im Hotelreservierungssystem verwendet.

Ereignisse werden vom Handy des Kunden gesendet, wenn sie in der Nähe eines Beacons festgestellt wurden. Sie müssen eine Mobilanwendung entwerfen, um Ereignisse vom Handy des Kunden an das Mobile SDK zu senden.

Das Feld &quot;Treueanwärter&quot;ist ein benutzerdefiniertes Feld und wurde in XDM für unsere spezifische Organisations-ID hinzugefügt.
