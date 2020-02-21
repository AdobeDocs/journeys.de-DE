---
title: Warteaktivität
description: Erfahren Sie mehr über die Warteaktivität
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
source-git-commit: 6274426ec04315149fb430b847498c0e20164bae

---


# Warteaktivität{#section_rlm_nft_dgb}

If you want to wait before executing the next activity in the path, you can use a **[!UICONTROL Wait]** activity. Sie können den Zeitpunkt festlegen, zu dem die nächste Aktivität ausgeführt wird. Es stehen vier Optionen zur Verfügung:

* [Dauer](#duration)
* [Festgelegtes Datum](#fixed_date)
* [Benutzerdefiniert](#custom)
* [Versandzeitoptimierung der E-Mail](#email_send_time_optimization)

## Informationen zur Warteaktivität{#about_wait}

Im Folgenden wird erläutert, wie die Wartezeiten priorisiert werden, wenn Sie mehrere Wartezeiten parallel verwenden. Wenn die Wartezeiten dieselbe Zeitkonfiguration und eine andere, aber überlappende Bedingung haben, wird die oben positionierte Wartezeit priorisiert. Die Bedingung der ersten Wartezeit ist zum Beispiel „ist eine Frau“ und die Bedingung der zweiten Wartezeit parallel dazu „ist ein VIP“. Die erste Warteaktivität wird priorisiert.

Beachten Sie auch, dass bei zwei parallelen Wartezeiten die zuerst auftretende unabhängig von ihrer vertikalen Position priorisiert wird. Wenn beispielsweise eine Wartezeit von 1 Stunde höher und eine Wartezeit von 30 Minuten niedriger positioniert ist, wird nach 30 Minuten die Wartezeit von 30 Minuten verarbeitet.

Sie können eine Bedingung definieren, wenn Sie die Wartezeit auf eine bestimmte Population beschränken möchten.

>[!NOTE]
>
>Die maximale Wartezeit beträgt 30 Tage.
>
>Im Testmodus werden alle Warteaktivitäten automatisch auf 5 Sekunden eingestellt. So können Sie schnell auf die Testergebnisse zugreifen.

## Wartezeit mit Dauer{#duration}

Wählen Sie die Dauer der Wartezeit vor der Ausführung der nächsten Aktivität aus.

![](../assets/journey55.png)

## Wartezeit mit festgelegtem Datum{#fixed_date}

Wählen Sie das Datum für die Ausführung der nächsten Aktivität aus. Wenn Sie ein festgelegtes Datum definieren, müssen Sie eine Zeitzone angeben. Siehe [](../building-journeys/timezone-management.md).

![](../assets/journey56.png)

## Benutzerdefinierte Wartezeit{#custom}

Mit dieser Option können Sie ein benutzerdefiniertes Datum definieren, z. B. den 12. Juli 2020 um 17 Uhr, wobei Sie einen erweiterten Ausdruck verwenden, der auf einem von einem Ereignis oder einer Datenquelle stammenden Feld basiert. Sie können keine benutzerdefinierte Dauer (z. B. 7 Tage) festlegen. Der Ausdruck im Ausdruckseditor sollte ein „dateTimeOnly“-Format aufweisen. Siehe [](../expression/expressionadvanced.md). Weitere Informationen zum „dateTimeOnly“-Format finden Sie unter [](../expression/data-types.md)

>[!NOTE]
>
>Sie können einen „dateTimeOnly“-Ausdruck nutzen oder eine Funktion zur Konvertierung in ein „dateTimeOnly“-Format verwenden. Beispiel: toDateTimeOnly(@{Event.offerOpened.activity.endTime}). Das Feld im Ereignis hat die folgende Form: 2016-08-12T09:46:06.
>
>Die **Zeitzone** wird an einer anderen Stelle im Konfigurationsbereich der benutzerdefinierten Wartezeit erwartet. Aus diesem Grund ist es heute nicht möglich, von der Oberfläche direkt auf eine Zeitstempelmischzeit nach ISO-8601 und einen Zeitzonenversatz (z. B. 2016-08-12T09:46:06.982-05) zu verweisen. Siehe [](../building-journeys/timezone-management.md).

![](../assets/journey57.png)

## Versandzeitoptimierung der E-Mail{#email_send_time_optimization}

>[!CAUTION]
>
>Die Funktion zur Versandzeitoptimierung der E-Mail steht nur Kunden zur Verfügung, die den Datendienst von Adobe Campaign Standard verwenden.

Diese Art des Wartens verwendet einen in der Plattform berechneten Wert. Der Wert berechnet basierend auf dem bisherigen Verhalten die Neigung, in Zukunft auf eine E-Mail zu klicken oder diese zu öffnen. Beachten Sie, dass der Algorithmus zur Berechnung des Werts eine bestimmte Datenmenge benötigt, um zu funktionieren. Wenn nicht genügend Daten vorhanden sind, wird die Standardwartezeit angewendet. Zum Zeitpunkt der Veröffentlichung wird Ihnen mitgeteilt, dass die Standardzeit gilt.

>[!NOTE]
>
>Das erste Ereignis Ihrer Journey muss über einen Namespace verfügen.
>
>Diese Funktion steht erst nach einer **[!UICONTROL Email]**-Aktivität zur Verfügung. Sie benötigen Adobe Campaign Standard.

1. In the **[!UICONTROL Amount of time]** field, define the number of hours to consider to optimize email sending.
1. In the **[!UICONTROL Optimization type]** field, choose if the optimization should increase clicks or opens.
1. Legen Sie im Feld **Standardzeit** die standardmäßige Wartezeit fest, wenn der Wert für die Versandzeitpunkt-Prognose nicht verfügbar ist.

   >[!NOTE]
   >
   >Beachten Sie, dass der Wert für den Versandzeitpunkt möglicherweise nicht verfügbar ist, da nicht genügend Daten für die Berechnung vorhanden sind. In diesem Fall werden Sie zum Zeitpunkt der Veröffentlichung darüber informiert, dass die Standardzeit gilt.

![](../assets/journey57bis.png)
