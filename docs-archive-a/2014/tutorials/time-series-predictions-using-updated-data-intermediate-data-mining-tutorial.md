---
title: Zeitreihen Vorhersagen mit aktualisierten Daten (Data Mining-Lernprogramm für Fortgeschrittene) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: af73681d-ce1c-4b6e-b195-6df3d2fb5275
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2017defaba74071b1a12bee14a5d8907e4c71cda
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608126"
---
# <a name="time-series-predictions-using-updated-data-intermediate-data-mining-tutorial"></a><span data-ttu-id="ea726-102">Erstellen von Zeitreihenvorhersagen mit aktualisierten Daten (Data Mining-Lernprogramm für Fortgeschrittene)</span><span class="sxs-lookup"><span data-stu-id="ea726-102">Time Series Predictions using Updated Data (Intermediate Data Mining Tutorial)</span></span>
    
## <a name="creating-predictions-using-the-extended-sales-data"></a><span data-ttu-id="ea726-103">Erstellen von Vorhersagen aus erweiterten Verkaufsdaten</span><span class="sxs-lookup"><span data-stu-id="ea726-103">Creating Predictions using the Extended Sales Data</span></span>  
 <span data-ttu-id="ea726-104">In dieser Lektion erstellen Sie eine Vorhersageabfrage, durch die dem Modell die neuen Umsatzdaten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ea726-104">In this lesson, you will create a prediction query that adds the new sales data to the model.</span></span> <span data-ttu-id="ea726-105">Indem Sie das Modell mit neuen Daten erweitern, erhalten Sie aktuelle Vorhersagen, in denen die neuesten Datenpunkte enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="ea726-105">By extending the model with new data, you can get up-to-date predictions that include the newest data points.</span></span>  
  
 <span data-ttu-id="ea726-106">Das Erstellen von Zeitreihen Vorhersagen, die neue Daten verwenden, ist einfach: Sie fügen einfach den Parameter EXTEND_MODEL_CASES der Funktion " [prättimeseries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) " hinzu, geben die Quelle der neuen Daten an und geben an, wie viele Vorhersagen Sie erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="ea726-106">Creating time series predictions that use new data is easy: you simply add the parameter EXTEND_MODEL_CASES to the [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) function, specify the source of the new data, and specify how many predictions you want to get.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="ea726-107">Der Parameter EXTEND_MODEL_CASES ist optional; standardmäßig wird das Modell immer dann erweitert, wenn Sie eine Vorhersageabfrage für eine Zeitreihe erstellen, indem neue Daten als Eingaben verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="ea726-107">The parameter EXTEND_MODEL_CASES is optional; by default the model is extended any time that you create a time series prediction query by joining new data as inputs.</span></span>  
  
#### <a name="to-build-the-prediction-query-and-add-new-data"></a><span data-ttu-id="ea726-108">So erstellen Sie die Vorhersageabfrage und fügen neue Daten hinzu</span><span class="sxs-lookup"><span data-stu-id="ea726-108">To build the prediction query and add new data</span></span>  
  
1.  <span data-ttu-id="ea726-109">Wenn das Modell nicht bereits geöffnet ist, doppelklicken Sie auf die Planungsstruktur, und klicken Sie im Data Mining-Designer auf die Registerkarte **Mining Modellvorhersage** .</span><span class="sxs-lookup"><span data-stu-id="ea726-109">If the model is not already open, double-click the Forecasting structure, and in Data Mining Designer, click the **Mining Model Prediction** tab.</span></span>  
  
2.  <span data-ttu-id="ea726-110">Im Bereich **Mining Modell** sollte die Modellvorhersage bereits ausgewählt sein.</span><span class="sxs-lookup"><span data-stu-id="ea726-110">In the **Mining Model** pane, the model Forecasting should already be selected.</span></span> <span data-ttu-id="ea726-111">Wenn diese Option nicht ausgewählt ist, klicken Sie auf **Modell auswählen**, und wählen Sie dann das Modell Vorhersagen aus.</span><span class="sxs-lookup"><span data-stu-id="ea726-111">If it is not selected, click **Select Model**, and then select the model, Forecasting.</span></span>  
  
3.  <span data-ttu-id="ea726-112">Klicken Sie im Bereich **Eingabe Tabelle (n) auswählen** auf **Fall Tabelle auswählen**.</span><span class="sxs-lookup"><span data-stu-id="ea726-112">In the **Select Input Table(s)** pane, click **Select Case Table**.</span></span>  
  
