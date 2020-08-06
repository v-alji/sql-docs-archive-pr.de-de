---
title: 'Lektion 3: Verarbeiten der Zeitreihen Struktur und-Modelle | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 16e27b57-eae1-47a7-a02c-47b6ed487d87
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 493d27c9836eb765c655eba5bbb004e4d48cde40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717089"
---
# <a name="lesson-3-processing-the-time-series-structure-and-models"></a><span data-ttu-id="7468c-102">Lektion 3: Verarbeiten der Zeitreihenstruktur und -modelle</span><span class="sxs-lookup"><span data-stu-id="7468c-102">Lesson 3: Processing the Time Series Structure and Models</span></span>
  <span data-ttu-id="7468c-103">In dieser Lektion verwenden Sie die [INSERT INTO-Anweisung &#40;DMX-&#41;](/sql/dmx/insert-into-dmx) , um die von Ihnen erstellten Zeitreihen-Mining Strukturen und Mining Modelle zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7468c-103">In this lesson, you will use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement to process the time series mining structures and mining models that you created.</span></span>  
  
 <span data-ttu-id="7468c-104">Wenn Sie eine Miningstruktur verarbeiten, liest [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] die Quelldaten und erstellt die Strukturen, die Miningmodelle unterstützen.</span><span class="sxs-lookup"><span data-stu-id="7468c-104">When you process a mining structure, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] reads the source data and builds the structures that support mining models.</span></span> <span data-ttu-id="7468c-105">Nachdem Sie ein Miningmodell und eine Struktur erstellt haben, müssen Sie diese immer zunächst verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7468c-105">You always have to process a mining model and structure when you first create it.</span></span> <span data-ttu-id="7468c-106">Wenn Sie die Miningstruktur bei Verwendung der INSERT INTO-Anweisung angegeben, wird die Miningstruktur zusammen mit allen zugehörigen Miningmodellen von der Struktur verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="7468c-106">If you specify the mining structure when using INSERT INTO, the statement processes the mining structure and all its associated mining models.</span></span>  
  
 <span data-ttu-id="7468c-107">Wenn Sie einer Miningstruktur, die bereits verarbeitet wurde, ein Miningmodell hinzufügen, können Sie nur das neue Miningmodell mithilfe der `INSERT INTO MINING MODEL`-Anweisung unter Verwendung von vorhandenen Daten verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7468c-107">When you add a mining model to a mining structure that has already been processed, you can use the `INSERT INTO MINING MODEL` statement to process just the new mining model by using the existing data.</span></span>  
  
 <span data-ttu-id="7468c-108">Weitere Informationen zum Verarbeiten von Mining Modellen finden Sie unter [Verarbeiten von Anforderungen und Überlegungen &#40;Data Mining-&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="7468c-108">For more information about processing mining models, see [Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span></span>  
  
## <a name="insert-into-statement"></a><span data-ttu-id="7468c-109">INSERT INTO-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7468c-109">INSERT INTO Statement</span></span>  
 <span data-ttu-id="7468c-110">Um die Zeitreihen-Mining Struktur und alle zugehörigen Mining Modelle zu trainieren, verwenden Sie die [INSERT INTO-Anweisung &#40;DMX-&#41;](/sql/dmx/insert-into-dmx) .</span><span class="sxs-lookup"><span data-stu-id="7468c-110">In order to train the time series mining structure and all its associated mining models, use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement.</span></span> <span data-ttu-id="7468c-111">Der in der Anweisung enthaltene Code umfasst folgende Abschnitte. </span><span class="sxs-lookup"><span data-stu-id="7468c-111">The code in the statement can be broken into the following parts.</span></span>  
  
-   <span data-ttu-id="7468c-112">Identifizieren der Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="7468c-112">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="7468c-113">Auflisten der Spalten in der Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="7468c-113">Listing the columns in the mining structure</span></span>  
  
-   <span data-ttu-id="7468c-114">Definieren der Trainingsdaten</span><span class="sxs-lookup"><span data-stu-id="7468c-114">Defining the training data</span></span>  
  
 <span data-ttu-id="7468c-115">Das folgende Beispiel ist ein allgemeines Beispiel für die `INSERT INTO`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="7468c-115">The following is a generic example of the `INSERT INTO` statement:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
(  
   <mining structure columns>  
)  
OPENQUERY (<source data definition>)  
```  
  
 <span data-ttu-id="7468c-116">Die erste Codezeile identifiziert die Miningstruktur, die Sie trainieren werden:</span><span class="sxs-lookup"><span data-stu-id="7468c-116">The first line of the code identifies the mining structure that you will train:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="7468c-117">Die nächsten Codezeilen geben die Spalten an, die durch die Miningstruktur definiert werden.</span><span class="sxs-lookup"><span data-stu-id="7468c-117">The next lines of the code specify the columns that are defined by the mining structure.</span></span> <span data-ttu-id="7468c-118">Sie müssen jede Spalte in der Miningstruktur auflisten, und jede Spalte muss einer in den Quellabfragedaten enthaltenen Spalte zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="7468c-118">You must list each column in the mining structure, and each column must map to a column contained within the source query data.</span></span>  
  
```  
(  
   <mining structure columns>  
)  
```  
  
 <span data-ttu-id="7468c-119">Die letzten Codezeilen definieren die Daten, die zum Trainieren der Miningstruktur verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7468c-119">The final lines of the code define the data that will be used to train the mining structure.</span></span>  
  
```  
OPENQUERY (<source data definition>)  
```  
  
 <span data-ttu-id="7468c-120">In dieser Lektion verwenden Sie `OPENQUERY` zum Definieren der Quelldaten.</span><span class="sxs-lookup"><span data-stu-id="7468c-120">In this lesson, you use `OPENQUERY` to define the source data.</span></span> <span data-ttu-id="7468c-121">Weitere Informationen zu anderen Methoden zum Definieren einer Abfrage für die Quelldaten finden Sie unter [&#60;Quelldaten Abfrage&#62;](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="7468c-121">For more information about other methods of defining a query on the source data, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="7468c-122">Lektionsaufgaben</span><span class="sxs-lookup"><span data-stu-id="7468c-122">Lesson Tasks</span></span>  
 <span data-ttu-id="7468c-123">Im Rahmen dieser Lektion führen Sie die folgende Aufgabe aus:</span><span class="sxs-lookup"><span data-stu-id="7468c-123">You will perform the following task in this lesson:</span></span>  
  
-   <span data-ttu-id="7468c-124">Verarbeiten der Miningstruktur Forecasting_MIXED_Structure</span><span class="sxs-lookup"><span data-stu-id="7468c-124">Process the mining structure Forecasting_MIXED_Structure</span></span>  
  
-   <span data-ttu-id="7468c-125">Verarbeiten der verwandten Miningmodelle Forecasting_MIXED, Forecasting_ARIMA und Forecasting_ARTXP</span><span class="sxs-lookup"><span data-stu-id="7468c-125">Process the related mining models Forecasting_MIXED, Forecasting_ARIMA, and Forecasting_ARTXP</span></span>  
  
## <a name="processing-the-time-series-mining-structure"></a><span data-ttu-id="7468c-126">Verarbeiten der Zeitreihen-Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="7468c-126">Processing the Time Series Mining Structure</span></span>  
  
#### <a name="to-process-the-mining-structure-and-related-mining-models-by-using-insert-into"></a><span data-ttu-id="7468c-127">So verarbeiten Sie die Miningstruktur sowie verwandte Miningmodelle mithilfe von INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="7468c-127">To process the mining structure and related mining models by using INSERT INTO</span></span>  
  
1.  <span data-ttu-id="7468c-128">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , zeigen Sie auf **neue Abfrage**, und klicken Sie dann auf **DMX**.</span><span class="sxs-lookup"><span data-stu-id="7468c-128">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="7468c-129">Der Abfrage-Editor wird mit einer neuen leeren Abfrage geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7468c-129">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="7468c-130">Kopieren Sie das Standardbeispiel der INSERT INTO-Anweisung in die leere Abfrage.</span><span class="sxs-lookup"><span data-stu-id="7468c-130">Copy the generic example of the INSERT INTO statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="7468c-131">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7468c-131">Replace the following:</span></span>  
  
    ```  
    [<mining structure>]  
    ```  
  
     <span data-ttu-id="7468c-132">durch:</span><span class="sxs-lookup"><span data-stu-id="7468c-132">with:</span></span>  
  
    ```  
    Forecasting_MIXED_Structure  
    ```  
  
4.  <span data-ttu-id="7468c-133">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7468c-133">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>  
    ```  
  
     <span data-ttu-id="7468c-134">durch:</span><span class="sxs-lookup"><span data-stu-id="7468c-134">with:</span></span>  
  
    ```  
    [ReportingDate],  
    [ModelRegion]   
    ```  
  
5.  <span data-ttu-id="7468c-135">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7468c-135">Replace the following:</span></span>  
  
    ```  
    OPENQUERY(<source data definition>)  
    ```  
  
     <span data-ttu-id="7468c-136">durch:</span><span class="sxs-lookup"><span data-stu-id="7468c-136">with:</span></span>  
  
    ```  
    OPENQUERY([Adventure Works DW 2008R2],'SELECT [ReportingDate], [ModelRegion], [Quantity], [Amount]  
    FROM vTimeSeries ORDER BY [ReportingDate]')  
    ```  
  
     <span data-ttu-id="7468c-137">Die Quell Abfrage verweist [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] auf die Datenquelle, die im Beispiel Projekt "IntermediateTutorial" definiert ist.</span><span class="sxs-lookup"><span data-stu-id="7468c-137">The source query references the  [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source defined in the IntermediateTutorial sample project.</span></span> <span data-ttu-id="7468c-138">Diese Datenquelle wird verwendet, um auf die vTimeSeries-Sicht zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="7468c-138">It uses this data source to access the view vTimeSeries.</span></span> <span data-ttu-id="7468c-139">Diese Sicht enthält die Quelldaten, die zum Trainieren des Miningmodells verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7468c-139">This view contains the source data that will be used to train the mining model.</span></span> <span data-ttu-id="7468c-140">Wenn Sie mit diesem Projekt oder diesen Sichten nicht vertraut sind, finden Sie weitere Informationen unter[Lektion 2: Erstellung eines Planungs Szenarios &#40;Data Mining ](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)-Lernprogramm für fortgeschrittene&#41;.</span><span class="sxs-lookup"><span data-stu-id="7468c-140">If you are not familiar with this project or this views, see[Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span></span>  
  
     <span data-ttu-id="7468c-141">Die gesamte Anweisung sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="7468c-141">The complete statement should now be as follows:</span></span>  
  
    ```  
    INSERT INTO MINING STRUCTURE [Forecasting_MIXED_Structure]  
    (  
       [ReportingDate],[ModelRegion],[Quantity],[Amount])  
    )  
    OPENQUERY(  
    [Adventure Works DW 2008R2],  
    'SELECT [ReportingDate],[ModelRegion],[Quantity],[Amount] FROM vTimeSeries ORDER BY [ReportingDate]'  
    )   
    ```  
  
6.  <span data-ttu-id="7468c-142">Klicken Sie im Menü **Datei** auf **DMXQuery1. DMX speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="7468c-142">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="7468c-143">Navigieren Sie im Dialogfeld **Speichern** unter in den entsprechenden Ordner, und benennen Sie die Datei `ProcessForecastingAll.dmx` .</span><span class="sxs-lookup"><span data-stu-id="7468c-143">In the **Save As** dialog box, browse to the appropriate folder, and name the file `ProcessForecastingAll.dmx`.</span></span>  
  
8.  <span data-ttu-id="7468c-144">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="7468c-144">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="7468c-145">Nachdem die Abfrage ausgeführt wurde, können Sie Vorhersagen mit den verarbeiteten Miningmodellen erstellen.</span><span class="sxs-lookup"><span data-stu-id="7468c-145">After the query has finished running, you can create predictions by using the processed mining models.</span></span> <span data-ttu-id="7468c-146">In der nächsten Lektion erstellen Sie mehrere Vorhersagen auf Grundlage der Miningmodelle, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="7468c-146">In the next lesson, you will create several predictions based on the mining models that you created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="7468c-147">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="7468c-147">Next Lesson</span></span>  
 [<span data-ttu-id="7468c-148">Lektion 4: Erstellen von Zeitreihenvorhersagen mit DMX</span><span class="sxs-lookup"><span data-stu-id="7468c-148">Lesson 4: Creating Time Series Predictions Using DMX</span></span>](../../2014/tutorials/lesson-4-creating-time-series-predictions-using-dmx.md)  
  
## <a name="see-also"></a><span data-ttu-id="7468c-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7468c-149">See Also</span></span>  
 <span data-ttu-id="7468c-150">[Verarbeitungsanforderungen und Überlegungen &#40;Data Mining-&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="7468c-150">[Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md) </span></span>  
 <span data-ttu-id="7468c-151">[&#60;Quelldaten Abfrage&#62;](/sql/dmx/source-data-query) </span><span class="sxs-lookup"><span data-stu-id="7468c-151">[&#60;source data query&#62;](/sql/dmx/source-data-query) </span></span>  
 [<span data-ttu-id="7468c-152">OPENQUERY-&#40;DMX-&#41;</span><span class="sxs-lookup"><span data-stu-id="7468c-152">OPENQUERY &#40;DMX&#41;</span></span>](/sql/dmx/source-data-query-openquery)  
  
  
