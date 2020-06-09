---
title: API-Beschreibung für Capping
description: Weitere Informationen zur Capping-API.
contentOwner: sauviat
products: journeys
audience: audiences
content-type: reference
topic-tags: journeys
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '1065'
ht-degree: 25%

---


# Arbeiten mit der Capping-API

## Einleitung

[!DNL Journey Orchestration]Die APIs von &quot;5000 Ereignis/Sekunden&quot;unterstützen einige externe Systeme oder APIs jedoch nicht über einen entsprechenden Durchsatz verfügen. Deshalb [!DNL Journey Orchestration] kommt eine spezielle Funktion namens Capping API zur Überwachung und Begrenzung der Rate, die wir externen Systemen auferlegen.

Während einer Datenquellenkonfiguration definieren Sie eine Verbindung zu einem System, um zusätzliche Informationen abzurufen, die auf Ihren Reisen verwendet werden, oder für eine Aktionsdefinition konfigurieren Sie die Verbindung eines Drittanbietersystems, um Nachrichten oder API-Aufrufe zu senden. Jedes Mal, wenn ein API-Aufruf von Journey ausgeführt wird, wird die Capping-API abgefragt. Der Aufruf erfolgt über die API-Engine. Wenn eine Begrenzung definiert ist, wird der Aufruf abgelehnt und das externe System wird nicht überlastet.