4.  <span data-ttu-id="ea726-113">Wählen Sie im Dialogfeld **Tabelle auswählen** die Datenquelle aus [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ea726-113">In the **Select Table** dialog box, select the data source, [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span>  
  
     <span data-ttu-id="ea726-114">Wählen Sie in der Liste der Datenquellen Sichten newsalesdata aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea726-114">From the list of data source views, select NewSalesData and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="ea726-115">Klicken Sie mit der rechten Maustaste auf die Oberfläche des Entwurfs Bereichs und wählen Sie **Verbindungen ändern**aus.</span><span class="sxs-lookup"><span data-stu-id="ea726-115">Right-click the surface of the design area and select **Modify Connections**.</span></span>  
  
6.  <span data-ttu-id="ea726-116">Ordnen Sie im Dialogfeld **Zuordnung ändern** die Spalten im Modell den Spalten in den externen Daten wie folgt zu:</span><span class="sxs-lookup"><span data-stu-id="ea726-116">Using the **Modify Mapping** dialog box, map the columns in the model to the columns in the external data as follows:</span></span>  
  
    -   <span data-ttu-id="ea726-117">Ordnen Sie die ReportingDate-Spalte im Mining Modell der NewDate-Spalte in den Eingabedaten zu.</span><span class="sxs-lookup"><span data-stu-id="ea726-117">Map the ReportingDate column in the mining model to the NewDate column in the input data.</span></span>  
  
    -   <span data-ttu-id="ea726-118">Ordnen Sie die Spalte Amount im Mining Modell der Spalte newamount in den Eingabedaten zu.</span><span class="sxs-lookup"><span data-stu-id="ea726-118">Map the Amount column in the mining model to the NewAmount column in the input data.</span></span>  
  
    -   <span data-ttu-id="ea726-119">Ordnen Sie die Spalte Menge im Mining Modell der Spalte newqty in den Eingabedaten zu.</span><span class="sxs-lookup"><span data-stu-id="ea726-119">Map the Quantity column in the mining model to the NewQty column in the input data.</span></span>  
  
    -   <span data-ttu-id="ea726-120">Ordnen Sie die Spalte ModelRegion im Mining Modell der Spalte Reihe in den Eingabedaten zu.</span><span class="sxs-lookup"><span data-stu-id="ea726-120">Map the ModelRegion column in the mining model to the Series column in the input data.</span></span>  
  
7.  <span data-ttu-id="ea726-121">Nun erstellen Sie die Vorhersageabfrage.</span><span class="sxs-lookup"><span data-stu-id="ea726-121">Now you will build the prediction query.</span></span>  
  
     <span data-ttu-id="ea726-122">Fügen Sie der Vorhersageabfrage zuerst eine Spalte für die Ausgabe der Reihe hinzu, für die Vorhersage gültig ist.</span><span class="sxs-lookup"><span data-stu-id="ea726-122">First, add a column to the prediction query to output the series the prediction applies to.</span></span>  
  
    1.  <span data-ttu-id="ea726-123">Klicken Sie im Raster auf die erste leere Zeile unter **Quelle**, und wählen Sie dann Vorhersagen aus.</span><span class="sxs-lookup"><span data-stu-id="ea726-123">In the grid, click the first empty row, under **Source**, and then select Forecasting.</span></span>  
  
    2.  <span data-ttu-id="ea726-124">Wählen Sie in der Spalte **Feld** die Option Modellbereich aus, und geben Sie als **Alias**ein `Model Region` .</span><span class="sxs-lookup"><span data-stu-id="ea726-124">In the **Field** column, select Model Region and for **Alias**, type `Model Region`.</span></span>  
  
8.  <span data-ttu-id="ea726-125">Fügen Sie dann die Vorhersagefunktion hinzu und bearbeiten Sie sie.</span><span class="sxs-lookup"><span data-stu-id="ea726-125">Next, add and edit the prediction function.</span></span>  
  
    1.  <span data-ttu-id="ea726-126">Klicken Sie auf eine leere Zeile, und wählen Sie unter **Quelle**die Option **Vorhersagefunktion**aus.</span><span class="sxs-lookup"><span data-stu-id="ea726-126">Click an empty row, and under **Source**, select **Prediction Function**.</span></span>  
  
    2.  <span data-ttu-id="ea726-127">Wählen Sie für **Feld**die Option **prättimeseries**aus.</span><span class="sxs-lookup"><span data-stu-id="ea726-127">For **Field**, select **PredictTimeSeries**.</span></span>  
  
    3.  <span data-ttu-id="ea726-128">Geben **Alias**Sie als Alias **vorhergesagte Werte**ein.</span><span class="sxs-lookup"><span data-stu-id="ea726-128">For **Alias**, type **Predicted Values**.</span></span>  
  
    4.  <span data-ttu-id="ea726-129">Ziehen Sie die FeldMenge aus dem Bereich **Mining Modell** in die Spalte **Kriterium/Argument** .</span><span class="sxs-lookup"><span data-stu-id="ea726-129">Drag the field Quantity from the **Mining Model** pane into the **Criteria/Argument** column.</span></span>  
  
    5.  <span data-ttu-id="ea726-130">Geben Sie in der Spalte **Kriterium/Argument** nach dem Feldnamen den folgenden Text ein: **5, EXTEND_MODEL_CASES**</span><span class="sxs-lookup"><span data-stu-id="ea726-130">In the **Criteria/Argument** column, after the field name, type the following text:  **5,EXTEND_MODEL_CASES**</span></span>  
  
         <span data-ttu-id="ea726-131">Der vollständige Text des Textfelds **Kriterium/Argument** sollte wie folgt lauten:`[Forecasting].[Quantity],5,EXTEND_MODEL_CASES`</span><span class="sxs-lookup"><span data-stu-id="ea726-131">The complete text of the **Criteria/Argument** text box should be as follows: `[Forecasting].[Quantity],5,EXTEND_MODEL_CASES`</span></span>  
  
9. <span data-ttu-id="ea726-132">Klicken Sie auf **Ergebnisse** , und überprüfen Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="ea726-132">Click **Results** and review the results.</span></span>  
  
     <span data-ttu-id="ea726-133">Die Vorhersagen beginnen im Juli (erste Zeitscheibe nach dem Ende der ursprünglichen Daten) und enden im November (fünfte Zeitscheibe nach dem Ende der ursprünglichen Daten).</span><span class="sxs-lookup"><span data-stu-id="ea726-133">The predictions begin in July (the first time slice after the end of the original data) and end at November (the fifth time slice after the end of the original data).</span></span>  
  
 <span data-ttu-id="ea726-134">Wie Sie sehen, müssen Sie das Ende der alten Daten wie auch die Anzahl der Zeitscheiben in den neuen Daten kennen, um effektiv mit Vorhersageabfragen dieses Typs zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="ea726-134">You can see that to use this type of prediction query effectively, you need to know when the old data ends, as well as how many time slices there are in the new data.</span></span>  
  
 <span data-ttu-id="ea726-135">In diesem Modell endete die ursprüngliche Datenreihe z. B. im Juni, und die Daten beziehen sich auf die Monate Juli, August und September.</span><span class="sxs-lookup"><span data-stu-id="ea726-135">For example, in this model, the original data series ended in June, and the data is for the months of July, August, and September.</span></span>  
  
 <span data-ttu-id="ea726-136">Vorhersagen, die EXTEND_MODEL_CASES verwenden, beginnen immer am Ende der ursprünglichen Datenreihe.</span><span class="sxs-lookup"><span data-stu-id="ea726-136">Predictions that use EXTEND_MODEL_CASES always begin at the end of the original data series.</span></span> <span data-ttu-id="ea726-137">Wenn Sie nur die Vorhersagen für die unbekannten Monate abrufen möchten, müssen Sie daher den Ausgangspunkt und den Endpunkt der Vorhersage angeben.</span><span class="sxs-lookup"><span data-stu-id="ea726-137">Therefore, if you want to get only the predictions for the unknown months, you need to specify the starting point and the end point for prediction.</span></span> <span data-ttu-id="ea726-138">Beide Werte werden als eine Reihe von Zeitscheiben angegeben, die am Ende der alten Daten startet.</span><span class="sxs-lookup"><span data-stu-id="ea726-138">Both values are specified as a number of time slices starting at the end of the old data.</span></span>  
  
 <span data-ttu-id="ea726-139">Das folgende Verfahren veranschaulicht das Vorgehen.</span><span class="sxs-lookup"><span data-stu-id="ea726-139">The following procedure demonstrates how to do this.</span></span>  
  
### <a name="change-the-start-and-end-points-of-the-predictions"></a><span data-ttu-id="ea726-140">Ändern der Ausgangs- und Endpunkte von Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="ea726-140">Change the start and end points of the predictions</span></span>  
  
1.  <span data-ttu-id="ea726-141">Klicken Sie in Vorhersage Abfrage-Generator auf **Abfrage** , um zur DMX-Ansicht zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="ea726-141">In Prediction Query Builder, click **Query** to switch to DMX view.</span></span>  
  
2.  <span data-ttu-id="ea726-142">Suchen Sie die DMX-Anweisung, die die PredictTimeSeries-Funktion enthält, und ändern Sie sie folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="ea726-142">Locate the DMX statement that contains the PredictTimeSeries function and change it as follows:</span></span>  
  
     `PredictTimeSeries([Forecasting 12].[Quantity],4,6,EXTEND_MODEL_CASES)`  
  
3.  <span data-ttu-id="ea726-143">Klicken Sie auf **Ergebnisse** , und überprüfen Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="ea726-143">Click **Results** and review the results.</span></span>  
  
     <span data-ttu-id="ea726-144">Nun beginnen die Vorhersagen im Oktober (vierte Zeitscheibe bei Zählung vom Ende der ursprünglichen Daten) und endet im Dezember (sechste Zeitscheibe bei Zählung vom Ende der ursprünglichen Daten).</span><span class="sxs-lookup"><span data-stu-id="ea726-144">Now the predictions begin at October (the fourth time slice, counting from the end of the original data) and end at December (the sixth time slice, counting from the end of the original data).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ea726-145">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="ea726-145">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ea726-146">Zeitreihen Vorhersagen mit Ersetzungs Daten &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="ea726-146">Time Series Predictions using Replacement Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
## <a name="see-also"></a><span data-ttu-id="ea726-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ea726-147">See Also</span></span>  
 <span data-ttu-id="ea726-148">[Technische Referenz für den Microsoft Time Series-Algorithmus](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ea726-148">[Microsoft Time Series Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="ea726-149">Miningmodellinhalt von Zeitreihenmodellen &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ea726-149">Mining Model Content for Time Series Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/mining-model-content-for-time-series-models-analysis-services-data-mining.md)  
  
  
