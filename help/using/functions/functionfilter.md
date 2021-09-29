---
product: adobe campaign
title: filter
description: Informationen zum Funktionsfister
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 729ee71e063ae73c7c10f20bb3a410c43cb75faf
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 15%

---

# filter{#filter}

Gibt ein listObject mit Objekten zurück, deren Schlüsselattribut einem der angegebenen Schlüsselwerte entspricht.

## Kategorie

Liste

## Funktionssyntax

`filter(<parameters>)`

## Parameter

| Parameter | Typ | Beschreibung |
|-----------|------------------|------------------|
| listToFilter | listObject | Liste der zu filternden Objekte. Es muss sich um einen Feldverweis handeln. |
| keyAttributeName | Zeichenfolge | Attributname in den Objekten der angegebenen Liste, der als Schlüssel für die Filterung verwendet wird |
| keyValueList | list | Array von Schlüsselwerten zum Filtern |

## Signaturen und zurückgegebene Typen

`filter(listObject, string, listString)`

`filter(listObject, string, listInteger)`

`filter(listObject, string, listDecimal)`

`filter(listObject, string, listDateTime)`

`filter(listObject, string, listDateTimeOnly)`

`filter(listObject, string, listDateOnly)`

`filter(listObject, string, listDuration)`

`filter(listObject, string, listBoolean)`

Gibt ein listObject zurück.

## Beispiele

Im Folgenden finden Sie ein Beispiel einer Payload, die an ein eingehendes Ereignis &quot;myevent&quot;übergeben wird:

```
"productListItems": [{
   "id": "product1",
   "name": "the product 1",
   "price": 20
},{
   "id": "product2",
   "name": "the product 2",
   "price": 30
},{
   "id": "product3",
   "name": "the product 3",
   "price": 50
}]
```

Sie können den folgenden Ausdruck verwenden:

```
filter(
 @{myevent.productListItems},
 id", 
 ["product2", "product3", "product4"]
)
```

Gibt ein listObject zurück, das die beiden Objekte mit &quot;product2&quot;und &quot;product3&quot;als ID enthält.
