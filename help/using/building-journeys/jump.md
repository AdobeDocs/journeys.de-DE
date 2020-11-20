---
product: adobe campaign
solution: Journey Orchestration
title: Springen zwischen Journeys
description: Springen zwischen Journeys
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 100%

---


# Springen zwischen Journeys {#jump}

>[!NOTE]
>
>Tatsächliche Verfügbarkeit: 15. November 2020

Mit der Aktionsaktivität **Sprung** können Sie Kontakte von einer Journey in eine andere bewegen. Diese Funktion unterstützt:

* Vereinfachung der Gestaltung sehr komplexer Journeys durch Aufteilung in mehrere Journeys
* Erstellung von Journeys anhand allgemeiner und wiederverwendbarer Journey-Muster

Fügen Sie in der Ursprungs-Journey einfach einen **Sprung** hinzu und wählen Sie eine Ziel-Journey aus. Wenn der Kontakt in den Sprungschritt eintritt, wird ein internes Ereignis an das erste Ereignis der Ziel-Journey gesendet. Wenn die Sprungaktion erfolgreich ist, schreitet der Kontakt in der Journey fort. Das Verhalten ist mit anderen Aktionen vergleichbar.

In der Ziel-Journey leitet das erste Ereignis, das intern durch den Sprung ausgelöst wurde, den Kontakt in die Journey.

## Lebenszyklus

Nehmen wir an, Sie haben in einer Journey A einen Sprung zu einer Journey B hinzugefügt. Journey A ist dann die **Ursprungs-Journey** und Journey B die **Ziel-Journey**.
Im Folgenden finden Sie die verschiedenen Schritte des Ausführungsprozesses:

**Journey A** wird von einem externen Ereignis ausgelöst:

1. Journey A empfängt ein externes Ereignis, das mit einem Kontakt in Verbindung steht.
1. Der Kontakt erreicht den Sprungschritt.
1. Der Kontakt wird in Journey B geleitet und fährt nach dem Sprung mit den nächsten Schritten in Journey A fort.

In **Journey B** kann das erste Ereignis extern (wie ein reguläres Ereignis) oder intern über einen Sprung von Journey A ausgelöst werden:

1. Journey B erhielt ein internes Ereignis von Journey A.
1. Das erste Ereignis von Journey B wird mit den Informationen von Journey A ausgelöst.
1. Die Kontakte werden in Journey B geleitet.

## Wichtige Hinweise

* Sie können nur in eine Journey springen, die denselben Namespace wie die Ursprungs-Journey verwendet.
* Sie können nicht in eine Journey springen, die mit einem **Segmentqualifikationsereignis** beginnt.
* Wenn der Sprung ausgeführt wird, wird die aktuelle Version der Ziel-Journey ausgelöst.
* Sie können so viele Sprünge in eine Journey aufnehmen, wie Sie benötigen. Nach einem Sprung können Sie jede erforderliche Aktivität hinzufügen.
* Sie können beliebig viele Sprungstufen einfügen. So kann z. B. Journey A zu Journey B springen, welche zu Journey C springt, usw.
* Auch die Ziel-Journey kann beliebig viele Sprünge umfassen.
* Schleifenmuster werden nicht unterstützt. Es gibt keine Möglichkeit, zwei oder mehr Journeys miteinander zu verbinden, die eine Endlosschleife erzeugen würden. Der Konfigurationsbildschirm für **Sprungaktivitäten** verhindert dies.
* Wie üblich darf sich ein eindeutiger Kontakt nur einmal in einer Journey befinden. Wenn sich der Kontakt, der aus der Ursprungs-Journey bewegt wurde, bereits in der Ziel-Journey befindet, tritt der Kontakt also nicht mehr in die Ziel-Journey ein. Beim Sprung wird kein Fehler gemeldet, da dies ein normales Verhalten ist.

## Konfigurieren des Sprungs

1. Gestalten Sie die Ursprungs-Journey.

   ![](../assets/jump1.png)

1. Fügen Sie einem beliebigen Schritt in der Journey eine **Sprungaktivität** der Kategorie **Aktion** hinzu. Fügen Sie einen Titel und eine Beschreibung hinzu.

   ![](../assets/jump2.png)

1. Klicken Sie in das Feld **Ziel-Journey**.
Die Liste zeigt alle Journey-Versionen an, die sich im Entwurfs-, Live- oder Testmodus befinden. Journeys, die einen anderen Namespace verwenden oder mit einem **Segmentqualifikationsereignis** beginnen, sind nicht verfügbar. Ziel-Journeys, die ein Schleifenmuster erzeugen würden, werden ebenfalls herausgefiltert.

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >Sie können rechts auf das Symbol **Zielgruppen-Journey öffnen** klicken, um die Ziel-Journey in einem neuen Tab zu öffnen.

1. Wählen Sie die Ziel-Journey aus, zu der Sie springen möchten.
Das Feld **Erstes Ereignis** wird vorab mit dem Namen des ersten Ereignisses der Ziel-Journey gefüllt. Wenn Ihre Ziel-Journey mehrere Ereignisse umfasst, ist der Sprung nur zum ersten Ereignis zulässig.

   ![](../assets/jump4.png)

1. Im Abschnitt **Aktionsparameter** werden alle Felder des Zielereignisses angezeigt. Ordnen Sie wie bei anderen Arten von Aktionen jedem Feld Felder aus dem Ursprungsereignis oder der Datenquelle zu. Diese Informationen werden zur Laufzeit an die Ziel-Journey weitergegeben.
1. Fügen Sie die nächsten Aktivitäten hinzu, um Ihre Ursprungs-Journey zu beenden.

   ![](../assets/jump5.png)

Ihr Sprung ist konfiguriert. Sobald Ihre Journey live oder im Testmodus ist, werden Kontakte, die den Sprung erreichen, in die Ziel-Journey geleitet.

Wenn in einer Journey ein Sprung konfiguriert ist, wird zu Beginn der Ziel-Journey automatisch ein Sprungeintrittssymbol hinzugefügt. Auf diese Weise können Sie erkennen, dass die Journey sowohl extern als auch intern durch einen Sprung ausgelöst werden kann.

## Fehlerbehebung

Wenn die Journey veröffentlicht wird oder sich im Testmodus befindet, treten Fehler auf, wenn:
* die Ziel-Journey nicht mehr existiert,
* der Zustand der Ziel-Journey „Entwurf“, „geschlossen“ oder „gestoppt“ ist,
* wenn sich das erste Ereignis der Ziel-Journey geändert hat und die Zuordnung unterbrochen ist.
