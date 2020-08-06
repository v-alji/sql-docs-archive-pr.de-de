---
title: Planungs-Assistent (Data Mining-Add-Ins für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- forecasting [data mining]
- time series [data mining]
ms.assetid: c5b33f75-42d4-4598-89e7-94815c142ce6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8c3fae97bf1c36154d8ae378840014f2fb997afd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610174"
---
# <a name="forecast-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="7726b-102">Planungs-Assistent (Data Mining-Add-Ins für Excel)</span><span class="sxs-lookup"><span data-stu-id="7726b-102">Forecast Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="7726b-103">![Zuordnungs-Assistent (Data Mining-Menüband)](media/dmc-forecast.gif "Zuordnungs-Assistent (Data Mining-Menüband)")</span><span class="sxs-lookup"><span data-stu-id="7726b-103">![Associate wizard in Data Mining ribbon](media/dmc-forecast.gif "Associate wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="7726b-104">Mit dem Planungs-Assistenten können Sie Werte in einer Zeitreihe vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="7726b-104">The Forecast wizard helps you predict values in a time series.</span></span> <span data-ttu-id="7726b-105">Für den Planungs-Assistenten wird der [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series-Algorithmus verwendet. Es handelt sich dabei um einen Regressionsalgorithmus, der für die Vorhersage kontinuierlicher Spalten (z. B. Produktverkaufszahlen) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7726b-105">The Forecast wizard uses the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm, which is a regression algorithm for use in predicting continuous columns, such as product sales.</span></span>  
  
 <span data-ttu-id="7726b-106">Jedes Planungsmodell muss eine Fallreihe enthalten. Damit ist die Spalte gemeint, die zwischen Punkten in einer Sequenz unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="7726b-106">Each forecasting model must contain a case series, which is the column that distinguishes between points in a sequence.</span></span> <span data-ttu-id="7726b-107">Beispiel: Wenn Sie Vergangenheitsdaten verwenden, um Verkaufszahlen über mehrere Monate hinweg zu planen, würden Sie als Fallreihe eine Spalte mit einer Datenreihe verwenden.</span><span class="sxs-lookup"><span data-stu-id="7726b-107">For example, if you are using historical data to forecast sales over a period of several months, you would use a column containing a series of dates as the case series.</span></span>  
  
 <span data-ttu-id="7726b-108">Sie können anhand eines Planungsmodells Vorhersagen erstellen, ohne neue Eingabedaten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="7726b-108">You can create predictions from a forecasting model without providing new input data.</span></span>  
  
 <span data-ttu-id="7726b-109">Mit dem [Vorhersage &#40;Tabellenanalyse Tools für Excel&#41;](forecast-table-analysis-tools-for-excel.md) Tool können Sie im Menüband **analysieren** auch Vorhersagemodelle erstellen, die jedoch weniger anpassbar sind und nur Daten in Excel-Tabellen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="7726b-109">The [Forecast &#40;Table Analysis Tools for Excel&#41;](forecast-table-analysis-tools-for-excel.md) tool, in the **Analyze** ribbon, also lets you create forecasting models, but it is less customizable and can only use data in Excel tables.</span></span>  
  
## <a name="using-the-forecast-wizard"></a><span data-ttu-id="7726b-110">Verwenden des Planungs-Assistenten</span><span class="sxs-lookup"><span data-stu-id="7726b-110">Using the Forecast Wizard</span></span>  
  
1.  <span data-ttu-id="7726b-111">Klicken Sie im **Data Mining** -Menüband auf **Vorhersagen**.</span><span class="sxs-lookup"><span data-stu-id="7726b-111">In the **Data Mining** ribbon, click **Forecast**.</span></span>  
  
2.  <span data-ttu-id="7726b-112">Wählen Sie in den **Quelldaten auswählen**die Excel-Tabelle, den Bereich oder die externe Datenquelle aus, die als Eingaben verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7726b-112">In the **Select Source Data**, choose the Excel table, range, or external data source to use as inputs.</span></span>  
  
     <span data-ttu-id="7726b-113">Wenn Sie eine externe Datenquelle verwenden, können Sie benutzerdefinierte Sichten oder Abfragen definieren und als [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Datenquelle speichern.</span><span class="sxs-lookup"><span data-stu-id="7726b-113">If you use an external data source, you can define custom view or queries and save it as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source.</span></span>  
  
3.  <span data-ttu-id="7726b-114">Wählen Sie auf der Seite **vorher** sagen für **Zeitstempel**eine Spalte aus, die einen eindeutigen numerischen Wert (einschließlich Datums-und Uhrzeitwerte) enthält, die als Fallreihe verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7726b-114">On the **Forecasting** page, for **Time stamp**, select a column that contains unique numeric value (this includes date and time values) that can be used as the case series.</span></span> <span data-ttu-id="7726b-115">Die Datenquelle muss nach dieser Spalte in aufsteigender Reihenfolge sortiert sein.</span><span class="sxs-lookup"><span data-stu-id="7726b-115">The data source must be sorted in ascending order by this column.</span></span>  
  
     <span data-ttu-id="7726b-116">Wenn Ihre Daten nicht über eine solche Spalte verfügen, können Sie die Option verwenden \<no time stamp> .</span><span class="sxs-lookup"><span data-stu-id="7726b-116">If your data does not have such a column, you can use the option \<no time stamp>.</span></span> <span data-ttu-id="7726b-117">Der Assistent fügt eine eindeutige Sortierspalte für die Eingabedaten hinzu. Daher müssen Sie sicherstellen, dass die Daten wie gewünscht sortiert sind, bevor Sie den Assistenten ausführen und diese Option auswählen.</span><span class="sxs-lookup"><span data-stu-id="7726b-117">The wizard will add a unique order column for the input data; therefore, you must make sure that the data is sorted the way you want before running the wizard and choosing this option.</span></span>  
  
4.  <span data-ttu-id="7726b-118">Optional können Sie auf **Parameter** klicken und das Verhalten des Mining Modells anpassen.</span><span class="sxs-lookup"><span data-stu-id="7726b-118">Optionally, you can click **Parameters** and customize the behavior of the mining model.</span></span>  
  
     <span data-ttu-id="7726b-119">Planungsmodelle unterstützen verschiedene Algorithmen:</span><span class="sxs-lookup"><span data-stu-id="7726b-119">Forecasting models support several different algorithms:</span></span>  
  
    -   <span data-ttu-id="7726b-120">ARIMA</span><span class="sxs-lookup"><span data-stu-id="7726b-120">ARIMA</span></span>  
  
    -   <span data-ttu-id="7726b-121">ARTXP (Regressionsmodelltyp)</span><span class="sxs-lookup"><span data-stu-id="7726b-121">ARTXP (a type of regression model)</span></span>  
  
    -   <span data-ttu-id="7726b-122">ARTXP und ARIMA in Kombination</span><span class="sxs-lookup"><span data-stu-id="7726b-122">ARTXP and ARIMA combined</span></span>  
  
     <span data-ttu-id="7726b-123">Weitere Informationen zu den Unterschieden finden Sie unter [Technische Referenz für den Microsoft Time Series-Algorithmus](data-mining/microsoft-time-series-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="7726b-123">For information about the differences, see [Microsoft Time Series Algorithm Technical Reference](data-mining/microsoft-time-series-algorithm-technical-reference.md).</span></span>  
  
     <span data-ttu-id="7726b-124">Sie können außerdem Periodizitätshinweise hinzufügen, Glättungsoptionen angeben und Regressionsoptionen für das Modell anpassen.</span><span class="sxs-lookup"><span data-stu-id="7726b-124">You can also add periodicity hints, specify smoothing options, and customize regression options for the model.</span></span>  
  
5.  <span data-ttu-id="7726b-125">Geben Sie auf der Seite **Fertig** stellen einen beschreibenden Namen für das DataSet und das Modell an, und legen Sie die folgenden Optionen fest, mit denen die Arbeit mit dem fertigen Modell gesteuert wird:</span><span class="sxs-lookup"><span data-stu-id="7726b-125">On the **Finish** page, provide a descriptive name for your data set and model, and set the following options that control how you work with the finished model:</span></span>  
  
    -   <span data-ttu-id="7726b-126">**Modell durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="7726b-126">**Browse model**.</span></span> <span data-ttu-id="7726b-127">Wenn diese Option ausgewählt ist, wird das Fenster **Durchsuchen** geöffnet, sobald der Assistent die Verarbeitung des Modells abgeschlossen hat, damit Sie die Ergebnisse untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="7726b-127">When this option is selected, as soon as the wizard finishes processing the model, it opens a **Browse** window to help you explore the results.</span></span> <span data-ttu-id="7726b-128">Der Inhalt des Viewers hängt vom Typ des erstellten Modells ab.</span><span class="sxs-lookup"><span data-stu-id="7726b-128">The contents of the viewer depend on the type of model you built.</span></span> <span data-ttu-id="7726b-129">Weitere Informationen finden Sie unter durch [Suchen eines Vorhersagemodells](browsing-a-forecasting-model.md).</span><span class="sxs-lookup"><span data-stu-id="7726b-129">For more information, see [Browsing a Forecasting Model](browsing-a-forecasting-model.md).</span></span>  
  
    -   <span data-ttu-id="7726b-130">**Drillthrough aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="7726b-130">**Enable drillthrough**.</span></span> <span data-ttu-id="7726b-131">Wählen Sie diese Option aus, um die zugrunde liegenden Daten des fertigen Modells anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7726b-131">Select this option to view the underlying data from the finished model.</span></span> <span data-ttu-id="7726b-132">Diese Option ist nur verfügbar, wenn Sie ein Decision Tree-Modell erstellen.</span><span class="sxs-lookup"><span data-stu-id="7726b-132">This option is only available if you build a Decision Tree model.</span></span>  
  
    -   <span data-ttu-id="7726b-133">**Temporäres Modell verwenden**.</span><span class="sxs-lookup"><span data-stu-id="7726b-133">**Use temporary model**.</span></span> <span data-ttu-id="7726b-134">Wenn Sie diese Option auswählen, wird das Modell nicht auf dem Server gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7726b-134">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="7726b-135">Temporäre Modelle werden beim Schließen von Excel gelöscht.</span><span class="sxs-lookup"><span data-stu-id="7726b-135">Temporary models are deleted when you close Excel.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="7726b-136">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7726b-136">Requirements</span></span>  
 <span data-ttu-id="7726b-137">Die Daten sollten mindestens eine Spalte umfassen, die als Zeitreihe verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7726b-137">Your data should include at least one column that can be used as the time series.</span></span> <span data-ttu-id="7726b-138">Die Werte in dieser Spalte sollten eindeutig und fortlaufend sein, d. h., es sollten keine Lücken vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="7726b-138">The values in this column should be unique and continuous - that is, there should be no gaps.</span></span> <span data-ttu-id="7726b-139">Bevor Sie den Assistenten ausführen, sortieren Sie die Daten nach der Zeitreihenspalte in aufsteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="7726b-139">Before running the wizard, sort the data by the time series column in ascending order.</span></span>  
  
 <span data-ttu-id="7726b-140">Falls Ihre Daten keine Zeit- oder Datumsspalte enthalten, können Sie eine beliebige numerische Reihe zuweisen oder die Spalte vom Assistenten erstellen lassen.</span><span class="sxs-lookup"><span data-stu-id="7726b-140">If your data does not include a time or date column, you can assign an arbitrary numeric series, or let the wizard create one.</span></span> <span data-ttu-id="7726b-141">Wenn der Assistent die Reihensortierspalte erstellen soll, vergewissern Sie sich, dass die anderen Spalten in der gewünschten Reihenfolge sortiert sind, bevor Sie den Assistenten starten.</span><span class="sxs-lookup"><span data-stu-id="7726b-141">F you let the wizard create the series order column, make sure the other columns are sorted in the worder you want them before starting the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7726b-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7726b-142">See Also</span></span>  
 <span data-ttu-id="7726b-143">[Erstellen eines Data Mining-Modells](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="7726b-143">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 <span data-ttu-id="7726b-144">[Vorhersage &#40;Tabellenanalyse Tools für Excel&#41;](forecast-table-analysis-tools-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="7726b-144">[Forecast &#40;Table Analysis Tools for Excel&#41;](forecast-table-analysis-tools-for-excel.md) </span></span>  
 [<span data-ttu-id="7726b-145">Durchsuchen eines Planungsmodells</span><span class="sxs-lookup"><span data-stu-id="7726b-145">Browsing a Forecasting Model</span></span>](browsing-a-forecasting-model.md)  
  
  
