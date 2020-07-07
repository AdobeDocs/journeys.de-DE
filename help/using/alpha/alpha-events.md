---
title: Regelbasierte Ereignis
description: Weitere Informationen zu regelbasierten Ereignissen.
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
source-git-commit: f146a22cec5ffbbc61b51f8fc3c875078b2ee6bf
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 8%

---


# Regelbasierte Ereignis{#simplified-events}

Wir haben die Einrichtung von Experience Ereignisses vereinfacht. Wir führen eine neue Methode ein, bei der keine eventID verwendet werden muss. Wenn Sie Ihr Ereignis in Journey Orchestration einrichten, können Sie jetzt ein regelbasiertes Ereignis definieren.

Dieser neue Typ von Ereignis generiert keine eventID. Mit dem einfachen Ausdruck-Editor definieren Sie jetzt einfach eine Regel, die vom System verwendet wird, um die relevanten Ereignis zu identifizieren, die Ihre Reise auslösen werden. Diese Regel kann auf allen in der Ereignis-Nutzlast verfügbaren Feldern basieren, z. B. auf der Position des Profils oder der Anzahl der dem Einkaufswagen des Profils hinzugefügten Artikel.

Diese neue Methode ist meist transparent für Benutzer. Die einzige Änderung ist ein neues Feld im Bildschirm &quot;Ereignis-Definition&quot;.

1. Klicken Sie im linken Menü auf das Symbol **Admin** und dann auf **Ereignis**. Die Liste der Ereignisse wird angezeigt.

   ![](../assets/alpha-event1.png)

1. Klicken Sie auf **Hinzufügen**, um ein neues Ereignis zu erstellen. Der Bereich für die Ereigniskonfiguration wird auf der rechten Seite des Bildschirms geöffnet.

   ![](../assets/alpha-event2.png)

1. Geben Sie den Namen Ihres Ereignisses ein. Sie können auch eine Beschreibung hinzufügen.

   ![](../assets/alpha-event3.png)

1. Wählen Sie im neuen Feld **Ereignis-ID-Typ** die Option **Regelbasiert**.

   ![](../assets/alpha-event4.png)

   >[!NOTE]
   >
   >Der **systemgenerierte** Typ ist die vorhandene Methode, für die eine eventID erforderlich ist. Siehe [diesen Abschnitt](../event/about-events.md).

1. Definieren Sie die **Schema** - und **Nutzdatenfelder**. Siehe [diesen Abschnitt](../event/defining-the-payload-fields.md).

   ![](../assets/alpha-event5.png)

   >[!NOTE]
   >
   >Wenn Sie den **systemgenerierten Typ** auswählen, sind nur Schema verfügbar, für die der eventID-Typ mixin verfügbar ist. Wenn Sie den **regelbasierten** Typ auswählen, stehen alle Experience Ereignis-Schema zur Verfügung.

1. Klicken Sie in das Feld **Ereignis-ID-Bedingung** . Definieren Sie mithilfe des Ausdruck-Editors die Bedingung, die vom System zur Identifizierung der Ereignis verwendet wird, die Ihre Reise auslösen.

   ![](../assets/alpha-event6.png)

   In unserem Beispiel haben wir eine Bedingung geschrieben, die auf der Stadt des Profils basiert. Das bedeutet, dass das System jedes Mal, wenn es ein Ereignis erhält, das dieser Bedingung entspricht (**City** -Feld und **Paris** -Wert), es an die Journey Orchestration übergeben wird.

1. Definieren des **Namensraums** und des **Schlüssels**. Siehe [Auswählen des Namensraums](../event/selecting-the-namespace.md) und [Definieren des Ereignis-Schlüssels](../event/defining-the-event-key.md).

   ![](../assets/alpha-event7.png)

Die anderen Schritte für die Konfiguration und Erstellung von Ereignissen bleiben unverändert.

Das Ereignis ist jetzt so konfiguriert und bereit, wie jedes andere Ereignis auf eine Reise gesetzt zu werden. Jedes Mal, wenn ein Ereignis, das der Regel entspricht, an das System gesendet wird, wird es an die Journey Orchestration übergeben, um Ihre Reisen auszulösen.

