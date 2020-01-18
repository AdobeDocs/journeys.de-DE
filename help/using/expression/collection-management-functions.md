---
title: Sammlungsverwaltungsfunktionen
description: Informationen zu Datentypen in Sammlungsverwaltungsfunktionen
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


# Sammlungsverwaltungsfunktionen {#collection-management-functions}

Die Ausdruckssprache bietet außerdem eine Reihe von Funktionen zum Abfragen von Sammlungen.

Diese Funktionen werden nachfolgend beschrieben. In den folgenden Beispielen verwenden wir die Ereignis-Nutzlast, die eine Sammlung enthält:

```
                { 
   "_experience":{ 
      "campaign":{ 
         "message":{ 
            "profile":{ 
               "pushNotificationTokens":[ 
                  { 
                     "token":"token_1",
                     "application":{ 
                        "_id":"APP1",
                        "name":"MarltonMobileApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_2",
                     "application":{ 
                        "_id":"APP2",
                        "name":"MarketplaceApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_3",
                     "application":{ 
                        "_id":"APP3",
                        "name":"VendorApp",
                        "version":"2.0"
                     }
                  }
               ]
            }
         }
      }
   },
   "timestamp":"1536160728"
}
```

**Die Funktion &quot;all(`<condition>`)&quot;**

Die Funktion **[!UICONTROL all]**ermöglicht die Definition eines Filters für eine bestimmte Sammlung mithilfe eines booleschen Ausdrucks.

```
<listExpression>.all(<condition>)
```

Unter allen App-Benutzern können Sie beispielsweise diejenigen mit IOS 13 abrufen (boolescher Ausdruck &quot;app used == IOS 13&quot;). Das Ergebnis dieser Funktion ist die gefilterte Liste mit Elementen, die dem booleschen Ausdruck entsprechen (Beispiel: App-Benutzer 1, App-Benutzer 34, App-Benutzer 432).

In einer Datenquellen-Bedingungsaktivität können Sie überprüfen, ob das Ergebnis der Funktion **[!UICONTROL all]**null ist. Sie können diese Funktion auch mit**[!UICONTROL  allen]** anderen Funktionen wie **[!UICONTROL Count]**kombinieren. Weitere Informationen finden Sie unter[Datenquellen-Bedingungsaktivität](../building-journeys/condition-activity.md#data_source_condition).

**Beispiel 1:**

Wir möchten überprüfen, ob ein Benutzer eine bestimmte Version einer Anwendung installiert hat. Hierfür erhalten wir alle Push-Benachrichtigungstoken, die mit mobilen Anwendungen verknüpft sind, für die die Version 1.0 ist. Dann führen wir eine Bedingung mit der Funktion **[!UICONTROL count]**aus, um zu überprüfen, ob die zurückgegebene Tokenliste mindestens ein Element enthält.

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

Das Ergebnis stimmt.

**Beispiel 2:**

Hier verwenden wir die Funktion **[!UICONTROL count]**, um zu überprüfen, ob in der Sammlung Push-Benachrichtigungstoken vorhanden sind.

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```

Das Ergebnis stimmt.

<!--Alternatively, you can check if there is no token in the collection:

   ```
   count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) == 0
   ```

The result will be false.

Here we use the count function in a condition to count the number of push notification tokens in the event.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token})`

The result is true.

Note that when the condition in the **all()** function is empty, the filter will return all the elements in the list. Hence, the expression above is equivalent to:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.application.name})`

In both cases, the result of the expression is **3**.

A query of experience events recorded on the platform may or may not include the current event that triggered the current Journey. This will depend on the relative processing time with which Journey Orchestration sees an event and started evaluating conditions, versus the time it takes for that event to be ingested into the platform. For example, when using the .all() syntax to query experience events from the platform, we recommend enforcing the exclusion of the current event (by requiring an
earlier timestamp) in order to only consider prior events.-->

>[!NOTE]
>
>Wenn die Filterbedingung in der Funktion **all()** leer ist, gibt der Filter alle Elemente in der Liste zurück. **Um jedoch die Anzahl der Elemente einer Sammlung zu zählen, ist die Funktion &quot;all&quot;nicht erforderlich.**


```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

