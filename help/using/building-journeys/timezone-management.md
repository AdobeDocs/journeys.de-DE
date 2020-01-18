---
title: Zeitzonen
description: Informationen zum Zeitzonenmanagement
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
source-git-commit: f57cc43d8f2a223c04cc4ccccb3b3c3e0bcadfc1

---



# Zeitzonen {#timezone_management}

Die Definition der Zeitzone ist in den folgenden Aktivitäten verfügbar:

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

Wenn das Einstiegsereignis der Reise einen Namespace hat, d. h. die Reise kann den Echtzeitkundenprofildienst der Datenplattform erreichen, wird die Zeitzone mit der im Profil des einzelnen, auf der Reise ablaufenden Benutzers festgelegten Zeitzone vordefiniert. Wenn das Profil des Benutzers keine Zeitzone enthält, wird die Zeitzone der Instanz verwendet. Wenden Sie sich an Ihren Administrator, um die Zeitzone der Instanz zu erfahren.

![](../assets/journey73.png)

Die Zeitzone kann auch festgelegt werden. Löschen Sie die vordefinierte Zeitzone und wählen Sie eine aus der Dropdownliste aus. Wenn Sie eine feste Zeitzone verwenden, ist diese für alle Personen gleich, die die Reise beginnen.

![](../assets/journey72.png)

Schließlich kann die Zeitzone für jede Person, die den Schritt betritt, dynamisch sein. In diesem Fall verwenden Sie den Ausdruckseditor, um auszuwählen, wo das System diese Informationen abrufen soll (sie können von einem Ereignis oder einer Datenquelle stammen). Näheres wird im Abschnitt [](../expression/expressionadvanced.md) beschrieben.


Start- und Enddaten einer Reise können nicht mit einer bestimmten Zeitzone verknüpft werden. Sie werden automatisch der Zeitzone der Instanz zugeordnet.
