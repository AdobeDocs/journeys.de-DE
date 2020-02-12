---
title: Zeitzonen-Management
description: Erfahren Sie mehr über das Zeitzonen-Management
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: f57cc43d8f2a223c04cc4ccccb3b3c3e0bcadfc1

---



# Zeitzonen-Management {#timezone_management}

Die Definition von Zeitzonen ist in den folgenden Aktivitäten verfügbar:

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

Wenn das Eintrittsereignis der Journey einen Namespace hat, d. h. die Journey kann den Echtzeit-Kundenprofildienst der Datenplattform erreichen, wird die Zeitzone mit jener im Profil des Kontakts vordefiniert, der sich in der Journey befindet. Wenn das Profil des Kontakts keine Zeitzone enthält, wird die Zeitzone der Instanz verwendet. Wenden Sie sich an Ihren Administrator, um die Zeitzone der Instanz zu erfragen.

![](../assets/journey73.png)

Die Zeitzone kann auch fest definiert werden. Löschen Sie die vordefinierte Zeitzone und wählen Sie eine aus der Dropdown-Liste aus. Wenn Sie eine feste Zeitzone verwenden, ist diese für alle Kontakte gleich, die die Journey beginnen.

![](../assets/journey72.png)

Schließlich kann die Zeitzone für jede Person, die den Schritt betritt, dynamisch sein. In diesem Fall verwenden Sie den Ausdruckseditor, um auszuwählen, wo das System diese Informationen abrufen soll (sie können von einem Ereignis oder einer Datenquelle stammen). Siehe [](../expression/expressionadvanced.md).


Das Start- und Enddatum einer Journey kann nicht mit einer bestimmten Zeitzone verknüpft werden. Es wird automatisch mit der Zeitzone der Instanz verbunden.
