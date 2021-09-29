---
product: adobe campaign
solution: Journey Orchestration
title: Dynamisches Übergeben von Sammlungen mithilfe benutzerdefinierter Aktionen
description: Senden von Nachrichten mit Campaign v7/v8
exl-id: 8832d306-5842-4be5-9fb9-509050fcbb01
source-git-commit: 5fa7df4f2e778c0b0fd31d81edab34e86ee40c47
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 5%

---


# Dynamisches Übergeben von Sammlungen mithilfe benutzerdefinierter Aktionen{#passing-collection}

Sie können eine Sammlung in benutzerdefinierten Aktionsparametern übergeben, die zur Laufzeit dynamisch gefüllt werden. Es werden zwei Arten von Sammlungen unterstützt:

* einfache Sammlungen: Arrays einfacher Datentypen, z. B. mit einer listString:

   ```
   {
    "deviceTypes": [
        "android",
        "ios"
    ]
   }
   ```

* Objektsammlungen: ein Array von JSON-Objekten, z. B.:

   ```
   {
   "products":[
      {
         "id":"productA",
         "name":"A",
         "price":20.1
      },
      {
         "id":"productB",
         "name":"B",
         "price":10.0
      },
      {
         "id":"productC",
         "name":"C",
         "price":5.99
      }
    ]
   }
   ```

## Einschränkungen {#limitations}

* Arrays von Objekten, die Unterobjekte enthalten, werden nicht unterstützt. Beispiel:

   ```
   {
   "products":[
     {
        "id":"productA",
        "name":"A",
        "details": {
        "color":"blue"
        },
        "price":20.0
     }
    ]
   }
   ```

* Verschachtelte Arrays von Objekten in einem Objekt-Array werden derzeit nicht unterstützt. Beispiel:

   ```
   {
   "products":[
     {
        "id":"productA",
        "name":"A",
        "price":20,
        "locations": [{"name": "Paris"}, {"name": "London"}]
     },
    ]
   }
   ```
* Um Sammlungen im Testmodus zu testen, müssen Sie den Codeansichtsmodus verwenden. Der Codeansichtsmodus wird derzeit für Geschäftsereignisse nicht unterstützt. Sie können eine Sammlung nur mit einem einzelnen Element senden.

## Allgemeines Verfahren {#general-procedure}

In diesem Abschnitt verwenden wir das folgende JSON-Payload-Beispiel. Dies ist ein Array von Objekten mit einem Feld, das eine einfache Sammlung ist.

```
{
  "ctxt": {
    "products": [
      {
        "id": "productA",
        "name": "A",
        "price": 20.1,
        "color":"blue",
        "locations": [
          "Paris",
          "London"
        ]
      },
      {
        "id": "productB",
        "name": "B",
        "price": 10.99
      }
    ]
  }
}
```

Sie können sehen, dass &quot;products&quot;ein Array von zwei Objekten ist. Sie müssen mindestens ein Objekt haben.

1. Erstellen Sie Ihre benutzerdefinierte Aktion. Weitere Informationen finden Sie auf [dieser Seite](../action/about-custom-action-configuration.md).

1. Fügen Sie im Abschnitt **[!UICONTROL Aktionsparameter]** das JSON-Beispiel ein. Die angezeigte Struktur ist statisch: Beim Einfügen der Payload werden alle Felder als Konstanten definiert.

   ![](../assets/uc-collection-1.png)

1. Passen Sie bei Bedarf die Feldtypen an. Die folgenden Feldtypen werden für Sammlungen unterstützt: listString, listInteger, listDecimal, listBoolean, listDateTime, listDateTimeOnly, listDateOnly, listObject

   >[!NOTE]
   >
   >Der Feldtyp wird gemäß dem Payload-Beispiel automatisch abgeleitet.

1. Wenn Sie Objekte dynamisch übergeben möchten, müssen Sie sie als Variablen festlegen. In diesem Beispiel legen wir &quot;products&quot;als Variable fest. Alle im Objekt enthaltenen Objektfelder werden automatisch auf Variablen gesetzt.

   >[!NOTE]
   >
   >Das erste Objekt des Payload-Beispiels wird verwendet, um die Felder zu definieren.

1. Definieren Sie für jedes Feld den Titel, der auf der Journey-Arbeitsfläche angezeigt werden soll.

   ![](../assets/uc-collection-2.png)

1. Erstellen Sie Ihre Journey und fügen Sie die von Ihnen erstellte benutzerdefinierte Aktion hinzu. Weitere Informationen finden Sie auf [dieser Seite](../building-journeys/using-custom-actions.md).

1. Definieren Sie im Abschnitt **[!UICONTROL Aktionsparameter]** den Array-Parameter (&quot;products&quot; in unserem Beispiel) mithilfe des erweiterten Ausdruckseditors.

   ![](../assets/uc-collection-3.png)

1. Geben Sie für jedes der folgenden Objektfelder den entsprechenden Feldnamen aus dem Quell-XDM-Schema ein. Wenn die Namen identisch sind, ist dies nicht erforderlich. In unserem Beispiel müssen wir nur &quot;Produkt-ID&quot;und &quot;Farbe&quot;definieren.

   ![](../assets/uc-collection-4.png)

Für das Array-Feld können Sie auch den erweiterten Ausdruckseditor verwenden, um Datenmanipulationen durchzuführen. Im folgenden Beispiel werden die Funktionen [filter](https://git.corp.adobe.com/AdobeDocs/journeys.en/blob/fvi-21.9/help/using/functions/functionfilter.md) und [intersect](https://git.corp.adobe.com/AdobeDocs/journeys.en/blob/fvi-21.9/help/using/functions/functiontintersect.md) verwendet:

![](../assets/uc-collection-5.png)

## Besondere Fälle{#examples}

Bei heterogenen Typen und Arrays von Arrays wird das Array mit dem Typ listAny definiert. Sie können nur einzelne Elemente zuordnen, das Array jedoch nicht in eine Variable ändern.

![](../assets/uc-collection-heterogeneous.png)

Beispiel eines heterogenen Typs:

```
{
    "data_mixed-types": [
        "test",
        "test2",
        null,
        0
    ]
}
```

Beispiel eines Arrays von Arrays:

```
{
    "data_multiple-arrays": [
        [
            "test",
            "test1",
            "test2"
        ]
    ]
}
```

**Verwandte Themen**

[Verwenden benutzerdefinierter Aktionen](../building-journeys/using-custom-actions.md)