---
product: adobe campaign
title: Arbeiten mit der Einschränkungs-API
description: Erfahren Sie mehr über die Einschränkungs-API.
products: journeys
feature: Journeys
role: User
level: Intermediate
source-git-commit: 1f91bae24dfcb291dd354e4bff9eab85afdaf5a1
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 22%

---

# Arbeiten mit der Einschränkungs-API

Mit der Einschränkungs-API können Sie Ihre Einschränkungskonfigurationen erstellen, konfigurieren und überwachen.

>[!IMPORTANT]
>
>Pro Organisation ist derzeit nur eine Konfiguration zulässig. Eine Konfiguration muss in einer Produktions-Sandbox definiert werden (in den Kopfzeilen über x-sandbox-name angegeben).
>
>Eine Konfiguration wird auf Unternehmensebene angewendet.

## Beschreibung der Einschränkungs-API {#description}

| Methode | Pfad | Beschreibung |
|---|---|---|
| [!DNL POST] | list/throttlingConfigs | Liste der Einschränkungskonfigurationen abrufen |
| [!DNL POST] | /throttlingConfigs | Erstellen einer Einschränkungskonfiguration |
| [!DNL POST] | /throttlingConfigs/`{uid}`/deploy | Implementieren einer Einschränkungskonfiguration |
| [!DNL POST] | /throttlingConfigs/`{uid}`/undeploy | Bereitstellung einer Einschränkungskonfiguration aufheben |
| [!DNL POST] | /throttlingConfigs/`{uid}`/canDeploy | Überprüfen, ob eine Einschränkungskonfiguration bereitgestellt werden kann oder nicht |
| [!DNL PUT] | /throttlingConfigs/`{uid}` | Aktualisieren einer Einschränkungskonfiguration |
| [!DNL GET] | /throttlingConfigs/`{uid}` | Abrufen einer Einschränkungskonfiguration |
| [!DNL DELETE] | /throttlingConfigs/`{uid}` | Eine Einschränkungskonfiguration löschen |

## Einschränkungskonfiguration {#configuration}

Hier finden Sie die Struktur einer Einschränkungskonfiguration. **name** und **description** -Attribute sind optional.

```
{
    "name": "<given name - free text>",
    "description": "<given description - free text>"
    "urlPattern": "<endpoint URL - wildcards are allowed>",
    "methods": [ "<HTTP method such as GET, POST, PUT>" ],
    "maxThroughput": <max call throughput>
}
```

Beispiel:

```
{
  "name": "throttling-config-external",
  "description": "example of throttling config for an external endpoint",
  "urlPattern": "https://api.example.org/data/2.5/*",
  "methods": ["POST", "PUT"],
  "maxThroughput": 4000
}
```

## Fehler

Beim Erstellen oder Aktualisieren einer Konfiguration validiert der Prozess die angegebene Konfiguration und gibt den durch seine eindeutige ID identifizierten Validierungsstatus zurück:

```
"ok" or "error"
```

>[!IMPORTANT]
>
>Die Attribute **maxThroughput**, **urlPattern** und **methods** sind zwingend erforderlich.
>
>**maxThroughput** -Wert muss zwischen 200 und 5000 liegen.

Beim Erstellen, Löschen oder Bereitstellen der Einschränkungskonfiguration können die folgenden Fehler auftreten:

