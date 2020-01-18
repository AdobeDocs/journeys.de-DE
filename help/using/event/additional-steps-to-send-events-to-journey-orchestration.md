---
title: Zusätzliche Schritte zum Senden von Veranstaltungen an das Reisebüro
description: Erfahren Sie mehr über die zusätzlichen Schritte zum Senden von Veranstaltungen an das Reisebüro
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---



# Zusätzliche Schritte zum Senden von Veranstaltungen an das Reisebüro {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>Beim Erstellen einer Veranstaltung generiert die Journey Orchestration automatisch eine ID für diese Veranstaltung. Das System, das das Ereignis durchführt, sollte keine ID generieren. Es sollte die ID verwenden, die in der Nutzdatenvorschau verfügbar ist. Näheres wird im Abschnitt [](../event/previewing-the-payload.md) beschrieben.

Um Ereignisse zu konfigurieren, die an **[!UICONTROL Streaming Ingestion APIs]**gesendet und in der Reiseorganisation verwendet werden sollen, müssen Sie die folgenden Schritte ausführen:

1. Rufen Sie die Einlass-URL von den Datenplattform-APIs ab (siehe [Streaming-Einschluss-APIs](https://www.adobe.io/apis/cloudplatform/dataservices/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/getting_started_with_platform_streaming_ingestion.md)).
1. Kopieren Sie die Nutzlast aus der Payload-Vorschau im Menü &quot; **[!UICONTROL Ereignis]**&quot;. Näheres wird im Abschnitt[](../event/defining-the-payload-fields.md)beschrieben.

Anschließend müssen Sie das Datensystem konfigurieren, das Ereignisse mithilfe der kopierten Nutzlast an Streaming Ingestion APIs sendet:

1. Richten Sie einen POST-API-Aufruf an die Streaming-Einschluss-APIs-URL ein (als Einlass bezeichnet).
1. Verwenden Sie die Nutzlast, die Sie aus dem Journey Orchestration im Hauptteil (&quot;Datenabschnitt&quot;) des API-Aufrufs zu Streaming Ingestion APIs kopiert haben. Beispiel siehe unten
1. Legen Sie fest, wo alle Variablen in der Nutzlast abgelegt werden sollen. Beispiel: Wenn das Ereignis die Adresse vermitteln soll, zeigt die eingefügte Nutzlast &quot;Adresse&quot;: &quot;string&quot;. &quot;string&quot; sollte durch die Variable ersetzt werden, die automatisch den richtigen Wert ausfüllt, die E-Mail der Person, an die eine Nachricht gesendet werden soll. Beachten Sie, dass in der Nutzdatenvorschau im Abschnitt **[!UICONTROL Kopfzeile]**viele Werte automatisch ausgefüllt werden, die Ihre Arbeit erleichtern sollen.
1. Wählen Sie &quot;application/json&quot;als Texttyp.
1. Geben Sie Ihre IMS ORG ID im Header mit dem Schlüssel &quot;x-gw-ims-org-id&quot;weiter. Verwenden Sie für den Wert Ihre IMS-ORG-ID (&quot;XXX@AdobeOrg&quot;).

Im Folgenden finden Sie ein Beispiel für ein Streaming Ingestion APIs-Ereignis:

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

Um die Identifizierung des Ortes zu erleichtern, an dem der &quot;Daten&quot;-Teil eingefügt werden soll, können Sie ein JSON-Visualisierungstool wie [https://jsonformatter.curiousconcept.com verwenden.](https://jsonformatter.curiousconcept.com)

Informationen zur Fehlerbehebung bei Streaming Ingestion APIs finden Sie auf dieser [Seite](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingestion_FAQ.md).
