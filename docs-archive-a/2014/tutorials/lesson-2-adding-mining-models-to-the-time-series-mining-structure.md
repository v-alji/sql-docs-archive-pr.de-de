---
title: 'Lektion 2: Hinzufügen von Mining Modellen zur Zeitreihen-Mining Struktur | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 75c2a74b-21ce-44fb-a26b-68be4c685c12
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: ae0bb91fafb53c0c077a4e0d82558b550d0e6070
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608178"
---
# <a name="lesson-2-adding-mining-models-to-the-time-series-mining-structure"></a><span data-ttu-id="17e10-102">Lektion 2: Hinzufügen von Miningmodellen zur Miningstruktur für Zeitreihen</span><span class="sxs-lookup"><span data-stu-id="17e10-102">Lesson 2: Adding Mining Models to the Time Series Mining Structure</span></span>
  <span data-ttu-id="17e10-103">In dieser Lektion fügen Sie der Mining Struktur, die Sie soeben in [Lektion 1: Erstellen eines Zeitreihen-Mining Modells und einer Mining Struktur](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md)erstellt haben, ein neues Mining Modell hinzu.</span><span class="sxs-lookup"><span data-stu-id="17e10-103">In this lesson, you will add a new mining model to the mining structure that you just created in [Lesson 1: Creating a Time Series Mining Model and Mining Structure](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md).</span></span>  
  
## <a name="alter-mining-structure-statement"></a><span data-ttu-id="17e10-104">ALTER MINING STRUCTURE-Anweisung</span><span class="sxs-lookup"><span data-stu-id="17e10-104">ALTER MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="17e10-105">Um einer vorhandenen Mining Struktur ein neues Mining Modell hinzuzufügen, verwenden Sie die Anweisung [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) .</span><span class="sxs-lookup"><span data-stu-id="17e10-105">In order to add a new mining model to an existing mining structure, you use the [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) statement.</span></span> <span data-ttu-id="17e10-106">Der in der Anweisung enthaltene Code umfasst folgende Abschnitte: </span><span class="sxs-lookup"><span data-stu-id="17e10-106">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="17e10-107">Identifizieren der Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="17e10-107">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="17e10-108">Benennen des Miningmodells</span><span class="sxs-lookup"><span data-stu-id="17e10-108">Naming the mining model</span></span>  
  
-   <span data-ttu-id="17e10-109">Definieren der Schlüsselspalte</span><span class="sxs-lookup"><span data-stu-id="17e10-109">Defining the key column</span></span>  
  
-   <span data-ttu-id="17e10-110">Definieren der vorhersagbaren Spalten</span><span class="sxs-lookup"><span data-stu-id="17e10-110">Defining the predictable columns</span></span>  
  
-   <span data-ttu-id="17e10-111">Angeben von Algorithmus- und Parameteränderungen</span><span class="sxs-lookup"><span data-stu-id="17e10-111">Specifying the algorithm and any parameter changes</span></span>  
  
 <span data-ttu-id="17e10-112">Es folgt ein allgemeines Beispiel für die ALTER MINING STRUCTURE-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="17e10-112">The following is a generic example of the ALTER MINING STRUCTURE statement:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
ADD MINING MODEL [<mining model name>]  
   ([<key columns>],  
    <mining model columns>  
   )  