Weitere Informationen zur Aktion oder Datenquellenkonfiguration finden Sie unter [Aktionen](https://docs.adobe.com/content/help/en/journeys/using/action-journeys/action.html) oder [Grundlagen zu Datenquellen](https://docs.adobe.com/content/help/en/journeys/using/data-source-journeys/about-data-sources.html)


## Ressourcen

Die [!DNL Journey Orchestration] Capping-API wird in einer Swagger-Datei beschrieben, die [hier](https://adobedocs.github.io/JourneyAPI/docs/)verfügbar ist.

Um diese API mit Ihrer [!DNL Journey Orchestration] Instanz zu verwenden, müssen Sie die AdobeIO-Konsole verwenden. Sie können Beginn ausführen, indem Sie diese [Schritte mit Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) ausführen und dann die Abschnitte auf dieser Seite verwenden.

Um Ihre Integration zu testen und vorzubereiten, steht [hier](https://github.com/AdobeDocs/JourneyAPI/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)eine Postman-Sammlung zur Verfügung.

## Authentifizierung

### Einrichten von API-Zugriff

[!DNL Journey Orchestration] Der API-Zugriff wird wie folgt eingerichtet: Jeder dieser Schritte wird in der [Adobe I/O-Dokumentation](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) beschrieben.

>[!CAUTION]
>
>Wenn Sie in Adobe I/O Zertifikate verwalten möchten, vergewissern Sie sich, dass Sie in der Admin Console über <b>Systemadministrator</b> -Rechte für das Unternehmen oder ein <a href="https://helpx.adobe.com/enterprise/using/manage-developers.html">Entwicklerkonto</a> verfügen.

1. **Überprüfen Sie, ob Sie ein digitales Zertifikat haben**, oder erstellen Sie bei Bedarf eines. Die mit dem Zertifikat bereitgestellten öffentlichen und privaten Schlüssel werden in den folgenden Schritten benötigt.
1. **[!DNL Journey Orchestration]Erstellen Sie eine neue Integration mit Service** in Adobe I/O und konfigurieren Sie sie. Der Produktzugriff auf das Profil ist für [!DNL Journey Orchestration] und Adobe Experience Platform erforderlich. Dann werden Ihre Zugangsdaten generiert (API-Schlüssel, Client-Geheimnis...).
1. **Erstellen Sie einen JSON-Web-Token (JWT)** aus den zuvor erstellten Anmeldedaten und signieren Sie ihn mit Ihrem privaten Schlüssel. Der JWT kodiert alle Identitäts- und Sicherheitsdaten, die Adobe zum Überprüfen Ihrer Identität und zum Erteilen des Zugriffs auf die API benötigt. Dieser Schritt wird in diesem [Abschnitt beschrieben.](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Tauschen Sie Ihre JWT für ein Zugriffstoken** über eine POST-Anforderung oder über die Developer Console-Oberfläche aus. Dieser Zugriffstoken muss in allen Kopfzeilen Ihrer API-Anfragen verwendet werden.

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

* **&lt;ACCESS_TOKEN>**: Ihr persönliches Zugriffstoken, das beim Austausch Ihrer JWT über eine POST-Anforderung abgerufen wurde.

* **&lt;API_KEY>**: Ihr persönlicher API-Schlüssel. It is provided in Adobe I/O after creating a new integration to [!DNL Journey Orchestration] Service.



## API-Beschreibung für Capping

Mit der Capping-API können Sie Ihre Capping-Konfigurationen erstellen, konfigurieren und überwachen.

| Vorgehensweise | Pfad | Beschreibung |
|---|---|---|
| POST | Liste/endpointConfigs | Liste der Endpunktverschlüsselungskonfigurationen abrufen |
| POST | /endpointConfigs | Konfiguration für Endpunktbegrenzung erstellen |
| POST | /endpointConfigs/{uid}/deploy | Konfiguration für Endpunktbegrenzung bereitstellen |
| POST | /endpointConfigs/{uid}/undeploy | Bereitstellung einer Endpunktverschlüsselungskonfiguration aufheben |
| POST | /endpointConfigs/{uid}/canDeploy | Überprüfen, ob eine Endpunktzuordnungskonfiguration bereitgestellt werden kann oder nicht |
| PUT | /endpointConfigs/{uid} | Konfiguration der Endpunktbegrenzung aktualisieren |
| GET | /endpointConfigs/{uid} | Abrufen einer Endpunktzuordnungskonfiguration |
| LÖSCHEN | /endpointConfigs/{uid} | Löschen einer Enpoint-Capping-Konfiguration |

Wenn eine Konfiguration erstellt oder aktualisiert wird, wird automatisch eine Überprüfung durchgeführt, um die Syntax und die Integrität der Nutzlast zu gewährleisten.
Wenn Probleme auftreten, gibt der Vorgang eine Warnung oder Fehler zurück, die Ihnen bei der Korrektur der Konfiguration helfen.



## Endpunktkonfiguration

Die Basisstruktur einer Endpunktkonfiguration lautet wie folgt:

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

Wenn eine **canDeploy** -Methode aufgerufen wird, validiert der Prozess die Konfiguration und gibt den durch seine eindeutige ID identifizierten Prüfstatus zurück:

```
"ok" or "error"
```

Mögliche Fehler sind:

* **ERR_ENDPOINTCONFIG_100**: capping config: fehlende oder ungültige URL
* **ERR_ENDPOINTCONFIG_101**: capping config: fehlerhafte URL
* **ERR_ENDPOINTCONFIG_102**: capping config: fehlerhafte URL: Platzhalter in URL in Host nicht zulässig:Anschluss
* **ERR_ENDPOINTCONFIG_103**: capping config: fehlende HTTP-Methoden
* **ERR_ENDPOINTCONFIG_104**: capping config: keine Call-Bewertung definiert
* **ERR_ENDPOINTCONFIG_107**: capping config: ungültige Anzahl der max. Aufrufe (maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**: capping config: ungültige maximale Anzahl von Anrufen (periodInMs)
* **ERR_ENDPOINTCONFIG_111**: capping config: Endpunktkonfiguration kann nicht erstellt werden: ungültige Nutzlast
* **ERR_ENDPOINTCONFIG_112**: capping config: Endpunktkonfiguration kann nicht erstellt werden: JSON-Nutzlast erwarten
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: ungültiger Dienstname <!--<given value>-->: muss &#39;dataSource&#39; oder &#39;action&#39; sein


Die potenzielle Warnung lautet:

**ERR_ENDPOINTCONFIG_106**: capping config: max. HTTP-Verbindungen nicht definiert: keine Einschränkung standardmäßig



## Anwendungsfälle

In diesem Abschnitt finden Sie die fünf Hauptverwendungsfälle, die Sie zur Verwaltung Ihrer Deckelkonfiguration in durchführen können [!DNL Journey Orchestration].

Um Ihnen bei Ihren Tests und Konfigurationen behilflich zu sein, steht [hier](https://github.com/AdobeDocs/JourneyAPI/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)eine Postman-Sammlung zur Verfügung.

Diese Postman Collection wurde eingerichtet, um die Postman-Variablensammlung freizugeben, die über die Integrationen __[der](https://console.adobe.io/integrations)Adobe I/O-Konsole > Testen Sie sie aus > Für Postman__ herunterladen generiert wurde. Dadurch wird eine Postman-Umgebung mit den ausgewählten Integrationswerten generiert.

Nach dem Herunterladen und Hochladen in Postman müssen Sie zwei Variablen hinzufügen: `{JO_HOST}` und `{Base_Path}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] Gateway-URL
* `{BASE_PATH}` : Einstiegspunkt für die API. Der Wert lautet &quot;/authoring&quot;



Verwendungsfall Nr. 1: **Erstellen und Bereitstellen einer neuen Konfiguration für die Begrenzung**

1. list
1. erstellen
1. candeploy
1. bereitstellen

Anwendungsfall Nr. 2: **Aktualisieren und Bereitstellen einer noch nicht bereitgestellten Capping-Konfiguration**

1. list
1. get
1. update
1. candeploy
1. bereitstellen

Anwendungsfall Nr. 3: **Bereitstellung und Löschen einer bereitgestellten Deckelkonfiguration aufheben**

1. list
1. undeploy
1. delete

Anwendungsfall Nr. 4: **Löschen Sie eine bereitgestellte Capping-Konfiguration.**

Bei nur einem API-Aufruf können Sie die Bereitstellung aufheben und die Konfiguration mithilfe des forceDelete-Parameters löschen.
1. list
1. delete mit forceDelete-Parameter

Anwendungsfall Nr. 5: **Bereits bereitgestellte Capping-Konfiguration aktualisieren**

1. list
1. get
1. update
1. undeploy
1. candeploy
1. bereitstellen

