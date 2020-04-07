---
title: Zusätzliche Schritte zum Senden von Ereignissen an Journey Orchestration
description: Erfahren Sie mehr über die zusätzlichen Schritte zum Senden von Ereignissen an Journey Orchestration
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
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1

---



# Zusätzliche Schritte zum Senden von Ereignissen an Journey Orchestration {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>Beim Erstellen eines Ereignisses generiert Journey Orchestration automatisch eine ID für dieses Ereignis. Das System, das das Ereignis per Push sendet, sollte keine ID generieren. Es sollte die ID verwenden, die in der Payload-Vorschau verfügbar ist. Siehe [](../event/previewing-the-payload.md).

To configure events to be sent to **[!UICONTROL Streaming Ingestion APIs]** and to be used in Journey Orchestration, you need to follow these steps:

1. Rufen Sie die Inlet-URL von den Datenplattform-APIs ab (siehe [Streaming-Aufnahme-APIs](https://docs.adobe.com/content/help/en/experience-platform/ingestion/streaming/overview.html)).
1. Copy the payload from the payload preview in the **[!UICONTROL Event]** menu. Siehe [](../event/defining-the-payload-fields.md).

Konfigurieren Sie anschließend das Datensystem, das Ereignisse mithilfe der kopierten Payload an die Streaming-Aufnahme-APIs pusht:

1. Richten Sie einen POST-API-Aufruf zur URL der Streaming-Aufnahme-APIs ein (als Inlet bezeichnet).
1. Verwenden Sie die Payload, die Sie aus Journey Orchestration im Hauptteil („Datenabschnitt“) des API-Aufrufs zu den Streaming-Aufnahme-APIs kopiert haben. Unten finden Sie ein Beispiel
1. Legen Sie fest, von wo alle Variablen in der Payload abgerufen werden sollen. Beispiel: Wenn das Ereignis die Adresse vermitteln soll, wird in der eingefügten Payload &quot;address&quot;: &quot;string&quot; angezeigt. „string“ sollte durch die Variable ersetzt werden, die automatisch mit dem richtigen Wert ausgefüllt wird, nämlich mit der E-Mail-Adresse der Person, an die eine Nachricht gesendet werden soll. Beachten Sie, dass in der Payload-Vorschau im Abschnitt **[!UICONTROL Header]** viele Werte automatisch ausgefüllt werden, was Ihre Arbeit erleichtern sollte.
1. Wählen Sie „application/json“ als Typ für den Hauptteil aus.
1. Übergeben Sie Ihre IMS-ORG-ID in der Kopfzeile mit dem Schlüssel „x-gw-ims-org-id“. Verwenden Sie Ihre IMS-ORG-ID („XXX@AdobeOrg“) für den Wert.

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

Informationen zur Fehlerbehebung bei Streaming-Aufnahme-APIs finden Sie auf dieser [Seite](https://docs.adobe.com/content/help/en/experience-platform/ingestion/streaming/troubleshooting.html).
