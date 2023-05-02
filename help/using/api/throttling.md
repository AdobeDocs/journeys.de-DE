---
product: adobe campaign
title: Arbeiten mit der Drosselungs-API
description: Erfahren Sie mehr über die Drosselungs-API
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 76afe397-3e18-4e01-9b0b-c21705927ce2
source-git-commit: 7b8c9d2bfe244b040a9064a7a240ea6f43cc8b41
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 95%

---

# Arbeiten mit der Drosselungs-API

Mit der Einschränkungs-API können Sie Ihre Einschränkungskonfigurationen erstellen, konfigurieren und überwachen, um die Anzahl der pro Sekunde gesendeten Ereignisse zu begrenzen.

>[!IMPORTANT]
>
>Pro Organisation ist derzeit nur eine Konfiguration zulässig. Eine Konfiguration muss in einer Produktions-Sandbox definiert werden (in den Kopfzeilen über x-sandbox-name angegeben).
>
>Eine Konfiguration wird auf Unternehmensebene angewendet.
>
>Wenn das in der API festgelegte Limit erreicht ist, werden weitere Ereignisse für bis zu 6 Stunden in die Warteschlange gestellt. Dieser Wert kann nicht geändert werden.

## Beschreibung der Drosselungs-API {#description}

| Methode | Pfad | Beschreibung |
|---|---|---|
| [!DNL POST] | list/throttlingConfigs | Abrufen einer Liste der Drosselungskonfigurationen |
| [!DNL POST] | /throttlingConfigs | Erstellen einer Drosselungskonfiguration |
| [!DNL POST] | /throttlingConfigs/`{uid}`/deploy | Implementieren einer Drosselungskonfiguration |
| [!DNL POST] | /throttlingConfigs/`{uid}`/undeploy | Bereitstellung einer Drosselungskonfiguration aufheben |
| [!DNL POST] | /throttlingConfigs/`{uid}`/canDeploy | Überprüfen, ob eine Drosselungskonfiguration bereitgestellt werden kann oder nicht |
| [!DNL PUT] | /throttlingConfigs/`{uid}` | Aktualisieren einer Drosselungskonfiguration |
| [!DNL GET] | /throttlingConfigs/`{uid}` | Abrufen einer Drosselungskonfiguration |
| [!DNL DELETE] | /throttlingConfigs/`{uid}` | Löschen einer Drosselungskonfiguration |

## Drosselungskonfiguration{#configuration}

Hier finden Sie die Struktur einer Drosselungskonfiguration. Die Attribute **name** und **description** sind optional.

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

Beim Erstellen oder Aktualisieren einer Konfiguration validiert der Prozess die angegebene Konfiguration und gibt den Validierungsstatus zurück, der durch seine eindeutige ID identifiziert wird, entweder:

```
"ok" or "error"
```

>[!IMPORTANT]
>
>Die Attribute **maxThroughput**, **urlPattern** und **methods** sind zwingend erforderlich.
>
>Der Wert für **maxThroughput** muss zwischen 200 und 5000 liegen.

Beim Erstellen, Löschen oder Bereitstellen einer Drosselungskonfiguration können die folgenden Fehler auftreten:

* **ERR_THROTTLING_CONFIG_100**: Drosselungskonfiguration: `<mandatory attribute>` erforderlich
* **ERR_THROTTLING_CONFIG_101**: Drosselungskonfiguration: maxThroughput ist erforderlich und muss größer oder gleich 200 und kleiner oder gleich 5.000 sein.
* **ERR_THROTTLING_CONFIG_104**: Drosselungskonfiguration: fehlerhaftes URL-Muster
* **ERR_THROTTLING_CONFIG_105**: Drosselungskonfiguration: Platzhalter sind im Host-Teil des URL-Musters nicht zulässig
* **ERR_THROTTLING_CONFIG_106**: Drosselungskonfiguration: ungültige Payload
* **THROTTLING_CONFIG_DELETE_FORBIDDEN_ERROR: 1456**, „Eine implementierte Drosselungskonfiguration kann nicht gelöscht werden. Bitte die Implementierung vor dem Löschen aufheben“
* **THROTTLING_CONFIG_DELETE_ERROR: 1457**, „Die Drosselungskonfiguration kann nicht gelöscht werden: unerwarteter Fehler“
* **THROTTLING_CONFIG_DEPLOY_ERROR: 1458**, „Die Drosselungskonfiguration kann nicht implementiert werden: unerwarteter Fehler“
* **THROTTLING_CONFIG_UNDEPLOY_ERROR: 1459**, „Die Implementierung der Drosselungskonfiguration kann nicht aufgehoben werden: unerwarteter Fehler“
* **THROTTLING_CONFIG_GET_ERROR: 1460**, „Drosselungskonfiguration kann nicht abgerufen werden: unerwarteter Fehler“
* **THROTTLING_CONFIG_UPDATE_NOT_ACTIVE_ERROR: 1461**, „Drosselungskonfiguration kann nicht aktualisiert werden: Laufzeitversion ist nicht aktiv“
* **THROTTLING_CONFIG_UPDATE_ERROR: 1462**, „Drosselungskonfiguration kann nicht aktualisiert werden: unerwarteter Fehler“
* **THROTTLING_CONFIG_NON_PROD_SANDBOX_ERROR: 1463**, „Vorgang bei Drosselungskonfiguration nicht zulässig: Nicht-Produktions-Sandbox“
* **THROTTLING_CONFIG_CREATE_ERROR: 1464**, „Drosselungskonfiguration kann nicht erstellt werden: unerwarteter Fehler“
* **THROTTLING_CONFIG_CREATE_LIMIT_ERROR: 1465**, „Drosselungskonfiguration kann nicht erstellt werden: nur eine Konfiguration pro Organisation zulässig“
* **THROTTLING_CONFIG_ALREADY_DEPLOYED_ERROR: 14466**, „Drosselungskonfiguration kann nicht implementiert werden: bereits implementiert“
* **THROTTLING_CONFIG_NOT_FOUND_ERROR: 14467**, „Drosselungskonfiguration nicht gefunden“
* **THROTTLING_CONFIG_NOT_DEPLOYED_ERROR: 14468**, „Implementierung der Drosselungskonfiguration kann nicht aufgehoben werden: noch nicht implementiert“

