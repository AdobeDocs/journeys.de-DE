---
product: adobe campaign
title: Ereignisdatenzyklus
description: Informationen zum Ereignisdatenzyklus.
feature: Journeys
role: User
level: Intermediate
exl-id: b362589a-32b0-4dbd-8ceb-a371e1e048ac
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 100%

---

# Datenzyklus {#section_r1f_xqt_pgb}

Ereignisse sind POST-API-Aufrufe. Ereignisse werden über Streaming-Aufnahme-APIs an Adobe Experience Platform gesendet. Das URL-Ziel von Ereignissen, die über Transaktionsnachrichten-APIs gesendet werden, wird als „Inlet“ bezeichnet. Die Payload der Ereignisse verwendet die XDM-Formatierung.

Die Payload enthält Informationen, die von Streaming-Aufnahme-APIs benötigt werden, um zu funktionieren (in der Kopfzeile), Informationen, die [!DNL Journey Orchestration] benötigt, um zu funktionieren (die Ereignis-ID, Teil des Payload-Hauptteils), und Informationen, die in Journeys verwendet werden (im Hauptteil z. B. der Betrag eines Transaktionsabbruchs). Es gibt zwei Modi für die Streaming-Aufnahme: authentifiziert und nicht authentifiziert. Weitere Informationen zu Streaming-Aufnahme-APIs finden Sie unter [diesem Link](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=de).

Nach dem Eingang über Streaming-Aufnahme-APIs fließen Ereignisse in einen internen Dienst, die sogenannte Pipeline, und dann in Adobe Experience Platform. Wenn für das Ereignisschema die Markierung „Echtzeit-Kundenprofildienst“ aktiviert ist und es über eine Datensatz-ID verfügt, die ebenfalls die Markierung „Echtzeit-Kundenprofil“ hat, fließt das Ereignis in den Echtzeit-Kundenprofildienst.

Systemgenerierte Ereignisse: Die Pipeline filtert Ereignisse mit einer Payload, die eventIDs von [!DNL Journey Orchestration] enthalten (siehe den Ereigniserstellungsprozess unten), die von [!DNL Journey Orchestration] bereitgestellt werden und in der Ereignis-Payload enthalten sind. Regelbasierte Ereignisse: Das System identifiziert das Ereignis mit der eventID-Bedingung. Diese Ereignisse werden von [!DNL Journey Orchestration] überwacht und die entsprechende Journey wird ausgelöst.