* **ERR_THROTTLING_CONFIG_100**: throttling config: `<mandatory attribute>` erforderlich
* **ERR_THROTTLING_CONFIG_101**: throttling config: maxThroughput ist erforderlich und muss größer oder gleich 200 und kleiner oder gleich 5000 sein.
* **ERR_THROTTLING_CONFIG_104**: throttling config: malformed url pattern
* **ERR_THROTTLING_CONFIG_105**: throttling config: Platzhalter sind im Host-Teil des URL-Musters nicht zulässig
* **ERR_THROTTLING_CONFIG_106**: throttling config: ungültige Payload
* **THROTTLING_CONFIG_DELETE_FORBIDDEN_ERROR: 1456**, &quot;Kann keine bereitgestellte Einschränkungskonfiguration löschen. Bereitstellung vor dem Löschen aufheben&quot;
* **THROTTLING_CONFIG_DELETE_ERROR: 1457**, &quot;Die Einschränkungskonfiguration kann nicht gelöscht werden: unerwarteter Fehler&quot;
* **THROTTLING_CONFIG_DEPLOY_ERROR: 1458**, &quot;Die Einschränkungskonfiguration kann nicht bereitgestellt werden: unerwarteter Fehler&quot;
* **THROTTLING_CONFIG_UNDEPLOY_ERROR: 1459**, &quot;Die Bereitstellung der Einschränkungskonfiguration kann nicht aufgehoben werden: unerwarteter Fehler&quot;
* **THROTTLING_CONFIG_GET_ERROR: 1460**, &quot;Kann keine Einschränkungskonfiguration erhalten: unerwarteter Fehler&quot;
* **THROTTLING_CONFIG_UPDATE_NOT_ACTIVE_ERROR: 1461**, &quot;Die Einschränkungskonfiguration kann nicht aktualisiert werden: Laufzeitversion ist nicht aktiv&quot;
* **THROTTLING_CONFIG_UPDATE_ERROR: 1462**, &quot;Die Einschränkungskonfiguration kann nicht aktualisiert werden: unerwarteter Fehler&quot;
* **THROTTLING_CONFIG_NON_PROD_SANDBOX_ERROR: 1463**, &quot;Operation not allowed on throtling config: Nicht-Produkt-Sandbox&quot;
* **THROTTLING_CONFIG_CREATE_ERROR: 1464**, &quot;Kann keine Einschränkungskonfiguration erstellen: unerwarteter Fehler&quot;
* **THROTTLING_CONFIG_CREATE_LIMIT_ERROR: 1465**, &quot;Kann keine Einschränkungskonfiguration erstellen: nur eine Konfiguration pro Organisation zulässig&quot;
* **THROTTLING_CONFIG_ALREADY_DEPLOYED_ERROR: 14466**, &quot;Die Einschränkungskonfiguration kann nicht bereitgestellt werden: bereits bereitgestellt&quot;
* **THROTTLING_CONFIG_NOT_FOUND_ERROR: 14467**, &quot;throttling config not found&quot;
* **THROTTLING_CONFIG_NOT_DEPLOYED_ERROR: 14468**, &quot;Die Bereitstellung der Einschränkungskonfiguration kann nicht aufgehoben werden: noch nicht bereitgestellt&quot;

**Fehlerbeispiele**

Wenn Sie versuchen, eine Konfiguration für Nicht-Produktions-Sandboxes zu erstellen:

```
{
    "status": 400,
    "error": "{\"code\":1463,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Operation not allowed on throttling config: non prod sandbox\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:384\",\"schema\":\"throttlingConfigs$ui-tests\"}",
    "requestId": "5sgnAYXs8mpswwjAFEIaAU2faQYbtyHc"
}
```

Falls es keine Sandbox gibt:

```
{
    "status": 500,
    "error": "{\"code\":4000,\"family\":\"INTERNAL_ERROR\",\"message\":\"INTERNAL ERROR\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.common.exceptions.ApiErrorException:43\"}",
    "requestId": "04ZJ4e5ki4bYs3lfO17a7hovRGewjvdK"
}
```

Wenn Sie versuchen, eine weitere Konfiguration zu erstellen:

```
{
    "status": 400,
    "error": "{\"code\":1465,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Can't create throttling config: only one config allowed per org\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:108\",\"schema\":\"throttlingConfigs$prod\"}",
    "requestId": "A7ezT8JhOQT4WIAf1Fv7K2wCDA8281qM"
}
```

## Anwendungsfälle {#uc}

Um Ihnen bei Tests und der Konfiguration behilflich zu sein, steht Ihnen [hier](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Throttling-API_postman-collection.json) eine Postman-Sammlung zur Verfügung.

