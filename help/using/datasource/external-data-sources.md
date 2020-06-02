---
title: 'Externe Datenquellen '
description: 'Erfahren Sie, wie Sie externe Datenquellen konfigurieren '
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
source-git-commit: 5e2e95090df708d72ade6366a62ea42eff3ac7f2
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 95%

---



# Externe Datenquellen {#concept_t2s_kqt_52b}

Mit externen Datenquellen können Sie eine Verbindung zu Drittanbietersystemen herstellen, z. B. wenn Sie ein Hotelbuchungssystem verwenden, um zu überprüfen, ob die Person ein Zimmer gebucht hat. Anders als bei der integrierten Experience Platform-Datenquelle können Sie beliebig viele externe Datenquellen erstellen.

REST-APIs, die POST oder GET verwenden und JSON zurückgeben, werden unterstützt. API-Schlüssel, einfache und benutzerdefinierte Authentifizierungsmodi werden unterstützt.

Nehmen wir das Beispiel eines Wetter-API-Dienstes, mit dem das Verhalten einer Journey anhand von Echtzeit-Wetterdaten angepasst werden soll.

Im Folgenden finden Sie zwei Beispiele für den API-Aufruf:

* _https://api.adobeweather.org/weather?city=London,uk&amp;appid=1234_
* _https://api.adobeweather.org/weather?lat=35&amp;lon=139&amp;appid=1234_

