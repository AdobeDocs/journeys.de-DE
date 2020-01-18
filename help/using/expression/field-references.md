---
title: Feldverweise
description: Informationen zu Feldverweisen in erweiterten Ausdrücken
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
source-git-commit: 8be9cd1803ab2f7093934424c36fcd7407a4a20a

---



# Feldverweise {#concept_fkj_ll5_dgb}

Ein Feldverweis kann an ein Ereignis oder eine Feldgruppe angehängt werden. Die einzigen aussagekräftigen Informationen sind der Name des Felds und sein Pfad.

Wenn Sie Sonderzeichen in einem Feld verwenden, müssen Sie doppelte oder einfache Anführungszeichen verwenden. In den folgenden Fällen sind Anführungszeichen erforderlich:

* das Feld beginnt mit numerischen Zeichen
* das Feld beginnt mit dem Zeichen &quot;-&quot;
* das Feld enthält alles andere als: _a_-_z_, _A_-_Z_, _0____-9, _,-_

Wenn Ihr Feld beispielsweise _3h_ ist: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

Im Ausdruck werden Ereignisfelder mit &quot;@&quot;referenziert und Datenquellenfelder mit &quot;#&quot;referenziert.

Eine Syntaxfarbe wird verwendet, um die Felder für Ereignisse (grün) von den Feldgruppen (blau) visuell zu unterscheiden.

**Standardwerte für Feldverweise**

Ein Standardwert kann mit einem Feldnamen verknüpft werden. Die Syntax lautet wie folgt:


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
>Der Feldtyp und der Standardwert müssen identisch sein. Beispiel: @{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue : 2} ist ungültig, da der Standardwert eine Ganzzahl ist, während der erwartete Wert eine Zeichenfolge sein sollte.

**Verweis auf ein Feld in Sammlungen**

Die in Sammlungen definierten Elemente werden mit den spezifischen Funktionen alle, zuerst und zuletzt referenziert. For more information, see [](../expression/collection-management-functions.md).

Beispiel :

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**Verweis auf ein Feld, das in einer Zuordnung** definiert ist. Um ein Element in einer Zuordnung abzurufen, verwenden wir die Eingabefunktion mit einem bestimmten Schlüssel. Sie wird beispielsweise beim Definieren des Schlüssels eines Ereignisses gemäß dem ausgewählten Namespace verwendet. Siehe Auswählen des Namespace. For more information, see [](../event/selecting-the-namespace.md).

```
@{MyEvent.identityMap.entry('Email').first().id}
```

In diesem Ausdruck erhalten wir den Eintrag für &quot;E-Mail&quot;-Schlüssel des Felds &quot;IdentityMap&quot; eines Ereignisses. Der Eintrag &quot;E-Mail&quot;ist eine Sammlung, aus der wir die &quot;ID&quot;im ersten Element mit &quot;first()&quot;nehmen. For more information, see [](../expression/collection-management-functions.md).

**Parameterwerte einer Datenquelle (dynamische Datenquellenwerte)**

Wenn Sie ein Feld aus einer externen Datenquelle auswählen, für das ein Parameter aufgerufen werden muss, wird rechts eine neue Registerkarte angezeigt, auf der Sie diesen Parameter angeben können. Näheres wird im Abschnitt [](../expression/expressionadvanced.md) beschrieben.

Bei komplexeren Anwendungsfällen können Sie, wenn Sie die Parameter der Datenquelle in den Hauptausdruck einbeziehen möchten, ihre Werte mithilfe der _Parameter_ mit Schlüsselwörtern definieren. Ein Parameter kann ein beliebiger gültiger Ausdruck sein, auch von einer anderen Datenquelle, die auch einen anderen Parameter enthält.

>[!NOTE]
>
>Wenn Sie die Parameterwerte im Ausdruck definieren, wird die Registerkarte auf der rechten Seite ausgeblendet.

Verwenden Sie die folgende Syntax:

```
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**: exakter Name des ersten Parameters aus der Datenquelle.
* **`<params-1-value>`**: der Wert des ersten Parameters. Es kann ein beliebiger gültiger Ausdruck sein.

Beispiel:

```
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