USING <algorithm name>([<algorithm parameters>])  
[WITH DRILLTHROUGH]  
```  
  
 <span data-ttu-id="17e10-113">Die erste Codezeile identifiziert die vorhandene Miningstruktur, der die Miningmodelle hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="17e10-113">The first line of the code identifies the existing mining structure to which the mining models will be added:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="17e10-114">Die nächste Codezeile benennt das Miningmodell, das zur Miningstruktur hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="17e10-114">The next line of the code names the mining model that will be added to the mining structure:</span></span>  
  
```  
ADD MINING MODEL [<mining model name>]  
```  
  
 <span data-ttu-id="17e10-115">Weitere Informationen zum Benennen eines Objekts in DMX finden Sie unter Bezeichner [&#40;DMX-&#41;](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="17e10-115">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="17e10-116">Die nächsten Codezeilen definieren Spalten der Miningstruktur, die vom Miningmodell verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="17e10-116">The next lines of the code define columns from the mining structure that will be used by the mining model:</span></span>  
  
```  
[<key columns>],  
<mining model columns>  
```  
  
 <span data-ttu-id="17e10-117">Sie können nur Spalten verwenden, die bereits in der Miningstruktur vorhanden sind; außerdem muss die erste Spalte in der Liste die Schlüsselspalte der Miningstruktur sein.</span><span class="sxs-lookup"><span data-stu-id="17e10-117">You can only use columns that already exist in the mining structure, and the first column in the list must be the key column from the mining structure.</span></span>  
  
 <span data-ttu-id="17e10-118">Die nächste Codezeile definiert den Miningalgorithmus, der das Miningmodell sowie die Algorithmusparameter generiert, die Sie für den Algorithmus festlegen können. Außerdem wird angegeben, ob ein Drilldown für das Miningmodell möglich ist, um Detaildaten in den Trainingsfällen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="17e10-118">The next lines of the code defines the mining algorithm that generates the mining model and the algorithm parameters that you can set on the algorithm, and specify whether you can drill down from the mining model into view detailed data in the training cases:</span></span>  
  
```  
USING <algorithm name>([<algorithm parameters>])  
WITH DRILLTHROUGH  
```  
  
 <span data-ttu-id="17e10-119">Weitere Informationen zu den Algorithmusparametern, die Sie anpassen können, finden Sie unter [Technische Referenz für den Microsoft Time Series-Algorithmus](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="17e10-119">For more information about the algorithm parameters that you can adjust, see [Microsoft Time Series Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="17e10-120">Mithilfe der folgenden Syntax können Sie angeben, dass eine Spalte des Miningmodells für Vorhersagen verwendet werden soll:</span><span class="sxs-lookup"><span data-stu-id="17e10-120">You can specify that a column in the mining model be used for prediction by using the following syntax:</span></span>  
  
```  
<mining model column> PREDICT  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="17e10-121">Lektionsaufgaben</span><span class="sxs-lookup"><span data-stu-id="17e10-121">Lesson Tasks</span></span>  
 <span data-ttu-id="17e10-122">Im Rahmen dieser Lektion führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="17e10-122">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="17e10-123">Hinzufügen eines neuen Zeitreihen-Miningmodells zur Struktur</span><span class="sxs-lookup"><span data-stu-id="17e10-123">Add a new time series mining model to the structure.</span></span>  
  
-   <span data-ttu-id="17e10-124">Ändern der Algorithmusparameter zur Verwendung anderer Analyse- und Vorhersagemethoden</span><span class="sxs-lookup"><span data-stu-id="17e10-124">Change the algorithm parameters to use a different method of analysis and prediction</span></span>  
  
