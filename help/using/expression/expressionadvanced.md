---
title: Informationen zum erweiterten Ausdruckseditor
description: Erfahren Sie, wie Sie erweiterte Ausdrücke erstellen
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


# Informationen zum erweiterten Ausdruckseditor {#concept_uyj_trt_52b}

Mit dem erweiterten Ausdruckseditor können Sie erweiterte Ausdrücke in verschiedenen Bildschirmen der Oberfläche erstellen, z. B. beim Definieren einer Datenquellenbedingung.
Sie steht auch immer dann zur Verfügung, wenn Sie Aktionsparameter definieren müssen, die bestimmte Datenmanipulation erfordern. Sie können Daten aus Ereignissen oder zusätzliche Informationen, die aus der Datenquelle abgerufen wurden, nutzen. Bei einer Reise ist die angezeigte Liste der Ereignisfelder kontextuell und variiert je nach Ereignis/Ereignissen, die während der Reise hinzugefügt werden.

Der erweiterte Ausdruckseditor bietet eine Reihe integrierter Funktionen und Operatoren, mit denen Sie Werte bearbeiten und einen Ausdruck definieren können, der Ihren Anforderungen entspricht. Mit dem erweiterten Ausdruckseditor können Sie auch die Werte des Parameters für die externe Datenquelle definieren, Zuordnungsfelder und Sammlungen, z. B. Erlebnisereignisse, bearbeiten.

![](../assets/journey65.png)

_Die Benutzeroberfläche des erweiterten Ausdrucks-Editors_

Der erweiterte Ausdruckseditor kann verwendet werden für:

* Erstellen [erweiterter Bedingungen](../building-journeys/condition-activity.md#about_condition) für Datenquellen und Ereignisinformationen
* Definieren benutzerdefinierter [Zeitzonen](../building-journeys/timezone-management.md) in Datumsbedingungen, Aktivitäten mit festem Datum und benutzerdefinierte Warteaktivitäten
* benutzerdefinierte [Warteaktivitäten definieren](../building-journeys/wait-activity.md#custom)
* Definieren der Aktionsparameter

Wenn möglich, können Sie zwischen den beiden Modi mit der Schaltfläche **[!UICONTROL Erweiterter Modus]**/**[!UICONTROL  Einfacher Modus]** wechseln. Der einfache Modus wird [hier](../building-journeys/condition-activity.md#about_condition)beschrieben.

>[!NOTE]
>
>Bedingungen können im einfachen oder erweiterten Ausdruckseditor definiert werden. Sie geben immer einen booleschen Typ zurück.
>
>Aktionsparameter können durch Auswahl von Feldern oder über den erweiterten Ausdruckseditor definiert werden. Sie geben einen bestimmten Datentyp gemäß ihrem Ausdruck zurück.

## Zugriff auf den erweiterten Ausdruckseditor {#section_fdz_4nj_cjb}

Sie können auf verschiedene Weise auf den erweiterten Ausdruckseditor zugreifen:

* Wenn Sie eine Datenquellenbedingung erstellen, können Sie auf den erweiterten Editor zugreifen, indem Sie auf **[!UICONTROL Erweiterter Modus]**klicken.

   ![](../assets/journeyuc2_33.png)

* Wenn Sie eine benutzerdefinierte Zeitzone oder einen benutzerdefinierten Timer erstellen, wird der erweiterte Editor direkt angezeigt.
* Wenn Sie den Aktionsparameter zuordnen, klicken Sie auf **[!UICONTROL Erweiterter Modus]**.

## Benutzeroberfläche{#section_otq_tnj_cjb}

In diesem Bildschirm können Sie Ihren Ausdruck manuell schreiben.

![](../assets/journey70.png)

Im linken Bildschirmbereich werden die verfügbaren Felder und Funktionen angezeigt:

* **[!UICONTROL Ereignisse]**: Wählen Sie eines der Felder aus, die vom Inbound-Ereignis empfangen wurden. Die angezeigte Liste der Ereignisfelder ist kontextuell und variiert je nach Ereignis/Ereignissen, die während der Reise hinzugefügt werden.
* **[!UICONTROL Datenquellen]**: Wählen Sie aus der Liste der verfügbaren Felder aus den Feldgruppen Ihrer Datenquellen.
* **[!UICONTROL Funktionen]**: Wählen Sie aus der Liste der integrierten Funktionen, die eine komplexe Filterung ermöglichen. Die Funktionen sind nach Kategorien geordnet.

![](../assets/journey65.png)

Ein automatischer Abschlussmechanismus zeigt kontextbezogene Vorschläge an.

![](../assets/journey68.png)

Ein Syntaxvalidierungsmechanismus überprüft die Integrität Ihres Codes. Fehler werden über dem Editor angezeigt.

![](../assets/journey69.png)

**Parameter beim Erstellen von Bedingungen mit dem erweiterten Ausdruckseditor erforderlich**

Wenn Sie ein Feld aus einer externen Datenquelle auswählen, für das ein Parameter aufgerufen werden muss (siehe [](../datasource/external-data-sources.md). Beispiel: In einer wetterbezogenen Datenquelle lautet ein häufig verwendeter Parameter &quot;city&quot;. Daher müssen Sie festlegen, wo Sie diesen Parameter &quot;city&quot;abrufen möchten. Funktionen können auch auf Parameter angewendet werden, um Formatänderungen oder Verkettungen durchzuführen.

![](../assets/journeyuc2_19.png)

Bei komplexeren Anwendungsfällen können Sie, wenn Sie die Parameter der Datenquelle in den Hauptausdruck aufnehmen möchten, ihre Werte mit dem Schlüsselwort &quot;params&quot;definieren. Siehe [diese Seite](../expression/field-references.md).
