---
title: 'Lektion 5: Ausführen von Vorhersage Abfragen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0037bd2f-aa2d-464b-bf86-b0210f0438b1
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a5f4d6dd79f62541e207df688349f694680e2421
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719075"
---
# <a name="lesson-5-executing-prediction-queries"></a><span data-ttu-id="bef15-102">Lektion 5: Ausführen von Vorhersageabfragen</span><span class="sxs-lookup"><span data-stu-id="bef15-102">Lesson 5: Executing Prediction Queries</span></span>
  <span data-ttu-id="bef15-103">In dieser Lektion verwenden Sie die [Select from \<model> Vorhersage Join (DMX)](/sql/dmx/select-from-model-cases-dmx) -Form der SELECT-Anweisung, um basierend auf dem Entscheidungsstruktur Modell, das Sie in [Lektion 2: Hinzufügen von Mining Modellen zur Association-Mining Struktur](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md)erstellt haben, zwei unterschiedliche Vorhersage Typen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bef15-103">In this lesson, you will use the [SELECT FROM \<model> PREDICTION JOIN (DMX)](/sql/dmx/select-from-model-cases-dmx) form of the SELECT statement to create two different types of predictions based on the decision tree model you created in [Lesson 2: Adding Mining Models to the Association Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span></span> <span data-ttu-id="bef15-104">Diese Vorhersagetypen werden weiter unten definiert.</span><span class="sxs-lookup"><span data-stu-id="bef15-104">These prediction types are defined below.</span></span>  
  
 <span data-ttu-id="bef15-105">SINGLETON-Abfrage</span><span class="sxs-lookup"><span data-stu-id="bef15-105">Singleton Query</span></span>  
 <span data-ttu-id="bef15-106">Verwenden Sie eine SINGLETON-Abfrage, um Ad-hoc-Werte bereitzustellen, wenn Sie Vorhersagen treffen.</span><span class="sxs-lookup"><span data-stu-id="bef15-106">Use a singleton query to provide ad hoc values when making predictions.</span></span> <span data-ttu-id="bef15-107">Sie können beispielsweise bestimmen, ob ein einzelner Kunde wahrscheinlich ein Fahrradkäufer ist, indem Sie Eingaben wie die Pendelstrecke, die Postleitzahl oder die Anzahl der Kinder des Kunden an die Abfrage übergeben.</span><span class="sxs-lookup"><span data-stu-id="bef15-107">For example, you can determine whether a single customer is likely to be a bike buyer, by passing inputs to the query such as the commute distance, the area code, or the number of children of the customer.</span></span> <span data-ttu-id="bef15-108">Die SINGLETON-Abfrage gibt basierend auf diesen Eingaben einen Wert zurück, der angibt, wie wahrscheinlich es ist, dass die Person ein Fahrrad kauft.</span><span class="sxs-lookup"><span data-stu-id="bef15-108">The singleton query returns a value that indicates how likely the person is to purchase a bicycle based on those inputs.</span></span>  
  
 <span data-ttu-id="bef15-109">Batchabfrage</span><span class="sxs-lookup"><span data-stu-id="bef15-109">Batch Query</span></span>  
 <span data-ttu-id="bef15-110">Verwenden Sie eine Batchabfrage, um zu bestimmen, wer in einer Tabelle möglicher Kunden wahrscheinlich ein Fahrrad kaufen wird.</span><span class="sxs-lookup"><span data-stu-id="bef15-110">Use a batch query to determine who in a table of potential customers is likely to purchase a bicycle.</span></span> <span data-ttu-id="bef15-111">Wenn Sie beispielsweise von der Marketingabteilung eine Liste mit Kunden und Kundenattributen erhalten, können Sie mithilfe einer Batchvorhersage bestimmen, wer wahrscheinlich ein Fahrrad kaufen wird.</span><span class="sxs-lookup"><span data-stu-id="bef15-111">For example, if your marketing department provides you with a list of customers and customer attributes, then you can use a batch prediction to determine who from the table is likely to purchase a bicycle.</span></span>  
  
 <span data-ttu-id="bef15-112">Das Formular [Select from \<model> Vorhersage Join (DMX)](/sql/dmx/select-from-model-cases-dmx) der SELECT-Anweisung enthält drei Teile:</span><span class="sxs-lookup"><span data-stu-id="bef15-112">The [SELECT FROM \<model> PREDICTION JOIN (DMX)](/sql/dmx/select-from-model-cases-dmx) form of the SELECT statement contains three parts:</span></span>  
  
