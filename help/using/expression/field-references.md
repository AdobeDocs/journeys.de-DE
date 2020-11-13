---
title: Feldverweise
description: Erfahren Sie mehr über Feldverweise in erweiterten Ausdrücken
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 2af6e632461a8c01451f96c121469c9a32ae7f32
workflow-type: tm+mt
source-wordcount: '433'
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

**Verweis auf ein Feld in Sammlungen**

Die in Sammlungen definierten Elemente werden mit den speziellen Funktionen (alle, zuerst und zuletzt) referenziert. Weiterführende Informationen dazu finden Sie auf dieser [Seite](../expression/collection-management-functions.md).

Beispiel:

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**Verweis auf ein in einer Zuordnung definiertes Feld**

Um ein Element in einer Zuordnung abzurufen, verwenden Sie die Eingabefunktion mit einem bestimmten Schlüssel. Sie wird beispielsweise beim Definieren des Schlüssels eines Ereignisses je nach ausgewähltem Namespace verwendet. Siehe „Auswählen des Namespace“. Weiterführende Informationen finden Sie auf [dieser Seite](../event/selecting-the-namespace.md).

```
@{MyEvent.identityMap.entry('Email').first().id}
```

In diesem Ausdruck erhalten wir den Eintrag für den Schlüssel „E-Mail“ des Felds „IdentityMap“ eines Ereignisses. Der Eintrag „E-Mail“ ist eine Sammlung, aus der wir mithilfe von „first()“ die „ID“ im ersten Element verwenden. Weiterführende Informationen finden Sie auf [dieser Seite](../expression/collection-management-functions.md).

**Parameterwerte einer Datenquelle (von Datenquelle abhängige Werte)**

Wenn Sie ein Feld aus einer externen Datenquelle auswählen, für das ein Parameter aufgerufen werden muss, wird rechts ein neuer Tab angezeigt, auf dem Sie den Parameter angeben können. Weiterführende Informationen finden Sie auf [dieser Seite](../expression/expressionadvanced.md).

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