Das Ergebnis des Ausdrucks ist **3**.

**Beispiel 3:**

Hier prüfen wir, ob eine Person innerhalb der letzten 24 Stunden keine Mitteilung erhalten hat. Wir filtern die Sammlung von Erlebnisereignissen, die aus der ExperiencePlatform-Datenquelle abgerufen werden, mit zwei Ausdrücken, die auf zwei Elementen der Sammlung basieren. Insbesondere wird der Zeitstempel des Ereignisses mit der von der Funktion **[!UICONTROL nowWithDelta]**zurückgegebenen dateTime verglichen.

```
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

Das Ergebnis lautet &quot;true&quot;(wahr), wenn kein Erlebnisereignis vorhanden ist, das den beiden Bedingungen entspricht.

**Beispiel 4:**

Hier möchten wir überprüfen, ob eine Person in den letzten 7 Tagen mindestens einmal eine Anwendung gestartet hat, um z.B. eine Push-Benachrichtigung auszulösen, in der sie eingeladen wird, ein Tutorial zu starten.

```
count(
 #{ExperiencePlatform.AnalyticsData.experienceevent.all(
 nowWithDelta(-7,"days") <= currentDataPackField.timestamp
 and currentDataPackField.application.firstLaunches.value > 0
)._id}) > 0
```


<!--**"All + Count" example 4:** here we use the count function in a boolean expression to see if there is push notification tokens in the collection.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) > 0`

The result will be:

`true`

Alternatively, you can check if there is NO token in the collection:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) =0`

The result will be:

`false`-->

>[!NOTE]
>
>**[!UICONTROL currentEventField]**ist nur verfügbar, wenn Ereignissammlungen und** currentDataPackField bearbeitet werden **>beim Bearbeiten von Datenquellen-Sammlungen. Bei der Verarbeitung von Sammlungen mit**[!UICONTROL  allen]**, **[!UICONTROL ersten]**und**[!UICONTROL  letzten]**, werden
>für jedes Element der Sammlung einzeln. **[!UICONTROL currentEventField]**und** currentDataPackField **>entsprechen dem Element, das in Schleife gestellt wird.

**Die Funktionen &quot;first(`<condition>`)&quot;und &quot;last(`<condition>`)&quot;**

Die **[!UICONTROL erste]**und die**[!UICONTROL  letzte]** Funktion ermöglichen auch die Definition eines Filters in der Sammlung, während das erste/letzte Element der Liste zurückgegeben wird, das dem Filter entspricht.

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**Beispiel 1:**

Dieser Ausdruck gibt das erste Push-Benachrichtigungstoken zurück, das mit mobilen Anwendungen verknüpft ist, für die die Version 1.0 gültig ist.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

Das Ergebnis ist &quot;token_1&quot;.

**Beispiel 2:**

Dieser Ausdruck gibt das letzte Push-Benachrichtigungstoken zurück, das mit mobilen Anwendungen verknüpft ist, für die die Version 1.0 gültig ist.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

Das Ergebnis ist &quot;token_2&quot;.

>[!NOTE]
>
>Die Erlebnisereignisse werden aus der Experience Platform in umgekehrter chronologischer Reihenfolge als Sammlung abgerufen. Daher:
>* **[!UICONTROL Die erste]**Funktion gibt das letzte Ereignis zurück
>* **[!UICONTROL last]**-Funktion gibt die älteste zurück.


**Beispiel 3:**

Wir prüfen, ob das erste (letzte) Adobe Analytics-Ereignis mit einem Wert ungleich null für DMA-ID den Wert 602 hat.

```
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**Die Funktion &quot;at(`<index>`)&quot;**

Mit der Funktion **[!UICONTROL at]**können Sie ein bestimmtes Element in einer Sammlung entsprechend einem Index referenzieren.
Index 0 ist der erste Index der Sammlung.

_`<listExpression>`.at(`<index>`)_

**Beispiel:**

Dieser Ausdruck gibt das zweite Token für die Push-Benachrichtigung der Liste zurück.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

Das Ergebnis ist &quot;token_2&quot;.