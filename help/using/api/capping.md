---
title: Beschreibung der Capping-API
description: Erfahren Sie mehr über die Capping-API.
contentOwner: sauviat
products: journeys
audience: audiences
content-type: reference
topic-tags: journeys
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6656c3a9b62f13d0cbffa3ac97c0a5314cb050a4
workflow-type: tm+mt
source-wordcount: '1108'
ht-degree: 99%

---


# Arbeiten mit der Capping-API

## Einleitung

Die APIs von [!DNL Journey Orchestration] unterstützen 5.000 Ereignisse/Sekunde, doch manche externe Systeme oder APIs verfügen nicht über den gleichen Durchsatz. Deshalb bietet [!DNL Journey Orchestration] eine spezielle Funktion namens Capping-API zur Überwachung und Begrenzung der Rate, die wir externen Systemen auferlegen.

Bei der Konfiguration von Datenquellen definieren Sie eine Verbindung zu einem System, um zusätzliche Informationen abzurufen, die in Ihren Journeys verwendet werden; für eine Aktionsdefinition konfigurieren Sie eine Verbindung zu einem Drittanbietersystem, um Nachrichten oder API-Aufrufe zu senden. Jedes Mal, wenn eine Journey einen API-Aufruf vornimmt, wird die Capping-API abgefragt, bevor der Aufruf über die API-Engine erfolgt. Wenn eine Begrenzung definiert wurde, wird der Aufruf abgelehnt, damit das externe System nicht überlastet wird.

Weitere Informationen zur Konfiguration von Aktionen oder Datenquellen finden Sie unter [Informationen zu Aktionen](https://docs.adobe.com/content/help/de-DE/journeys/using/action-journeys/action.html) oder [Informationen zu Datenquellen](https://docs.adobe.com/content/help/de-DE/journeys/using/data-source-journeys/about-data-sources.html)


## Ressourcen

>[!NOTE]
>
>Die Capping-API von [!DNL Journey Orchestration] wird in einer Swagger-Datei beschrieben, die [hier](https://adobedocs.github.io/JourneyAPI/docs/)verfügbar ist.

Um diese API mit Ihrer [!DNL Journey Orchestration]-Instanz verwenden zu können, müssen Sie die Adobe I/O-Konsole verwenden. Sie können damit beginnen, indem Sie zuerst [Erste Schritte mit Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) und dann die Abschnitte auf dieser Seite befolgen.

Um Ihre Integration zu testen und vorzubereiten, steht Ihnen [hier](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json) eine Postman-Kollektion zur Verfügung.

## Authentifizierung

### Einrichten von API-Zugriff

Der API-Zugriff für [!DNL Journey Orchestration] wird wie folgt eingerichtet: Jeder dieser Schritte wird in der [Adobe I/O-Dokumentation](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) beschrieben.

>[!CAUTION]
>
>Wenn Sie Zertifikate in Adobe I/O verwalten möchten, vergewissern Sie sich, dass Sie in der Admin Console über <b>Systemadministrator</b>-Rechte für das Unternehmen oder ein [Entwicklerkonto](https://helpx.adobe.com/de/enterprise/using/manage-developers.html) verfügen.

1. **Überprüfen Sie, ob Sie ein digitales Zertifikat haben**, oder erstellen Sie bei Bedarf eines. Die mit dem Zertifikat bereitgestellten öffentlichen und privaten Schlüssel werden in den folgenden Schritten benötigt.
1. **Erstellen Sie eine neue Integration mit dem[!DNL Journey Orchestration]-Service** in Adobe I/O und konfigurieren Sie sie. Der Produktprofilzugriff wird für [!DNL Journey Orchestration] und Adobe Experience Platform benötigt. Dann werden Ihre Zugangsdaten generiert (API-Schlüssel, Client-Geheimnis...).
1. **Erstellen Sie einen JSON-Web-Token (JWT)** aus den zuvor erstellten Anmeldedaten und signieren Sie ihn mit Ihrem privaten Schlüssel. Der JWT kodiert alle Identitäts- und Sicherheitsdaten, die Adobe zum Überprüfen Ihrer Identität und zum Erteilen des Zugriffs auf die API benötigt. Dieser Schritt wird in diesem [Abschnitt](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) genau beschrieben.
1. **Ersetzen Sie Ihr JWT durch einen Zugriffstoken**, und zwar über eine POST-Anfrage oder über die Developer Console-Oberfläche. Dieser Zugriffstoken muss in allen Kopfzeilen Ihrer API-Anfragen verwendet werden.

Um eine sichere Service-to-Service-Adobe I/O-API-Sitzung herzustellen, muss jede Anfrage an einen Adobe-Dienst folgende Informationen in der Autorisierungskopfzeile umfassen.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>**: Dies ist Ihre persönliche Organisationskennung; von Adobe erhalten Sie für jede Ihrer Instanzen eine Organisationskennung:

   * &lt;ORGANIZATION>: Ihre Produktionsinstanz

   Wenden Sie sich an Ihren Administrator oder Ihren technischen Ansprechpartner bei Adobe, um den Wert Ihrer Organisationskennung zu erhalten. Sie können sie auch beim Erstellen einer neuen Integration in Adobe I/O abrufen, und zwar in der Lizenzliste (siehe <a href="https://www.adobe.io/authentication.html">Adobe I/O-Dokumentation</a>).

* **&lt;ACCESS_TOKEN>**: Ihr persönlicher Zugriffstoken, der beim Austausch Ihres JWT über eine POST-Anfrage abgerufen wurde.

* **&lt;API_KEY>**: Ihr persönlicher API-Schlüssel. Er wird in Adobe I/O bereitgestellt, nachdem eine neue Integration mit dem [!DNL Journey Orchestration]-Service erstellt wurde.



## Beschreibung der Capping-API

Mit der Capping-API können Sie Begrenzungskonfigurationen erstellen, konfigurieren und überwachen.

| Vorgehensweise | Pfad | Beschreibung |
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
            "maxHttpConnections": <max connections count to the endpoint>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

### Beispiel:

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 30000,
      "rating": {
        "maxCallsCount": 5000,
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

Um Ihnen bei Tests und der Konfiguration behilflich zu sein, steht Ihnen [hier](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json) eine Postman-Kollektion zur Verfügung.

Diese Postman-Kollektion wurde eingerichtet, um die Postman-Variablenkollektion freizugeben, die über __[Integrationen der Adobe I/O-Konsole](https://console.adobe.io/integrations)> Testen > Für Postman herunterladen__ generiert wurde. Dadurch wird eine Postman-Umgebung mit den ausgewählten Integrationswerten erzeugt.

Nach dem Herunterladen und Hochladen in Postman müssen Sie drei Variablen hinzufügen: `{JO_HOST}`, `{Base_Path}` und `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration]-Gateway-URL
* `{BASE_PATH}` : Einstiegspunkt für die API. Der Wert lautet „/authoring“
* `{SANDBOX_NAME}`: der Header **x-sandbox-name** (z. B. „prod“), der dem Sandbox-Namen entspricht, in dem die API-Vorgänge stattfinden. Weitere Informationen finden Sie in der [Übersicht über Sandboxes](https://docs.adobe.com/content/help/de-DE/experience-platform/sandbox/home.html).

Im folgenden Abschnitt finden Sie die sortierte Liste der Rest-API-Aufrufe, um den Anwendungsfalls auszuführen.

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

