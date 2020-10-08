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
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 100%

---



# Ändern von Eigenschaften {#concept_prq_wqt_52b}

Klicken Sie auf das Bleistiftsymbol oben rechts, um auf die Eigenschaften der Journey zuzugreifen. 

Wenn Sie ein Administrator sind, können Sie den Namen der Journey ändern, eine Beschreibung hinzufügen, den erneuten Eintritt erlauben, Start- und Enddatum auswählen und eine Dauer für **[!UICONTROL Zeitüberschreitung und Fehler]** festlegen.

![](../assets/journey32.png)

## Eintritt{#entrance}

Standardmäßig ist bei neuen Journeys der erneute Eintritt erlaubt. Sie können die Option für „einmalige“ Journeys deaktivieren, z. B. wenn Sie ein einmaliges Geschenk anbieten möchten, wenn eine Person einen Shop betritt. In diesem Fall möchten Sie nicht, dass der Kunde die Journey erneut betreten und das Angebot erneut wahrnehmen kann.

Wenn eine Journey „endet“, weist sie den Status **[!UICONTROL Geschlossen (kein Eintritt)]** auf. Die Journey erlaubt den Eintritt neuer Kontakte nicht mehr. Personen, die sich bereits in der Journey befinden, beenden die Journey wie gewohnt.

## Zeitüberschreitung und Fehler bei Journey-Aktivitäten {#timeout_and_error}

Beim Bearbeiten einer Aktions- oder Bedingungsaktivität können Sie im Falle eines Fehlers oder einer Zeitüberschreitung einen alternativen Pfad definieren. Wenn die Verarbeitung der Aktivität, die ein Drittanbietersystem abfragt, die in den Eigenschaften der Journey festgelegte Zeitüberschreitungsdauer überschreitet (Feld **[!UICONTROL Zeitüberschreitung und Fehler]**), wird der zweite Pfad ausgewählt, um eine potenzielle Ausweichaktion durchzuführen.

Die zulässigen Werte liegen zwischen 1 und 30 Sekunden.

Es wird empfohlen, unter **[!UICONTROL Zeitüberschreitung und Fehler]** einen sehr kurzen Wert festzulegen, wenn Ihre Journey zeitkritisch ist (z. B. Reaktion auf den Echtzeit-Standort einer Person), da Sie Ihre Aktion nicht länger als einige Sekunden verzögern können. Wenn Ihre Journey weniger zeitkritisch ist, können Sie einen längeren Wert verwenden, um dem aufgerufenen System mehr Zeit zum Senden einer gültigen Antwort zu geben.

Bei [!DNL Journey Orchestration] wird auch eine globale Zeitüberschreitung verwendet. Siehe [nächster Abschnitt](#global_timeout).

## Globale Journey-Zeitüberschreitung {#global_timeout}

Zusätzlich zu der in den Journey-Aktivitäten verwendeten [Zeitüberschreitung](#timeout_and_error) gibt es auch eine globale Journey-Zeitüberschreitung, die nicht auf der Benutzeroberfläche angezeigt wird und nicht geändert werden kann. Diese Zeitüberschreitung stoppt den Fortschritt von Kontakten in der Journey 30 Tage nach ihrem Eintritt. Das bedeutet, dass die Journey eines Kontakts nicht länger als 30 Tage dauern kann. Nach Ablauf des Zeitraums von 30 Tagen werden die Daten des Kontakts gelöscht. Kontakte, die sich nach der Zeitüberschreitung noch in der Journey befinden, werden gestoppt und beim Reporting als Fehler gewertet.

>[!NOTE]
>
>[!DNL Journey Orchestration] reagiert nicht direkt auf Datenschutz-Opt-out-, Zugriffs- oder Löschanfragen. Die globale Zeitüberschreitung stellt jedoch sicher, dass Kontakte auf keinen Fall länger als 30 Tage in der Journey bleiben.

Aufgrund der Journey-Zeitüberschreitung nach 30 Tagen können wir, wenn der erneute Eintritt nicht erlaubt ist, nicht sicherstellen, dass die Sperrung des erneuten Eintritts nach mehr als 30 Tagen erhalten bleibt. Da wir alle Informationen über Personen, die an der Journey teilgenommen haben, 30 Tage nach deren Eintritt entfernen, können wir nicht wissen, dass die Person vor mehr als 30 Tagen bereits Eintritt hatte.

## Zeitzone und Zeitzone des Profils {#timezone}

Die Zeitzone wird auf Journey-Ebene definiert.

Sie können eine feste Zeitzone eingeben oder Adobe Experience Platform-Profile verwenden, um die Zeitzone der Journey festzulegen.

Weitere Informationen zum Zeitzonen-Management finden Sie unter [](../building-journeys/timezone-management.md).
