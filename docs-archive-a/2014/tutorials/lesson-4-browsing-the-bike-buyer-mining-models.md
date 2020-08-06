---
title: 'Lektion 4: Durchsuchen der Bike Buyer-Mining Modelle | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8de3c500-f881-42da-a096-b6c03300d58d
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 709df371d840d4b24e420b4fcd08750fd31e8075
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616879"
---
# <a name="lesson-4-browsing-the-bike-buyer-mining-models"></a><span data-ttu-id="cb2b7-102">Lektion 4: Durchsuchen des Bike Buyer-Miningmodells</span><span class="sxs-lookup"><span data-stu-id="cb2b7-102">Lesson 4: Browsing the Bike Buyer Mining Models</span></span>
  <span data-ttu-id="cb2b7-103">In dieser Lektion verwenden Sie die SELECT-Anweisung [(DMX)](/sql/dmx/select-dmx) zum Durchsuchen des Inhalts in den Entscheidungsstruktur-und Clustering-Mining Modellen, die Sie in [Lektion 2: Hinzufügen von Mining Modellen zur Vorhersage Mining Struktur](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md)erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-103">In this lesson, you will use the [SELECT (DMX)](/sql/dmx/select-dmx) statement to explore the content in the decision tree and clustering mining models that you created in [Lesson 2: Adding Mining Models to the Predictive Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span></span>  
  
 <span data-ttu-id="cb2b7-104">Die in einem Miningmodell enthaltenen Spalten entsprechen nicht den Spalten, die durch die Miningstruktur definiert werden; stattdessen handelt es sich um eine bestimmte Gruppe von Spalten, die die vom Algorithmus ermittelten Tendenzen und Muster beschreiben.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-104">The columns contained in a mining model are not the columns defined by the mining structure, but instead are a specific set of columns that describe the trends and patterns that are found by the algorithm.</span></span> <span data-ttu-id="cb2b7-105">Diese Mining Modell Spalten werden im [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset) -Schemarowset beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-105">These mining model columns are described in the [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset) schema rowset.</span></span> <span data-ttu-id="cb2b7-106">Beispielsweise enthält die MODEL_NAME-Spalte im Schemarowset für den Inhalt den Namen des Miningmodells.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-106">For example, the MODEL_NAME column in the content schema rowset contains the name of the mining model.</span></span> <span data-ttu-id="cb2b7-107">Für ein Clustering-Miningmodell enthält die NODE_CAPTION-Spalte den Namen des jeweiligen Clusters und die NODE_DESCRIPTION-Spalte eine Beschreibung der Merkmale des jeweiligen Clusters.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-107">For a clustering mining model, the NODE_CAPTION column contains the name of each cluster, and the NODE_DESCRIPTION column contains a description of the characteristics of each cluster.</span></span> <span data-ttu-id="cb2b7-108">Sie können diese Spalten durchsuchen, indem Sie die Select from-Option verwenden \<model> . Die Content-Anweisung in DMX.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-108">You can browse these columns by using the SELECT FROM \<model>.CONTENT statement in DMX.</span></span> <span data-ttu-id="cb2b7-109">Sie können diese Anweisung auch verwenden, um die zum Erstellen des Miningmodells verwendeten Daten zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-109">You can also use this statement to explore the data that was used to create the mining model.</span></span> <span data-ttu-id="cb2b7-110">Drillthrough muss in der Miningstruktur aktiviert sein, um diese Anweisung verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-110">Drillthrough must be enabled on the mining structure in order to use this statement.</span></span> <span data-ttu-id="cb2b7-111">Weitere Informationen zur-Anweisung finden Sie unter [Select from &#60;Model&#62;. Fälle &#40;DMX-&#41;](/sql/dmx/select-from-model-content-dmx).</span><span class="sxs-lookup"><span data-stu-id="cb2b7-111">For more information about the statement, see [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx).</span></span>  
  
 <span data-ttu-id="cb2b7-112">Sie können auch alle Statuswerte einer diskreten Spalte zurückgeben, indem Sie die SELECT DISTINCT-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-112">You can also return all the states of a discrete column by using the SELECT DISTINCT statement.</span></span> <span data-ttu-id="cb2b7-113">Wenn Sie diesen Vorgang beispielsweise für eine Geschlechterspalte durchführen, gibt die Abfrage `male` und `female` zurück.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-113">For example, if you perform this operation on a gender column, the query will return `male` and `female`.</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="cb2b7-114">Lektionsaufgaben</span><span class="sxs-lookup"><span data-stu-id="cb2b7-114">Lesson Tasks</span></span>  
 <span data-ttu-id="cb2b7-115">Im Rahmen dieser Lektion führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-115">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="cb2b7-116">Durchsuchen des Inhalts der Miningmodelle</span><span class="sxs-lookup"><span data-stu-id="cb2b7-116">Explore the content contained within the mining models</span></span>  
  
