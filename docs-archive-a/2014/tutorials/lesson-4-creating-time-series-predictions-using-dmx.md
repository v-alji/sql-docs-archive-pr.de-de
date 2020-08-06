---
title: 'Lektion 4: Erstellen von Zeitreihen Vorhersagen mit DMX | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6b883e43-209d-489a-8dc3-9349f88acae8
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 772e5f5f71ca82dd18fec48730522c80e907414f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694857"
---
# <a name="lesson-4-creating-time-series-predictions-using-dmx"></a><span data-ttu-id="5ce1e-102">Lektion 4: Erstellen von Zeitreihenvorhersagen mit DMX</span><span class="sxs-lookup"><span data-stu-id="5ce1e-102">Lesson 4: Creating Time Series Predictions Using DMX</span></span>
  <span data-ttu-id="5ce1e-103">In dieser Lektion und in der folgenden Lektion verwenden Sie Data Mining-Erweiterungen (DMX), um unterschiedliche Typen von Vorhersagen basierend auf den Zeitreihen Modellen zu erstellen, die Sie in [Lektion 1: Erstellen eines Zeitreihen-Mining Modells und einer Mining Struktur](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md) erstellt haben, und [Lektion 2: Hinzufügen von Mining Modellen zur Zeitreihen-Mining Struktur](../../2014/tutorials/lesson-2-adding-mining-models-to-the-time-series-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="5ce1e-103">In this lesson and the following lesson, you will use Data Mining Extensions (DMX) to create different types of predictions based on the time series models that you created in [Lesson 1: Creating a Time Series Mining Model and Mining Structure](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md) and [Lesson 2: Adding Mining Models to the Time Series Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-time-series-mining-structure.md).</span></span>  
  
 <span data-ttu-id="5ce1e-104">Ein Zeitreihenmodell bietet zahlreiche Optionen im Hinblick auf Vorhersagen:</span><span class="sxs-lookup"><span data-stu-id="5ce1e-104">With a time series model, you have many options for making predictions:</span></span>  
  
-   <span data-ttu-id="5ce1e-105">Verwendung vorhandener Muster im Miningmodell mit bestehenden Daten</span><span class="sxs-lookup"><span data-stu-id="5ce1e-105">Use the existing patterns and data in the mining model</span></span>  
  
-   <span data-ttu-id="5ce1e-106">Verwendung vorhandener Muster im Miningmodell mit neuen Daten</span><span class="sxs-lookup"><span data-stu-id="5ce1e-106">Use the existing patterns in the mining model but supply new data</span></span>  
  
-   <span data-ttu-id="5ce1e-107">Aufnahme neuer Daten in das Modell oder Update des Modells</span><span class="sxs-lookup"><span data-stu-id="5ce1e-107">Add new data to the model or update the model.</span></span>  
  
 <span data-ttu-id="5ce1e-108">Nachfolgend finden Sie eine Zusammenfassung der Syntax für diese Vorhersagetypen:</span><span class="sxs-lookup"><span data-stu-id="5ce1e-108">The syntax for making these prediction types is summarized below:</span></span>  
  
 <span data-ttu-id="5ce1e-109">Zeitreihenvorhersage (Standard)</span><span class="sxs-lookup"><span data-stu-id="5ce1e-109">Default time series prediction</span></span>  
 <span data-ttu-id="5ce1e-110">Verwenden Sie die [prättimeseries-&#40;DMX-&#41;](/sql/dmx/predicttimeseries-dmx) , um die angegebene Anzahl von Vorhersagen aus dem trainierten Mining Modell zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="5ce1e-110">Use [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) to return the specified number of predictions from the trained mining model.</span></span>  
  
 <span data-ttu-id="5ce1e-111">Informationen hierzu finden Sie beispielsweise unter " [prättimeseries &#40;DMX-&#41;](/sql/dmx/predicttimeseries-dmx) oder [Zeitreihen Modell-Abfrage Beispiele](../../2014/analysis-services/data-mining/time-series-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="5ce1e-111">For example, see [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) or [Time Series Model Query Examples](../../2014/analysis-services/data-mining/time-series-model-query-examples.md).</span></span>  
  
 <span data-ttu-id="5ce1e-112">EXTEND_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="5ce1e-112">EXTEND_MODEL_CASES</span></span>  
 <span data-ttu-id="5ce1e-113">Verwenden Sie die [&#40;DMX-&#41;](/sql/dmx/predicttimeseries-dmx) mit dem EXTEND_MODEL_CASES-Argument, um neue Daten hinzuzufügen, die Reihe zu erweitern und Vorhersagen basierend auf dem aktualisierten Mining Modell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5ce1e-113">Use [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) with the EXTEND_MODEL_CASES argument to add new data, extend the series, and create predictions based on the updated mining model.</span></span>  
  
 <span data-ttu-id="5ce1e-114">Dieses Lernprogramm enthält ein Beispiel zur Verwendung des EXTEND_MODEL_CASES-Arguments.</span><span class="sxs-lookup"><span data-stu-id="5ce1e-114">This tutorial contains an example of how to use EXTEND_MODEL_CASES.</span></span>  
  
 <span data-ttu-id="5ce1e-115">REPLACE_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="5ce1e-115">REPLACE_MODEL_CASES</span></span>  
 <span data-ttu-id="5ce1e-116">Verwenden Sie " [prättimeseries &#40;DMX-&#41;](/sql/dmx/predicttimeseries-dmx) mit dem REPLACE_MODEL_CASES-Argument, um die ursprünglichen Daten durch eine neue Datenreihe zu ersetzen, und erstellen Sie dann Vorhersagen basierend auf dem Anwenden der Muster im Mining Modell auf die neue Datenreihe.</span><span class="sxs-lookup"><span data-stu-id="5ce1e-116">Use [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) with the REPLACE_MODEL_CASES argument to replace the original data with a new data series, and then create predictions based on applying the patterns in the mining model to the new data series.</span></span>  
  
 <span data-ttu-id="5ce1e-117">Ein Beispiel für die Verwendung von REPLACE_MODEL_CASES finden Sie unter [Lektion 2: Erstellung eines Planungs Szenarios &#40;Data Mining ](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)-Lernprogramm für fortgeschrittene&#41;.</span><span class="sxs-lookup"><span data-stu-id="5ce1e-117">For an example of how to use REPLACE_MODEL_CASES, see [Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="5ce1e-118">Lektionsaufgaben</span><span class="sxs-lookup"><span data-stu-id="5ce1e-118">Lesson Tasks</span></span>  
 <span data-ttu-id="5ce1e-119">Im Rahmen dieser Lektion führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="5ce1e-119">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="5ce1e-120">Erstellen einer Abfrage zum Abrufen der Standardvorhersagen auf Basis vorhandener Daten</span><span class="sxs-lookup"><span data-stu-id="5ce1e-120">Create a query to get the default predictions based on existing data.</span></span>  
  
 <span data-ttu-id="5ce1e-121">In der folgenden Lektion führen Sie die nachstehenden verwandten Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="5ce1e-121">In the following lesson you will perform the following related tasks:</span></span>  
  
-   <span data-ttu-id="5ce1e-122">Erstellen einer Abfrage zur Bereitstellung neuer Daten sowie zum Abrufen aktualisierter Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="5ce1e-122">Create a query to supply new data and get updated predictions.</span></span>  
  
 <span data-ttu-id="5ce1e-123">Sie können Abfragen sowohl manuell mit DMX als auch mit dem Generator für Vorhersageabfragen in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] erstellen.</span><span class="sxs-lookup"><span data-stu-id="5ce1e-123">In addition to creating queries manually by using DMX, you can also create predictions by using the prediction query builder in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="simple-time-series-prediction-query"></a><span data-ttu-id="5ce1e-124">Einfache Vorhersageabfragen für Zeitreihen</span><span class="sxs-lookup"><span data-stu-id="5ce1e-124">Simple Time Series Prediction Query</span></span>  
 <span data-ttu-id="5ce1e-125">Der erste Schritt besteht darin, mit der `SELECT FROM`-Anweisung und der `PredictTimeSeries`-Funktion Zeitreihenvorhersagen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5ce1e-125">The first step is to use the `SELECT FROM` statement together with the `PredictTimeSeries` function to create time series predictions.</span></span> <span data-ttu-id="5ce1e-126">Zeitreihenmodelle unterstützen eine vereinfachte Syntax zum Erstellen von Vorhersagen. Sie müssen lediglich angeben, wie viele Vorhersagen erstellt werden sollen; eine Bereitstellung von Eingaben ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5ce1e-126">Time series models support a simplified syntax for creating predictions: you do not need to supply any inputs, but only have to specify the number of predictions to create.</span></span> <span data-ttu-id="5ce1e-127">Die folgende Zeile stellt ein allgemeines Beispiel für die verwendete Anweisung dar:</span><span class="sxs-lookup"><span data-stu-id="5ce1e-127">The following is a generic example of the statement you will use:</span></span>  
  
```  
SELECT <select list>   
FROM [<mining model name>]   
WHERE [<criteria>]  
```  
  
 <span data-ttu-id="5ce1e-128">Die Auswahlliste kann Spalten aus dem Modell enthalten, wie z. b. den Namen der Produktlinie, für die Sie die Vorhersagen erstellen, oder Vorhersagefunktionen, wie z. b. [lag &#40;DMX-&#41;](/sql/dmx/lag-dmx) oder [prättimeseries &#40;DMX-&#41;](/sql/dmx/predicttimeseries-dmx), die speziell für Zeitreihen-Mining Modelle gelten.</span><span class="sxs-lookup"><span data-stu-id="5ce1e-128">The select list can contain columns from the model, such as the name of the product line that you are creating the predictions for, or prediction functions, such as [Lag &#40;DMX&#41;](/sql/dmx/lag-dmx) or [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx), which are specifically for time series mining models.</span></span>  
  
#### <a name="to-create-a-simple-time-series-prediction-query"></a><span data-ttu-id="5ce1e-129">So erstellen Sie eine einfache Vorhersageabfrage für Zeitreihen</span><span class="sxs-lookup"><span data-stu-id="5ce1e-129">To create a simple time series prediction query</span></span>  
  
1.  <span data-ttu-id="5ce1e-130">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , zeigen Sie auf **neue Abfrage**, und klicken Sie dann auf **DMX**.</span><span class="sxs-lookup"><span data-stu-id="5ce1e-130">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="5ce1e-131">Der Abfrage-Editor wird mit einer neuen leeren Abfrage geöffnet.</span><span class="sxs-lookup"><span data-stu-id="5ce1e-131">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="5ce1e-132">Kopieren Sie das allgemeine Beispiel der Anweisung in die leere Abfrage.</span><span class="sxs-lookup"><span data-stu-id="5ce1e-132">Copy the generic example of the statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="5ce1e-133">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5ce1e-133">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="5ce1e-134">durch:</span><span class="sxs-lookup"><span data-stu-id="5ce1e-134">with:</span></span>  
  
    ```  
    [Forecasting_MIXED].[ModelRegion],  
    PredictTimeSeries([Forecasting_MIXED].[Quantity],6) AS PredictQty,  
    PredictTimeSeries ([Forecasting_MIXED].[Amount],6) AS PredictAmt  
    ```  
  
     <span data-ttu-id="5ce1e-135">In der ersten Zeile wird ein Wert vom Miningmodell abgerufen, der die Reihe identifiziert.</span><span class="sxs-lookup"><span data-stu-id="5ce1e-135">The first line retrieves a value from the mining model that identifies the series.</span></span>  
  
     <span data-ttu-id="5ce1e-136">In der zweiten und dritten Zeile wird die `PredictTimeSeries`-Funktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="5ce1e-136">The second and third lines use the `PredictTimeSeries` function.</span></span> <span data-ttu-id="5ce1e-137">In jeder Zeile wird ein anderes Attribut vorhergesagt: `[Quantity]` oder `[Amount]`.</span><span class="sxs-lookup"><span data-stu-id="5ce1e-137">Each line predicts a different attribute, `[Quantity]` or `[Amount]`.</span></span> <span data-ttu-id="5ce1e-138">Die Zahlen hinter den Namen der vorhersagbaren Attribute geben die Anzahl der Zeitschritte an, die vorhergesagt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5ce1e-138">The numbers after the names of the predictable attributes specify the number of time steps to predict.</span></span>  
  
     <span data-ttu-id="5ce1e-139">Mit der `AS`-Klausel wird ein Name für die Spalte bereitgestellt, die von der jeweiligen Vorhersagefunktion zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5ce1e-139">The `AS` clause is used to provide a name for the column that is returned by each prediction function.</span></span> <span data-ttu-id="5ce1e-140">Wenn Sie keinen Alias angeben, werden beide Spalten standardmäßig mit der Bezeichnung `Expression` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5ce1e-140">If you do not supply an alias, by default both columns are returned with the label, `Expression`.</span></span>  
  
4.  <span data-ttu-id="5ce1e-141">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5ce1e-141">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="5ce1e-142">durch:</span><span class="sxs-lookup"><span data-stu-id="5ce1e-142">with:</span></span>  
  
    ```  
    [Forecasting_MIXED]  
    ```  
  
5.  <span data-ttu-id="5ce1e-143">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5ce1e-143">Replace the following:</span></span>  
  
    ```  
    WHERE [criteria>]   
    ```  
  
     <span data-ttu-id="5ce1e-144">durch:</span><span class="sxs-lookup"><span data-stu-id="5ce1e-144">with:</span></span>  
  
    ```  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
     <span data-ttu-id="5ce1e-145">Die gesamte Anweisung sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="5ce1e-145">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
    [Forecasting_MIXED].[ModelRegion],  
    PredictTimeSeries([Forecasting_MIXED].[Quantity],6) AS PredictQty,  
    PredictTimeSeries ([Forecasting_MIXED].[Amount],6) AS PredictAmt  
    FROM   
    [Forecasting_MIXED]  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
6.  <span data-ttu-id="5ce1e-146">Klicken Sie im Menü **Datei** auf **DMXQuery1. DMX speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="5ce1e-146">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="5ce1e-147">Navigieren Sie im Dialogfeld **Speichern** unter in den entsprechenden Ordner, und benennen Sie die Datei `SimpleTimeSeriesPrediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="5ce1e-147">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SimpleTimeSeriesPrediction.dmx`.</span></span>  
  
8.  <span data-ttu-id="5ce1e-148">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="5ce1e-148">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="5ce1e-149">Nach Ausführung der Abfrage werden 6 Vorhersagen für jede der zwei Kombinationen aus Produkt und Region in der `WHERE`-Klausel zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5ce1e-149">The query returns 6 predictions for each of the two combinations of product and region that are specified in the `WHERE` clause.</span></span>  
  
 <span data-ttu-id="5ce1e-150">In der nächsten Lektion erstellen Sie eine Abfrage, mit der neue Daten für das Modell bereitgestellt werden. Außerdem vergleichen Sie die Ergebnisse dieser Vorhersage mit der Vorhersage, die Sie gerade erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="5ce1e-150">In the next lesson, you will create a query that supplies new data to the model, and compare the results of that prediction with the one you just created.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="5ce1e-151">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="5ce1e-151">Next Task in Lesson</span></span>  
 [<span data-ttu-id="5ce1e-152">Lektion 5: Erweitern des Zeitreihenmodells</span><span class="sxs-lookup"><span data-stu-id="5ce1e-152">Lesson 5: Extending the Time Series Model</span></span>](../../2014/tutorials/lesson-5-extending-the-time-series-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="5ce1e-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ce1e-153">See Also</span></span>  
 <span data-ttu-id="5ce1e-154">[Prättimeseries &#40;DMX-&#41;](/sql/dmx/predicttimeseries-dmx) </span><span class="sxs-lookup"><span data-stu-id="5ce1e-154">[PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) </span></span>  
 <span data-ttu-id="5ce1e-155">[Verzögerung &#40;DMX-&#41;](/sql/dmx/lag-dmx) </span><span class="sxs-lookup"><span data-stu-id="5ce1e-155">[Lag &#40;DMX&#41;](/sql/dmx/lag-dmx) </span></span>  
 <span data-ttu-id="5ce1e-156">[Abfrage Beispiele für Zeitreihen Modelle](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span><span class="sxs-lookup"><span data-stu-id="5ce1e-156">[Time Series Model Query Examples](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span></span>  
 [<span data-ttu-id="5ce1e-157">Lektion 2: Erstellung eines Vorhersage Szenarios &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="5ce1e-157">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
  
