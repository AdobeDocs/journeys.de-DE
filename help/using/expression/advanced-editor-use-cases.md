---
title: Verwenden des erweiterten Ausdruckseditors
description: Erfahren Sie, wie Sie erweiterte Ausdrücke erstellen
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: benzaama
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 100%

---


# Verwenden des erweiterten Ausdruckseditors

Der erweiterte Ausdruckseditor kann verwendet werden, um Bedingungen zum Filtern von Benutzern in Ihren Journeys zu erstellen. Mit diesen Bedingungen können Sie Benutzer nach Uhrzeit, Datum, Ort, Dauer oder Aktionen wie Kauf oder Warenkorbabbruch ansprechen, damit diese in der Journey erneut angesprochen werden können.

>[!NOTE]
>
>Ereignisse beginnen mit @, Datenquellen mit #.

## Erstellen von Bedingungen anhand von Erlebnisereignissen

Sie benötigen den erweiterten Ausdruckseditor, um Abfragen zu Zeitreihen wie eine Liste der Käufe oder vergangene Klicks auf Nachrichten durchzuführen. Solche Abfragen können nicht mit dem einfachen Editor ausgeführt werden.

Die Erlebnisereignisse werden von Adobe Experience Platform als Sammlung in umgekehrter chronologischer Reihenfolge abgerufen. Entsprechend gilt:

* Die Funktion &quot;first&quot; gibt das neueste Ereignis zurück.
* Die Funktion &quot;last&quot; gibt das älteste zurück.

Angenommen, Sie möchten Kunden mit einem Warenkorbabbruch in den letzten sieben Tagen ansprechen. Dazu möchten Sie diesen Kunden, wenn sie sich in der Nähe eines Stores befinden, eine Nachricht mit einem Angebot für Artikel in diesem Store senden, an denen die Kunden interessiert sind.

**Erstellen Sie dazu die folgenden Bedingungen:**

Sprechen Sie in erster Linie Kunden an, die den Online-Store besucht, aber in den letzten sieben Tagen keine Bestellung abgeschlossen haben.

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**Dieser Ausdruck sucht nach allen Ereignissen für diesen Benutzer, die in den letzten sieben Tagen spezifiziert wurden:**

Anschließend werden alle Ereignisse vom Typ addtocart ausgewählt, die nicht in completePurchase umgewandelt wurden.

>[!NOTE]
>
>Um Felder schnell in den Ausdruck einzufügen, doppelklicken Sie auf das Feld im linken Bereich des Editors.

Der angegebene Zeitstempel dient als Datums- und Uhrzeitwert, der zweite als Anzahl von Tagen.

    ```
    In( “addToCart”, #{ExperiencePlatformDataSource
    .ExperienceEventFieldGroup
    .experienceevent
    .all(
    inLastDays(currentDataPackField.timestamp, 7 ))
    .productData
    .productInteraction})
    And
    Not(In( “completePurchase”, #{ExperiencePlatformDataSource
    .ExperienceEventFieldGroup
    .experienceevent
    .all(
    inLastDays(currentDataPackField.timestamp, 7 ))
    .productData
    .productInteraction})
    
    ```

Dieser Ausdruck gibt einen booleschen Wert zurück.

**Erstellen Sie nun einen Ausdruck, der überprüft, ob das Produkt vorrätig ist**

* Dieser Ausdruck such im Inventar nach dem Mengenfeld eines Produkts mit der Angabe, dass es größer als 0 sein soll.

`#{Inventory.fieldgroup3.quantity} > 0`

* Rechts werden die erforderlichen Werte angegeben. Hier müssen wir den Ort des Stores abrufen, der der Position des Ereignisses &quot;ArriveLumaStudio&quot; zugeordnet ist:

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* Geben Sie die SKU unter Verwendung der `first`-Funktion an, um die jüngste &quot;addToCart&quot; -Interaktion abzurufen:

   ```
       #{ExperiencePlatformDataSource
                       .ExperienceEventFieldGroup
                       .experienceevent
                       .first(
                       currentDataPackField
                       .productData
                       .productInteraction == “addToCart”
                       )
                       .SKU}
   ```

Von dort können Sie einen weiteren Pfad zu Ihrer Journey hinzufügen, wenn das Produkt nicht im Store ist, und eine Benachrichtigung mit einem Interaktionsangebot senden. Konfigurieren Sie die Nachrichten entsprechend und verwenden Sie Personalisierungsdaten, um die Nachricht zu verbessern.

## Beispiele für Zeichenfolgenmanipulationen mit dem erweiterten Ausdruckseditor

**In Bedingungen**

Diese Bedingung ruft nur die Geofence-Ereignisse ab, die in &quot;Arlington&quot; ausgelöst wurden:

    ```
    @{GeofenceEntry
    .placeContext
    .POIinteraction
    .POIDetail
    .name} == &quot;Arlington&quot;
    ```

Erklärung: Dies ist ein strikter Zeichenfolgenvergleich (Groß-/Kleinschreibung beachten), der einer Abfrage im einfachen Modus entspricht, die `equal to` mit der aktivierten Option `Is sensitive` verwendet.

Die gleiche Abfrage mit der deaktivierten Option `Is sensitive` generiert den folgenden Ausdruck im erweiterten Modus:

    ```
    equalIgnoreCase(@{GeofenceEntry
    .placeContext
    .POIinteraction
    .POIDetail
    .name}, &quot;Arlington&quot;)
    
    ```

**In Aktionen**

Mit dem folgenden Ausdruck können Sie die CRM-ID in einem Feld zur Aktionspersonalisierung definieren:

    ```
    substr(@{MobileAppLaunch
    ._myorganization
    .identification
    .crmid}, 1,
    lastIndexOf(@{MobileAppLaunch
    ._myorganization
    .identification
    .crmid}
    }
    ))
    
    ```

Erläuterung: In diesem Beispiel werden die `substr`- und `lastIndexOf`-Funktionen verwendet, um geschweifte Klammern zu entfernen, die die CRM-ID einschließen, die bei einem App-Startereignis übergeben wurde.

Weitere Informationen zur Verwendung des erweiterten Ausdruckseditors finden Sie in [diesem Video](https://docs.adobe.com/content/help/de-DE/journey-orchestration-learn/tutorials/create-a-journey.html).
