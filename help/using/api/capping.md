---
product: adobe campaign
title: Beschreibung der Begrenzungs-API
description: Erfahren Sie mehr über die Capping-API.
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 92%

---


# Arbeiten mit der Begrenzungs-API {#work}


>[!CAUTION]
>
>**Suche nach Adobe Journey Optimizer**? Klicken Sie [hier](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/ajo-home){target="_blank"}, um die Dokumentation zu Journey Optimizer anzuzeigen.
>
>
>_Diese Dokumentation bezieht sich auf veraltete Journey Orchestration-Materialien, die durch Journey Optimizer ersetzt wurden. Wenden Sie sich an Ihr Account-Team, wenn Sie Fragen zu Ihrem Zugriff auf Journey Orchestration oder Journey Optimizer haben._


Mit der Begrenzungs-API können Sie Begrenzungskonfigurationen erstellen, konfigurieren und überwachen.

## Beschreibung der Begrenzungs-API

| Methode | Pfad | Beschreibung |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | Liste der Endpunktbegrenzungskonfigurationen abrufen |
| [!DNL POST] | /endpointConfigs | Endpunktbegrenzungskonfiguration erstellen |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | Endpunktbegrenzungskonfiguration bereitstellen |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeploy | Bereitstellung einer Endpunktbegrenzungskonfiguration aufheben |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | Überprüfen, ob eine Endpunktbegrenzungskonfiguration bereitgestellt werden kann oder nicht |
| [!DNL PUT] | /endpointConfigs/`{uid}` | Endpunktbegrenzungskonfiguration aktualisieren |
| [!DNL GET] | /endpointConfigs/`{uid}` | Endpunktbegrenzungskonfiguration abrufen |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | Endpunktbegrenzungskonfiguration löschen |

Bei der Erstellung oder Aktualisierung einer Konfiguration wird automatisch eine Überprüfung durchgeführt, um die Syntax und Integrität der Payload sicherzustellen.
Wenn Probleme auftreten, gibt der Vorgang eine Warnung oder Fehler zurück, die Ihnen beim Korrigieren der Konfiguration helfen.

## Endpunktkonfiguration

Die grundlegende Struktur einer Endpunktkonfiguration sieht wie folgt aus:

```
{
    "url": "<endpoint URL>",  //wildcards are allowed in the endpoint URL
    "methods": [ "<HTTP method such as GET, POST, >, ...],
    "services": {
        "<service name>": { . //must be "action" or "dataSource" 
            "maxHttpConnections": <max connections count to the endpoint (optional)>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

>[!IMPORTANT]
>
>Der Parameter **maxHttpConnections** ist optional. Dadurch können Sie die Anzahl der Verbindungen einschränken, die Journey Optimizer für das externe System öffnet.
>
>Der maximale Wert, der festgelegt werden kann, ist 400. Wenn nichts angegeben ist, kann das System abhängig von seiner dynamischen Skalierung bis zu mehreren tausend Verbindungen öffnen.

### Beispiel:

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 50,
      "rating": {
        "maxCallsCount": 500,
        "periodInMs": 1000
      }
    }
  },
  "orgId": "<IMS Org Id>"
}
```

## Warnung und Fehler

Wenn eine **canDeploy**-Methode aufgerufen wird, validiert der Prozess die Konfiguration und gibt den durch seine eindeutige Kennung identifizierten Validierungsstatus zurück:

```
"ok" or "error"
```

Mögliche Fehler sind:

* **ERR_ENDPOINTCONFIG_100**: capping config: missing or invalid url
* **ERR_ENDPOINTCONFIG_101**: capping config: malformed url
* **ERR_ENDPOINTCONFIG_102**: capping config: malformed url: wildchar in url not allowed in host:port
* **ERR_ENDPOINTCONFIG_103**: capping config: missing HTTP methods
* **ERR_ENDPOINTCONFIG_104**: capping config: no call rating defined
* **ERR_ENDPOINTCONFIG_107**: capping config: invalid max calls count (maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**: capping config: invalid max calls count (periodInMs)
* **ERR_ENDPOINTCONFIG_111**: capping config: can&#39;t create endpoint config: invalid payload
* **ERR_ENDPOINTCONFIG_112**: capping config: can&#39;t create endpoint config: expecting a JSON payload
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: invalid service name `<!--<given value>-->`: must be &#39;dataSource&#39; or &#39;action&#39;

Die potenzielle Warnung lautet:

**ERR_ENDPOINTCONFIG_106**: capping config: max HTTP connections not defined: no limitation by default

## Anwendungsfälle

In diesem Abschnitt finden Sie die fünf Hauptanwendungsfälle für die Verwaltung Ihrer Begrenzungskonfiguration in [!DNL Journey Orchestration].

Um Ihnen bei Tests und der Konfiguration behilflich zu sein, steht Ihnen [hier](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json) eine Postman-Sammlung zur Verfügung.

Diese Postman-Sammlung wurde eingerichtet, um die Postman-Variablensammlung freizugeben, die über __[Integrationen der Adobe I/O-Konsole](https://console.adobe.io/integrations) > Testen > Für Postman herunterladen__ generiert wurde. Dadurch wird eine Postman-Umgebung mit den ausgewählten Integrationswerten erzeugt.

Nach dem Herunterladen und Hochladen in Postman müssen Sie drei Variablen hinzufügen: `{JO_HOST}`, `{BASE_PATH}` und `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration]-Gateway-URL
* `{BASE_PATH}`: Einstiegspunkt für die API. Der Wert lautet „/authoring“
* `{SANDBOX_NAME}`: der Header **x-sandbox-name** (z. B. „prod“), der dem Sandbox-Namen entspricht, in dem die API-Vorgänge stattfinden. Weiterführende Informationen dazu finden Sie unter [Sandbox-Übersicht](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=de).

Im folgenden Abschnitt finden Sie die sortierte Liste der Rest-API-Aufrufe, um den Anwendungsfall auszuführen.

Anwendungsfall 1: **Erstellen und Bereitstellen einer neuen Begrenzungskonfiguration**

1. list
1. create
1. candeploy
1. deploy

Anwendungsfall 2: **Aktualisieren und Bereitstellen einer noch nicht bereitgestellten Begrenzungskonfiguration**

1. list
1. get
1. update
1. candeploy
1. deploy

Anwendungsfall 3: **Aufheben einer Bereitstellung und Löschen einer bereitgestellten Begrenzungskonfiguration**

1. list
1. undeploy
1. delete

Anwendungsfall 4: **Löschen einer bereitgestellten Begrenzungskonfiguration.**

In nur einem API-Aufruf können Sie die Bereitstellung aufheben und die Konfiguration mithilfe des forceDelete-Parameters löschen.
1. list
1. delete mit forceDelete-Parameter

Anwendungsfall 5: **Aktualisieren einer bereits bereitgestellten Begrenzungskonfiguration**

1. list
1. get
1. update
1. undeploy
1. candeploy
1. deploy
