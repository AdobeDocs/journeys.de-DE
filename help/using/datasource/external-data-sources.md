---
title: 'Externe Datenquellen '
description: 'Informationen zum Konfigurieren externer Datenquellen '
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



# Externe Datenquellen {#concept_t2s_kqt_52b}

Mit externen Datenquellen können Sie eine Verbindung zu Drittanbietersystemen herstellen, z. B. wenn Sie ein Hotelbuchungssystem verwenden, um zu überprüfen, ob die Person ein Zimmer registriert hat. Im Gegensatz zur integrierten Experience Platform-Datenquelle können Sie so viele externe Datenquellen wie nötig erstellen.

REST-APIs, die POST oder GET verwenden und JSON zurückgeben, werden unterstützt. API-Schlüssel, einfache und benutzerdefinierte Authentifizierungsmodi werden unterstützt.

Nehmen wir das Beispiel eines Wetter-API-Dienstes, den ich verwenden möchte, um das Verhalten meiner Reise anhand von Echtzeit-Wetterdaten anzupassen.

Im Folgenden finden Sie zwei Beispiele für den API-Aufruf:

* _https://api.adobeweather.org/weather?city=London,uk&amp;appid=1234_
* _https://api.adobeweather.org/weather?lat=35&amp;lon=139&amp;appid=1234_