**Fehlerbeispiele**

Beim Versuch, eine Konfiguration für Nicht-Produktions-Sandboxes zu erstellen:

```
{
    "status": 400,
    "error": "{\"code\":1463,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Operation not allowed on throttling config: non prod sandbox\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:384\",\"schema\":\"throttlingConfigs$ui-tests\"}",
    "requestId": "5sgnAYXs8mpswwjAFEIaAU2faQYbtyHc"
}
```

Falls eine angegebene Sandbox nicht vorhanden ist:

```
{
    "status": 500,
    "error": "{\"code\":4000,\"family\":\"INTERNAL_ERROR\",\"message\":\"INTERNAL ERROR\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.common.exceptions.ApiErrorException:43\"}",
    "requestId": "04ZJ4e5ki4bYs3lfO17a7hovRGewjvdK"
}
```

Beim Versuch, eine weitere Konfiguration zu erstellen:

```
{
    "status": 400,
    "error": "{\"code\":1465,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Can't create throttling config: only one config allowed per org\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:108\",\"schema\":\"throttlingConfigs$prod\"}",
    "requestId": "A7ezT8JhOQT4WIAf1Fv7K2wCDA8281qM"
}
```

## Anwendungsfälle {#uc}

Um Ihnen bei Tests und der Konfiguration behilflich zu sein, steht Ihnen [hier](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Throttling-API_postman-collection.json) eine Postman-Sammlung zur Verfügung.

Diese Postman-Sammlung wurde eingerichtet, um die Postman-Variablensammlung freizugeben, die über __[Integrationen der Adobe I/O-Konsole](https://console.adobe.io/integrations) > Testen > Für Postman herunterladen__ generiert wurde. Dadurch wird eine Postman-Umgebung mit den ausgewählten Integrationswerten erzeugt.

Nach dem Herunterladen und Hochladen in Postman müssen Sie drei Variablen hinzufügen: `{JO_HOST}`, `{BASE_PATH}` und `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration]-Gateway-URL
* `{BASE_PATH}` : Einstiegspunkt für die API. Der Wert lautet „/authoring“
* `{SANDBOX_NAME}`: der Header **x-sandbox-name** (z. B. „prod“), der dem Sandbox-Namen entspricht, in dem die API-Vorgänge stattfinden. Weiterführende Informationen dazu finden Sie unter [Sandbox-Übersicht](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=de).

Im folgenden Abschnitt finden Sie die sortierte Liste der Rest-API-Aufrufe, um den Anwendungsfall auszuführen.

Anwendungsfall 1: **Erstellen und Implementieren einer neuen Drosselungskonfiguration**

1. list
1. create
1. candeploy
1. deploy

Anwendungsfall 2: **Aktualisieren und Implementieren einer noch nicht implementierten Drosselungskonfiguration**

1. list
1. get
1. update
1. candeploy
1. deploy

Anwendungsfall 3: **Aufheben der Implementierung und Löschen einer implementierten Drosselungskonfiguration**

1. list
1. undeploy
1. delete

Anwendungsfall 4: **Löschen einer implementierten Drosselungskonfiguration**

In nur einem API-Aufruf können Sie die Bereitstellung aufheben und die Konfiguration mithilfe des forceDelete-Parameters löschen.

1. list
1. delete mit forceDelete-Parameter

Anwendungsfall 5: **Aktualisieren einer bereits implementierten Drosselungskonfiguration**

>[!NOTE]
>
>Es ist nicht erforderlich, die Implementierung der Konfiguration vor der Aktualisierung aufzuheben

1. list
1. get
1. update

## Lebenszyklus der Konfiguration auf Laufzeitebene {#config}

Wenn die Implementierung einer Konfiguration aufgehoben wird, wird sie auf Laufzeitebene als inaktiv markiert, und ausstehende Ereignisse werden 24 Stunden lang weiter verarbeitet. Sie wird dann im Laufzeit-Service gelöscht.

Nachdem die Implementierung einer Konfiguration aufgehoben wurde, ist es möglich, die Konfiguration zu aktualisieren und erneut zu implementieren. Dadurch wird eine neue Laufzeitkonfiguration erstellt, die bei der bevorstehenden Aktionsausführung berücksichtigt wird.

Beim Aktualisieren einer bereits implementierten Konfiguration werden die neuen Werte sofort berücksichtigt. Die zugrunde liegenden Systemressourcen werden automatisch angepasst. Dies ist besser, als die Implementierung der Konfiguration rückgängig zu machen und sie dann erneut zu implementieren.

## Beispiele für Antworten {#responses}

**Erstellung – POST**

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

**Aktualisieren – PUT**

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

**Lesen (nach Aktualisierung) – GET**

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

**Lesen (nach Implementierung) – GET**

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