-   <span data-ttu-id="cb2b7-117">Zurückgeben der Fälle aus den Quelldaten, die zum Trainieren der Miningmodelle verwendet wurden</span><span class="sxs-lookup"><span data-stu-id="cb2b7-117">Return the cases from the source data that was used to train the mining models</span></span>  
  
-   <span data-ttu-id="cb2b7-118">Prüfen der verschiedenen Status, die für eine bestimmte diskrete Spalte zur Verfügung stehen</span><span class="sxs-lookup"><span data-stu-id="cb2b7-118">Explore the different states available for a specific discrete column</span></span>  
  
## <a name="returning-the-content-of-a-mining-model"></a><span data-ttu-id="cb2b7-119">Zurückgeben des Inhalts eines Miningmodells</span><span class="sxs-lookup"><span data-stu-id="cb2b7-119">Returning the Content of a Mining Model</span></span>  
 <span data-ttu-id="cb2b7-120">In dieser Lektion verwenden Sie das [&#62; Select from &#60;Model. Inhalt &#40;DMX-&#41;](/sql/dmx/select-from-model-dimension-content-dmx) Anweisung, um den Inhalt des Clustering-Modells zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-120">In this lesson, you use the [SELECT FROM &#60;model&#62;.CONTENT &#40;DMX&#41;](/sql/dmx/select-from-model-dimension-content-dmx) statement to return the contents of the clustering model.</span></span>  
  
 <span data-ttu-id="cb2b7-121">Im folgenden finden Sie ein allgemeines Beispiel für SELECT FROM \<model> . Inhalts Anweisung:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-121">The following is a generic example of the SELECT FROM \<model>.CONTENT statement:</span></span>  
  
```  
SELECT <select list> FROM [<mining model>].CONTENT  
WHERE <where clause>  
```  
  
 <span data-ttu-id="cb2b7-122">Die erste Codezeile definiert die vom Inhalt des Miningmodells zurückzugebenden Spalten und das Miningmodell, dem sie zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-122">The first line of the code defines the columns to return from the mining model content, and the mining model they are associated with:</span></span>  
  
```  
SELECT <select list> FROM [<mining model].CONTENT  
```  
  
 <span data-ttu-id="cb2b7-123">Die .CONTENT-Klausel neben dem Namen des Miningmodells gibt an, dass Inhalt aus dem Miningmodell zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-123">The .CONTENT clause next to the name of the mining model specifies that you are returning content from the mining model.</span></span> <span data-ttu-id="cb2b7-124">Weitere Informationen zu den Spalten, die im Mining Modell enthalten sind, finden Sie unter [DMSCHEMA_MINING_MODEL_CONTENT-Rowsets](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span><span class="sxs-lookup"><span data-stu-id="cb2b7-124">For more information about the columns contained in the mining model, see [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span></span>  
  
 <span data-ttu-id="cb2b7-125">Optional können Sie die letzte Codezeile zum Filtern der von der Anweisung zurückgegebenen Ergebnisse verwenden:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-125">You can optionally use the final line of the code to filter the results returned by the statement:</span></span>  
  
```  
WHERE <where clause>  
```  
  
 <span data-ttu-id="cb2b7-126">Wenn Sie beispielsweise die Ergebnisse der Abfrage auf die Cluster beschränken möchten, die eine hohe Anzahl von Fällen enthalten, können Sie der SELECT-Anweisung die folgende WHERE-Klausel hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-126">For example, if you want to restrict the results of the query to only the clusters that contain a high number of cases, you can add the following WHERE clause to the SELECT statement:</span></span>  
  
```  
WHERE NODE_SUPPORT > 100  
```  
  
 <span data-ttu-id="cb2b7-127">Weitere Informationen zum Verwenden der WHERE-Anweisung finden [Sie unter SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span><span class="sxs-lookup"><span data-stu-id="cb2b7-127">For more information about using the WHERE statement, see [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span></span>  
  
#### <a name="to-return-the-content-of-the-clustering-mining-model"></a><span data-ttu-id="cb2b7-128">So geben Sie den Inhalt des Clustering-Miningmodells zurück</span><span class="sxs-lookup"><span data-stu-id="cb2b7-128">To return the content of the clustering mining model</span></span>  
  
1.  <span data-ttu-id="cb2b7-129">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , zeigen Sie auf **neue Abfrage**, und klicken Sie dann auf **DMX**.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-129">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="cb2b7-130">Der Abfrage-Editor wird mit einer neuen leeren Abfrage geöffnet.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-130">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="cb2b7-131">Kopieren Sie das allgemeine Beispiel für SELECT FROM \<model> . Inhalts Anweisung in die leere Abfrage.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-131">Copy the generic example of the SELECT FROM \<model>.CONTENT statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="cb2b7-132">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-132">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="cb2b7-133">durch:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-133">with:</span></span>  
  
    ```  
    *  
    ```  
  
     <span data-ttu-id="cb2b7-134">Sie können \* auch durch eine Liste aller Spalten ersetzen, die im [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset)enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-134">You can also replace \* with a list of any of the columns contained within the [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span></span>  
  
4.  <span data-ttu-id="cb2b7-135">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-135">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="cb2b7-136">durch:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-136">with:</span></span>  
  
    ```  
    [Clustering]  
    ```  
  
     <span data-ttu-id="cb2b7-137">Die gesamte Anweisung sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-137">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT * FROM [Clustering].CONTENT  
    ```  
  
5.  <span data-ttu-id="cb2b7-138">Klicken Sie im Menü **Datei** auf **DMXQuery1. DMX speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-138">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="cb2b7-139">Navigieren Sie im Dialogfeld **Speichern** unter in den entsprechenden Ordner, und benennen Sie die Datei `SELECT_CONTENT.dmx` .</span><span class="sxs-lookup"><span data-stu-id="cb2b7-139">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SELECT_CONTENT.dmx`.</span></span>  
  
7.  <span data-ttu-id="cb2b7-140">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="cb2b7-140">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="cb2b7-141">Die Abfrage gibt den Inhalt des Miningmodells zurück.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-141">The query returns the content of the mining model.</span></span>  
  
## <a name="use-drillthrough"></a><span data-ttu-id="cb2b7-142">Verwenden von Drillthrough</span><span class="sxs-lookup"><span data-stu-id="cb2b7-142">Use Drillthrough</span></span>  
 <span data-ttu-id="cb2b7-143">Im nächsten Schritt verwenden Sie die Drillthroughanweisung, um eine Stichprobe der Fälle zurückzugeben, die zum Trainieren des Decision Tree-Miningmodells verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-143">The next step is to use the drillthrough statement to return a sampling of the cases that were used to train the decision tree mining model.</span></span> <span data-ttu-id="cb2b7-144">In dieser Lektion verwenden Sie das [&#62; Select from &#60;Model. Fälle &#40;DMX-&#41;](/sql/dmx/select-from-model-content-dmx) Anweisung, um den Inhalt des Entscheidungsstruktur Modells zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-144">In this lesson, you use the [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx) statement to return the contents of the decision tree model.</span></span>  
  
 <span data-ttu-id="cb2b7-145">Im folgenden finden Sie ein allgemeines Beispiel für SELECT FROM \<model> . Cases-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-145">The following is a generic example of the SELECT FROM \<model>.CASES statement:</span></span>  
  
```  
SELECT <select list>   
FROM [<mining model>].CASES  
WHERE IsInNode('<node id>')  
```  
  
 <span data-ttu-id="cb2b7-146">Die erste Codezeile definiert die aus den Quelldaten zurückzugebenden Spalten sowie das Miningmodell, in dem sie enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-146">The first line of the code defines the columns to return from the source data, and the mining model they are contained within:</span></span>  
  
```  
SELECT <select list> FROM [<mining model>].CASES  
```  
  
 <span data-ttu-id="cb2b7-147">Die .CASES-Klausel gibt an, dass Sie eine Drillthroughabfrage durchführen.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-147">The .CASES clause specifies that you are performing a drillthrough query.</span></span> <span data-ttu-id="cb2b7-148">Um Drillthrough verwenden zu können, müssen Sie beim Erstellen des Miningmodells Drillthrough aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-148">In order to use drillthrough you must enable drillthrough when you create the mining model.</span></span>  
  
 <span data-ttu-id="cb2b7-149">Die letzte Codezeile ist optional und gibt den Knoten des Miningmodells an, aus dem Sie Fälle anfordern:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-149">The final line of the code is optional and specifies the node in the mining model that you are requesting cases from:</span></span>  
  
```  
WHERE IsInNode('<node id>')  
```  
  
 <span data-ttu-id="cb2b7-150">Weitere Informationen zum Verwenden der WHERE-Anweisung mit IsInNode finden [Sie unter Select from &#60;Model&#62;. Fälle &#40;DMX-&#41;](/sql/dmx/select-from-model-content-dmx).</span><span class="sxs-lookup"><span data-stu-id="cb2b7-150">For more information about using the WHERE statement with IsInNode, see [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx).</span></span>  
  
#### <a name="to-return-the-cases-that-were-used-to-train-the-mining-model"></a><span data-ttu-id="cb2b7-151">So geben Sie die Fälle zurück, die zum Trainieren des Miningmodells verwendet wurden</span><span class="sxs-lookup"><span data-stu-id="cb2b7-151">To return the cases that were used to train the mining model</span></span>  
  
1.  <span data-ttu-id="cb2b7-152">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , zeigen Sie auf **neue Abfrage**, und klicken Sie dann auf **DMX**.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-152">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="cb2b7-153">Der Abfrage-Editor wird mit einer neuen leeren Abfrage geöffnet.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-153">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="cb2b7-154">Kopieren Sie das allgemeine Beispiel für SELECT FROM \<model> . Cases-Anweisung in die leere Abfrage.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-154">Copy the generic example of the SELECT FROM \<model>.CASES statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="cb2b7-155">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-155">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="cb2b7-156">durch:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-156">with:</span></span>  
  
    ```  
    *  
    ```  
  
     <span data-ttu-id="cb2b7-157">Sie können \* auch durch eine Liste mit beliebigen Spalten aus den Quelldaten ersetzen (z. B. [Bike Buyer]).</span><span class="sxs-lookup"><span data-stu-id="cb2b7-157">You can also replace \* with a list of any of the columns contained within the source data (such as [Bike Buyer]).</span></span>  
  
4.  <span data-ttu-id="cb2b7-158">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-158">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="cb2b7-159">durch:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-159">with:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
     <span data-ttu-id="cb2b7-160">Die gesamte Anweisung sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-160">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT *   
    FROM [Decision Tree].CASES  
    ```  
  
5.  <span data-ttu-id="cb2b7-161">Klicken Sie im Menü **Datei** auf **DMXQuery1. DMX speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-161">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="cb2b7-162">Navigieren Sie im Dialogfeld **Speichern** unter in den entsprechenden Ordner, und benennen Sie die Datei `SELECT_DRILLTHROUGH.dmx` .</span><span class="sxs-lookup"><span data-stu-id="cb2b7-162">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SELECT_DRILLTHROUGH.dmx`.</span></span>  
  
7.  <span data-ttu-id="cb2b7-163">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="cb2b7-163">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="cb2b7-164">Die Abfrage gibt die Quelldaten zurück, die zum Trainieren des Decision Tree-Miningmodells verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-164">The query returns the source data that was used to train the decision tree mining model.</span></span>  
  
## <a name="return-the-states-of-a-discrete-mining-model-column"></a><span data-ttu-id="cb2b7-165">Zurückgeben der Status einer diskreten Miningmodellspalte</span><span class="sxs-lookup"><span data-stu-id="cb2b7-165">Return the States of a Discrete Mining Model Column</span></span>  
 <span data-ttu-id="cb2b7-166">Im nächsten Schritt verwenden Sie die SELECT DISTINCT-Anweisung, um die möglichen verschiedenen Status in der angegebenen Miningmodellspalte zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-166">The next step is to use the SELECT DISTINCT statement to return the different possible states in the specified mining model column.</span></span>  
  
 <span data-ttu-id="cb2b7-167">Die folgende Zeile ist ein allgemeines Beispiel für die SELECT DISTINCT-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-167">The following is a generic example of the SELECT DISTINCT statement:</span></span>  
  
```  
SELECT DISTINCT [<column>]   
FROM [<mining model>]  
```  
  
 <span data-ttu-id="cb2b7-168">Die erste Codezeile definiert die Miningmodellspalten, für die die Status zurückgegeben werden:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-168">The first line of the code defines the mining model columns for which the states are returned:</span></span>  
  
```  
SELECT DISTINCT [<column>]   
```  
  
 <span data-ttu-id="cb2b7-169">Sie müssen DISTINCT einschließen, damit alle Status der Spalte zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-169">You must include DISTINCT in order to return all of the states of the column.</span></span> <span data-ttu-id="cb2b7-170">Wenn Sie DISTINCT nicht angeben, wird die Anweisung zu einer Abkürzung für eine Vorhersage und gibt den wahrscheinlichsten Status der angegebenen Spalte zurück.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-170">If you exclude DISTINCT, then the full statement becomes a shortcut for a prediction and returns the most likely state of the specified column.</span></span> <span data-ttu-id="cb2b7-171">Weitere Informationen finden Sie unter [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span><span class="sxs-lookup"><span data-stu-id="cb2b7-171">For more information, see [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span></span>  
  
#### <a name="to-return-the-states-of-a-discrete-column"></a><span data-ttu-id="cb2b7-172">So geben Sie die Status einer diskreten Spalte zurück</span><span class="sxs-lookup"><span data-stu-id="cb2b7-172">To return the states of a discrete column</span></span>  
  
1.  <span data-ttu-id="cb2b7-173">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , zeigen Sie auf **neue Abfrage**, und klicken Sie dann auf **DMX**.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-173">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="cb2b7-174">Der Abfrage-Editor wird mit einer neuen leeren Abfrage geöffnet.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-174">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="cb2b7-175">Kopieren Sie das allgemeine Beispiel der SELECT-Anweisung in die leere Abfrage.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-175">Copy the generic example of the SELECT Distinct statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="cb2b7-176">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-176">Replace the following:</span></span>  
  
    ```  
    [<column,name>   
    ```  
  
     <span data-ttu-id="cb2b7-177">durch:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-177">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
4.  <span data-ttu-id="cb2b7-178">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-178">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="cb2b7-179">durch:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-179">with:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
     <span data-ttu-id="cb2b7-180">Die gesamte Anweisung sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="cb2b7-180">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT DISTINCT [Bike Buyer]   
    FROM [Decision Tree]  
    ```  
  
5.  <span data-ttu-id="cb2b7-181">Klicken Sie im Menü **Datei** auf **DMXQuery1. DMX speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-181">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="cb2b7-182">Navigieren Sie im Dialogfeld **Speichern** unter in den entsprechenden Ordner, und benennen Sie die Datei `SELECT_DISCRETE.dmx` .</span><span class="sxs-lookup"><span data-stu-id="cb2b7-182">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SELECT_DISCRETE.dmx`.</span></span>  
  
7.  <span data-ttu-id="cb2b7-183">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="cb2b7-183">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="cb2b7-184">Die Abfrage gibt die möglichen Status der Bike Buyer-Spalte zurück.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-184">The query returns the possible states of the Bike Buyer column.</span></span>  
  
 <span data-ttu-id="cb2b7-185">In der nächsten Lektion sagen Sie mithilfe des Decision Tree-Miningmodells vorher, ob potenzielle Kunden ein Fahrrad kaufen werden.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-185">In the next lesson, you will predict whether potential customers will be bike buyers by using the decision tree mining model.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="cb2b7-186">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="cb2b7-186">Next Lesson</span></span>  
 [<span data-ttu-id="cb2b7-187">Lektion 5: Ausführen von Vorhersageabfragen</span><span class="sxs-lookup"><span data-stu-id="cb2b7-187">Lesson 5: Executing Prediction Queries</span></span>](../../2014/tutorials/lesson-5-executing-prediction-queries.md)  
  
  
