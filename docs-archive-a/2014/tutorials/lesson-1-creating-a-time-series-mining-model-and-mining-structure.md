---
title: 'Lektion 1: Erstellen eines Zeitreihen-Mining Modells und einer Mining Struktur | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b201f2b8-9ab5-425b-9ff3-fe321a60a7b7
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2513bc3837dd224f6561eb0015ced538ea3add8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609597"
---
# <a name="lesson-1-creating-a-time-series-mining-model-and-mining-structure"></a><span data-ttu-id="a90a5-102">Lektion 1: Erstellen eines Miningmodells und einer Miningstruktur für eine Zeitreihe</span><span class="sxs-lookup"><span data-stu-id="a90a5-102">Lesson 1: Creating a Time Series Mining Model and Mining Structure</span></span>
  <span data-ttu-id="a90a5-103">In dieser Lektion erstellen Sie ein Miningmodell, mit dem Sie auf Basis von Vergangenheitsdaten Werte für einen Zeitraum vorhersagen können.</span><span class="sxs-lookup"><span data-stu-id="a90a5-103">In this lesson, you will create a mining model that allows you to predict values over time, based on historical data.</span></span> <span data-ttu-id="a90a5-104">Beim Erstellen des Modells wird die zugrunde liegende Struktur automatisch generiert und kann als Basis für weitere Miningmodelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a90a5-104">When you create the model, the underlying structure will be generated automatically and can be used as the basis for additional mining models.</span></span>  
  
 <span data-ttu-id="a90a5-105">In dieser Lektion wird davon ausgegangen, dass Sie mit Forecasting-Modellen sowie mit den Anforderungen des Microsoft Time Series-Algorithmus vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="a90a5-105">This lesson assumes that you are familiar with forecasting models and with the requirements of the Microsoft Time Series algorithm.</span></span> <span data-ttu-id="a90a5-106">Weitere Informationen finden Sie unter [Microsoft Time Series Algorithm](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="a90a5-106">For more information, see [Microsoft Time Series Algorithm](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md).</span></span>  
  
## <a name="create-mining-model-statement"></a><span data-ttu-id="a90a5-107">Create Mining Model-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a90a5-107">CREATE MINING MODEL Statement</span></span>  
 <span data-ttu-id="a90a5-108">Um ein Mining Modell direkt zu erstellen und die zugrunde liegende Mining Struktur automatisch zu generieren, verwenden Sie die Anweisung [Create Mining Model &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx) .</span><span class="sxs-lookup"><span data-stu-id="a90a5-108">In order to create a mining model directly and automatically generate the underlying mining structure, you use the [CREATE MINING MODEL &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx) statement.</span></span> <span data-ttu-id="a90a5-109">Der in der Anweisung enthaltene Code umfasst folgende Abschnitte: </span><span class="sxs-lookup"><span data-stu-id="a90a5-109">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="a90a5-110">Benennen des Modells</span><span class="sxs-lookup"><span data-stu-id="a90a5-110">Naming the model</span></span>  
  
-   <span data-ttu-id="a90a5-111">Definieren des Zeitstempels</span><span class="sxs-lookup"><span data-stu-id="a90a5-111">Defining the time stamp</span></span>  
  
-   <span data-ttu-id="a90a5-112">Definieren der optionalen Reihenschlüsselspalte</span><span class="sxs-lookup"><span data-stu-id="a90a5-112">Defining the optional series key column</span></span>  
  
-   <span data-ttu-id="a90a5-113">Definieren der vorhersagbaren Attribute</span><span class="sxs-lookup"><span data-stu-id="a90a5-113">Defining the predictable attribute or attributes</span></span>  
  
 <span data-ttu-id="a90a5-114">Es folgt ein allgemeines Beispiel für die CREATE MINING MODEL-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="a90a5-114">The following is a generic example of the CREATE MINING MODEL statement:</span></span>  
  
```  
CREATE MINING MODEL [<Mining Structure Name>]  
(  
   <key columns>,  
   <predictable attribute columns>  
)  
USING <algorithm name>([parameter list])  
WITH DRILLTHROUGH  
```  
  
 <span data-ttu-id="a90a5-115">Die erste Codezeile definiert den Namen des Miningmodells:</span><span class="sxs-lookup"><span data-stu-id="a90a5-115">The first line of the code defines the name of the mining model:</span></span>  
  
```  
CREATE MINING MODEL [Mining Model Name]  
```  
  
 <span data-ttu-id="a90a5-116">Der Name für die zugrunde liegende Struktur wird von Analysis Services automatisch generiert, indem "_structure" an den Modellnamen angefügt wird. Dadurch ist sichergestellt, dass sich der Strukturname vom Modellnamen unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="a90a5-116">Analysis Services automatically generates a name for the underlying structure, by appending "_structure" to the model name, which ensures that the structure name is unique from the model name.</span></span> <span data-ttu-id="a90a5-117">Weitere Informationen zum Benennen eines Objekts in DMX finden Sie unter Bezeichner [&#40;DMX-&#41;](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="a90a5-117">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="a90a5-118">Die nächste Codezeile definiert die Schlüsselspalte für das Miningmodell, mit der bei einem Zeitreihenmodell ein Zeitschritt in den Quelldaten eindeutig identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="a90a5-118">The next line of the code defines the key column for the mining model, which in the case of a time series model uniquely identifies a time step in the source data.</span></span> <span data-ttu-id="a90a5-119">Der Zeit Schritt wird durch die `KEY TIME` Schlüsselwörter nach dem Spaltennamen und den Datentypen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="a90a5-119">The time step is identified with the `KEY TIME` keywords after the column name and data types.</span></span> <span data-ttu-id="a90a5-120">Wenn ein Zeitreihenmodell über einen separaten Reihenschlüssel verfügt, wird es anhand des `KEY`-Schlüsselworts identifiziert.</span><span class="sxs-lookup"><span data-stu-id="a90a5-120">If the time series model has a separate series key, it is identified by using the `KEY` keyword.</span></span>  
  
```  
<key columns>  
```  
  
 <span data-ttu-id="a90a5-121">Die nächste Codezeile definiert die Spalten im Modell, die vorhergesagt werden.</span><span class="sxs-lookup"><span data-stu-id="a90a5-121">The next line of the code is used to define the columns in the model that will be predicted.</span></span> <span data-ttu-id="a90a5-122">Sie können mehrere vorhersagbare Attribute in einem Miningmodell verwenden.</span><span class="sxs-lookup"><span data-stu-id="a90a5-122">You can have multiple predictable attributes in a single mining model.</span></span> <span data-ttu-id="a90a5-123">Bei mehreren vorhersagbaren Attributen wird vom Microsoft Time Series-Algorithmus eine separate Analyse für jede Reihe generiert:</span><span class="sxs-lookup"><span data-stu-id="a90a5-123">When there are multiple predictable attributes, the Microsoft Time Series algorithm generates a separate analysis for each series:</span></span>  
  
```  
<predictable attribute columns>  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="a90a5-124">Lektionsaufgaben</span><span class="sxs-lookup"><span data-stu-id="a90a5-124">Lesson Tasks</span></span>  
 <span data-ttu-id="a90a5-125">Im Rahmen dieser Lektion führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="a90a5-125">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="a90a5-126">Erstellen einer neuen leeren Abfrage</span><span class="sxs-lookup"><span data-stu-id="a90a5-126">Create a new blank query</span></span>  
  
-   <span data-ttu-id="a90a5-127">Ändern der Abfrage zum Erstellen des Miningmodells</span><span class="sxs-lookup"><span data-stu-id="a90a5-127">Alter the query to create the mining model</span></span>  
  
-   <span data-ttu-id="a90a5-128">Ausführen der Abfrage</span><span class="sxs-lookup"><span data-stu-id="a90a5-128">Execute the query</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="a90a5-129">Erstellen einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="a90a5-129">Creating the Query</span></span>  
 <span data-ttu-id="a90a5-130">Im ersten Schritt stellen Sie eine Verbindung zu einer Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] her und erstellen eine neue DMX-Abfrage in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a90a5-130">The first step is to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and create a new DMX query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-create-a-new-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="a90a5-131">So erstellen Sie eine neue DMX-Abfrage in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a90a5-131">To create a new DMX query in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="a90a5-132">Öffnen Sie [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a90a5-132">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="a90a5-133">Wählen Sie im Dialogfeld **Verbindung mit Server herstellen** unter **Servertyp**die Option **Analysis Services**aus.</span><span class="sxs-lookup"><span data-stu-id="a90a5-133">In the **Connect to Server** dialog box, for **Server type**, select **Analysis Services**.</span></span> <span data-ttu-id="a90a5-134">Geben Sie unter **Server Name**den Namen ein `LocalHost` , oder geben Sie den Namen der Instanz von ein, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] mit der Sie für diese Lektion eine Verbindung herstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="a90a5-134">In **Server name**, type `LocalHost`, or the name of the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you want to connect to for this lesson.</span></span> <span data-ttu-id="a90a5-135">Klicken Sie auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="a90a5-135">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="a90a5-136">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , zeigen Sie auf **neue Abfrage**, und klicken Sie dann auf **DMX**.</span><span class="sxs-lookup"><span data-stu-id="a90a5-136">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="a90a5-137">Der Abfrage-Editor wird mit einer neuen leeren Abfrage geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a90a5-137">Query Editor opens and contains a new, blank query.</span></span>  
  
## <a name="altering-the-query"></a><span data-ttu-id="a90a5-138">Ändern der Abfrage</span><span class="sxs-lookup"><span data-stu-id="a90a5-138">Altering the Query</span></span>  
 <span data-ttu-id="a90a5-139">Im nächsten Schritt ändern Sie die CREATE MINING MODEL-Anweisung und erstellen das Miningmodell für Vorhersagen mit der zugrunde liegenden Struktur.</span><span class="sxs-lookup"><span data-stu-id="a90a5-139">The next step is to modify the CREATE MINING MODEL statement to create the mining model used for forecasting, together with its underlying mining structure.</span></span>  
  
#### <a name="to-customize-the-create-mining-model-statement"></a><span data-ttu-id="a90a5-140">So passen Sie die CREATE MINING MODEL-Anweisung an</span><span class="sxs-lookup"><span data-stu-id="a90a5-140">To customize the CREATE MINING MODEL statement</span></span>  
  
1.  <span data-ttu-id="a90a5-141">Kopieren Sie im Abfrage-Editor das allgemeine Beispiel der CREATE MINING MODEL-Anweisung in die leere Abfrage.</span><span class="sxs-lookup"><span data-stu-id="a90a5-141">In Query Editor, copy the generic example of the CREATE MINING MODEL statement into the blank query.</span></span>  
  
2.  <span data-ttu-id="a90a5-142">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a90a5-142">Replace the following:</span></span>  
  
    ```  
    [mining model name]   
    ```  
  
     <span data-ttu-id="a90a5-143">durch:</span><span class="sxs-lookup"><span data-stu-id="a90a5-143">with:</span></span>  
  
    ```  
    [Forecasting_MIXED]  
    ```  
  
3.  <span data-ttu-id="a90a5-144">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a90a5-144">Replace the following:</span></span>  
  
    ```  
    <key columns>  
    ```  
  
     <span data-ttu-id="a90a5-145">durch:</span><span class="sxs-lookup"><span data-stu-id="a90a5-145">with:</span></span>  
  
    ```  
    [Reporting Date] DATE KEY TIME,  
    [Model Region] TEXT KEY  
    ```  
  
     <span data-ttu-id="a90a5-146">Das `TIME KEY`-Schlüsselwort gibt an, dass die ReportingDate-Spalte die Zeitschrittwerte enthält, die zur Sortierung der Werte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a90a5-146">The `TIME KEY` keyword indicates that the ReportingDate column contains the time step values used to order the values.</span></span> <span data-ttu-id="a90a5-147">Zeitschritte können Daten und Uhrzeiten, ganze Zahlen oder jeder beliebige geordnete Datentyp sein; die Werte müssen lediglich eindeutig und sortiert sein.</span><span class="sxs-lookup"><span data-stu-id="a90a5-147">Time steps can be dates and times, integers, or any ordered data type, so long as the values are unique and the data is sorted.</span></span>  
  
     <span data-ttu-id="a90a5-148">Das `TEXT`-Schlüsselwort und `KEY`-Schlüsselwort geben an, dass die ModelRegion-Spalte einen weiteren Reihenschlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="a90a5-148">The `TEXT` and `KEY` keywords indicate that the ModelRegion column contains an additional series key.</span></span> <span data-ttu-id="a90a5-149">Sie können nur einen Reihenschlüssel verwenden, und die Werte in der Spalte müssen unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="a90a5-149">You can have only one series key, and the values in the column must be distinct.</span></span>  
  
4.  <span data-ttu-id="a90a5-150">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a90a5-150">Replace the following:</span></span>  
  
    ```  
    < predictable attribute columns> )  
    ```  
  
     <span data-ttu-id="a90a5-151">durch:</span><span class="sxs-lookup"><span data-stu-id="a90a5-151">with:</span></span>  
  
    ```  
    [Quantity] LONG CONTINUOUS PREDICT,  
    [Amount] DOUBLE CONTINUOUS PREDICT  
    )  
    ```  
  
5.  <span data-ttu-id="a90a5-152">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a90a5-152">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>([parameter list])  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="a90a5-153">durch:</span><span class="sxs-lookup"><span data-stu-id="a90a5-153">with:</span></span>  
  
    ```  
    USING Microsoft_Time_Series(AUTO_DETECT_PERIODICITY = 0.8, FORECAST_METHOD = 'MIXED')  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="a90a5-154">Der Algorithmusparameter `AUTO_DETECT_PERIODICITY` = 0,8 gibt an, dass Zyklen in den Daten vom Algorithmus erkannt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a90a5-154">The algorithm parameter, `AUTO_DETECT_PERIODICITY` = 0.8, indicates that you want the algorithm to detect cycles in the data.</span></span> <span data-ttu-id="a90a5-155">Das Festlegen dieses Werts näher bei 1 begünstigt die Ermittlung vieler Muster, verlangsamt jedoch die Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="a90a5-155">Setting this value closer to 1 favors the discovery of many patterns but can slow processing.</span></span>  
  
     <span data-ttu-id="a90a5-156">Der Algorithumsparameter `FORECAST_METHOD` gibt an, dass die Daten mit ARTXP, ARIMA oder einer Kombination aus beiden analysiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a90a5-156">The algorithm parameter, `FORECAST_METHOD`, indicates whether you want the data to be analyzed using ARTXP, ARIMA, or a mixture of both.</span></span>  
  
     <span data-ttu-id="a90a5-157">Das Schlüsselwort `WITH DRILLTHROUGH` gibt an, dass detaillierte Statistiken in den Quelldaten verfügbar sein sollen, sobald das Modell vollständig ist.</span><span class="sxs-lookup"><span data-stu-id="a90a5-157">The keyword, `WITH DRILLTHROUGH`, specify that you want to be able to view detailed statistics in the source data after the model is complete.</span></span> <span data-ttu-id="a90a5-158">Diese Klausel muss hinzugefügt werden, wenn Sie das Modell mit dem Microsoft Time Series-Viewer durchsuchen möchten.</span><span class="sxs-lookup"><span data-stu-id="a90a5-158">You must add this clause if you want to browse the model by using the Microsoft Time Series Viewer.</span></span> <span data-ttu-id="a90a5-159">Für Vorhersagen ist die Klausel nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a90a5-159">It is not required for prediction.</span></span>  
  
     <span data-ttu-id="a90a5-160">Die gesamte Anweisung sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="a90a5-160">The complete statement should now be as follows:</span></span>  
  
    ```  
    CREATE MINING MODEL [Forecasting_MIXED]  
         (  
        [Reporting Date] DATE KEY TIME,  
        [Model Region] TEXT KEY,  
        [Quantity] LONG CONTINUOUS PREDICT,  
        [Amount] DOUBLE CONTINUOUS PREDICT  
        )  
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = 0.8, FORECAST_METHOD = 'MIXED')  
    WITH DRILLTHROUGH  
  
    ```  
  