-   <span data-ttu-id="bef15-113">Einer Liste der Miningmodellspalten und Vorhersagefunktionen, die in den Ergebnissen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bef15-113">A list of the mining model columns and prediction functions that are returned in the results.</span></span> <span data-ttu-id="bef15-114">Die Ergebnisse können auch Eingabespalten aus den Quelldaten enthalten.</span><span class="sxs-lookup"><span data-stu-id="bef15-114">The results can also contain input columns from the source data.</span></span>  
  
-   <span data-ttu-id="bef15-115">Der Quellabfrage, die die zum Erstellen einer Vorhersage verwendeten Daten definiert.</span><span class="sxs-lookup"><span data-stu-id="bef15-115">The source query defining the data that is being used to create a prediction.</span></span> <span data-ttu-id="bef15-116">In einer Batchabfrage könnte dies beispielsweise eine Kundenliste sein.</span><span class="sxs-lookup"><span data-stu-id="bef15-116">For example, in a batch query this could be a list of customers.</span></span>  
  
-   <span data-ttu-id="bef15-117">Einer Zuordnung von Miningmodellspalten und Quelldaten.</span><span class="sxs-lookup"><span data-stu-id="bef15-117">A mapping between the mining model columns and the source data.</span></span> <span data-ttu-id="bef15-118">Wenn diese Namen übereinstimmen, können Sie NATURAL-Syntax verwenden und auf die Spaltenzuordnungen verzichten.</span><span class="sxs-lookup"><span data-stu-id="bef15-118">If these names match, then you can use NATURAL syntax and leave out the column mappings.</span></span>  
  
 <span data-ttu-id="bef15-119">Mithilfe von Vorhersagefunktionen lässt sich die Abfrage zusätzlich optimieren.</span><span class="sxs-lookup"><span data-stu-id="bef15-119">You can further enhance the query by using prediction functions.</span></span> <span data-ttu-id="bef15-120">Vorhersagefunktionen stellen zusätzliche Informationen bereit, z. B. die Wahrscheinlichkeit des Eintreffens einer Vorhersage; außerdem bieten sie Unterstützung für die Vorhersage im Trainings-Dataset.</span><span class="sxs-lookup"><span data-stu-id="bef15-120">Prediction functions provide additional information, such as the probability of a prediction occurring, and provide support for the prediction in the training dataset.</span></span> <span data-ttu-id="bef15-121">Weitere Informationen zu Vorhersagefunktionen finden Sie unter [Functions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="bef15-121">For more information about prediction functions, see [Functions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span></span>  
  
 <span data-ttu-id="bef15-122">Die Vorhersagen in diesem Lernprogramm basieren auf der ProspectiveBuyer-Tabelle in der [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)]-Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="bef15-122">The predictions in this tutorial are based on the ProspectiveBuyer table in the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample database.</span></span> <span data-ttu-id="bef15-123">Die ProspectiveBuyer-Tabelle enthält eine Liste potenzieller Kunden und die Merkmale dieser Kunden.</span><span class="sxs-lookup"><span data-stu-id="bef15-123">The ProspectiveBuyer table contains a list of potential customers and their associated characteristics.</span></span> <span data-ttu-id="bef15-124">Die Kunden in dieser Tabelle sind von den zum Erstellen des Entscheidungsstruktur-Miningmodells verwendeten Kunden unabhängig.</span><span class="sxs-lookup"><span data-stu-id="bef15-124">The customers in this table are independent of the customers that were used to create the decision tree mining model.</span></span>  
  
 <span data-ttu-id="bef15-125">Vorhersagen können auch mit dem Generator für Vorhersageabfragen in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="bef15-125">You can also create predictions by using the prediction query builder in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="bef15-126">Lektionsaufgaben</span><span class="sxs-lookup"><span data-stu-id="bef15-126">Lesson Tasks</span></span>  
 <span data-ttu-id="bef15-127">Im Rahmen dieser Lektion führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="bef15-127">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="bef15-128">Erstellen einer SINGLETON-Abfrage, um zu ermitteln, ob ein bestimmter Kunde wahrscheinlich ein Fahrrad kaufen wird.</span><span class="sxs-lookup"><span data-stu-id="bef15-128">Create a singleton query to determine whether a specific customer is likely to purchase a bicycle.</span></span>  
  
-   <span data-ttu-id="bef15-129">Erstellen einer Batchabfrage, um zu bestimmen, wer in einer Tabelle möglicher Kunden wahrscheinlich ein Fahrrad kaufen wird.</span><span class="sxs-lookup"><span data-stu-id="bef15-129">Create a batch query to determine which customers, listed in a table of customers, are likely to purchase a bicycle.</span></span>  
  
## <a name="singleton-query"></a><span data-ttu-id="bef15-130">SINGLETON-Abfrage</span><span class="sxs-lookup"><span data-stu-id="bef15-130">Singleton Query</span></span>  
 <span data-ttu-id="bef15-131">Der erste Schritt besteht darin, das [Select from &#60;Model&#62; Vorhersage Join &#40;DMX-&#41;](/sql/dmx/select-from-model-cases-dmx) in einer SINGLETON-Vorhersage Abfrage zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="bef15-131">The first step is to use the [SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) in a singleton prediction query.</span></span> <span data-ttu-id="bef15-132">Es folgt ein allgemeines Beispiel für die SINGLETON-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="bef15-132">The following is a generic example of the singleton statement:</span></span>  
  
```  
SELECT <select list> FROM [<mining model name>]   
NATURAL PREDICTION JOIN  
(SELECT '<value>' AS [<column>], ...)  
AS [<input alias>]  
```  
  
 <span data-ttu-id="bef15-133">In der ersten Codezeile werden die Spalten des Miningmodells definiert, das die Abfrage zurückgibt, und der Name des Miningmodells angegeben, mit dem die Vorhersage generiert wurde:</span><span class="sxs-lookup"><span data-stu-id="bef15-133">The first line of the code defines the columns from the mining model that the query should return, and specifies the mining model that is used to generate the prediction:</span></span>  
  
```  
SELECT <select list> FROM [<mining model name>]   
```  
  
 <span data-ttu-id="bef15-134">In den nächsten Codezeilen werden die Merkmale des Kunden definiert, die Sie zum Erstellen einer Vorhersage verwenden:</span><span class="sxs-lookup"><span data-stu-id="bef15-134">The next lines of the code define the characteristics of the customer that you use to create a prediction:</span></span>  
  
```  
NATURAL PREDICTION JOIN  
(SELECT '<value>' AS [<column>], ...)  
AS [<input alias>]  
ORDER BY <expression>  
```  
  
 <span data-ttu-id="bef15-135">Wenn Sie NATURAL PREDICTION JOIN angeben, gleicht der Server den Namen jeder Spalte aus dem Modell mit den Namen der Spalten aus der Eingabe ab.</span><span class="sxs-lookup"><span data-stu-id="bef15-135">If you specify NATURAL PREDICTION JOIN, the server matches each column from the model to a column from the input, based on column names.</span></span> <span data-ttu-id="bef15-136">Wenn Spaltennamen nicht übereinstimmen, werden die Spalten ignoriert.</span><span class="sxs-lookup"><span data-stu-id="bef15-136">If column names do not match, the columns are ignored.</span></span>  
  
#### <a name="to-create-a-singleton-prediction-query"></a><span data-ttu-id="bef15-137">So erstellen Sie eine SINGLETON-Vorhersageabfrage</span><span class="sxs-lookup"><span data-stu-id="bef15-137">To create a singleton prediction query</span></span>  
  
1.  <span data-ttu-id="bef15-138">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , zeigen Sie auf **neue Abfrage**, und klicken Sie dann auf **DMX**.</span><span class="sxs-lookup"><span data-stu-id="bef15-138">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="bef15-139">Der Abfrage-Editor wird mit einer neuen leeren Abfrage geöffnet.</span><span class="sxs-lookup"><span data-stu-id="bef15-139">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="bef15-140">Kopieren Sie das allgemeine Beispiel der SINGLETON-Anweisung in die leere Abfrage.</span><span class="sxs-lookup"><span data-stu-id="bef15-140">Copy the generic example of the singleton statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="bef15-141">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="bef15-141">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="bef15-142">durch:</span><span class="sxs-lookup"><span data-stu-id="bef15-142">with:</span></span>  
  
    ```  
    [Bike Buyer] AS Buyer, PredictHistogram([Bike Buyer]) AS Statistics  
    ```  
  
     <span data-ttu-id="bef15-143">Die AS-Anweisung wird verwendet, um einen Alias für von der Abfrage zurückgegebene Spalten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bef15-143">The AS statement is used to alias columns returned by the query.</span></span> <span data-ttu-id="bef15-144">Die Funktion " [präthistogram](/sql/dmx/predicthistogram-dmx) " gibt Statistiken zur Vorhersage zurück, einschließlich der Wahrscheinlichkeit und der Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="bef15-144">The [PredictHistogram](/sql/dmx/predicthistogram-dmx) function returns statistics about the prediction, including the probability and the support.</span></span> <span data-ttu-id="bef15-145">Weitere Informationen zu den Funktionen, die in einer Vorhersage Anweisung verwendet werden können, finden Sie unter [Functions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="bef15-145">For more information about the functions that can be used in a prediction statement, see [Functions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span></span>  
  
4.  <span data-ttu-id="bef15-146">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="bef15-146">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="bef15-147">durch:</span><span class="sxs-lookup"><span data-stu-id="bef15-147">with:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
5.  <span data-ttu-id="bef15-148">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="bef15-148">Replace the following:</span></span>  
  
    ```  
    (SELECT '<value>' AS [<column name>], ...)  AS t  
    ```  
  
     <span data-ttu-id="bef15-149">durch:</span><span class="sxs-lookup"><span data-stu-id="bef15-149">with:</span></span>  
  
    ```  
    (SELECT 35 AS [Age],  
      '5-10 Miles' AS [Commute Distance],  
      '1' AS [House Owner Flag],  
      2 AS [Number Cars Owned],  
      2 AS [Total Children]) AS t  
    ```  
  
     <span data-ttu-id="bef15-150">Die gesamte Anweisung sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="bef15-150">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
       [Bike Buyer] AS Buyer,  
       PredictHistogram([Bike Buyer]) AS Statistics  
    FROM  
       [Decision Tree]  
    NATURAL PREDICTION JOIN  
    (SELECT 35 AS [Age],  
       '5-10 Miles' AS [Commute Distance],  
       '1' AS [House Owner Flag],  
       2 AS [Number Cars Owned],  
       2 AS [Total Children]) AS t  
    ```  
  
6.  <span data-ttu-id="bef15-151">Klicken Sie im Menü **Datei** auf **DMXQuery1. DMX speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="bef15-151">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="bef15-152">Navigieren Sie im Dialogfeld **Speichern** unter in den entsprechenden Ordner, und benennen Sie die Datei `Singleton_Query.dmx` .</span><span class="sxs-lookup"><span data-stu-id="bef15-152">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Singleton_Query.dmx`.</span></span>  
  
8.  <span data-ttu-id="bef15-153">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="bef15-153">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="bef15-154">Die Abfrage gibt eine Vorhersage dazu zurück, ob ein Kunde mit den angegebenen Merkmalen ein Fahrrad kaufen wird, und sie stellt statistische Informationen zu der betreffenden Vorhersage zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="bef15-154">The query returns a prediction about whether a customer with the specified characteristics will purchase a bicycle, as well as statistics about that prediction.</span></span>  
  
## <a name="batch-query"></a><span data-ttu-id="bef15-155">Batchabfrage</span><span class="sxs-lookup"><span data-stu-id="bef15-155">Batch Query</span></span>  
 <span data-ttu-id="bef15-156">Der nächste Schritt besteht darin, das [Select from &#60;Model&#62; Vorhersage Join &#40;DMX-&#41;](/sql/dmx/select-from-model-cases-dmx) in einer Batch Vorhersage Abfrage zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="bef15-156">The next step is to use the [SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) in a batch prediction query.</span></span> <span data-ttu-id="bef15-157">Das folgende Beispiel ist ein allgemeines Beispiel für eine Batchanweisung:</span><span class="sxs-lookup"><span data-stu-id="bef15-157">The following is a generic example of a batch statement:</span></span>  
  
```  
SELECT TOP <number> <select list>   
FROM [<mining model name>]  
PREDICTION JOIN  
OPENQUERY([<datasource>],'<SELECT statement>')  
  AS [<input alias>]  
ON <on clause, mapping,>  
WHERE <where clause, boolean expression,>  
ORDER BY <expression>  
```  
  
 <span data-ttu-id="bef15-158">Wie in der SINGLETON-Abfrage definieren die ersten beiden Codezeilen die Spalten aus dem von der Abfrage zurückgegebenen Miningmodell sowie aus dem Namen des zum Generieren der Vorhersage verwendeten Miningmodells.</span><span class="sxs-lookup"><span data-stu-id="bef15-158">As in the singleton query, the first two lines of the code define the columns from mining model that the query returns, as well as the name of the mining model that is used to generate the prediction.</span></span> <span data-ttu-id="bef15-159">Die Top- \<number> Anweisung gibt an, dass die Abfrage nur die Anzahl oder die durch angegebenen Ergebnisse zurückgibt \<number> .</span><span class="sxs-lookup"><span data-stu-id="bef15-159">The TOP \<number> statement specifies that the query will only return the number or the results specified by \<number>.</span></span>  
  
 <span data-ttu-id="bef15-160">Die nächsten Codezeilen definieren die Quelldaten, auf denen die Vorhersagen basieren:</span><span class="sxs-lookup"><span data-stu-id="bef15-160">The next lines of the code define the source data that the predictions are based on:</span></span>  
  
```  
OPENQUERY([<datasource>],'<SELECT statement>')  
  AS [<input alias>]  
```  
  
 <span data-ttu-id="bef15-161">Für das Abrufen von Quelldaten stehen Ihnen eine Reihe verschiedener Optionen zur Verfügung, jedoch verwenden Sie in diesem Lernprogramm OPENQUERY.</span><span class="sxs-lookup"><span data-stu-id="bef15-161">You have several options for the method of retrieving the source data, but in this tutorial, you will use OPENQUERY.</span></span> <span data-ttu-id="bef15-162">Weitere Informationen zu den verfügbaren Optionen finden Sie unter [&#60;Quelldaten Abfrage&#62;](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="bef15-162">For more information about the options available, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
 <span data-ttu-id="bef15-163">Die nächste Zeile definiert die Zuordnung zwischen den Quellspalten im Miningmodell und den Spalten in den Quelldaten:</span><span class="sxs-lookup"><span data-stu-id="bef15-163">The next line defines the mapping between the source columns in the mining model and the columns in the source data:</span></span>  
  
```  
ON <column mappings>  
```  
  
 <span data-ttu-id="bef15-164">Die WHERE-Klausel filtert die von der Vorhersageabfrage zurückgegebenen Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="bef15-164">The WHERE clause filters the results returned by the prediction query:</span></span>  
  
```  
WHERE <where clause, boolean expression,>  
```  
  
 <span data-ttu-id="bef15-165">Die letzte und optionale Zeile des Codes gibt die Spalte an, nach der die Ergebnisse sortiert werden:</span><span class="sxs-lookup"><span data-stu-id="bef15-165">The last and optional line of the code specifies the column that the results will be ordered by:</span></span>  
  
```  
ORDER BY <expression> [DESC|ASC]  
```  
  
 <span data-ttu-id="bef15-166">Verwenden Sie Order by in Kombination mit der Top- \<number> Anweisung, um die zurückgegebenen Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="bef15-166">Use ORDER BY in combination with the TOP \<number> statement, to filter the results that are returned.</span></span> <span data-ttu-id="bef15-167">In dieser Vorhersage geben Sie z. B. die obersten 10 Fahrradkäufer zurück (sortiert nach der Wahrscheinlichkeit, dass die Vorhersage richtig ist).</span><span class="sxs-lookup"><span data-stu-id="bef15-167">For example, in this prediction you will return the top ten bike buyers, ordered by the probability of the prediction being correct.</span></span> <span data-ttu-id="bef15-168">Mithilfe der [DESC|ASC]-Syntax können Sie festlegen, in welcher Reihenfolge die Ergebnisse angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bef15-168">You can use [DESC|ASC] syntax to control the order in which the results are displayed.</span></span>  
  
#### <a name="to-create-a-batch-prediction-query"></a><span data-ttu-id="bef15-169">So erstellen Sie eine Batchvorhersageabfrage</span><span class="sxs-lookup"><span data-stu-id="bef15-169">To create a batch prediction query</span></span>  
  
1.  <span data-ttu-id="bef15-170">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , zeigen Sie auf **neue Abfrage**, und klicken Sie dann auf **DMX**.</span><span class="sxs-lookup"><span data-stu-id="bef15-170">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="bef15-171">Der Abfrage-Editor wird mit einer neuen leeren Abfrage geöffnet.</span><span class="sxs-lookup"><span data-stu-id="bef15-171">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="bef15-172">Kopieren Sie das allgemeine Beispiel der Batchanweisung in die leere Abfrage.</span><span class="sxs-lookup"><span data-stu-id="bef15-172">Copy the generic example of the batch statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="bef15-173">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="bef15-173">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="bef15-174">durch:</span><span class="sxs-lookup"><span data-stu-id="bef15-174">with:</span></span>  
  
    ```  
    SELECT  
      TOP 10  
      t.[LastName],  
      t.[FirstName],  
      [Decision Tree].[Bike Buyer],  
      PredictProbability([Bike Buyer])  
    ```  
  
     <span data-ttu-id="bef15-175">Die TOP 10-Klausel gibt an, dass nur die ersten zehn Ergebnisse von der Abfrage zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bef15-175">The TOP 10 clause specifies that only the top ten results will be returned by the query.</span></span> <span data-ttu-id="bef15-176">Mit der ORDER BY-Anweisung in dieser Abfrage werden die Ergebnisse nach der Wahrscheinlichkeit, dass die Vorhersage richtig ist, sortiert. Dies bedeutet, dass nur die zehn Ergebnisse mit der höchsten Wahrscheinlichkeit zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bef15-176">The ORDER BY statement in this query orders the results by the probability of the prediction being correct, so only the ten most likely results will be returned.</span></span>  
  
4.  <span data-ttu-id="bef15-177">Ersetzen Sie den folgenden Platzhalter:</span><span class="sxs-lookup"><span data-stu-id="bef15-177">Replace the following placeholder:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="bef15-178">Durch den Namen des Modells:</span><span class="sxs-lookup"><span data-stu-id="bef15-178">With the name of the model:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
5.  <span data-ttu-id="bef15-179">Ersetzen Sie die folgende generische OPENQUERY-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="bef15-179">Replace the following generic OPENQUERY statement:</span></span>  
  
    ```  
    OPENQUERY([<datasource>],'<SELECT statement>')  
    ```  
  
     <span data-ttu-id="bef15-180">Durch eine Anweisung, die auf das aktuelle Adventureworks-Data Warehouse verweist, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="bef15-180">With a statement that references the current Adventureworks data warehouse, such as:</span></span>  
  
    ```  
    OPENQUERY([Adventure Works DW 2014],  
      'SELECT  
        [LastName],  
        [FirstName],  
        [MaritalStatus],  
        [Gender],  
        [YearlyIncome],  
        [TotalChildren],  
        [NumberChildrenAtHome],  
        [Education],  
        [Occupation],  
        [HouseOwnerFlag],  
        [NumberCarsOwned]  
      FROM  
        [dbo].[ProspectiveBuyer]  
      ') AS t  
    ```  
  
6.  <span data-ttu-id="bef15-181">Ersetzen Sie die folgende generische Syntax:</span><span class="sxs-lookup"><span data-stu-id="bef15-181">Replace the following generic syntax:</span></span>  
  
    ```  
    <ON clause, mapping,>   
    WHERE <where clause, boolean expression,>  
    ORDER BY <expression>  
    ```  
  
     <span data-ttu-id="bef15-182">Durch die Spaltenzuordnungen, die für dieses Modell und Eingabedataset erforderlich sind:</span><span class="sxs-lookup"><span data-stu-id="bef15-182">With the column mappings needed for this model and input data set:</span></span>  
  
    ```  
    [Decision Tree].[Marital Status] = t.[MaritalStatus] AND  
      [Decision Tree].[Gender] = t.[Gender] AND  
      [Decision Tree].[Yearly Income] = t.[YearlyIncome] AND  
      [Decision Tree].[Total Children] = t.[TotalChildren] AND  
      [Decision Tree].[Number Children At Home] = t.[NumberChildrenAtHome] AND  
      [Decision Tree].[Education] = t.[Education] AND  
      [Decision Tree].[Occupation] = t.[Occupation] AND  
      [Decision Tree].[House Owner Flag] = t.[HouseOwnerFlag] AND  
      [Decision Tree].[Number Cars Owned] = t.[NumberCarsOwned]  
    WHERE [Decision Tree].[Bike Buyer] =1  
    ORDER BY PredictProbability([Bike Buyer]) DESC  
    ```  
  
     <span data-ttu-id="bef15-183">Geben Sie `DESC` an, um die Ergebnisse mit der höchsten Wahrscheinlichkeit zuerst aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="bef15-183">Specify `DESC` in order to list the results with the highest probability first.</span></span>  
  
     <span data-ttu-id="bef15-184">Die gesamte Anweisung sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="bef15-184">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
      TOP 10  
      t.[LastName],  
      t.[FirstName],  
      [Decision Tree].[Bike Buyer],  
      PredictProbability([Bike Buyer])  
    FROM  
      [Decision Tree]  
    PREDICTION JOIN  
      OPENQUERY([Adventure Works DW 2014],  
        'SELECT  
          [LastName],  
          [FirstName],  
          [MaritalStatus],  
          [Gender],  
          [YearlyIncome],  
          [TotalChildren],  
          [NumberChildrenAtHome],  
          [Education],  
          [Occupation],  
          [HouseOwnerFlag],  
          [NumberCarsOwned]  
        FROM  
          [dbo].[ProspectiveBuyer]  
        ') AS t  
    ON  
      [Decision Tree].[Marital Status] = t.[MaritalStatus] AND  
      [Decision Tree].[Gender] = t.[Gender] AND  
      [Decision Tree].[Yearly Income] = t.[YearlyIncome] AND  
      [Decision Tree].[Total Children] = t.[TotalChildren] AND  
      [Decision Tree].[Number Children At Home] = t.[NumberChildrenAtHome] AND  
      [Decision Tree].[Education] = t.[Education] AND  
      [Decision Tree].[Occupation] = t.[Occupation] AND  
      [Decision Tree].[House Owner Flag] = t.[HouseOwnerFlag] AND  
      [Decision Tree].[Number Cars Owned] = t.[NumberCarsOwned]  
    WHERE [Decision Tree].[Bike Buyer] =1  
    ORDER BY PredictProbability([Bike Buyer]) DESC  
    ```  
  
7.  <span data-ttu-id="bef15-185">Klicken Sie im Menü **Datei** auf **DMXQuery1. DMX speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="bef15-185">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="bef15-186">Navigieren Sie im Dialogfeld **Speichern** unter in den entsprechenden Ordner, und benennen Sie die Datei `Batch_Prediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="bef15-186">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Batch_Prediction.dmx`.</span></span>  
  
9. <span data-ttu-id="bef15-187">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="bef15-187">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="bef15-188">Die Abfrage gibt eine Tabelle mit Kundennamen zurück, eine Vorhersage dazu, ob jeder Kunde ein Fahrrad kaufen wird, und die Wahrscheinlichkeit des Eintreffens der Vorhersage.</span><span class="sxs-lookup"><span data-stu-id="bef15-188">The query returns a table containing customer names, a prediction of whether each customer will purchase a bicycle, and the probability of the prediction.</span></span>  
  
 <span data-ttu-id="bef15-189">Dies ist der letzte Schritt im Bike Buyer-Lernprogramm.</span><span class="sxs-lookup"><span data-stu-id="bef15-189">This is the last step in the Bike Buyer tutorial.</span></span> <span data-ttu-id="bef15-190">Sie verfügen jetzt über mehrere Miningmodelle, mit denen Sie Ähnlichkeiten zwischen Ihren Kunden untersuchen und vorhersagen können, ob potenzielle Kunden ein Fahrrad kaufen werden.</span><span class="sxs-lookup"><span data-stu-id="bef15-190">You now have a set of mining models that you can use to explore similarities between you customers and predict whether potential customers will purchase a bicycle.</span></span>  
  
 <span data-ttu-id="bef15-191">Informationen zur Verwendung von DMX in einem Market Basket-Szenario finden Sie unter [Market Basket DMX Tutorial](../../2014/tutorials/market-basket-dmx-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="bef15-191">To learn how to use DMX in a Market Basket scenario, see [Market Basket DMX Tutorial](../../2014/tutorials/market-basket-dmx-tutorial.md).</span></span>  
  
  
