---
product: adobe campaign
solution: Journey Orchestration
title: Ereignisdatenzyklus
description: Informationen zum Ereignisdatenzyklus.
feature: Journeys
role: Business Practitioner
level: Fortgeschrittene
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 100%

---


# Datenzyklus {#section_r1f_xqt_pgb}

Ereignisse sind POST-API-Aufrufe. Ereignisse werden über Streaming-Aufnahme-APIs an Adobe Experience Platform gesendet. Das URL-Ziel von Ereignissen, die über Transaktionsnachrichten-APIs gesendet werden, wird als „Inlet“ bezeichnet. Die Payload der Ereignisse verwendet die XDM-Formatierung.

Die Payload enthält Informationen, die von Streaming-Aufnahme-APIs benötigt werden, um zu funktionieren (in der Kopfzeile), Informationen, die [!DNL Journey Orchestration] benötigt, um zu funktionieren (die Ereignis-ID, Teil des Payload-Hauptteils), und Informationen, die in Journeys verwendet werden (im Hauptteil z. B. der Betrag eines Transaktionsabbruchs). Es gibt zwei Modi für die Streaming-Aufnahme: authentifiziert und nicht authentifiziert. Weitere Informationen zu Streaming-Aufnahme-APIs finden Sie unter [diesem Link](https://docs.adobe.com/content/help/de-DE/experience-platform/xdm/api/getting-started.html).

Nach dem Eingang über Streaming-Aufnahme-APIs fließen Ereignisse in einen internen Dienst, die sogenannte Pipeline, und dann in Adobe Experience Platform. Wenn für das Ereignisschema die Markierung „Echtzeit-Kundenprofildienst“ aktiviert ist und es über eine Datensatz-ID verfügt, die ebenfalls die Markierung „Echtzeit-Kundenprofil“ hat, fließt das Ereignis in den Echtzeit-Kundenprofildienst.

Systemgenerierte Ereignisse: Die Pipeline filtert Ereignisse mit einer Payload, die eventIDs von [!DNL Journey Orchestration] enthalten (siehe den Ereigniserstellungsprozess unten), die von [!DNL Journey Orchestration] bereitgestellt werden und in der Ereignis-Payload enthalten sind. Regelbasierte Ereignisse: Das System identifiziert das Ereignis mit der eventID-Bedingung. Diese Ereignisse werden von [!DNL Journey Orchestration] überwacht und die entsprechende Journey wird ausgelöst.