## <a name="adding-an-arima-time-series-model-to-the-structure"></a><span data-ttu-id="17e10-125">Hinzufügen eines ARIMA-Zeitreihenmodells zur Struktur</span><span class="sxs-lookup"><span data-stu-id="17e10-125">Adding an ARIMA Time Series Model to the Structure</span></span>  
 <span data-ttu-id="17e10-126">Im ersten Schritt fügen Sie der bestehenden Struktur ein neues &lt;legacyBold&gt;Forecasting&lt;/legacyBold&gt;-Miningmodell hinzu.</span><span class="sxs-lookup"><span data-stu-id="17e10-126">The first step is to add a new forecasting mining model to the existing structure.</span></span> <span data-ttu-id="17e10-127">Zeitreihen-Miningmodelle werden vom [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series-Algorithmus standardmäßig mit den Algorithmen ARIMA und ARTXP erstellt, und die Ergebnisse werden kombiniert.</span><span class="sxs-lookup"><span data-stu-id="17e10-127">By default, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm creates time series mining models by using two algorithms, ARIMA and ARTXP, and blending the results.</span></span> <span data-ttu-id="17e10-128">Sie können jedoch auch angeben, dass nur ein Algorithmus verwendet wird, oder Sie können die exakte Kombination der Algorithmen festlegen.</span><span class="sxs-lookup"><span data-stu-id="17e10-128">However, you can specify a single algorithm to use, or you can specify the exact blend of algorithms.</span></span> <span data-ttu-id="17e10-129">In diesem Schritt fügen Sie ein neues Modell hinzu, das nur den ARIMA-Algorithmus verwendet.</span><span class="sxs-lookup"><span data-stu-id="17e10-129">In this step, you will add a new model that uses only the ARIMA algorithm.</span></span> <span data-ttu-id="17e10-130">Dieser Algorithmus ist für die langfristige Vorhersage optimiert.</span><span class="sxs-lookup"><span data-stu-id="17e10-130">This algorithm is optimized for long-term prediction.</span></span>  
  
#### <a name="to-add-an-arima-time-series-mining-model"></a><span data-ttu-id="17e10-131">So fügen Sie ein ARIMA-Zeitreihen-Miningmodell hinzu</span><span class="sxs-lookup"><span data-stu-id="17e10-131">To add an ARIMA time series mining model</span></span>  
  
1.  <span data-ttu-id="17e10-132">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , zeigen Sie auf **neue Abfrage**, und klicken Sie dann auf **DMX** , um den Abfrage-Editor und eine neue, leere Abfrage zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="17e10-132">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open Query Editor and a new, blank query.</span></span>  
  
2.  <span data-ttu-id="17e10-133">Kopieren Sie das allgemeine Beispiel der ALTER MINING STRUCTURE-Anweisung in die leere Abfrage.</span><span class="sxs-lookup"><span data-stu-id="17e10-133">Copy the generic example of the ALTER MINING STRUCTURE statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="17e10-134">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="17e10-134">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="17e10-135">durch:</span><span class="sxs-lookup"><span data-stu-id="17e10-135">with:</span></span>  
  
    ```  
    [Forecasting_MIXED_Structure]  
    ```  
  
4.  <span data-ttu-id="17e10-136">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="17e10-136">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="17e10-137">durch:</span><span class="sxs-lookup"><span data-stu-id="17e10-137">with:</span></span>  
  
    ```  
    Forecasting_ARIMA  
    ```  
  
5.  <span data-ttu-id="17e10-138">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="17e10-138">Replace the following:</span></span>  
  
    ```  
    <key columns>,  
    ```  
  
     <span data-ttu-id="17e10-139">durch:</span><span class="sxs-lookup"><span data-stu-id="17e10-139">with:</span></span>  
  
    ```  
    [ReportingDate],  
    [ModelRegion]  
    ```  
  
     <span data-ttu-id="17e10-140">Eine Wiederholung von Datentypen oder Inhaltstypinformationen, die in der CREATE MINING MODEL-Anweisung bereitgestellt wurden, ist nicht erforderlich. Diese Informationen sind bereits in der Miningstruktur gespeichert.</span><span class="sxs-lookup"><span data-stu-id="17e10-140">Note that you do not need to repeat any of the date type or content type information that you provided in the CREATE MINING MODEL statement, because this information is already stored in the mining structure.</span></span>  
  
6.  <span data-ttu-id="17e10-141">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="17e10-141">Replace the following:</span></span>  
  
    ```  
    <mining model columns>  
    ```  
  
     <span data-ttu-id="17e10-142">durch:</span><span class="sxs-lookup"><span data-stu-id="17e10-142">with:</span></span>  
  
    ```  
    ([Quantity] PREDICT,  
    [Amount] PREDICT  
    )  
    ```  
  
7.  <span data-ttu-id="17e10-143">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="17e10-143">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>([<algorithm parameters>])   
    [WITH DRILLTHROUGH]  
    ```  
  
     <span data-ttu-id="17e10-144">durch:</span><span class="sxs-lookup"><span data-stu-id="17e10-144">with:</span></span>  
  
    ```  
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = .08, FORECAST_METHOD = 'ARIMA')  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="17e10-145">Die resultierende Anweisung sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="17e10-145">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Forecasting_MIXED_Structure]  
    ADD MINING MODEL [Forecasting_ARIMA]  
       (  
       ([ReportingDate],  
        [ModelRegion],  
        ([Quantity] PREDICT,  
        [Amount] PREDICT  
       )   
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = .08, FORECAST_METHOD = 'ARIMA')  
    WITH DRILLTHROUGH  
    ```  
  
8.  <span data-ttu-id="17e10-146">Klicken Sie im Menü **Datei** auf **DMXQuery1. DMX speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="17e10-146">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
9. <span data-ttu-id="17e10-147">Navigieren Sie im Dialogfeld **Speichern** unter in den entsprechenden Ordner, und benennen Sie die Datei `Forecasting_ARIMA.dmx` .</span><span class="sxs-lookup"><span data-stu-id="17e10-147">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Forecasting_ARIMA.dmx`.</span></span>  
  
10. <span data-ttu-id="17e10-148">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="17e10-148">On the toolbar, click the **Execute** button.</span></span>  
  
## <a name="adding-an-artxp-time-series-model-to-the-structure"></a><span data-ttu-id="17e10-149">Hinzufügen eines ARTXP-Zeitreihenmodells zur Struktur</span><span class="sxs-lookup"><span data-stu-id="17e10-149">Adding an ARTXP Time Series Model to the Structure</span></span>  
 <span data-ttu-id="17e10-150">Der ARTXP-Algorithmus ist der Standardalgorithmus für Zeitreihen in SQL Server 2005 und wurde für kurzfristige Vorhersagen optimiert.</span><span class="sxs-lookup"><span data-stu-id="17e10-150">The ARTXP algorithm was the default time series algorithm in SQL Server 2005 and is optimized for short-term prediction.</span></span> <span data-ttu-id="17e10-151">Um Vorhersagen mit allen drei Algorithmen für Zeitreihen zu vergleichen, fügen Sie ein weiteres Modell auf Basis des ARTXP-Algorithmus hinzu.</span><span class="sxs-lookup"><span data-stu-id="17e10-151">To compare predictions by using all three time series algorithms, you will add one more model that is based on the ARTXP algorithm.</span></span>  
  
#### <a name="to-add-an-artxp-time-series-mining-model"></a><span data-ttu-id="17e10-152">So fügen Sie ein ARTXP-Zeitreihen-Miningmodell hinzu</span><span class="sxs-lookup"><span data-stu-id="17e10-152">To add an ARTXP time series mining model</span></span>  
  
1.  <span data-ttu-id="17e10-153">Kopieren Sie den folgenden Code in ein leeres Abfragefenster.</span><span class="sxs-lookup"><span data-stu-id="17e10-153">Copy the following code into a blank query window.</span></span>  
  
     <span data-ttu-id="17e10-154">Sie müssen nur den Namen des neuen Miningmodells sowie den Wert des FORECAST_METHOD-Parameters ändern; weitere Änderungen sind nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="17e10-154">Note that you do not need to change anything except the name of the new mining model, and the value of the FORECAST_METHOD parameter.</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Forecasting_MIXED_Structure]  
    ADD MINING MODEL [Forecasting_ARTXP]  
       (  
       ([ReportingDate],  
        [ModelRegion],  
        ([Quantity] PREDICT,  
        [Amount] PREDICT  
       )   
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = .08, FORECAST_METHOD = 'ARTXP')  
    WITH DRILLTHROUGH  
    ```  
  
2.  <span data-ttu-id="17e10-155">Klicken Sie im Menü **Datei** auf **DMXQuery1. DMX speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="17e10-155">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
3.  <span data-ttu-id="17e10-156">Navigieren Sie im Dialogfeld **Speichern** unter in den entsprechenden Ordner, und benennen Sie die Datei `Forecasting_ARTXP.dmx` .</span><span class="sxs-lookup"><span data-stu-id="17e10-156">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Forecasting_ARTXP.dmx`.</span></span>  
  
4.  <span data-ttu-id="17e10-157">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="17e10-157">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="17e10-158">In der nächsten Lektion verarbeiten Sie alle Modelle und die Miningstruktur.</span><span class="sxs-lookup"><span data-stu-id="17e10-158">In the next lesson, you will process all of the models and the mining structure.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="17e10-159">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="17e10-159">Next Lesson</span></span>  
 [<span data-ttu-id="17e10-160">Lektion 3: Verarbeiten der Zeitreihenstruktur und -modelle</span><span class="sxs-lookup"><span data-stu-id="17e10-160">Lesson 3: Processing the Time Series Structure and Models</span></span>](../../2014/tutorials/lesson-3-processing-the-time-series-structure-and-models.md)  
  
## <a name="see-also"></a><span data-ttu-id="17e10-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="17e10-161">See Also</span></span>  
 <span data-ttu-id="17e10-162">[Microsoft Time Series-Algorithmus](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="17e10-162">[Microsoft Time Series Algorithm](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span></span>  
 [<span data-ttu-id="17e10-163">Microsoft Time Series Algorithm Technical Reference</span><span class="sxs-lookup"><span data-stu-id="17e10-163">Microsoft Time Series Algorithm Technical Reference</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md)  
  
  
