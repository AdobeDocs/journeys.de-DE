---
product: adobe campaign
title: Zusätzliche Schritte zum Senden von Ereignissen an Journey Orchestration
description: Erfahren Sie mehr über die zusätzlichen Schritte zum Senden von Ereignissen an Journey Orchestration
feature: Journeys
role: User
level: Intermediate
exl-id: 11e337c6-5e05-4898-9953-b6b821af8fd1
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 87%

---

# Zusätzliche Schritte zum Senden von Ereignissen an [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}



>[!CAUTION]
>
>**Suche nach Adobe Journey Optimizer**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um die Dokumentation zu Journey Optimizer anzuzeigen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Account-Team, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._


>[!NOTE]
>
>Beim Erstellen eines Ereignisses generiert [!DNL Journey Orchestration] automatisch eine ID für dieses Ereignis. Das System, das das Ereignis per Push sendet, sollte keine ID generieren, sondern die ID verwenden, die in der Payload-Vorschau verfügbar ist. Weitere Informationen finden Sie auf [dieser Seite](../event/previewing-the-payload.md).

Um Ereignisse zu konfigurieren, die an **[!UICONTROL Streaming-Aufnahme-APIs]** gesendet und in [!DNL Journey Orchestration] verwendet werden sollen, müssen Sie die folgenden Schritte ausführen:

1. Rufen Sie die Inlet-URL von den Adobe Experience Platform-APIs ab (siehe [Streaming-Aufnahme-APIs](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=de)).
1. Kopieren Sie die Payload aus der Payload-Vorschau im Menü **[!UICONTROL Ereignis]**. Weitere Informationen finden Sie auf [dieser Seite](../event/defining-the-payload-fields.md).

Konfigurieren Sie anschließend das Datensystem, das Ereignisse mithilfe der kopierten Payload an die Streaming-Aufnahme-APIs pusht:

1. Richten Sie einen POST-API-Aufruf zur URL der Streaming-Aufnahme-APIs ein (als Inlet bezeichnet).
1. Verwenden Sie die Payload, die Sie im Hauptteil („Datenabschnitt“) des API-Aufrufs aus [!DNL Journey Orchestration] zu den Streaming-Aufnahme-APIs kopiert haben. Unten finden Sie ein Beispiel
1. Legen Sie fest, von wo alle Variablen in der Payload abgerufen werden sollen. Beispiel: Wenn das Ereignis die Adresse vermitteln soll, wird in der eingefügten Payload &quot;address&quot;: &quot;string&quot; angezeigt. „string“ sollte durch die Variable ersetzt werden, die automatisch mit dem richtigen Wert ausgefüllt wird, nämlich mit der E-Mail-Adresse der Person, an die eine Nachricht gesendet werden soll. Beachten Sie, dass in der Payload-Vorschau im Abschnitt **[!UICONTROL Kopfzeile]** viele Werte automatisch ausgefüllt werden, was Ihre Arbeit erleichtern sollte.
1. Wählen Sie „application/json“ als Typ für den Hauptteil aus.
1. Übergeben Sie Ihre IMS-Organisations-ID in der Kopfzeile mit dem Schlüssel „x-gw-ims-org-id“. Verwenden Sie für den Wert Ihre IMS-Organisations-ID („XXX@AdobeOrg“).

Im Folgenden finden Sie ein Beispiel für ein Streaming-Aufnahme-API-Ereignis:

```
{
    "header": {
        "msgType": "xdmEntityCreate",
        "msgId": "c25585b9-252e-431d-b562-e73da70c04e7",
        "msgVersion": "1.0",
        "xactionId": "f5995abe-c49d-4848-9577-a7a4fc2996fb",
        "datasetId": "string - required if you want the data to land in a specific dataset - not mandatory",
        "imsOrgId": "XXX@AdobeOrg",
        "schemaRef": {
            "id": "XXX",
            "contentType": "application/vnd.adobe.xed-full+json;version=1"
        },
        "source": {
            "name": "Journeys"
        }
    },
    "body": {
        "xdmMeta": {
            "schemaRef": {
                "id": "XXX",
                "contentType": "application/vnd.adobe.xed-full+json;version=1"
            }
        },
        "xdmEntity": {
            "_instance_name": {
                "person": {
                    "firstName": "string",
                    "lastName": "string",
                    "gender": "string",
                    "birthYear": 10,
                    "emailAddress": "string"
                }
            },
            "identityMap": {
                "Email": [
                {
                    "id": "string"
                    }
                ]
            },
            "_id": "string",
            "timestamp": "2018-05-29T00:00:00.000Z",
            "_experience": {
                "campaign": {
                    "orchestration": {
                    "eventID": "XXX"
                    }
                }
            }
        }
    }
}
```

Um die Identifizierung der Stelle zu erleichtern, an der der „Daten“-Teil eingefügt werden soll, können Sie ein JSON-Visualisierungs-Tool verwenden, z. B. [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

Informationen zur Fehlerbehebung bei Streaming-Aufnahme-APIs finden Sie auf dieser [Seite](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html?lang=de).