6.  <span data-ttu-id="a90a5-161">Klicken Sie im Menü **Datei** auf **DMXQuery1. DMX speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="a90a5-161">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="a90a5-162">Navigieren Sie im Dialogfeld **Speichern** unter in den entsprechenden Ordner, und benennen Sie die Datei `Forecasting_MIXED.dmx` .</span><span class="sxs-lookup"><span data-stu-id="a90a5-162">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Forecasting_MIXED.dmx`.</span></span>  
  
## <a name="executing-the-query"></a><span data-ttu-id="a90a5-163">Ausführen der Abfrage</span><span class="sxs-lookup"><span data-stu-id="a90a5-163">Executing the Query</span></span>  
 <span data-ttu-id="a90a5-164">Im letzten Schritt führen Sie die Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="a90a5-164">The final step is to execute the query.</span></span> <span data-ttu-id="a90a5-165">Nachdem Sie eine Abfrage erstellt und gespeichert haben, muss diese ausgeführt werden, damit das Miningmodell und die Miningstruktur auf dem Server erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a90a5-165">After a query is created and saved, it needs to be executed to create the mining model and its mining structure on the server.</span></span> <span data-ttu-id="a90a5-166">Weitere Informationen zum Ausführen von Abfragen im Abfrage-Editor finden Sie unter [Datenbank-Engine-Abfrage-Editor &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="a90a5-166">For more information about executing queries in Query Editor, see [Database Engine Query Editor &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="a90a5-167">So führen Sie die Abfrage aus</span><span class="sxs-lookup"><span data-stu-id="a90a5-167">To execute the query</span></span>  
  
-   <span data-ttu-id="a90a5-168">Klicken Sie im Abfrage-Editor auf der Symbolleiste auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a90a5-168">In Query Editor, on the toolbar, click **Execute**.</span></span>  
  
     <span data-ttu-id="a90a5-169">Der Status der Abfrage wird auf der Registerkarte **Nachrichten** unten im Abfrage-Editor angezeigt, nachdem die Ausführung der Anweisung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="a90a5-169">The status of the query is displayed in the **Messages** tab at the bottom of Query Editor after the statement finishes executing.</span></span> <span data-ttu-id="a90a5-170">Die Meldung sollte Folgendes anzeigen:</span><span class="sxs-lookup"><span data-stu-id="a90a5-170">Messages should display:</span></span>  
  
    ```  
    Executing the query   
    Execution complete  
    ```  
  
     <span data-ttu-id="a90a5-171">Auf dem Server ist nun eine neue Struktur mit dem Namen **Forecasting_MIXED_Structure** vorhanden, zusammen mit dem zugehörigen Mining Modell **Forecasting_MIXED**.</span><span class="sxs-lookup"><span data-stu-id="a90a5-171">A new structure named **Forecasting_MIXED_Structure** now exists on the server, together with the related mining model **Forecasting_MIXED**.</span></span>  
  
 <span data-ttu-id="a90a5-172">In der nächsten Lektion fügen Sie der **Forecasting_MIXED** Mining Struktur, die Sie soeben erstellt haben, ein Mining Modell hinzu.</span><span class="sxs-lookup"><span data-stu-id="a90a5-172">In the next lesson, you will add a mining model to the **Forecasting_MIXED** mining structure that you just created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="a90a5-173">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="a90a5-173">Next Lesson</span></span>  
 [<span data-ttu-id="a90a5-174">Lektion 2: Hinzufügen von Miningmodellen zur Miningstruktur für Zeitreihen</span><span class="sxs-lookup"><span data-stu-id="a90a5-174">Lesson 2: Adding Mining Models to the Time Series Mining Structure</span></span>](../../2014/tutorials/lesson-2-adding-mining-models-to-the-time-series-mining-structure.md)  
  
## <a name="see-also"></a><span data-ttu-id="a90a5-175">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a90a5-175">See Also</span></span>  
 <span data-ttu-id="a90a5-176">[Mining Modell Inhalt von Zeitreihen Modellen &#40;Analysis Services Data Mining-&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-time-series-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="a90a5-176">[Mining Model Content for Time Series Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-time-series-models-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="a90a5-177">Microsoft Time Series Algorithm Technical Reference</span><span class="sxs-lookup"><span data-stu-id="a90a5-177">Microsoft Time Series Algorithm Technical Reference</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md)  
  
  