Diese Postman-Sammlung wurde eingerichtet, um die Postman-Variablensammlung freizugeben, die über __[Integrationen der Adobe I/O-Konsole](https://console.adobe.io/integrations) > Testen > Für Postman herunterladen__ generiert wurde. Dadurch wird eine Postman-Umgebung mit den ausgewählten Integrationswerten erzeugt.

Nach dem Herunterladen und Hochladen in Postman müssen Sie drei Variablen hinzufügen: `{JO_HOST}`, `{BASE_PATH}` und `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration]-Gateway-URL
* `{BASE_PATH}` : Einstiegspunkt für die API. Der Wert lautet „/authoring“
* `{SANDBOX_NAME}`: der Header **x-sandbox-name** (z. B. „prod“), der dem Sandbox-Namen entspricht, in dem die API-Vorgänge stattfinden. Weiterführende Informationen dazu finden Sie unter [Sandbox-Übersicht](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=de).

Im folgenden Abschnitt finden Sie die sortierte Liste der Rest-API-Aufrufe, um den Anwendungsfalls auszuführen.

Anwendungsfall 1: **Erstellung und Implementierung einer neuen Einschränkungskonfiguration**

1. list
1. create
1. candeploy
1. deploy

Anwendungsfall 2: **Aktualisieren und Bereitstellen einer noch nicht bereitgestellten Einschränkungskonfiguration**

1. list
1. get
1. Aktualisieren
1. candeploy
1. deploy

Anwendungsfall 3: **Bereitstellung und Löschen einer bereitgestellten Einschränkungskonfiguration aufheben**

1. list
1. undeploy
1. delete

Anwendungsfall 4: **Löschen einer bereitgestellten Einschränkungskonfiguration**

In nur einem API-Aufruf können Sie die Bereitstellung aufheben und die Konfiguration mithilfe des forceDelete-Parameters löschen.

1. list
1. delete mit forceDelete-Parameter

Anwendungsfall Nr. 5: **Aktualisieren einer bereits bereitgestellten Einschränkungskonfiguration**

>[!NOTE]
>
>Es ist nicht erforderlich, die Bereitstellung der Konfiguration vor der Aktualisierung aufzuheben

1. list
1. get
1. Aktualisieren

## Konfigurationslebenszyklus auf Laufzeitebene {#config}

Wenn die Bereitstellung einer Konfiguration aufgehoben wird, wird sie auf Laufzeitebene als inaktiv markiert und ausstehende Ereignisse werden weiterhin 24 Stunden verarbeitet. Er wird dann im Laufzeitdienst gelöscht.

Nachdem die Bereitstellung einer Konfiguration aufgehoben wurde, ist es möglich, die Konfiguration zu aktualisieren und erneut bereitzustellen. Dadurch wird eine neue Laufzeitkonfiguration erstellt, die bei der bevorstehenden Aktionsausführung berücksichtigt wird.

Beim Aktualisieren einer bereits bereitgestellten Konfiguration werden die neuen Werte sofort berücksichtigt. Die zugrunde liegenden Systemressourcen werden automatisch angepasst. Dies ist im Vergleich zum Aufheben der Bereitstellung und erneuten Bereitstellen der Konfiguration optimal.

## Beispiele für Antworten {#responses}

**Erstellung - POST**

```
{
    "canDeploy": {
        "validationStatus": "ok"
    },
    "createdElement": {
        "name": "throttling-config-external",
        "description": "example of throttling config for an external endpoint",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "PUT",
            "POST"
        ],
        "maxThroughput": 4000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T10:48:16.099647Z"
        },
        "state": "created",
        "authoringFormatVersion": "1.0"
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "created"
}
```

**Aktualisieren - PUT**

```
{
    "updatedElement": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "updated",
    "canDeploy": {
        "validationStatus": "ok"
    }
}
```

**Lesen (nach Aktualisierung) - GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    }
}
```

**Lesen (nach der Bereitstellung) - GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "authoringFormatVersion": "1.0",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "version": "1.0",
        "state": "deployed",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z",
            "lastDeployedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastDeployedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastDeployedAt": "2023-03-22T11:46:07.532648Z"
        },
        "hasBeenDeployed": true
    }
}
```
