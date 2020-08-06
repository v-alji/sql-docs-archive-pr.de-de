---
title: 'Lektion 5: Erweitern des Zeitreihen Modells | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7aad4946-c903-4e25-88b9-b087c20cb67d
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2716e985897f8115d189d9410b7cdb13fb1af291
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615718"
---
# <a name="lesson-5-extending-the-time-series-model"></a><span data-ttu-id="8224d-102">Lektion 5: Erweitern des Zeitreihenmodells</span><span class="sxs-lookup"><span data-stu-id="8224d-102">Lesson 5: Extending the Time Series Model</span></span>
  <span data-ttu-id="8224d-103">In [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Enterprise können Sie einem Zeitreihenmodell neue Daten hinzufügen und die neuen Daten automatisch in das Modell einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="8224d-103">In [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Enterprise, you can add new data to a time series model and automatically incorporate the new data into the model.</span></span> <span data-ttu-id="8224d-104">Es gibt zwei Möglichkeiten, einem Zeitreihen-Miningmodell neue Daten hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="8224d-104">You add new data to a time series mining model in one of two ways:</span></span>  
  
-   <span data-ttu-id="8224d-105">Verknüpfen von Daten in einer externen Quelle mit den Trainingsdaten durch eine PREDICTION JOIN-Anweisung </span><span class="sxs-lookup"><span data-stu-id="8224d-105">Use a PREDICTION JOIN to join data in an external source to the training data.</span></span>  
  
-   <span data-ttu-id="8224d-106">Bereitstellen von Daten in einzelnen Slices mit einer SINGLETON-Vorhersageabfrage</span><span class="sxs-lookup"><span data-stu-id="8224d-106">Use a singleton prediction query to provide data one slice at a time.</span></span>  
  
 <span data-ttu-id="8224d-107">Angenommen, Sie haben das Miningmodell vor einigen Monaten mit vorhandenen Umsatzdaten trainiert.</span><span class="sxs-lookup"><span data-stu-id="8224d-107">For example, assume that you trained the mining model on existing sales data some months ago.</span></span> <span data-ttu-id="8224d-108">Wenn neue Umsatzzahlen vorliegen, können Sie diese verwenden, um die entsprechenden Vorhersagen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8224d-108">When you get new sales, you might want to update the sales predictions to incorporate the new data.</span></span> <span data-ttu-id="8224d-109">Dazu können Sie die neuen Umsatzzahlen als Eingabedaten bereitstellen und anhand des zusammengesetzten Datasets neue Vorhersagen generieren.</span><span class="sxs-lookup"><span data-stu-id="8224d-109">You can do this in one step, by supplying the new sales figures as input data and generating new predictions based on the composite data set.</span></span>  
  
## <a name="making-predictions-with-extend_model_cases"></a><span data-ttu-id="8224d-110">Treffen von Vorhersagen mit EXTEND_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="8224d-110">Making Predictions with EXTEND_MODEL_CASES</span></span>  
 <span data-ttu-id="8224d-111">Nachfolgend finden Sie allgemeine Beispiele für eine Zeitreihenvorhersage mit dem EXTEND_MODEL_CASES-Parameter.</span><span class="sxs-lookup"><span data-stu-id="8224d-111">The following are generic examples of a time series prediction using EXTEND_MODEL_CASES.</span></span> <span data-ttu-id="8224d-112">Mit dem ersten Beispiel können Sie die Anzahl der Vorhersagen ab dem letzten Zeitschritt des ursprünglichen Modells angeben:</span><span class="sxs-lookup"><span data-stu-id="8224d-112">The first example enables you to specify the number of predictions starting from the last time step of the original model:</span></span>  
  
```  
SELECT [<model columns>,] PredictTimeSeries(<table column reference>, n, EXTEND_MODEL_CASES)   
FROM <mining model>  
PREDICTION JOIN <source query>  
[WHERE <criteria>]  
```  
  
 <span data-ttu-id="8224d-113">Im zweiten Beispiel können Sie den Zeitschritt für Beginn und Ende der Vorhersagen angeben.</span><span class="sxs-lookup"><span data-stu-id="8224d-113">The second example enables you to specify the time step where predictions should start, and where they should end.</span></span> <span data-ttu-id="8224d-114">Diese Option spielt eine wichtige Rolle bei der Erweiterung von Modellfällen, da Zeitschritte für Vorhersageabfragen standardmäßig immer am Ende der ursprünglichen Reihe beginnen.</span><span class="sxs-lookup"><span data-stu-id="8224d-114">This option is important when you extend the model cases because, by default, the time steps used for prediction queries always start at the end of the original series.</span></span>  
  
```  
SELECT [<model columns>,] PredictTimeSeries(<table column reference>, n-start, n-end, EXTEND_MODEL_CASES)   
FROM <mining model>  
PREDICTION JOIN <source query>  
[WHERE <criteria>}  
```  
  
 <span data-ttu-id="8224d-115">In diesem Lernprogramm erstellen Sie beide Arten von Abfragen.</span><span class="sxs-lookup"><span data-stu-id="8224d-115">In this tutorial, you will create both kinds of queries.</span></span>  
  
#### <a name="to-create-a-singleton-prediction-query-on-a-time-series-model"></a><span data-ttu-id="8224d-116">So erstellen Sie eine SINGLETON-Vorhersageabfrage für ein Zeitreihenmodell</span><span class="sxs-lookup"><span data-stu-id="8224d-116">To create a singleton prediction query on a time series model</span></span>  
  
1.  <span data-ttu-id="8224d-117">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , zeigen Sie auf **neue Abfrage**, und klicken Sie dann auf **DMX**.</span><span class="sxs-lookup"><span data-stu-id="8224d-117">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="8224d-118">Der Abfrage-Editor wird mit einer neuen leeren Abfrage geöffnet.</span><span class="sxs-lookup"><span data-stu-id="8224d-118">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="8224d-119">Kopieren Sie das allgemeine Beispiel der SINGLETON-Anweisung in die leere Abfrage.</span><span class="sxs-lookup"><span data-stu-id="8224d-119">Copy the generic example of the singleton statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="8224d-120">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8224d-120">Replace the following:</span></span>  
  
    ```  
    SELECT [<model columns>,] PredictTimeSeries(<table column reference>, n, EXTEND_MODEL_CASES)   
    ```  
  
     <span data-ttu-id="8224d-121">durch:</span><span class="sxs-lookup"><span data-stu-id="8224d-121">with:</span></span>  
  
    ```  
    SELECT [Model Region],  
    PredictTimeSeries([Quantity],6, EXTEND_MODEL_CASES) AS PredictQty  
    ```  
  
     <span data-ttu-id="8224d-122">In der ersten Zeile wird ein Wert aus dem Modell zur Identifizierung der Reihe abgerufen.</span><span class="sxs-lookup"><span data-stu-id="8224d-122">The first line retrieves a value from the model that identifies the series.</span></span>  
  
     <span data-ttu-id="8224d-123">Die zweite Zeile enthält die Vorhersagefunktion, mit der 6 Vorhersagen für Quantity abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8224d-123">The second line contains the prediction function, which gets 6 predictions for Quantity.</span></span> <span data-ttu-id="8224d-124">Zum besseren Verständnis der Ergebnisse wird der Ergebnisspalte für die Vorhersage der Alias `PredictQty` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="8224d-124">An alias, `PredictQty`, is assigned to the prediction result column to make it easier to understand the results.</span></span>  
  
4.  <span data-ttu-id="8224d-125">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8224d-125">Replace the following:</span></span>  
  
    ```  
    FROM <mining model>  
    ```  
  
     <span data-ttu-id="8224d-126">durch:</span><span class="sxs-lookup"><span data-stu-id="8224d-126">with:</span></span>  
  
    ```  
    FROM [Forecasting_MIXED]  
    ```  
  
5.  <span data-ttu-id="8224d-127">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8224d-127">Replace the following:</span></span>  
  
    ```  
    PREDICTION JOIN <source query>  
    ```  
  
     <span data-ttu-id="8224d-128">durch:</span><span class="sxs-lookup"><span data-stu-id="8224d-128">with:</span></span>  
  
    ```  
    NATURAL PREDICTION JOIN   
    (  
       SELECT 1 AS [Reporting Date],  
       '10' AS [Quantity],  
       'M200 Europe' AS [Model Region]  
       UNION SELECT  
       2 AS [Reporting Date],  
       15 AS [Quantity]),  
       'M200 Europe' AS [Model Region]  
    ) AS t  
    ```  
  
6.  <span data-ttu-id="8224d-129">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8224d-129">Replace the following:</span></span>  
  
    ```  
    [WHERE <criteria>]  
    ```  
  
     <span data-ttu-id="8224d-130">durch:</span><span class="sxs-lookup"><span data-stu-id="8224d-130">with:</span></span>  
  
    ```  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
     <span data-ttu-id="8224d-131">Die gesamte Anweisung sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="8224d-131">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT [Model Region],  
    PredictTimeSeries([Quantity],6, EXTEND_MODEL_CASES) AS PredictQty  
    FROM  
       [Forecasting_MIXED]  
    NATURAL PREDICTION JOIN   
       SELECT 1 AS [ReportingDate],  
      '10' AS [Quantity],  
      'M200 Europe' AS [ModelRegion]  
    UNION SELECT  
      2 AS [ReportingDate],  
      15 AS [Quantity]),  
      'M200 Europe' AS [ModelRegion]  
    ) AS t  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
7.  <span data-ttu-id="8224d-132">Klicken Sie im Menü **Datei** auf **DMXQuery1. DMX speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="8224d-132">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="8224d-133">Navigieren Sie im Dialogfeld **Speichern** unter in den entsprechenden Ordner, und benennen Sie die Datei `Singleton_TimeSeries_Query.dmx` .</span><span class="sxs-lookup"><span data-stu-id="8224d-133">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Singleton_TimeSeries_Query.dmx`.</span></span>  
  
9. <span data-ttu-id="8224d-134">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="8224d-134">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="8224d-135">Die Abfrage gibt Vorhersagen mit der Verkaufsmenge des Fahrradmodells M200 für die Regionen Europa und Pazifik zurück.</span><span class="sxs-lookup"><span data-stu-id="8224d-135">The query returns predictions of sales quantity for the M200 bicycle in the Europe and Pacific regions.</span></span>  
  
## <a name="understanding-prediction-start-with-extend_model_cases"></a><span data-ttu-id="8224d-136">Grundlegendes zum Beginn der Vorhersage mit EXTEND_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="8224d-136">Understanding Prediction Start with EXTEND_MODEL_CASES</span></span>  
 <span data-ttu-id="8224d-137">Nachdem Sie Vorhersagen auf der Grundlage des ursprünglichen Modells und mit neuen Daten erstellt haben, können Sie nun die Ergebnisse vergleichen, um zu sehen, wie sich das Update der Umsatzdaten auf die Vorhersagen auswirkt.</span><span class="sxs-lookup"><span data-stu-id="8224d-137">Now that you have created predictions based on the original model, and with new data, you can compare the results to see how updating the sales data affects the predictions.</span></span> <span data-ttu-id="8224d-138">Überprüfen Sie jedoch zuvor den Code, den Sie gerade erstellt haben, und beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8224d-138">Before you do so, review the code that you just created, and notice the following:</span></span>  
  
-   <span data-ttu-id="8224d-139">Sie haben neue Daten nur für die Region Europa angegeben.</span><span class="sxs-lookup"><span data-stu-id="8224d-139">You supplied new data for only the Europe region.</span></span>  
  
-   <span data-ttu-id="8224d-140">Die neuen Daten umfassen nur einen Zeitraum von zwei Monaten.</span><span class="sxs-lookup"><span data-stu-id="8224d-140">You supplied only two months' worth of new data.</span></span>  
  
 <span data-ttu-id="8224d-141">Die folgende Tabelle zeigt, wie sich die neuen Werte für das M200-Modell in Europa auf die Vorhersagen auswirken.</span><span class="sxs-lookup"><span data-stu-id="8224d-141">The following table shows how the new values supplied for M200 Europe affect predictions.</span></span> <span data-ttu-id="8224d-142">Da Sie keine neuen Daten für das M200-Modell in der Region Pazifik angegeben haben, wird diese Reihe zum Vergleich dargestellt:</span><span class="sxs-lookup"><span data-stu-id="8224d-142">You did not provide any new data for the M200 product in the Pacific region, but this series is presented for comparison:</span></span>  
  
 <span data-ttu-id="8224d-143">**Produkt und Region: M200 Europe**</span><span class="sxs-lookup"><span data-stu-id="8224d-143">**Product and Region: M200 Europe**</span></span>  
  
|||||  
|-|-|-|-|  
|||<span data-ttu-id="8224d-144">Gegebenes Modell (`PredictTimeSeries`)</span><span class="sxs-lookup"><span data-stu-id="8224d-144">Existing model (`PredictTimeSeries`)</span></span>|<span data-ttu-id="8224d-145">Modell mit aktualisierten Umsatzdaten (`PredictTimeSeries` mit `EXTEND_MODEL_CASES`)</span><span class="sxs-lookup"><span data-stu-id="8224d-145">Model with updated sales data (`PredictTimeSeries` with `EXTEND_MODEL_CASES`)</span></span>|  
|<span data-ttu-id="8224d-146">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="8224d-146">M200 Europe</span></span>|<span data-ttu-id="8224d-147">7/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8224d-147">7/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="8224d-148">77</span><span class="sxs-lookup"><span data-stu-id="8224d-148">77</span></span>|<span data-ttu-id="8224d-149">10</span><span class="sxs-lookup"><span data-stu-id="8224d-149">10</span></span>|  
|<span data-ttu-id="8224d-150">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="8224d-150">M200 Europe</span></span>|<span data-ttu-id="8224d-151">8/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8224d-151">8/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="8224d-152">64</span><span class="sxs-lookup"><span data-stu-id="8224d-152">64</span></span>|<span data-ttu-id="8224d-153">15</span><span class="sxs-lookup"><span data-stu-id="8224d-153">15</span></span>|  
|<span data-ttu-id="8224d-154">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="8224d-154">M200 Europe</span></span>|<span data-ttu-id="8224d-155">9/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8224d-155">9/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="8224d-156">59</span><span class="sxs-lookup"><span data-stu-id="8224d-156">59</span></span>|<span data-ttu-id="8224d-157">72</span><span class="sxs-lookup"><span data-stu-id="8224d-157">72</span></span>|  
|<span data-ttu-id="8224d-158">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="8224d-158">M200 Europe</span></span>|<span data-ttu-id="8224d-159">10/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8224d-159">10/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="8224d-160">56</span><span class="sxs-lookup"><span data-stu-id="8224d-160">56</span></span>|<span data-ttu-id="8224d-161">69</span><span class="sxs-lookup"><span data-stu-id="8224d-161">69</span></span>|  
|<span data-ttu-id="8224d-162">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="8224d-162">M200 Europe</span></span>|<span data-ttu-id="8224d-163">11/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8224d-163">11/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="8224d-164">56</span><span class="sxs-lookup"><span data-stu-id="8224d-164">56</span></span>|<span data-ttu-id="8224d-165">68</span><span class="sxs-lookup"><span data-stu-id="8224d-165">68</span></span>|  
|<span data-ttu-id="8224d-166">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="8224d-166">M200 Europe</span></span>|<span data-ttu-id="8224d-167">12/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8224d-167">12/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="8224d-168">74</span><span class="sxs-lookup"><span data-stu-id="8224d-168">74</span></span>|<span data-ttu-id="8224d-169">89</span><span class="sxs-lookup"><span data-stu-id="8224d-169">89</span></span>|  
  
 <span data-ttu-id="8224d-170">**Produkt und Region: M200 Pacific**</span><span class="sxs-lookup"><span data-stu-id="8224d-170">**Product and Region: M200 Pacific**</span></span>  
  
|||||  
|-|-|-|-|  
|||<span data-ttu-id="8224d-171">Gegebenes Modell (`PredictTimeSeries`)</span><span class="sxs-lookup"><span data-stu-id="8224d-171">Existing model (`PredictTimeSeries`)</span></span>|<span data-ttu-id="8224d-172">Modell mit aktualisierten Umsatzdaten (`PredictTimeSeries` mit `EXTEND_MODEL_CASES`)</span><span class="sxs-lookup"><span data-stu-id="8224d-172">Model with updated sales data (`PredictTimeSeries` with `EXTEND_MODEL_CASES`)</span></span>|  
|<span data-ttu-id="8224d-173">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="8224d-173">M200 Pacific</span></span>|<span data-ttu-id="8224d-174">7/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8224d-174">7/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="8224d-175">41</span><span class="sxs-lookup"><span data-stu-id="8224d-175">41</span></span>|<span data-ttu-id="8224d-176">41</span><span class="sxs-lookup"><span data-stu-id="8224d-176">41</span></span>|  
|<span data-ttu-id="8224d-177">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="8224d-177">M200 Pacific</span></span>|<span data-ttu-id="8224d-178">8/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8224d-178">8/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="8224d-179">44</span><span class="sxs-lookup"><span data-stu-id="8224d-179">44</span></span>|<span data-ttu-id="8224d-180">44</span><span class="sxs-lookup"><span data-stu-id="8224d-180">44</span></span>|  
|<span data-ttu-id="8224d-181">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="8224d-181">M200 Pacific</span></span>|<span data-ttu-id="8224d-182">9/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8224d-182">9/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="8224d-183">38</span><span class="sxs-lookup"><span data-stu-id="8224d-183">38</span></span>|<span data-ttu-id="8224d-184">38</span><span class="sxs-lookup"><span data-stu-id="8224d-184">38</span></span>|  
|<span data-ttu-id="8224d-185">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="8224d-185">M200 Pacific</span></span>|<span data-ttu-id="8224d-186">10/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8224d-186">10/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="8224d-187">41</span><span class="sxs-lookup"><span data-stu-id="8224d-187">41</span></span>|<span data-ttu-id="8224d-188">41</span><span class="sxs-lookup"><span data-stu-id="8224d-188">41</span></span>|  
|<span data-ttu-id="8224d-189">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="8224d-189">M200 Pacific</span></span>|<span data-ttu-id="8224d-190">11/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8224d-190">11/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="8224d-191">36</span><span class="sxs-lookup"><span data-stu-id="8224d-191">36</span></span>|<span data-ttu-id="8224d-192">36</span><span class="sxs-lookup"><span data-stu-id="8224d-192">36</span></span>|  
|<span data-ttu-id="8224d-193">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="8224d-193">M200 Pacific</span></span>|<span data-ttu-id="8224d-194">12/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8224d-194">12/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="8224d-195">39</span><span class="sxs-lookup"><span data-stu-id="8224d-195">39</span></span>|<span data-ttu-id="8224d-196">39</span><span class="sxs-lookup"><span data-stu-id="8224d-196">39</span></span>|  
  
 <span data-ttu-id="8224d-197">Aus diesen Ergebnissen sind zwei Dinge ersichtlich:</span><span class="sxs-lookup"><span data-stu-id="8224d-197">From these results, you can see two things:</span></span>  
  
-   <span data-ttu-id="8224d-198">Die ersten beiden Vorhersagen für die Datenreihe M200 Europe stimmen exakt mit den neuen Daten überein, die Sie bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="8224d-198">The first two predictions for the M200 Europe series are exactly the same as the new data you supplied.</span></span> <span data-ttu-id="8224d-199">Analysis Services gibt programmbedingt die tatsächlichen neuen Datenpunkte zurück, statt eine Vorhersage zu treffen.</span><span class="sxs-lookup"><span data-stu-id="8224d-199">By design, Analysis Services returns the actual new data points instead of making a prediction.</span></span> <span data-ttu-id="8224d-200">Dies liegt daran, dass bei der Erweiterung der Modellfälle die Zeitschritte für Vorhersageabfragen standardmäßig immer am Ende der ursprünglichen Reihe beginnen.</span><span class="sxs-lookup"><span data-stu-id="8224d-200">That is because when you extend the model cases, the time steps used for prediction queries always start at the end of the original series.</span></span> <span data-ttu-id="8224d-201">Wenn Sie daher zwei neue Datenpunkte hinzufügen, überschneiden sich die ersten zwei zurückgegebenen Vorhersagen mit den neuen Daten.</span><span class="sxs-lookup"><span data-stu-id="8224d-201">Therefore, if you add two new data points, the first two predictions returned overlap with the new data.</span></span>  
  
-   <span data-ttu-id="8224d-202">Nachdem alle neuen Datenpunkte verwendet wurden, erstellt [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Vorhersagen auf Grundlage des aktualisierten Modells.</span><span class="sxs-lookup"><span data-stu-id="8224d-202">After all the new data points are used up, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] makes predictions based on the updated model.</span></span> <span data-ttu-id="8224d-203">Ab September 2005 wird daher der Unterschied zwischen den Vorhersagen für die Datenreihe M200 Europe und dem ursprünglichen Modell (linke Spalte) sowie dem Modell mit EXTEND_MODEL_CASES (rechte Spalte) ersichtlich.</span><span class="sxs-lookup"><span data-stu-id="8224d-203">Therefore, starting in September 2005, you can see the difference between predictions for M200 Europe from the original model, in the left-hand column, and the model that uses EXTEND_MODEL_CASES, in the right-hand column.</span></span> <span data-ttu-id="8224d-204">Die Vorhersagen unterscheiden sich, da das Modell mit den neuen Daten aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="8224d-204">The predictions are different because the model has been updated with the new data.</span></span>  
  
## <a name="using-start-and-end-time-steps-to-control-predictions"></a><span data-ttu-id="8224d-205">Verwenden von Zeitschritten für Beginn und Ende zur Steuerung von Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="8224d-205">Using Start and End Time Steps to Control Predictions</span></span>  
 <span data-ttu-id="8224d-206">Wenn Sie ein Modell erweitern, werden die neuen Daten immer am Ende der Reihe angefügt.</span><span class="sxs-lookup"><span data-stu-id="8224d-206">When you extend a model, the new data is always attached to the end of the series.</span></span> <span data-ttu-id="8224d-207">Die für Vorhersageabfragen verwendeten Zeitscheiben beginnen jedoch immer am Ende der ursprünglichen Reihe.</span><span class="sxs-lookup"><span data-stu-id="8224d-207">However, for the purpose of prediction, the time slices used for prediction queries start at the end of the original series.</span></span> <span data-ttu-id="8224d-208">Damit beim Hinzufügen von neuen Daten nur die neuen Vorhersagen abgerufen werden, müssen Sie den Startpunkt als Anzahl von Zeitscheiben angeben.</span><span class="sxs-lookup"><span data-stu-id="8224d-208">If you want to obtain only the new predictions when you add the new data, you must specify the starting point as a number of time slices.</span></span> <span data-ttu-id="8224d-209">Wenn Sie beispielsweise zwei neue Datenpunkte hinzufügen und vier neue Vorhersagen treffen möchten, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="8224d-209">For example, if you are adding two new data points and want to make four new predictions, you would do the following:</span></span>  
  
-   <span data-ttu-id="8224d-210">Erstellen Sie eine PREDICTION JOIN-Anweisung für ein Zeitreihenmodell, und geben Sie neue Daten für einen Zeitraum von zwei Monaten an.</span><span class="sxs-lookup"><span data-stu-id="8224d-210">Create a PREDICTION JOIN on a time series model, and specify two months of new data.</span></span>  
  
-   <span data-ttu-id="8224d-211">Fordern Sie Vorhersagen für vier Zeitscheiben an, wobei der Startpunkt Zeitscheibe 3 und der Endpunkt Zeitscheibe 6 ist.</span><span class="sxs-lookup"><span data-stu-id="8224d-211">Request predictions for four time slices, where the starting point is 3, and the ending point is time slice 6.</span></span>  
  
 <span data-ttu-id="8224d-212">Anders ausgedrückt: Wenn die neuen Daten n Zeit Scheiben enthalten und Sie Vorhersagen für die Zeit Schritte 1 bis n anfordern, stimmen die Vorhersagen mit dem gleichen Zeitraum wie die neuen Daten überein.</span><span class="sxs-lookup"><span data-stu-id="8224d-212">In other words, if your new data contains n time slices, and you request predictions for time steps 1 through n, the predictions will coincide with the same period as the new data.</span></span> <span data-ttu-id="8224d-213">Wenn Sie neue Vorhersagen für Zeiträume benötigen, die nicht von den Daten abgedeckt werden, müssen die Vorhersagen bei Zeitscheibe n+1 nach der neuen Datenreihe beginnen, oder Sie müssen sicherstellen, dass Sie zusätzliche Zeitscheiben anfordern.</span><span class="sxs-lookup"><span data-stu-id="8224d-213">To get new predictions for a time periods not covered by your data, you must either start predictions at the time slice n+1 after the new data series, or make sure that you request additional time slices.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8224d-214">Wenn Sie neue Daten hinzufügen, sind keine Vergangenheitsvorhersagen möglich.</span><span class="sxs-lookup"><span data-stu-id="8224d-214">You cannot make historical predictions when you add new data.</span></span>  
  
 <span data-ttu-id="8224d-215">Im folgenden Beispiel wird die DMX-Anweisung veranschaulicht, mit der nur die neuen Vorhersagen für zwei Reihen im vorangehenden Beispiel abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="8224d-215">The following example shows the DMX statement that lets you get only the new predictions for the two series in the previous example.</span></span>  
  
```  
SELECT [Model Region],  
PredictTimeSeries([Quantity],3,6, EXTEND_MODEL_CASES) AS PredictQty  
FROM  
   [Forecasting_MIXED]  
NATURAL PREDICTION JOIN   
   SELECT 1 AS [ReportingDate],  
  '10' AS [Quantity],  
  'M200 Europe' AS [ModelRegion]  
UNION SELECT  
  2 AS [ReportingDate],  
  15 AS [Quantity]),  
  'M200 Europe' AS [ModelRegion]  
) AS t  
WHERE [ModelRegion] = 'M200 Europe'  
```  
  
 <span data-ttu-id="8224d-216">Die Vorhersage beginnt bei der Zeitscheibe 3, also nach dem Zeitraum von 2 Monaten, den die neuen Daten umfassen.</span><span class="sxs-lookup"><span data-stu-id="8224d-216">The prediction results start at time slice 3, which is after the 2 months of new data that you supplied.</span></span>  
  
 <span data-ttu-id="8224d-217">**Produkt und Region: M200 Europe**</span><span class="sxs-lookup"><span data-stu-id="8224d-217">**Product and Region: M200 Europe**</span></span>  
  
 <span data-ttu-id="8224d-218">Modell mit aktualisierten Daten (PredictTimeSeries mit EXTEND_MODEL_CASES)</span><span class="sxs-lookup"><span data-stu-id="8224d-218">Model with updated data (PredictTimeSeries with EXTEND_MODEL_CASES)</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="8224d-219">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="8224d-219">M200 Europe</span></span>|<span data-ttu-id="8224d-220">9/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8224d-220">9/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="8224d-221">72</span><span class="sxs-lookup"><span data-stu-id="8224d-221">72</span></span>|  
|<span data-ttu-id="8224d-222">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="8224d-222">M200 Europe</span></span>|<span data-ttu-id="8224d-223">10/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8224d-223">10/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="8224d-224">69</span><span class="sxs-lookup"><span data-stu-id="8224d-224">69</span></span>|  
|<span data-ttu-id="8224d-225">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="8224d-225">M200 Europe</span></span>|<span data-ttu-id="8224d-226">11/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8224d-226">11/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="8224d-227">68</span><span class="sxs-lookup"><span data-stu-id="8224d-227">68</span></span>|  
|<span data-ttu-id="8224d-228">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="8224d-228">M200 Europe</span></span>|<span data-ttu-id="8224d-229">12/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="8224d-229">12/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="8224d-230">89</span><span class="sxs-lookup"><span data-stu-id="8224d-230">89</span></span>|  
  
## <a name="making-predictions-with-replace_model_cases"></a><span data-ttu-id="8224d-231">Treffen von Vorhersagen mit REPLACE_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="8224d-231">Making Predictions with REPLACE_MODEL_CASES</span></span>  
 <span data-ttu-id="8224d-232">Das Ersetzen der Modellfälle ist sinnvoll, wenn Sie ein Modell mit einem Satz von Fällen trainieren und dieses Modell auf eine andere Datenreihe anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="8224d-232">Replacing the model cases is useful when you want to train a model on one set of cases and then apply that model to a different data series.</span></span> <span data-ttu-id="8224d-233">Eine ausführliche Exemplarische Vorgehensweise dieses Szenarios finden Sie in [Lektion 2: Erstellung eines Planungs Szenarios &#40;Data Mining ](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)-Lernprogramm für fortgeschrittene&#41;.</span><span class="sxs-lookup"><span data-stu-id="8224d-233">A detailed walkthrough of this scenario is presented in [Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8224d-234">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8224d-234">See Also</span></span>  
 <span data-ttu-id="8224d-235">[Abfrage Beispiele für Zeitreihen Modelle](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span><span class="sxs-lookup"><span data-stu-id="8224d-235">[Time Series Model Query Examples](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span></span>  
 [<span data-ttu-id="8224d-236">PredictTimeSeries &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="8224d-236">PredictTimeSeries &#40;DMX&#41;</span></span>](/sql/dmx/predicttimeseries-dmx)  
  
  