Der Aufruf besteht aus einer Haupt-URL (_https://api.adobeweather.org/weather_), zwei Parametersätzen (&quot;Ort&quot;für die Stadt und &quot;lat/long&quot;für Breiten- und Längengrad) und dem API-Schlüssel (appid).

Im Folgenden werden die wichtigsten Schritte zum Erstellen und Konfigurieren einer neuen externen Datenquelle beschrieben:

1. Klicken Sie in der Liste der Datenquellen auf **[!UICONTROL Hinzufügen]**, um eine neue externe Datenquelle zu erstellen.

   ![](../assets/journey25.png)

   Dadurch wird der Bereich für die Datenquellenkonfiguration auf der rechten Seite des Bildschirms geöffnet.

   ![](../assets/journey26.png)

1. Geben Sie einen Namen für Ihre Datenquelle ein.

   >[!NOTE]
   >
   >Verwenden Sie keine Leerzeichen oder Sonderzeichen. Verwenden Sie nicht mehr als 30 Zeichen.

1. Fügen Sie Ihrer Datenquelle eine Beschreibung hinzu. Dieser Schritt ist optional.
1. Fügen Sie die URL des externen Dienstes hinzu. In unserem Beispiel: _https://api.adobeweather.org/weather_.

   >[!CAUTION]
   >
   >Aus Sicherheitsgründen wird die Verwendung von HTTPS dringend empfohlen. Beachten Sie außerdem, dass wir die Verwendung von Adobe-Adressen, die nicht öffentlich zugänglich sind, und die Verwendung von IP-Adressen nicht zulassen.

   ![](../assets/journey27.png)

1. Konfigurieren Sie die Authentifizierung je nach Konfiguration des externen Dienstes: **[!UICONTROL Keine Authentifizierung]**,**[!UICONTROL  Grundlegender]**, **[!UICONTROL Benutzerdefinierter]**oder**[!UICONTROL  API-Schlüssel]**. Weitere Informationen zum benutzerdefinierten Authentifizierungsmodus finden Sie unter [](../datasource/external-data-sources.md#section_wjp_nl5_nhb). In unserem Beispiel wählen wir:


   * **[!UICONTROL Typ]**: &quot;API-Schlüssel&quot;
   * **[!UICONTROL Wert]**: &quot;1234&quot;(dies ist der Wert unseres API-Schlüssels)
   * **[!UICONTROL Name]**: &quot;appid&quot;(dies ist der Parametername des API-Schlüssels)
   * **[!UICONTROL Ort]**: &quot;Abfrageparameter&quot;(der API-Schlüssel befindet sich in der URL)
   ![](../assets/journey28.png)

1. Fügen Sie für jeden API-Parametersatz eine neue Feldgruppe hinzu, indem Sie auf Neue Feldgruppe **[!UICONTROL hinzufügen klicken]**. Verwenden Sie keine Leerzeichen oder Sonderzeichen im Namen der Feldgruppe. In unserem Beispiel müssen wir zwei Feldgruppen erstellen, eine für jeden Parametersatz (Stadt und lang/lang).

Für den Parametersatz &quot;long/lat&quot;erstellen wir eine Feldgruppe mit den folgenden Informationen:

* **[!UICONTROL Verwendet in]**: zeigt die Anzahl der Reisen an, die eine Feldgruppe verwenden. Sie können auf das Symbol &quot;Reisen**[!UICONTROL  anzeigen]** &quot;klicken, um die Liste der Reisen mit dieser Feldgruppe anzuzeigen.
* **[!UICONTROL Methode]**: wählen Sie die POST- oder GET-Methode. In unserem Fall wählen wir die GET-Methode.
* **[!UICONTROL Cachedauer]**: in unserem Fall möchten wir, dass das Wetter 10 Minuten lang zwischengespeichert wird.
* **[!UICONTROL Antwortnutzlast]**: Klicken Sie in das Feld**[!UICONTROL  Nutzlast]** und fügen Sie ein Beispiel der vom Aufruf zurückgegebenen Nutzlast ein. Für unser Beispiel haben wir eine Nutzlast verwendet, die auf einer Wetter-API-Website gefunden wurde. Überprüfen Sie, ob die Feldtypen korrekt sind. Jedes Mal, wenn die API aufgerufen wird, ruft das System alle im Payload-Beispiel enthaltenen Felder ab. Beachten Sie, dass Sie auf Neue Nutzlast ****einfügen klicken können, wenn Sie die aktuell übergebene Nutzlast ändern möchten.
* **[!UICONTROL Dynamische Werte]**: Geben Sie die verschiedenen Parameter getrennt durch ein Koma ein, &quot;long,lat&quot; in unserem Beispiel. Da die Parameterwerte vom Ausführungskontext abhängen, werden sie in den Fahrten definiert. Näheres wird im Abschnitt[](../expression/expressionadvanced.md)beschrieben.
* **[!UICONTROL Gesendete Nutzlast]**: Dieses Feld wird nicht in unserem Beispiel angezeigt. Sie ist nur verfügbar, wenn Sie die POST-Methode auswählen. Fügen Sie die Nutzlast ein, die an das Drittanbietersystem gesendet wird.

Bei einem GET-Aufruf, der Parameter erfordert, geben Sie die Parameter in das Feld **[!UICONTROL Parameter]**ein und sie werden automatisch am Ende des Aufrufs hinzugefügt. Bei einem POST-Aufruf müssen Sie:

* listet die Parameter auf, die zur Anrufzeit im Feld **[!UICONTROL Parameter]**übergeben werden sollen (im folgenden Beispiel: &quot;identifier&quot;).
* sie auch mit der exakt gleichen Syntax im Hauptteil der gesendeten Nutzlast angeben. Dazu müssen Sie Folgendes hinzufügen: &quot;param&quot;: &quot;Name Ihres Parameters&quot;(im folgenden Beispiel: &quot;identifier&quot;). Führen Sie die folgende Syntax aus:

   ```
   {“id”:{“param”:“identifier”}}
   ```

![](../assets/journey29.png)

Wählen Sie **[!UICONTROL Speichern]**aus.

Die Datenquelle ist jetzt konfiguriert und kann für Ihre Reisen genutzt werden, z.B. in Ihren Bedingungen oder zur Personalisierung einer E-Mail. Wenn die Temperatur über 30°C liegt, können Sie sich entscheiden, eine bestimmte Mitteilung zu senden.

## Benutzerdefinierter Authentifizierungsmodus{#section_wjp_nl5_nhb}

Dieser Authentifizierungsmodus wird für die komplexe Authentifizierung verwendet, die häufig zum Aufrufen von API-Umbruchprotokollen wie OAuth2 verwendet wird, um ein Zugriffstoken abzurufen, das in die eigentliche HTTP-Anforderung für die Aktion eingefügt werden soll.

Wenn Sie die benutzerdefinierte Authentifizierung konfigurieren, können Sie auf die Schaltfläche unten klicken, um zu prüfen, ob die benutzerdefinierte Authentifizierungsnutzlast korrekt konfiguriert ist.

![](../assets/journey29-bis.png)

Ist der Test erfolgreich, wird die Schaltfläche grün.

![](../assets/journey29-ter.png)

Bei dieser Authentifizierung erfolgt die Aktionsausführung in zwei Schritten:

1. Rufen Sie den Endpunkt auf, um das Zugriffstoken zu generieren.
1. Rufen Sie die REST-API auf, indem Sie das Zugriffstoken ordnungsgemäß einfügen.

Diese Authentifizierung besteht aus zwei Teilen.

Die Definition des Endpunkts, der aufgerufen werden soll, um das Zugriffstoken zu generieren:

* endpoint: URL zum Generieren des Endpunkts
* Methode der HTTP-Anforderung am Endpunkt (GET oder POST)
* Kopfzeilen: Schlüssel/Wert-Paare, die bei Bedarf als Header in diesen Aufruf eingefügt werden sollen
* body: beschreibt den Hauptteil des Aufrufs, wenn die Methode POST ist. Wir unterstützen eine begrenzte Körperstruktur, die in bodyParams definiert ist (Schlüssel/Wert Paare). Der bodyType beschreibt Format und Kodierung des Textkörpers im Aufruf:
   * &quot;form&quot;: Das bedeutet, dass der Inhaltstyp application/x-www-form-urlencoded (Zeichensatz UTF-8) lautet und die Schlüssel/Wert-Paare wie folgt serialisiert werden: key1=value1&amp;key2=value2&amp;...
   * &quot;json&quot;: Das bedeutet, dass der Inhaltstyp application/json (Zeichensatz UTF-8) ist und die Schlüsselwertpaare wie folgt als JSON-Objekt serialisiert werden: _{ &quot;key1&quot;: &quot;value1&quot;, &quot;key2&quot;: &quot;value2&quot;, ...}_

Die Definition der Art und Weise, wie das Zugriffstoken in die HTTP-Anforderung der Aktion eingefügt werden muss:

* authorizedType: definiert, wie das generierte Zugriffstoken in den HTTP-Aufruf für die Aktion eingefügt werden muss. Mögliche Werte sind:

   * Träger: gibt an, dass das Zugriffstoken in den Autorisierungsheader eingefügt werden muss, z. B.: _Genehmigung: Bearer &lt;access token>_
   * header: gibt an, dass das Zugriffstoken als Kopfzeile eingefügt werden muss, der von der Eigenschaft tokenTarget definierte Kopfzeilenname. Wenn das tokenTarget beispielsweise myHeader ist, wird das Zugriffstoken als Kopfzeile wie folgt eingefügt: _myHeader: &lt;access token>_
   * queryParam: gibt an, dass das Zugriffstoken als queryParam eingefügt werden muss, der Abfrageparam-Name, der von der Eigenschaft tokenTarget definiert wird. Wenn das tokenTarget beispielsweise myQueryParam ist, lautet die URL des Aktionsaufrufs wie folgt: _&lt;url>?myQueryParam=&lt;access token>_

* tokenInResponse: zeigt an, wie das Zugriffstoken aus dem Authentifizierungsaufruf extrahiert wird. Diese Eigenschaft kann:
   * &quot;response&quot;: gibt an, dass die HTTP-Antwort das Zugriffstoken ist
   * einen Selektor in einer JSON (vorausgesetzt, dass die Antwort ein JSON ist, werden andere Formate wie XML nicht unterstützt). Das Format dieser Auswahl ist _json://&lt;Pfad zur Eigenschaft des Zugriffstokens>_. Beispiel: _{ &quot;access_token&quot;: &quot;theToken&quot;, &quot;timestamp&quot;: 12323445656_) lautet die Zeichenfolge tokenInResponse wie folgt: _json: //access_token_

Das Format dieser Authentifizierung ist:

```
{
    "type": "customAuthorization",
    "authorizationType": "<value in 'bearer', 'header' or 'queryParam'>",
    (optional, mandatory if authorizationType is 'header' or 'queryParam') "tokenTarget": "<name of the header or queryParam if the authorizationType is 'header' or 'queryParam'>",
    "endpoint": "<URL of the authentication endpoint>",
    "method": "<HTTP method to call the authentication endpoint, in 'GET' or 'POST'>",
    (optional) "headers: {
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
