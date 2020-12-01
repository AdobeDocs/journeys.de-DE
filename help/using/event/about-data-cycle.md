---
product: adobe campaign
solution: Journey Orchestration
title: Ereignis-Datenzyklus
description: Informationen zum Ereignis-Datenzyklus
translation-type: tm+mt
source-git-commit: b3ed5d305ddd1c86814373fc923390dc50a80c7e
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 78%

---


# Datenzyklus {#section_r1f_xqt_pgb}

Ereignisse sind POST-API-Aufrufe. Ereignisse werden über Streaming-Aufnahme-APIs an Adobe Experience Platform gesendet. Das URL-Ziel von Ereignissen, die über Transaktionsnachrichten-APIs gesendet werden, wird als „Inlet“ bezeichnet. Die Payload der Ereignisse verwendet die XDM-Formatierung.

Die Payload enthält Informationen, die von Streaming-Aufnahme-APIs benötigt werden, um zu funktionieren (in der Kopfzeile), Informationen, die [!DNL Journey Orchestration] benötigt, um zu funktionieren (die Ereignis-ID, Teil des Payload-Hauptteils), und Informationen, die in Journeys verwendet werden (im Hauptteil z. B. der Betrag eines Transaktionsabbruchs). Es gibt zwei Modi für die Streaming-Aufnahme: authentifiziert und nicht authentifiziert. Weitere Informationen zu Streaming-Aufnahme-APIs finden Sie unter [diesem Link](https://docs.adobe.com/content/help/de-DE/experience-platform/xdm/api/getting-started.html).

Nach dem Eingang über Streaming-Aufnahme-APIs fließen Ereignisse in einen internen Dienst, die sogenannte Pipeline, und dann in Adobe Experience Platform. Wenn für das Ereignisschema die Markierung „Echtzeit-Kundenprofildienst“ aktiviert ist und es über eine Datensatz-ID verfügt, die ebenfalls die Markierung „Echtzeit-Kundenprofil“ hat, fließt das Ereignis in den Echtzeit-Kundenprofildienst.

For system-generated events, the Pipeline filters events which have a payload containing [!DNL Journey Orchestration] eventIDs (see the event creation process below) provided by [!DNL Journey Orchestration] and contained in event payload. Bei regelbasierten Ereignissen identifiziert das System das Ereignis mit der eventID-Bedingung. Diese Ereignisse werden von [!DNL Journey Orchestration] überwacht und die entsprechende Journey wird ausgelöst.
