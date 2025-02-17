---
product: adobe campaign
title: Externe Datenquellen
description: Erfahren Sie, wie Sie externe Datenquellen konfigurieren
feature: Journeys
role: User
level: Intermediate
exl-id: 9b666c15-2215-4ca5-bc72-40109749dc15
source-git-commit: 3856e323569054fac9e73f2a6af2b86518f62ab9
workflow-type: ht
source-wordcount: '1344'
ht-degree: 100%

---

# Externe Datenquellen {#concept_t2s_kqt_52b}

Mit externen Datenquellen können Sie eine Verbindung zu Drittanbietersystemen herstellen, z. B. wenn Sie ein Hotelbuchungssystem verwenden, um zu überprüfen, ob die Person ein Zimmer gebucht hat. Im Gegensatz zur integrierten Adobe Experience Platform-Datenquelle können Sie beliebig viele externe Datenquellen erstellen.

REST-APIs, die POST oder GET verwenden und JSON zurückgeben, werden unterstützt. API-Schlüssel sowie einfache und benutzerdefinierte Authentifizierungsmodi werden unterstützt.

Nehmen wir als Beispiel einen Wetter-API-Dienst, mit dem ich das Verhalten meiner Journey an Echtzeit-Wetterdaten anpassen möchte.

Im Folgenden finden Sie zwei Beispiele für den API-Aufruf:

* _https://api.adobeweather.org/weather?city=London,uk&amp;appid=1234_
* _https://api.adobeweather.org/weather?lat=35&amp;lon=139&amp;appid=1234_

