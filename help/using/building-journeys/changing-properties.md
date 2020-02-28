---
title: Ändern von Eigenschaften
description: Erfahren Sie, wie Sie Eigenschaften ändern
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
source-git-commit: 76369cd714c513e0038278ad058bf1ba43fcd240

---



# Ändern von Eigenschaften {#concept_prq_wqt_52b}

Klicken Sie auf das Bleistiftsymbol oben rechts, um auf die Eigenschaften der Journey zuzugreifen.

You can change the name of the journey, add a description, allow re-entrance, choose start and end dates and define a **[!UICONTROL Timeout and error]** duration if you are admin.

![](../assets/journey32.png)

## Zutritt{#entrance}

Standardmäßig ist bei neuen Journeys der erneute Zutritt erlaubt. Sie können die Option für „einmalige“ Journeys deaktivieren, z. B. wenn Sie ein einmaliges Geschenk anbieten möchten, wenn eine Person einen Shop betritt. In diesem Fall möchten Sie nicht, dass der Kunde die Journey erneut betreten und das Angebot erneut wahrnehmen kann.

When a journey &quot;ends&quot;, it will have the status **[!UICONTROL Finished]**. Die Journey erlaubt den Zutritt neuer Kontakte nicht mehr. Personen, die sich bereits in der Journey befinden, beenden die Journey wie gewohnt.

## Zeitüberschreitung und Fehler bei Journey-Aktivitäten {#timeout_and_error}

Beim Bearbeiten einer Aktions- oder Bedingungsaktivität können Sie im Falle eines Fehlers oder einer Zeitüberschreitung einen alternativen Pfad definieren. If the processing of the activity interrogating a third-party system exceeds the timeout duration defined in the journey&#39;s properties (**[!UICONTROL Timeout and  error]** field), the second path will be chosen to perform a potential fallback action.

Die zulässigen Werte liegen zwischen 1 und 30 Sekunden.

We recommend that you define a very short **[!UICONTROL Timeout and error]** value if your journey is time sensitive (example: reacting to the real-time location of a person) because you cannot delay your action for more than a few seconds. Wenn Ihre Journey weniger zeitkritisch ist, können Sie einen längeren Wert verwenden, um dem aufgerufenen System mehr Zeit zum Senden einer gültigen Antwort zu geben.

Bei Journey Orchestration wird auch eine globale Zeitüberschreitung verwendet. Siehe [nächster Abschnitt](#global_timeout).

## Globale Journey-Zeitüberschreitung {#global_timeout}

Zusätzlich zu der in den Journey-Aktivitäten verwendeten [Zeitüberschreitung](#timeout_and_error) gibt es auch eine globale Journey-Zeitüberschreitung, die nicht auf der Benutzeroberfläche angezeigt wird und nicht geändert werden kann. Diese Zeitüberschreitung stoppt den Fortschritt von Kontakten in der Journey 30 Tage nach ihrem Eintritt. Das bedeutet, dass die Journey eines Kontakts nicht länger als 30 Tage dauern kann. Nach Ablauf des Zeitraums von 30 Tagen werden die Daten des Kontakts gelöscht. Kontakte, die sich nach der Zeitüberschreitung noch in der Journey befinden, werden gestoppt und beim Reporting als Fehler gewertet.

>[!NOTE]
>
>Journey Orchestration reagiert nicht direkt auf Datenschutz-Opt-out-, Zugriffs- oder Löschanfragen. Die globale Zeitüberschreitung stellt jedoch sicher, dass Kontakte auf keinen Fall länger als 30 Tage in der Journey bleiben.

Aufgrund der Journey-Zeitüberschreitung nach 30 Tagen können wir, wenn der erneute Zutritt nicht erlaubt ist, nicht sicherstellen, dass die Sperrung des erneuten Zutritts nach mehr als 30 Tagen erhalten bleibt. Da wir alle Informationen über Personen, die an der Journey teilgenommen haben, 30 Tage nach deren Eintritt entfernen, können wir nicht wissen, dass die Person vor mehr als 30 Tagen bereits Zutritt hatte.

## Zeitzone und Profilzeitzone {#timezone}

Die Zeitzone wird auf der Ebene der Reise definiert.

Sie können eine feste Zeitzone eingeben oder Experience Platform-Profile verwenden, um die Zeitzone der Reise zu definieren.

Weitere Informationen zur Zeitzonenverwaltung finden Sie unter [](../building-journeys/timezone-management.md).
