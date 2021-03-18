---
product: adobe campaign
solution: Journey Orchestration
title: Feldverweise
description: Erfahren Sie mehr über Feldverweise in erweiterten Ausdrücken
feature: Journeys
role: Data Engineer
level: Erfahren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 100%

---



# Feldverweise {#concept_fkj_ll5_dgb}

Ein Feldverweis kann an ein Ereignis oder eine Feldgruppe angehängt werden. Die einzigen aussagekräftigen Informationen sind der Name des Feldes und sein Pfad.

Wenn Sie in einem Feld Sonderzeichen verwenden, müssen Sie doppelte oder einfache Anführungszeichen nutzen. In den folgenden Fällen sind Anführungszeichen erforderlich:

* das Feld beginnt mit numerischen Zeichen;
* das Feld beginnt mit dem Zeichen „-“;
* das Feld enthält andere Zeichen als: _a_–_z_, _A_–_Z_, _0_–_9_, _ , _-_.

Wenn Ihr Feld zum Beispiel folgendermaßen lautet: _3h_: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

Im Ausdruck wird auf Ereignisfelder mit „@“ und auf Datenquellenfelder mit „#“ verwiesen.

Es wird eine Syntaxfarbe verwendet, um die Ereignisfelder (grün) optisch von Feldgruppen (blau) zu unterscheiden.

**Standardwerte für Feldverweise**

Ein Standardwert kann mit einem Feldnamen verknüpft werden. Die Syntax sieht folgendermaßen aus:

```
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>Der Feldtyp und der Standardwert müssen übereinstimmen. Beispiel: @{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue : 2} ist ungültig, da der Standardwert eine Ganzzahl ist, während der erwartete Wert eine Zeichenfolge ist.

Beispiele:

```
// for an event 'OrderEvent' having the following payload:
{
    "orderId": "12345"
}
 
expression example:
- @{OrderEvent.orderId}                                    -> "12345"
- @{OrderEvent.producdId, defaultValue : "not specified" } -> "not specified" // default value, productId is not a field present in the payload
- @{OrderEvent.productId}                                  -> null
 
 
// for an entity 'Profile' on datasource 'ACP' having fields person/lastName, with fetched data such as:
{
    "person": {
        "lastName":"Snow"
    },
    "emails": [
        { "email":"john.snow@winterfell.westeros" },
        { "email":"snow@thewall.westeros" }
    ]
}
 
expression examples:
- #{ACP.Profile.person.lastName}                 -> "Snow"
- #{ACP.Profile.emails.at(1).email}              -> "snow@thewall.westeros"
- #{ACP.Profile.person.age, defaultValue : -1}   -> -1 // default value, age is not a field present in the payload
- #{ACP.Profile.person.age}                      -> null
```

**Verweis auf ein Feld in Sammlungen**

Die in Sammlungen definierten Elemente werden mit den speziellen Funktionen (alle, zuerst und zuletzt) referenziert. Weitere Informationen dazu finden Sie auf dieser [Seite](../expression/collection-management-functions.md).

Beispiel:

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**Verweis auf ein in einer Zuordnung definiertes Feld**

Um ein Element in einer Zuordnung abzurufen, verwenden Sie die Eingabefunktion mit einem bestimmten Schlüssel. Sie wird beispielsweise beim Definieren des Schlüssels eines Ereignisses je nach ausgewähltem Namespace verwendet. Siehe „Auswählen des Namespace“. Weitere Informationen finden Sie auf [dieser Seite](../event/selecting-the-namespace.md).

```
@{MyEvent.identityMap.entry('Email').first().id}
```

In diesem Ausdruck erhalten wir den Eintrag für den Schlüssel „E-Mail“ des Felds „IdentityMap“ eines Ereignisses. Der Eintrag „E-Mail“ ist eine Sammlung, aus der wir mithilfe von „first()“ die „ID“ im ersten Element verwenden. Weitere Informationen finden Sie auf [dieser Seite](../expression/collection-management-functions.md).

**Parameterwerte einer Datenquelle (von Datenquelle abhängige Werte)**

Wenn Sie ein Feld aus einer externen Datenquelle auswählen, für das ein Parameter aufgerufen werden muss, wird rechts ein neuer Tab angezeigt, auf dem Sie den Parameter angeben können. Weitere Informationen finden Sie auf [dieser Seite](../expression/expressionadvanced.md).

Bei komplexeren Anwendungsfällen können Sie, wenn Sie die Parameter der Datenquelle in den Hauptausdruck einbeziehen möchten, deren Werte mit dem Keyword _params_ definieren. Ein Parameter kann ein beliebiger gültiger Ausdruck sein und selbst aus einer anderen Datenquelle stammen, die ebenfalls einen anderen Parameter enthält.

>[!NOTE]
>
>Wenn Sie die Parameterwerte im Ausdruck definieren, wird der Tab auf der rechten Seite ausgeblendet.

Verwenden Sie die folgende Syntax:

```
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**: genauer Name des ersten Parameters aus der Datenquelle.
* **`<params-1-value>`**: der Wert des ersten Parameters. Dies kann ein beliebiger gültiger Ausdruck sein.

Beispiel:

```
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
