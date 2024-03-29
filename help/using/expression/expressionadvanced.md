---
product: adobe campaign
title: Informationen zum erweiterten Ausdruckseditor
description: Erfahren Sie, wie Sie erweiterte Ausdrücke erstellen
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: f6f0004d-8a33-4671-9c16-e56edfe2a45e
source-git-commit: f0cb883a09d553bb47491b750fabde54c92f3225
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 100%

---

# Informationen zum erweiterten Ausdruckseditor {#concept_uyj_trt_52b}

Verwenden Sie den erweiterten Ausdruckseditor, um in verschiedenen Bildschirmen der Benutzeroberfläche erweiterte Ausdrücke zu erstellen. Beispielsweise können Sie Ausdrücke erstellen, wenn Sie Journeys konfigurieren und verwenden oder eine Datenquellenbedingung definieren.
Der Editor steht auch immer dann zur Verfügung, wenn Sie Aktionsparameter definieren müssen, die eine bestimmte Datenbearbeitung erfordern. Sie können Daten aus den Ereignissen oder zusätzliche Informationen nutzen, die aus der Datenquelle abgerufen wurden. Bei einer Journey ist die angezeigte Liste der Ereignisfelder kontextuell und variiert je nach den Ereignissen, die in der Journey hinzugefügt werden.

Der erweiterte Ausdruckseditor bietet eine Reihe integrierter Funktionen und Operatoren, mit denen Sie Werte bearbeiten und einen Ausdruck definieren können, der Ihren Anforderungen entspricht. Mit dem erweiterten Ausdruckseditor können Sie auch die Werte des Parameters für die externe Datenquelle definieren sowie Zuordnungsfelder und Sammlungen (z. B. Erlebnisereignisse) bearbeiten.

![](../assets/journey65.png)

_Die Benutzeroberfläche des erweiterten Ausdruckseditors_

Der erweiterte Ausdruckseditor kann für folgende Aufgaben verwendet werden:

* Erstellen von [erweiterten Bedingungen](../building-journeys/condition-activity.md#about_condition) für Datenquellen und Ereignisinformationen
* Definieren von benutzerdefinierten [Warteaktivitäten](../building-journeys/wait-activity.md#custom)
* Definieren der Zuordnung von Aktionsparametern

Wenn möglich, können Sie mit der Schaltfläche **[!UICONTROL Erweiterter Modus]**/**[!UICONTROL Einfacher Modus]** zwischen den beiden Modi wechseln. Der einfache Modus wird [hier](../building-journeys/condition-activity.md#about_condition) beschrieben.

>[!NOTE]
>
>Bedingungen können im einfachen oder erweiterten Ausdruckseditor definiert werden. Sie geben stets einen booleschen Typ zurück.
>
>Aktionsparameter können durch Auswahl von Feldern oder über den erweiterten Ausdruckseditor definiert werden. Sie geben je nach Ausdruck einen bestimmten Datentyp zurück.

## Zugreifen auf den erweiterten Ausdruckseditor {#section_fdz_4nj_cjb}

Sie können den erweiterten Ausdruckseditor auf verschiedene Weise aufrufen:

* Wenn Sie eine Bedingung der Datenquelle erstellen, können Sie den erweiterten Ausdruckseditor nutzen, indem Sie auf **[!UICONTROL Erweiterter Modus]** klicken.

  ![](../assets/journeyuc2_33.png)

* Wenn Sie einen benutzerdefinierten Timer erstellen, wird der erweiterte Editor direkt angezeigt.
* Wenn Sie Aktionsparameter zuordnen, klicken Sie auf **[!UICONTROL Erweiterter Modus]**.

## Kennenlernen der Benutzeroberfläche{#section_otq_tnj_cjb}

In diesem Bildschirm können Sie Ihren Ausdruck manuell schreiben.

![](../assets/journey70.png)

Im linken Bildschirmbereich werden die verfügbaren Felder und Funktionen angezeigt:

* **[!UICONTROL Ereignisse]**: Wählen Sie eines der Felder aus, die vom eingehenden Ereignis empfangen wurden. Die angezeigte Liste der Ereignisfelder ist kontextuell und variiert je nach Ereignissen, die in der Journey hinzugefügt werden. [Weitere Informationen](../event/about-events.md)
* **[!UICONTROL Segmente]**: Wenn Sie ein Ereignis vom Typ **[!UICONTROL Segmentqualifizierung]** abgelegt haben, wählen Sie das Segment aus, das Sie in Ihrem Ausdruck verwenden möchten. [Weitere Informationen](../segment/using-a-segment.md)
* **[!UICONTROL Datenquellen]**: Wählen Sie aus der Liste der Felder, die in den Feldergruppen Ihrer Datenquellen verfügbar sind. [Weitere Informationen](../datasource/about-data-sources.md)
* **[!UICONTROL Journey-Eigenschaften]**: In diesem Abschnitt werden die technischen Felder der Journey für ein bestimmtes Profil zusammengefasst. [Weitere Informationen](../expression/journey-properties.md)
* **[!UICONTROL Funktionen]**: Wählen Sie aus der Liste der integrierten Funktionen, die eine komplexe Filterung ermöglichen. Die Funktionen sind nach Kategorien geordnet. [Weitere Informationen](../expression/functions.md)

![](../assets/journey65.png)

Ein Mechanismus für die automatische Vervollständigung zeigt kontextuelle Vorschläge an.

![](../assets/journey68.png)

Ein Syntaxvalidierungsverfahren überprüft die Integrität Ihres Codes. Fehler werden über dem Editor angezeigt.

![](../assets/journey69.png)

**Bedarf an Parametern beim Erstellen von Bedingungen mit dem erweiterten Ausdruckseditor**

Wenn Sie ein Feld aus einer externen Datenquelle auswählen, für das ein Parameter aufgerufen werden muss, siehe [diese Seite](../datasource/external-data-sources.md). Beispiel: In einer wetterbezogenen Datenquelle lautet ein häufig verwendeter Parameter „city“. Darum müssen Sie festlegen, wo Sie diesen Parameter „city“ abrufen möchten. Funktionen können auch auf Parameter angewendet werden, um Formatänderungen oder Verkettungen vorzunehmen.

![](../assets/journeyuc2_19.png)

Bei komplexeren Anwendungsfällen können Sie, wenn Sie die Parameter der Datenquelle in den Hauptausdruck aufnehmen möchten, deren Werte mit dem Keyword „params“ definieren. Weitere Informationen finden Sie auf [dieser Seite](../expression/field-references.md).
