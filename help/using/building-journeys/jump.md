---
title: Springen von einer Reise zur nächsten
description: Springen von einer Reise zur nächsten
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 1ec824dcfd54bde5f3aab80ce30dbc9a19b9e4c1
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---


# Springen von einer Reise zur nächsten {#jump}

>[!NOTE]
>
>Wirksame Verfügbarkeit: 15. November 2020

Mit der Aktivität **Sprungaktion** können Sie Einzelpersonen von einer Reise zur nächsten verschieben. Mit dieser Funktion können Sie:

* Vereinfachung der Gestaltung sehr komplexer Fahrten durch Aufteilung in mehrere Fahrten
* Aufbau von Fahrten auf der Grundlage gemeinsamer und wiederverwendbarer Reisemuster

Fügen Sie in der Herkunft einfach einen **Sprung** hinzu und wählen Sie eine Zielgruppe Reise. Wenn der Einzelne in den Sprungschritt eintritt, wird ein internes Ereignis an das erste Ereignis der Zielgruppe gesendet. Wenn die Sprungaktion erfolgreich ist, wird der Einzelne auf der Reise weiter vorankommen. Das Verhalten ist mit anderen Aktionen vergleichbar.

Auf dem Weg zur Zielgruppe wird das erste intern durch den Sprung ausgelöste Ereignis den individuellen Verlauf der Reise ausmachen.

## Lebenszyklus

Nehmen wir an, Sie haben einen Sprung in eine Reise A zu einer Reise B hinzugefügt. Reise A ist die **Herkunft Reise** und Reise B, die **Zielgruppe Reise**.
Im Folgenden sind die verschiedenen Schritte des Ausführungsprozesses aufgeführt:

**Reise A** wird von einem externen Ereignis ausgelöst:

1. Die Reise A erhält ein externes Ereignis, das mit einer Einzelperson verbunden ist.
1. Das Individuum erreicht den Sprungschritt.
1. Der Einzelne wird nach dem Sprung zu Journey B gedrängt und fährt mit den nächsten Schritten in der Reise A fort.

Auf **Reise B** kann das erste Ereignis extern (wie ein reguläres Ereignis) oder intern über einen Sprung von Reise A ausgelöst werden:

1. Journey B erhielt ein internes Ereignis von Journey A.
1. Das erste Ereignis von Journey B wird durch die Informationen von Journey A ausgelöst.
1. Die einzelnen Beginn fließen in der Reise B.

## Wichtige Hinweise              

* Sie können nur zu einer Reise springen, die denselben Namensraum wie die Herkunft verwendet.
* Sie können nicht zu einer Reise springen, die Beginn mit einem **Segmentqualifizierungs** -Ereignis führen.
* Wenn der Sprung ausgeführt wird, wird die neueste Version der Zielgruppe-Reise ausgelöst.
* Sie können so viele Sprünge wie nötig in eine Reise einbeziehen. Nach einem Sprung können Sie jede erforderliche Aktivität hinzufügen.
* Sie können so viele Sprungstufen wie nötig haben. So springt z.B. &quot;Reise A&quot;zu &quot;Reise B&quot;, die zu &quot;Reise C&quot;springt usw.
* Die Zielgruppe-Reise kann auch so viele Sprünge wie nötig umfassen.
* Schleifenmuster werden nicht unterstützt. Es gibt keine Möglichkeit, zwei oder mehr Reisen miteinander zu verbinden, was zu einer unendlichen Schleife führen würde. Der Konfigurationsbildschirm für die **Schnellstartkonfiguration** verhindert dies.
* Wie üblich kann eine individuelle Person nur einmal auf einer Reise anwesend sein. Wenn sich das Individuum, das von der Herkunft gedrängt wird, bereits auf der Zielgruppe befindet, wird das Individuum nicht in die Zielgruppe reisen. Beim Sprung wird kein Fehler gemeldet, da dies ein normales Verhalten ist.

## Konfigurieren des Sprungs

1. Entwerfen Sie Ihre Herkunft.

   ![](../assets/jump1.png)

1. Fügen Sie bei jedem Schritt der Reise eine **Sprung** -Aktivität aus der **Action** -Kategorie hinzu. hinzufügen einer Bezeichnung und Beschreibung.

   ![](../assets/jump2.png)

1. Klicken Sie in das Feld **Zielgruppe Reise** .
Die Liste zeigt alle Reiseversionen an, die Entwurfs-, Live- oder Testversionen sind. Reisen, die einen anderen Namensraum oder diesen Beginn mit einem Ereignis für die **Segmentqualifikation** verwenden, sind nicht verfügbar. Reisen mit Zielgruppen, die ein Schleifenmuster erzeugen würden, werden ebenfalls herausgefiltert.

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >Sie können auf das Symbol **Offene Zielgruppe Reise** auf der rechten Seite klicken, um die Zielgruppe Reise in einem neuen Register zu öffnen.

1. Wählen Sie die Zielgruppe, zu der Sie springen möchten.
Das Feld &quot; **Erstes Ereignis** &quot;wird vorab mit dem Namen des ersten Ereignisses der Zielgruppe gefüllt. Wenn Ihre Zielgruppe mehrere Ereignis umfasst, ist der Sprung nur am ersten Ereignis zulässig.

   ![](../assets/jump4.png)

1. Im Abschnitt **Aktionsparameter** werden alle Felder des Ereignisses Zielgruppe angezeigt. Ordnen Sie wie bei anderen Aktionstypen die Felder aus dem Ereignis der Herkunft oder der Datenquelle jedem Feld zu. Diese Informationen werden zur Laufzeit an die Zielgruppe weitergeleitet.
1. hinzufügen die nächsten Aktivitäten, um Ihre Herkunft zu beenden.

   ![](../assets/jump5.png)

Ihr Sprung ist konfiguriert. Sobald Ihre Reise live oder im Testmodus ist, werden Personen, die den Sprung erreichen, von der Zielgruppe auf die Reise gedrängt.

Wenn ein Sprung auf einer Zielgruppe konfiguriert ist, wird automatisch ein Sprungeingabesymbol zu Beginn der Fahrt hinzugefügt. Auf diese Weise können Sie erkennen, dass die Reise extern, aber auch intern von einem Sprung aus ausgelöst werden kann.

## Fehlerbehebung

Wenn die Reise veröffentlicht wird oder sich im Testmodus befindet, treten Fehler auf, wenn:
* die Zielgruppe nicht mehr existiert
* die Zielgruppe wird als Entwurf, geschlossen oder gestoppt
* wenn sich das erste Ereignis der Zielgruppe-Reise geändert hat und die Zuordnung beschädigt ist
