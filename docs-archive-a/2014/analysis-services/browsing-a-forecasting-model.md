---
title: Durchsuchen eines Vorhersagemodells | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- forecasting [data mining]
- mining models, viewing
- mining model, time series
- time series [data mining]
ms.assetid: ad35a528-1949-4048-8678-3b9760c1c88c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7d0b188c4ed6fba9bc5b1082725b17c99081c1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610315"
---
# <a name="browsing-a-forecasting-model"></a><span data-ttu-id="4ade7-102">Durchsuchen eines Planungsmodells</span><span class="sxs-lookup"><span data-stu-id="4ade7-102">Browsing a Forecasting Model</span></span>
  <span data-ttu-id="4ade7-103">Wenn Sie ein Vorhersagemodell mithilfe von **Durchsuchen**öffnen, wird das Modell in einem interaktiven Viewer angezeigt, der dem Zeitreihen Modell-Viewer in ähnelt [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4ade7-103">When you open a forecasting model using **Browse**, the model is displayed in an interactive viewer, similar to the time series model viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="4ade7-104">Mithilfe des Viewers können Sie Trends untersuchen, Reihen vergleichen, Vorhersagen erstellen und Informationen zum Modell und zu den zugrunde liegenden Daten abrufen.</span><span class="sxs-lookup"><span data-stu-id="4ade7-104">The viewer helps you explore trends, compare series, create predictions, and get information about the model and the underlying data.</span></span>  
  
##  <a name="explore-the-model"></a><a name="bkmk_Top"></a><span data-ttu-id="4ade7-105">Untersuchen des Modells</span><span class="sxs-lookup"><span data-stu-id="4ade7-105">Explore the Model</span></span>  
 <span data-ttu-id="4ade7-106">Der **Such Viewer für** Vorhersagemodelle bietet eine Diagramm Ansicht, in der die Trends im Laufe der Zeit angezeigt werden, und Sie können Vorhersagen erstellen, und eine Modell Ansicht, die die Zeitreihe als Entscheidungsstruktur oder Regressions Struktur darstellt.</span><span class="sxs-lookup"><span data-stu-id="4ade7-106">The **Browse** viewer for forecasting models provides a chart view, which shows the trends over time and lets you create predictions, and a model view, which represents the time series as a decision tree or a regression tree.</span></span>  
  
-   [<span data-ttu-id="4ade7-107">Diagrammansicht</span><span class="sxs-lookup"><span data-stu-id="4ade7-107">Chart view</span></span>](#bkmk_charts)  
  
-   [<span data-ttu-id="4ade7-108">Modellansicht</span><span class="sxs-lookup"><span data-stu-id="4ade7-108">Model view</span></span>](#bkmk_Model)  
  
 <span data-ttu-id="4ade7-109">Um mit einem Vorhersagemodell zu experimentieren, können Sie die Beispiel Daten auf der Registerkarte "vorhersagen" der Beispiel Daten-Arbeitsmappe verwenden und ein Zeitreihen Modell mithilfe des Planungs- [Assistenten &#40;Data Mining-Add-Ins für Excel&#41;](forecast-wizard-data-mining-add-ins-for-excel.md) im **Data Mining** -Menüband erstellen oder [&#40;Tabellenanalyse Tools für Excel&#41;](forecast-table-analysis-tools-for-excel.md) auf dem Menüband **analysieren** erstellen.</span><span class="sxs-lookup"><span data-stu-id="4ade7-109">To experiment with a forecasting model, you can use the sample data on the Forecast tab of the sample data workbook, and build a time series model using the [Forecast Wizard &#40;Data Mining Add-ins for Excel&#41;](forecast-wizard-data-mining-add-ins-for-excel.md) in the **Data Mining** ribbon, or [Forecast &#40;Table Analysis Tools for Excel&#41;](forecast-table-analysis-tools-for-excel.md) in the **Analyze** ribbon.</span></span>  
  
###  <a name="chart"></a><a name="bkmk_charts"></a><span data-ttu-id="4ade7-110">Fluss</span><span class="sxs-lookup"><span data-stu-id="4ade7-110">Chart</span></span>  
 <span data-ttu-id="4ade7-111">Die Registerkarte **Diagramm** zeigt den Trend in der Datenreihe im Laufe der Zeit sowie die vorhergesagten Werte an.</span><span class="sxs-lookup"><span data-stu-id="4ade7-111">The **Chart** tab displays the trend in your data series over time, together with the predicted values.</span></span> <span data-ttu-id="4ade7-112">Die vertikale Achse des Diagramms stellt die Werte der Reihe dar, und die horizontale Achse stellt die Zeit dar.</span><span class="sxs-lookup"><span data-stu-id="4ade7-112">The vertical axis of the chart represents the values of the series, and the horizontal axis represents time.</span></span>  
  
##### <a name="explore-the-forecasting-chart"></a><span data-ttu-id="4ade7-113">Untersuchen des Prognosediagramms</span><span class="sxs-lookup"><span data-stu-id="4ade7-113">Explore the forecasting chart</span></span>  
  
1.  <span data-ttu-id="4ade7-114">Dieses Modell enthält mehrere Zeitreihen. Um das Diagramm jedoch zu vereinfachen, können Sie eine einzelne Reihe oder nur wenige aufeinander bezogene Reihen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4ade7-114">This model contains multiple time series, but to simplify the chart, you can display a single series, or just a few related series.</span></span>  
  
     <span data-ttu-id="4ade7-115">![Vergangenheitsvorhersagen im Prognosemodell](media/dm13-forecast-chart-historicpredictions.gif "Vergangenheitsvorhersagen im Prognosemodell")</span><span class="sxs-lookup"><span data-stu-id="4ade7-115">![historical predictions in the forecasting model](media/dm13-forecast-chart-historicpredictions.gif "historical predictions in the forecasting model")</span></span>  
  
     <span data-ttu-id="4ade7-116">Verwenden Sie die Kontrollkästchen, um die Vorhersage nur für Nordamerika oder nur für die Verkaufsmenge auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="4ade7-116">Use the check boxes to select the forecast for just North America, and just for sales Amount.</span></span>  
  
2.  <span data-ttu-id="4ade7-117">Klicken Sie auf **Vorhersage Schritte** , und geben Sie einen neuen Wert ein, um zu steuern, wie viele zukünftige Zeit Werte im Diagramm angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4ade7-117">Click **Prediction Steps** and type a new value to control how many future time values you want to see in the chart.</span></span>  
  
     <span data-ttu-id="4ade7-118">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="4ade7-118">The default is 5.</span></span>  
  
3.  <span data-ttu-id="4ade7-119">Klicken Sie auf einen beliebigen Punkt in der Zeile (Verlauf oder Zukunft), um die genauen Werte für diesen Zeitpunkt anzuzeigen, die in der **Mining Legende**angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4ade7-119">Click any point in the line, either historical or future, to see the exact values for that point in time, displayed in the **Mining Legend**.</span></span>  
  
4.  <span data-ttu-id="4ade7-120">Im Diagramm werden Vergangenheits- und Zukunftsdaten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4ade7-120">The chart displays both historical and future data.</span></span> <span data-ttu-id="4ade7-121">Beachten Sie die gepunktete Linie mit einem schattierten Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="4ade7-121">Note the dotted line, with a shaded background.</span></span> <span data-ttu-id="4ade7-122">Diese Werte sind die künftigen Vorhersagen, die auf dem Modell basieren.</span><span class="sxs-lookup"><span data-stu-id="4ade7-122">These values are the future predictions, based on the model.</span></span>  
  
     <span data-ttu-id="4ade7-123">Die Vergangenheitsdaten (mit denen Sie das Modell erstellt haben) werden auf der linken Seite des Diagramms angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4ade7-123">The historical data (which you used to build the model) is shown in the left side of the chart.</span></span>  
  
5.  <span data-ttu-id="4ade7-124">Wählen Sie die Option **historische Vorhersagen anzeigen** aus, um einen Sinn für die Stabilität der Zeitreihe zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4ade7-124">Select the **Show historic predictions** option to get a sense for the stability of the time series.</span></span>  
  
     <span data-ttu-id="4ade7-125">![Prognosen für eine einzelne Reihe im Modell](media/dm13-forecast-chart-singleseries.gif "Prognosen für eine einzelne Reihe im Modell")</span><span class="sxs-lookup"><span data-stu-id="4ade7-125">![forecasts for a single series in the model](media/dm13-forecast-chart-singleseries.gif "forecasts for a single series in the model")</span></span>  
  
     <span data-ttu-id="4ade7-126">Vergangene Vorhersagen sind Werte, die basierend auf der Reihe bis zum entsprechenden Zeitpunkt vorhergesagt wurden und die mit tatsächlichen Vergangenheitswerten verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="4ade7-126">Historical predictions are values predicted based on the series to that point, which are compared to actual historical values.</span></span> <span data-ttu-id="4ade7-127">Wenn die gepunktete Linie (mit den vorhergesagten Werten) weit von der durchgezogenen Linie (die tatsächlichen Werte) entfernt ist, bedeutet das, dass der erste Teil der Reihe die späteren Werte vielleicht nicht genau vorhersagt.</span><span class="sxs-lookup"><span data-stu-id="4ade7-127">If the dotted line (with the predicted values) is far apart from the solid line (the actual values), it means the first part of the series perhaps does not accurately predict the later values.</span></span> <span data-ttu-id="4ade7-128">Möglicherweise sind mehr Daten erforderlich, oder es könnte lediglich ein Hinweis auf die Flüchtigkeit im Zyklus sein.</span><span class="sxs-lookup"><span data-stu-id="4ade7-128">You might need more data, or it might simply be an indicator of volatility in the cycle.</span></span>  
  
6.  <span data-ttu-id="4ade7-129">Wählen Sie die Option **Abweichungen anzeigen** aus, um Fehlerindikatoren im Diagramm anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4ade7-129">Select the **Show Deviations** option to display error bars in the chart.</span></span>  
  
     <span data-ttu-id="4ade7-130">Mithilfe der Fehlerindikatoren können Sie die Variabilität der Vorhersagen visuell bewerten.</span><span class="sxs-lookup"><span data-stu-id="4ade7-130">The error bars let you visually assess the variability of the predictions.</span></span> <span data-ttu-id="4ade7-131">Die Qualität der Vorhersagen hängt von den Quelldaten ab. Wenn Sie die Anzahl der Vorhersageschritte erhöhen, sollten Sie jedoch einen stetigen Anstieg der Abweichungen feststellen.</span><span class="sxs-lookup"><span data-stu-id="4ade7-131">The quality of predictions varies depending on your source data, but as you increase the number of prediction steps, you should see the deviations steadily increase.</span></span>  
  
 <span data-ttu-id="4ade7-132">**Tipps**</span><span class="sxs-lookup"><span data-stu-id="4ade7-132">**Tips**</span></span>  
  
-   <span data-ttu-id="4ade7-133">Zum Umschalten der Anzeige der **Mining Legende**klicken Sie mit der rechten Maustaste auf einen beliebigen Punkt im Diagramm.</span><span class="sxs-lookup"><span data-stu-id="4ade7-133">To toggle display of the **Mining Legend**, right-click any point in the chart.</span></span>  
  
     <span data-ttu-id="4ade7-134">Sie können einen bestimmten Zeitbereich anzeigen, indem Sie auf das Diagramm klicken, eine Zeitauswahl über das Diagramm ziehen und dann durch erneutes Klicken den ausgewählten Bereich vergrößern.</span><span class="sxs-lookup"><span data-stu-id="4ade7-134">You can view a specific time range by clicking the chart, dragging a time selection across the chart, and then clicking again to zoom in on the selected range.</span></span>  
  
-   <span data-ttu-id="4ade7-135">Um eine Kopie des aktuellen Diagramms zu erhalten, klicken Sie auf **nach Excel kopieren**, und klicken Sie dann auf ein Arbeitsblatt in Excel.</span><span class="sxs-lookup"><span data-stu-id="4ade7-135">To get a copy of the current chart, click **Copy to Excel**, then click a worksheet in Excel.</span></span> <span data-ttu-id="4ade7-136">Im Arbeitsblatt wird eine Grafik mit allen festgelegten Optionen eingefügt, einschließlich einer Legende.</span><span class="sxs-lookup"><span data-stu-id="4ade7-136">A graphic is inserted in the sheet using all the options you had set, including a legend.</span></span>  
  
     <span data-ttu-id="4ade7-137">Diese Grafik ist jedoch statisch, sodass Sie die Legende nicht bearbeiten oder die zugrunde liegenden Daten anzeigen können. Wenn Sie eine interaktive Diagramm Ansicht benötigen, verwenden Sie die [Visio-Viewer](viewing-data-mining-models-in-visio-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="4ade7-137">However, this graphic is static so you cannot edit the legend or view the underlying data; if you need a more interactive chart view, use the [Visio viewers](viewing-data-mining-models-in-visio-data-mining-add-ins.md).</span></span>  
  
-   <span data-ttu-id="4ade7-138">Klicken Sie in der Viewer-Menüleiste auf **ABS** , um zwischen absoluten und relativen Kurven zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="4ade7-138">Click **Abs** in the viewer menu bar to toggle between absolute and relative curves.</span></span>  
  
     <span data-ttu-id="4ade7-139">Diese Option ist nützlich, falls das Diagramm mehrere Modelle enthält, die Skalierung der Daten der einzelnen Modelle sich jedoch erheblich unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="4ade7-139">This option is useful if your chart contains multiple models, but the scale of the data for each model is very different.</span></span>  
  
     <span data-ttu-id="4ade7-140">Wenn zum Beispiel die Geschäfte in der Pazifikregion neu sind und wenig Verkäufe verzeichnen, und wenn absolute Werte verwendet werden, wird die Linie, die die Verkäufe der Pazifikregion darstellt, möglicherweise flach dargestellt und tatsächliche Änderungen sind nur schwer erkennbar. Die anderen Modelle würden in diesem Fall jedoch mit einer stärker normalisierten Skalierung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4ade7-140">For example, if the Pacific region stores were new and sales were low, and if absolute values are used, the line showing Pacific sales might appear flat, making it difficult to see actual changes, whereas the other models would be displayed at a more normal scale.</span></span>  
  
     <span data-ttu-id="4ade7-141">Durch den Wechsel zur Anzeige mit relativen Werten können Sie die Skalierung verschiedener Modelle normalisieren und Unterschiede als Änderungsprozentsatz anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4ade7-141">By switching the view to use relative values, you can normalize the scale of different models, and display differences as a percent of change.</span></span> <span data-ttu-id="4ade7-142">Wenn Änderungen für jedes Modell relativ sind, können diese ohne signifikante Verzerrung in demselben Diagramm angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4ade7-142">When change is relative to each model, they can be displayed in the same graph without significant distortion.</span></span>  
  
 [<span data-ttu-id="4ade7-143">Untersuchen des Modells</span><span class="sxs-lookup"><span data-stu-id="4ade7-143">Explore the Model</span></span>](#bkmk_Top)  
  
###  <a name="model"></a><a name="bkmk_Model"></a><span data-ttu-id="4ade7-144">Modells</span><span class="sxs-lookup"><span data-stu-id="4ade7-144">Model</span></span>  
 <span data-ttu-id="4ade7-145">Ein Planungsmodell kann auch als Entscheidungsstruktur oder, bei einer größtenteils linearen Reihe, als Regressionsmodell dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4ade7-145">A forecasting model can also be represented as a decision tree, or, if the series is mostly linear, a regression model.</span></span>  
  
 <span data-ttu-id="4ade7-146">In diesem Modell liegt zum Beispiel basierend auf einer bestimmten Bedingung ein Unterschied in der Regressionsformel vor, sodass die Struktur in zwei Verzweigungen mit einer jeweils unterschiedlichen Regressionsformel aufgeteilt wird.</span><span class="sxs-lookup"><span data-stu-id="4ade7-146">For example, in this model, there is a difference in the regression formula based on a certain condition, so the tree splits into two branches, each with a different regression formula.</span></span>  
  
 <span data-ttu-id="4ade7-147">![Filtern einer einzelnen Reihe im Prognosemodell](media/dm13-forecast-model-northamerica.gif "Filtern einer einzelnen Reihe im Prognosemodell")</span><span class="sxs-lookup"><span data-stu-id="4ade7-147">![Filter single series in the forecasting model](media/dm13-forecast-model-northamerica.gif "Filter single series in the forecasting model")</span></span>  
  
##### <a name="explore-the-forecasting-model-as-a-tree"></a><span data-ttu-id="4ade7-148">Untersuchen des Prognosemodells als Struktur</span><span class="sxs-lookup"><span data-stu-id="4ade7-148">Explore the forecasting model as a tree</span></span>  
  
1.  <span data-ttu-id="4ade7-149">Klicken Sie **auf die** Dropdown Liste Struktur, und wählen Sie ein Modell für die Anzeige aus.</span><span class="sxs-lookup"><span data-stu-id="4ade7-149">Click the **Tree** dropdown list and choose a model to display.</span></span>  
  
     <span data-ttu-id="4ade7-150">Für jedes vorhersagbare Attribut wird eine separate Struktur oder ein Regressionsknoten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4ade7-150">A separate tree or regression node is displayed for each predictable attribute.</span></span> <span data-ttu-id="4ade7-151">Wenn Ihre Daten beispielsweise Verkäufe für Europa, Nordamerika und Pazifik enthalten, sind drei verschiedene Modelle vorhanden, eines für jede Datenreihe.</span><span class="sxs-lookup"><span data-stu-id="4ade7-151">For example, if your data contains sales for Europe, North America, and the Pacific, there would three different models, one for each data series.</span></span>  
  
2.  <span data-ttu-id="4ade7-152">Ziehen Sie den Schieberegler **Ebene anzeigen** , um die unteren Ebenen der Struktur herauszufiltern, und konzentrieren Sie sich auf die wichtigsten Teilungen.</span><span class="sxs-lookup"><span data-stu-id="4ade7-152">Drag the **Show Level** slider to filter out lower levels of the tree, and focus on the most important splits.</span></span>  
  
3.  <span data-ttu-id="4ade7-153">Klicken Sie auf jeden Knoten, um einige beschreibende Statistiken in der **Mining Legende**anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4ade7-153">Click each node to view some descriptive statistics in the **Mining Legend**.</span></span>  
  
     <span data-ttu-id="4ade7-154">Wenn Sie mit der Maus auf einen Knoten zeigen, zeigt die QuickInfo ebenfalls diese statistischen Daten sowie die vollständige Formel an, die den betreffenden Knoten beschreibt.</span><span class="sxs-lookup"><span data-stu-id="4ade7-154">As you pause over a node with the mouse, a ToolTip also displays the same statistics, as well as the full formula describing that node.</span></span>  
  
4.  <span data-ttu-id="4ade7-155">Wenn Sie die Informationen in der **Mining Legende**kopieren möchten, klicken Sie mit der rechten Maustaste auf die **Mining Legende**, wählen Sie **Kopieren**aus, und klicken Sie dann in das Excel-Arbeitsblatt.</span><span class="sxs-lookup"><span data-stu-id="4ade7-155">If you want to copy the information in the **Mining Legend**, right-click the **Mining Legend**, select **Copy**, and click inside your Excel worksheet.</span></span> <span data-ttu-id="4ade7-156">Die Option **in Excel kopieren** kopiert das Diagramm, nicht die Statistiken.</span><span class="sxs-lookup"><span data-stu-id="4ade7-156">The **Copy to Excel** option copies the graph, not the statistics.</span></span>  
  
 [<span data-ttu-id="4ade7-157">Untersuchen des Modells</span><span class="sxs-lookup"><span data-stu-id="4ade7-157">Explore the Model</span></span>](#bkmk_Top)  
  
## <a name="see-also"></a><span data-ttu-id="4ade7-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4ade7-158">See Also</span></span>  
 [<span data-ttu-id="4ade7-159">Durchsuchen von Modellen in Excel &#40;SQL Server Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="4ade7-159">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
