---
title: 'Informationen zu ExperienceEvent-Schemas für Ereignisse zur Reiseorganisation '
description: 'Erfahren Sie mehr über ExperienceEvent-Schemas für Ereignisse der Reiseorganisation '
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
source-git-commit: 9b8d4bebe024e90733cb1ae6d31b36fb6ce4b606

---



# Informationen zu ExperienceEvent-Schemas für Ereignisse zur Reiseorganisation

Journey Orchestration Ereignisses sind XDM Experience Ereignisses, die über Streaming Ingestion an die Adobe Experience Platform gesendet werden.

Eine wichtige Voraussetzung für das Einrichten von Ereignissen für die Reiseorganisation ist, dass Sie mit dem Erlebnisdatenmodell (XDM) der Plattform vertraut sind und wie Sie XDM Experience Ereignis-Schema zusammenstellen sowie wie Sie XDM-formatierte Daten an die Plattform streamen können.

## Anforderungen an das Schema von Ereignissen für die Reiseorganisation

Der erste Schritt beim Einrichten eines Ereignisses für die Reiseorganisation besteht darin, sicherzustellen, dass ein XDM-Schema zur Darstellung des Ereignisses definiert ist und ein Datensatz erstellt wurde, um Instanzen des Ereignisses auf der Plattform aufzuzeichnen. Ein Datensatz für Ihre Ereignis ist nicht unbedingt erforderlich, aber das Senden der Ereignis an einen bestimmten Datensatz ermöglicht es Ihnen, den Benutzerverlauf für die spätere Referenz und Analyse beizubehalten. Daher ist es immer eine gute Idee, einen Datensatz zu erstellen. Wenn Sie noch kein geeignetes Schema und einen entsprechenden Datensatz für Ihr Ereignis haben, können beide Aufgaben über die Plattform-Weboberfläche vorgenommen werden.

![](../assets/schema1.png)

Für jedes XDM-Schema, das für Ereignisse der Journey Orchestration verwendet wird, gelten folgende Anforderungen:

* Das Schema muss der XDM ExperienceEvent-Klasse angehören.

![](../assets/schema2.png)

* Das Schema muss das Mixin Orchestration eventID enthalten. Die Reiseorganisation verwendet dieses Feld, um Ereignis zu identifizieren, die auf Reisen verwendet werden.

![](../assets/schema3.png)

* Deklarieren Sie ein Identitätsfeld zur Identifizierung des Objekts des Ereignisses. Wenn keine Identität angegeben ist, kann eine Identitätskarte verwendet werden. Dies wird nicht empfohlen.

![](../assets/schema4.png)

* Wenn Sie möchten, dass diese Daten später auf einer Reise zur Verfügung stehen, markieren Sie das Schema und den Datensatz zum Profil.

![](../assets/schema5.png)

![](../assets/schema6.png)

* Sie können Datenfelder einschließen, um andere Kontextdaten zu erfassen, die Sie in das Ereignis einschließen möchten, z. B. Informationen zum Benutzer, zum Gerät, von dem das Ereignis generiert wurde, zum Speicherort oder andere aussagekräftige Umstände in Zusammenhang mit dem Ereignis.

![](../assets/schema7.png)

![](../assets/schema8.png)