Der Aufruf besteht aus einer Haupt-URL (_https://api.adobeweather.org/weather_), zwei Parametersätzen („city“ für die Stadt und „lat/long“ für Breiten- und Längengrad) und dem API-Schlüssel (appid).

Im Folgenden werden die wichtigsten Schritte zum Erstellen und Konfigurieren einer neuen externen Datenquelle beschrieben:

1. Klicken Sie in der Liste der Datenquellen auf **[!UICONTROL Hinzufügen]**, um eine neue externe Datenquelle zu erstellen.

   ![](../assets/journey25.png)

   Dadurch wird der Konfigurationsbereich für die Datenquellen auf der rechten Seite des Bildschirms geöffnet.

   ![](../assets/journey26.png)

1. Geben Sie einen Namen für Ihre Datenquelle ein.

   >[!NOTE]
   >
   >Verwenden Sie keine Leerzeichen oder Sonderzeichen. Verwenden Sie nicht mehr als 30 Zeichen.

1. Fügen Sie Ihrer Datenquelle eine Beschreibung hinzu. Dieser Schritt ist optional.
1. Fügen Sie die URL des externen Dienstes hinzu. In unserem Beispiel: _https://api.adobeweather.org/weather_.

   >[!CAUTION]
   >
   >Aus Sicherheitsgründen wird die Verwendung von HTTPS dringend empfohlen. Beachten Sie außerdem, dass die Verwendung nicht öffentlich zugänglicher Adobe-Adressen und die Verwendung von IP-Adressen nicht zulässig sind.

   ![](../assets/journey27.png)

1. Konfigurieren Sie die Authentifizierung je nach Konfiguration des externen Dienstes: **[!UICONTROL Keine Authentifizierung]**, **[!UICONTROL Einfach]**, **[!UICONTROL Benutzerdefiniert]** oder **[!UICONTROL API-Schlüssel]**. Weitere Informationen zum benutzerdefinierten Authentifizierungsmodus finden Sie unter [](../datasource/external-data-sources.md#section_wjp_nl5_nhb). In unserem Beispiel wählen wir:


   * **[!UICONTROL Typ]**: „API-Schlüssel“
   * **[!UICONTROL Wert]**: „1234“ (dies ist der Wert unseres API-Schlüssels)
   * **[!UICONTROL Name]**: „appid“ (dies ist der Name des API-Schlüsselparameters)
   * **[!UICONTROL Position]**: „Abfrageparameter“ (der API-Schlüssel befindet sich in der URL)
   ![](../assets/journey28.png)

1. Fügen Sie für jeden API-Parametersatz eine neue Feldergruppe hinzu, indem Sie auf **[!UICONTROL Neue Feldergruppe hinzufügen]** klicken. Verwenden Sie keine Leerzeichen oder Sonderzeichen im Namen der Feldergruppe. In unserem Beispiel müssen wir zwei Feldergruppen erstellen, eine für jeden Parametersatz („city“ und „lang/lat“).

Für den Parametersatz „long/lat“ erstellen wir eine Feldergruppe mit den folgenden Informationen:

* **[!UICONTROL Verwendet in]**: zeigt die Anzahl der Journeys an, die eine Feldergruppe verwenden. Sie können auf **[!UICONTROL Customer Journeys anzeigen]** klicken, um die Liste der Journeys mit dieser Feldergruppe anzuzeigen.
* **[!UICONTROL Methode]**: Wählen Sie die POST- oder GET-Methode aus. In unserem Fall wählen wir die GET-Methode.
* **[!UICONTROL Aufbewahrungsfrist im Cache]**: In unserem Fall möchten wir, dass das Wetter 10 Minuten lang zwischengespeichert wird.
* **[!UICONTROL Antwort-Payload]**: Klicken Sie in das Feld **[!UICONTROL Payload]** und fügen Sie ein Beispiel der vom Aufruf zurückgegebenen Payload ein. Für unser Beispiel haben wir eine Payload verwendet, die auf einer Wetter-API-Website gefunden wurde. Überprüfen Sie, ob die Feldtypen korrekt sind. Jedes Mal, wenn die API aufgerufen wird, ruft das System alle im Payload-Beispiel enthaltenen Felder ab. Beachten Sie, dass Sie auf **[!UICONTROL Fügen Sie eine neue Payload ein]** klicken können, wenn Sie die aktuell übergebene Payload ändern möchten.
* **[!UICONTROL Dynamische Werte]**: Geben Sie die verschiedenen Parameter getrennt durch ein Komma ein, in unserem Beispiel „long,lat“. Da die Parameterwerte vom Ausführungskontext abhängen, werden sie in den Journeys definiert. Siehe [](../expression/expressionadvanced.md).
* **[!UICONTROL Gesendete Payload]**: Dieses Feld wird nicht in unserem Beispiel angezeigt. Es ist nur verfügbar, wenn Sie die POST-Methode auswählen. Fügen Sie die Payload ein, die an das Drittanbietersystem gesendet wird.

Bei einem GET-Aufruf, der Parameter erfordert, geben Sie die Parameter in das Feld **[!UICONTROL Parameter]** ein und sie werden automatisch am Ende des Aufrufs hinzugefügt. Bei einem POST-Aufruf müssen Sie:

* die beim Aufruf zu übergebenden Parameter im Feld **[!UICONTROL Parameter]** auflisten (im Beispiel unten: „identifier“).
* diese auch mit exakt derselben Syntax im Hauptteil der gesendeten Payload angeben. Dazu müssen Sie Folgendes hinzufügen: „param“: „Name Ihres Parameters“ (im folgenden Beispiel: „identifier“). Folgen Sie der Syntax unten:

   ```
   {"id":{"param":"identifier"}}
   ```

![](../assets/journey29.png)

Klicken Sie auf **[!UICONTROL Speichern]**.

Die Datenquelle ist jetzt konfiguriert und kann in Ihren Journeys verwendet werden, z. B. in Ihren Bedingungen oder zur Personalisierung einer E-Mail. Wenn die Temperatur über 30° C liegt, können Sie sich entscheiden, eine bestimmte Mitteilung zu senden.

## Benutzerdefinierter Authentifizierungsmodus{#section_wjp_nl5_nhb}

>[!CONTEXTUALHELP]
>id="jo_authentication_payload"
>title="Informationen zur benutzerdefinierten Authentifizierung"
>abstract="Der benutzerdefinierte Authentifizierungsmodus wird für die komplexe Authentifizierung verwendet, um API-Wrapping-Protokolle wie OAuth2 aufzurufen. Die Aktionsausführung erfolgt in zwei Schritten. Zunächst wird der Endpunkt aufgerufen, um das Zugriffs-Token zu generieren. Anschließend wird das Zugriffs-Token in die HTTP-Anfrage der Aktion eingefügt."

Dieser Authentifizierungsmodus wird für die komplexe Authentifizierung verwendet, die häufig zum Aufrufen von API-Wrapping-Protokollen wie OAuth2 verwendet wird, um ein Zugriffstoken abzurufen, das in die eigentliche HTTP-Anfrage für die Aktion eingefügt werden soll.

Wenn Sie die benutzerdefinierte Authentifizierung konfigurieren, können Sie auf die Schaltfläche unten klicken, um zu prüfen, ob die Payload der benutzerdefinierten Authentifizierung korrekt konfiguriert ist.

![](../assets/journey29-bis.png)

Ist der Test erfolgreich, wird die Schaltfläche grün.

![](../assets/journey29-ter.png)

Bei dieser Authentifizierung erfolgt die Aktionsausführung in zwei Schritten:

1. Rufen Sie den Endpunkt auf, um das Zugriffstoken zu generieren.
1. Rufen Sie die REST-API auf, indem Sie das Zugriffstoken ordnungsgemäß einfügen.

Diese Authentifizierung besteht aus zwei Teilen.

Die Definition des Endpunkts, der aufgerufen werden soll, um das Zugriffstoken zu generieren:

* endpoint: URL zum Generieren des Endpunkts
* Methode der HTTP-Anfrage am Endpunkt (GET oder POST)
* headers: Schlüssel/Wert-Paare, die bei Bedarf als Kopfzeilen in diesen Aufruf eingefügt werden sollen
* body: beschreibt den Hauptteil des Aufrufs, wenn die Methode POST ist. Für den Hauptteil unterstützen wir eine begrenzte Struktur, die in bodyParams definiert ist (Schlüssel/Wert-Paare). Der bodyType beschreibt Format und Kodierung des Hauptteils (body) im Aufruf:
   * &#39;form&#39;: bedeutet, dass der Inhaltstyp application/x-www-form-urlencoded (Zeichensatz UTF-8) lautet und die Schlüssel/Wert-Paare wie folgt serialisiert werden: Schlüssel1=Wert1&amp;Schlüssel2=Wert2&amp; ...
   * &#39;json&#39;: bedeutet, dass der Inhaltstyp application/json (Zeichensatz UTF-8) ist und die Schlüssel/Wert-Paare wie folgt als JSON-Objekt serialisiert werden: _{ &quot;Schlüssel1&quot;: &quot;Wert1&quot;, &quot;Schlüssel2&quot;: &quot;Wert2&quot;, ...}_

Die Definition der Art und Weise, wie das Zugriffstoken in die HTTP-Anfrage der Aktion eingefügt werden muss:

* authorizationType: definiert, wie das generierte Zugriffstoken in den HTTP-Aufruf für die Aktion eingefügt werden muss. Die möglichen Werte sind:

   * bearer: gibt an, dass das Zugriffstoken in die Autorisierungskopfzeile eingefügt werden muss, z. B.: _Autorisierung: bearer &lt;Zugriffstoken>_
   * header: gibt an, dass das Zugriffstoken als Kopfzeile eingefügt werden muss, der Kopfzeilenname wird von der Eigenschaft tokenTarget definiert. Wenn tokenTarget beispielsweise myHeader ist, wird das Zugriffstoken als Kopfzeile wie folgt eingefügt: _myHeader: &lt;Zugriffstoken>_
   * queryParam: gibt an, dass das Zugriffstoken als queryParam eingefügt werden muss, der queryParam-Name wird von der Eigenschaft tokenTarget definiert. Wenn tokenTarget beispielsweise myQueryParam ist, lautet die URL des Aktionsaufrufs wie folgt: _&lt;URL>?myQueryParam=&lt;Zugriffstoken>_

* tokenInResponse: zeigt an, wie das Zugriffstoken aus dem Authentifizierungsaufruf extrahiert wird. Diese Eigenschaft kann Folgendes sein:
   * &#39;response&#39;: gibt an, dass die HTTP-Antwort das Zugriffstoken ist
   * ein Selektor in einem json (vorausgesetzt, dass die Antwort ein json ist, werden andere Formate wie XML nicht unterstützt). Das Format dieses Selektors ist _json://&lt;Pfad zur Zugriffstoken-Eigenschaft>_. Beispiel: Wenn die Antwort des Aufrufs: _{ &quot;access_token&quot;: &quot;theToken&quot;, &quot;timestamp&quot;: 12323445656 }_ ist, dann ist tokenInResponse: _json: //access_token_

Das Format dieser Authentifizierung ist:

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

Sie können die Cachedauer des Tokens für eine benutzerdefinierte Authentifizierungsdatenquelle ändern. Nachstehend finden Sie ein Beispiel für eine benutzerdefinierte Nutzlast für die Authentifizierung. Die Cachedauer wird im Parameter &quot;cacheDuration&quot;definiert. Es gibt die Speicherungsdauer des generierten Tokens im Cache an. Die Einheit kann Millisekunden, Sekunden, Minuten, Stunden, Tage, Monate, Jahre sein.

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