Der Aufruf besteht aus einer Haupt-URL (_https://api.adobeweather.org/weather_), zwei Parametersätzen („city“ für die Stadt und „lat/long“ für den Breiten- und Längengrad) und dem API-Schlüssel (appid).

Im Folgenden finden Sie die wichtigsten Schritte zum Erstellen und Konfigurieren einer neuen externen Datenquelle:

1. Klicken Sie in der Liste der Datenquellen auf **[!UICONTROL Datenquelle erstellen]**, um eine neue externe Datenquelle zu erstellen.

   ![](../assets/journey25.png)

   Dadurch wird der Konfigurationsbereich für die Datenquelle auf der rechten Seite des Bildschirms geöffnet.

   ![](../assets/journey26.png)

1. Geben Sie einen Namen für Ihre Datenquelle ein.

   >[!NOTE]
   >
   >Verwenden Sie keine Leerzeichen oder Sonderzeichen. Verwenden Sie nicht mehr als 30 Zeichen.

1. Fügen Sie Ihrer Datenquelle eine Beschreibung hinzu. Dieser Schritt ist optional.
1. Fügen Sie die URL des externen Dienstes hinzu. In unserem Beispiel: _https://api.adobeweather.org/weather_.

   >[!CAUTION]
   >
   >Aus Sicherheitsgründen wird die Verwendung von HTTPS dringend empfohlen. Beachten Sie auch, dass wir die Verwendung von nicht öffentlich zugänglichen Adobe-Adressen und die Verwendung von IP-Adressen nicht zulassen.

   ![](../assets/journey27.png)

1. Konfigurieren Sie die Authentifizierung je nach Konfiguration des externen Dienstes: **[!UICONTROL Keine Authentifizierung]**, **[!UICONTROL Einfach]**, **[!UICONTROL Benutzerdefiniert]** oder **[!UICONTROL API-Schlüssel]**. Weitere Informationen zum benutzerdefinierten Authentifizierungsmodus finden Sie in [diesem Abschnitt](../datasource/external-data-sources.md#section_wjp_nl5_nhb). In unserem Beispiel wählen wir:


   * **[!UICONTROL Typ]**: „API-Schlüssel“
   * **[!UICONTROL Wert]**: „1234“ (dies ist der Wert unseres API-Schlüssels)
   * **[!UICONTROL Name]**: „appid“ (dies ist der Name des API-Schlüsselparameters)
   * **[!UICONTROL Standort]**: „Abfrageparameter“ (der API-Schlüssel befindet sich in der URL)

   ![](../assets/journey28.png)

1. Fügen Sie für jeden festgelegten API-Parameter eine neue Feldergruppe hinzu, indem Sie auf **[!UICONTROL Neue Feldergruppe hinzufügen]** klicken. Verwenden Sie keine Leerzeichen oder Sonderzeichen im Namen der Feldergruppe. In unserem Beispiel müssen wir zwei Feldergruppen erstellen, eine für jeden Parametersatz (city und long/lat).

Für den Parametersatz „long/lat“ erstellen wir eine Feldergruppe mit folgenden Informationen:

* **[!UICONTROL Verwendet in]**: zeigt die Anzahl der Journeys an, die eine Feldergruppe verwenden. Sie können auf das Symbol **[!UICONTROL Journeys anzeigen]** klicken, um die Liste der Journeys anzuzeigen, die diese Feldergruppe verwenden.
* **[!UICONTROL Methode]**: Wählen Sie die POST- oder GET-Methode aus. In unserem Beispiel wählen wir die GET-Methode aus.
* **[!UICONTROL Antwort-Payload]**: Klicken Sie in das Feld **[!UICONTROL Payload]** und fügen Sie ein Beispiel für die Payload ein, die vom Aufruf zurückgegeben wird. Für unser Beispiel haben wir eine Payload verwendet, die auf einer Wetter-API-Website gefunden wurde. Überprüfen Sie, ob die Feldtypen korrekt sind. Jedes Mal, wenn die API aufgerufen wird, ruft das System alle im Payload-Beispiel enthaltenen Felder ab. Beachten Sie, dass Sie auf **[!UICONTROL Neue Payload einfügen]** klicken können, wenn Sie die aktuell übergebene Payload ändern möchten.
* **[!UICONTROL Dynamische Werte]**: Geben Sie die verschiedenen Parameter getrennt durch ein Komma ein, in unserem Beispiel „long,lat“. Da die Parameterwerte vom Ausführungskontext abhängen, werden sie in den Journeys definiert. Weitere Informationen finden Sie auf [dieser Seite](../expression/expressionadvanced.md).
* **[!UICONTROL Gesendete Payload]**: Dieses Feld wird in unserem Beispiel nicht angezeigt. Es ist nur verfügbar, wenn Sie die POST-Methode auswählen. Fügen Sie die Payload ein, die an das Drittanbietersystem gesendet wird.

Bei einem GET-Aufruf, der Parameter erfordert, geben Sie die Parameter in das Feld **[!UICONTROL Dynamische Werte]** ein und sie werden automatisch am Ende des Aufrufs hinzugefügt. Bei einem POST-Aufruf müssen Sie:

* die bei der Anfrage zu übergebenden Parameter im Feld **[!UICONTROL Dynamische Werte]** auflisten (im Beispiel unten: „identifier“).
* diese auch mit exakt derselben Syntax im Hauptteil der gesendeten Payload angeben. Dazu müssen Sie Folgendes hinzufügen: „param“: „Name Ihres Parameters“ (im folgenden Beispiel: „identifier“). Folgen Sie der unten stehenden Syntax:

  ```
  {"id":{"param":"identifier"}}
  ```

![](../assets/journey29.png)

Klicken Sie auf **[!UICONTROL Speichern]**.

Die Datenquelle ist jetzt konfiguriert und kann in Ihren Journeys verwendet werden, z. B. in Ihren Bedingungen oder zur Personalisierung einer E-Mail. Wenn die Temperatur über 30 °C liegt, können Sie eine bestimmte Mitteilung versenden.

## Benutzerdefinierter Authentifizierungsmodus{#section_wjp_nl5_nhb}

>[!CONTEXTUALHELP]
>id="jo_authentication_payload"
>title="Über benutzerdefinierte Authentifizierung"
>abstract="Der benutzerdefinierte Authentifizierungsmodus wird für die komplexe Authentifizierung verwendet, um API-Wrapping-Protokolle wie OAuth2 aufzurufen. Die Aktionsausführung erfolgt in zwei Schritten. Zunächst wird der Endpunkt aufgerufen, um das Zugriffstoken zu generieren. Anschließend wird das Zugriffstoken in die HTTP-Anfrage der Aktion eingefügt."

Dieser Authentifizierungsmodus wird für die komplexe Authentifizierung verwendet, die häufig zum Aufrufen von API-Wrapping-Protokollen wie OAuth2 verwendet wird, um ein Zugriffstoken abzurufen, das in die eigentliche HTTP-Anfrage für die Aktion eingefügt werden soll.

Wenn Sie die benutzerdefinierte Authentifizierung konfigurieren, können Sie auf die Schaltfläche unten klicken, um zu überprüfen, ob die Payload der benutzerdefinierten Authentifizierung korrekt konfiguriert ist.

![](../assets/journey29-bis.png)

Wenn der Test erfolgreich ist, wird die Schaltfläche grün.

![](../assets/journey29-ter.png)

Bei dieser Authentifizierung erfolgt die Aktionsausführung in zwei Schritten:

1. Rufen Sie den Endpunkt auf, um das Zugriffstoken zu generieren.
1. Rufen Sie die REST-API auf, indem Sie das Zugriffstoken ordnungsgemäß einfügen.

Diese Authentifizierung besteht aus zwei Teilen.

Die Definition des Endpunkts, der aufgerufen werden soll, um das Zugriffstoken zu generieren:

* endpoint: URL zum Generieren des Endpunkts
* Methode der HTTP-Anfrage am Endpunkt (GET oder POST)
* headers: Schlüssel/Wert-Paare, die bei Bedarf als Kopfzeilen in diesen Aufruf eingefügt werden sollen
* body: beschreibt den Haupttextteil des Aufrufs, wenn die Methode POST ist. Für den Hauptteil unterstützen wir eine begrenzte Struktur, die in bodyParams definiert ist (Schlüssel/Wert-Paare). Der bodyType beschreibt Format und Codierung des Haupttextteils (body) im Aufruf:
   * &#39;form&#39;: bedeutet, dass der Inhaltstyp application/x-www-form-urlencoded (Zeichensatz UTF-8) lautet und die Schlüssel/Wert-Paare wie folgt serialisiert werden: Schlüssel1=Wert1&amp;Schlüssel2=Wert2&amp; ...
   * &#39;json&#39;: bedeutet, dass der Inhaltstyp application/json (Zeichensatz UTF-8) ist und die Schlüssel/Wert-Paare wie folgt als JSON-Objekt serialisiert werden: _{ &quot;Schlüssel1&quot;: &quot;Wert1&quot;, &quot;Schlüssel2&quot;: &quot;Wert2&quot;, ...}_

Die Definition der Art und Weise, wie das Zugriffstoken in die HTTP-Anfrage der Aktion eingefügt werden muss:

* authorizationType: definiert, wie das generierte Zugriffstoken in den HTTP-Aufruf für die Aktion eingefügt werden muss. Die möglichen Werte sind:

   * bearer: gibt an, dass das Zugriffstoken in der Autorisierungskopfzeile eingefügt werden muss, z. B.: _Authorization: Bearer &lt;access token>_
   * header: gibt an, dass das Zugriffstoken als Kopfzeile eingefügt werden muss, wobei der Kopfzeilenname durch die Eigenschaft „tokenTarget“ definiert wird. Wenn das tokenTarget z. B. myHeader ist, wird das Zugriffstoken wie folgt als Kopfzeile eingefügt: _myHeader: &lt;access token>_
   * queryParam: gibt an, dass das Zugriffstoken als queryParam eingefügt werden muss, wobei der Abfrageparametername durch die Eigenschaft „tokenTarget“ definiert wird. Wenn das tokenTarget beispielsweise myQueryParam ist, lautet die URL des Aktionsaufrufs: _&lt;url>?myQueryParam=&lt;access token>_

* tokenInResponse: Gibt an, wie das Zugriffstoken aus dem Authentifizierungsaufruf extrahiert wird. Diese Eigenschaft kann Folgendes sein:
   * &#39;response&#39;: gibt an, dass die HTTP-Antwort das Zugriffstoken ist
   * eine Auswahl in einer JSON-Datei (es wird vorausgesetzt, die Antwort ist eine JSON-Datei, und andere Formate wie XML werden nicht unterstützt). Das Format dieser Auswahl ist _json://&lt;Pfad zur Zugriffstoken-Eigenschaft>_. Wenn die Antwort des Aufrufs zum Beispiel folgendermaßen lautet: _{ &quot;access_token&quot;: &quot;theToken&quot;, &quot;timestamp&quot;: 12323445656 }_, wird die tokenInResponse Folgendes sein: _json: //access_token_

Das Format dieser Authentifizierung lautet:

```
{
    "type": "customAuthorization",
    "authorizationType": "<value in 'bearer', 'header' or 'queryParam'>",
    (optional, mandatory if authorizationType is 'header' or 'queryParam') "tokenTarget": "<name of the header or queryParam if the authorizationType is 'header' or 'queryParam'>",
    "endpoint": "<URL of the authentication endpoint>",
    "method": "<HTTP method to call the authentication endpoint, in 'GET' or 'POST'>",
    (optional) "headers": {
        "<header name>": "<header value>",
        ...
    },
    (optional, mandatory if method is 'POST') "body": {
        "bodyType": "<'form'or 'json'>,
        "bodyParams": {
            "param1": value1,
            ...

        }
    },
    "tokenInResponse": "<'response' or json selector in format 'json://<field path to access token>'"
}
```

Sie können die Aufbewahrungsfrist im Cache des Tokens für eine benutzerdefinierte Authentifizierungsdatenquelle ändern. Nachstehend finden Sie ein Beispiel für eine benutzerdefinierte Authentifizierungs-Payload. Die Aufbewahrungsfrist im Cache wird im Parameter „cacheDuration“ definiert. Sie gibt die Aufbewahrungsdauer des generierten Tokens im Cache an. Die Einheit kann Millisekunden, Sekunden, Minuten, Stunden, Tage, Monate oder Jahre sein.

```
"authentication": {
    "type":"customAuthorization",
    "authorizationType":"Bearer",
    "endpoint":"http://localhost:${port}/epsilon/oauth2/access_token",
    "method":"POST",
    "headers": {
        "Authorization":"Basic EncodeBase64(${epsilonClientId}:${epsilonClientSecret})"
        },
    "body": {
        "bodyType":"form",
        "bodyParams": {
             "scope":"cn mail givenname uid employeeNumber",
             "grant_type":"password",
             "username":"${epsilonUserName}",
             "password":"${epsilonUserPassword}"
             }
        },
    "tokenInResponse":"json://access_token",
    "cacheDuration":
             { "duration":5, "timeUnit":"seconds" }
    }
```

>[!NOTE]
>
>Die Aufbewahrungsfrist im Cache hilft, zu viele Aufrufe an die Authentifizierungsendpunkte zu vermeiden. Die Aufbewahrung des Authentifizierungs-Tokens erfolgt im Cache des entsprechenden Service. Er wird also nicht dauerhaft gespeichert. Wenn ein Service neu gestartet wird, beginnt er mit einem leeren Cache. Die Aufbewahrungsfrist im Cache beträgt standardmäßig 1 Stunde. Sie kann in der benutzerdefinierten Authentifizierungs-Payload angepasst werden, indem eine andere Aufbewahrungsfrist angegeben wird.
