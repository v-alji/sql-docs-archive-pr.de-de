---
title: Beispiele für lineare Regressionsmodell Abfragen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- linear regression algorithms [Analysis Services]
- linear regression [Analysis Services]
- content queries [DMX]
ms.assetid: fd3cf312-57a1-44b6-b772-fce6fc1c26d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 02d4b7309d7b5ea3d6295089f0fb2e778b1c9b4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622308"
---
# <a name="linear-regression-model-query-examples"></a><span data-ttu-id="12cb9-102">Beispiele für lineare Regressionsmodellabfrage</span><span class="sxs-lookup"><span data-stu-id="12cb9-102">Linear Regression Model Query Examples</span></span>
  <span data-ttu-id="12cb9-103">Beim Erstellen einer Abfrage für ein Data Mining-Modell können Sie eine Inhaltsabfrage erstellen, die Details über die bei der Analyse ermittelten Muster liefert. Alternativ dazu können Sie auch eine Vorhersageabfrage erstellen, die Vorhersagen für neue Daten anhand der im Modell befindlichen Muster vornimmt.</span><span class="sxs-lookup"><span data-stu-id="12cb9-103">When you create a query against a data mining model, you can create a content query, which provides details about the patterns discovered in analysis, or you can create a prediction query, which uses the patterns in the model to make predictions for new data.</span></span> <span data-ttu-id="12cb9-104">Eine Inhaltsabfrage stellt beispielsweise zusätzliche Details über die Regressionsformel zur Verfügung, während eine Vorhersageabfrage Aufschluss darüber gibt, ob ein neuer Datenpunkt in das Modell passt.</span><span class="sxs-lookup"><span data-stu-id="12cb9-104">For example, a content query might provide additional details about the regression formula, while a prediction query might tell you if a new data point fits the model.</span></span> <span data-ttu-id="12cb9-105">Mit einer Abfrage können Sie auch Metadaten zum Modell abrufen.</span><span class="sxs-lookup"><span data-stu-id="12cb9-105">You can also retrieve metadata about the model by using a query.</span></span>  
  
 <span data-ttu-id="12cb9-106">In diesem Abschnitt wird erläutert, wie Abfragen für Modelle erstellt werden, die auf dem Microsoft Linear Regression-Algorithmus basieren.</span><span class="sxs-lookup"><span data-stu-id="12cb9-106">This section explains how to create queries for models that are based on the Microsoft Linear Regression algorithm.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12cb9-107">Da die lineare Regression auf einem Sonderfall des Microsoft Decision Trees-Algorithmus basiert, gibt es einige Ähnlichkeiten. Einige Entscheidungsstrukturmodelle, die kontinuierliche vorhersagbare Attribute verwenden, können Regressionsformeln enthalten.</span><span class="sxs-lookup"><span data-stu-id="12cb9-107">Because linear regression is based on a special case of the Microsoft Decision Trees algorithm, there are many similarities, and some decision tree models that use continuous predictable attributes can contain regression formulas.</span></span> <span data-ttu-id="12cb9-108">Weitere Informationen finden Sie unter [Technische Referenz für den Microsoft Decision Trees-Algorithmus](microsoft-decision-trees-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="12cb9-108">For more information, see [Microsoft Decision Trees Algorithm Technical Reference](microsoft-decision-trees-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="12cb9-109">**Inhalts Abfragen**</span><span class="sxs-lookup"><span data-stu-id="12cb9-109">**Content queries**</span></span>  
  
 [<span data-ttu-id="12cb9-110">Verwenden des Data Mining-Schemarowsets zur Ermittlung der für ein Modell verwendeten Parameter</span><span class="sxs-lookup"><span data-stu-id="12cb9-110">Using the Data Mining Schema Rowset to determine parameters used for a model</span></span>](#bkmk_Query1)  
  
 [<span data-ttu-id="12cb9-111">Verwenden von DMX zur Ermittlung der Regressionsformel für das Modell</span><span class="sxs-lookup"><span data-stu-id="12cb9-111">Using DMX to return the regression formula for the model</span></span>](#bkmk_Query2)  
  
 [<span data-ttu-id="12cb9-112">Zurückgeben des Koeffizienten für das Modell</span><span class="sxs-lookup"><span data-stu-id="12cb9-112">Returning only the coefficient for the model</span></span>](#bkmk_Query3)  
  
 <span data-ttu-id="12cb9-113">**Vorhersage Abfragen**</span><span class="sxs-lookup"><span data-stu-id="12cb9-113">**Prediction queries**</span></span>  
  
 [<span data-ttu-id="12cb9-114">Vorhersagen von Einkommen mit einer SINGLETON-Abfrage</span><span class="sxs-lookup"><span data-stu-id="12cb9-114">Predicting income using a singleton query</span></span>](#bkmk_Query4)  
  
 [<span data-ttu-id="12cb9-115">Verwenden von Vorhersagefunktionen mit einem Regressionsmodell</span><span class="sxs-lookup"><span data-stu-id="12cb9-115">Using prediction functions with a regression model</span></span>](#bkmk_Query5)  
  
##  <a name="finding-information-about-the-linear-regression-model"></a><a name="bkmk_top"></a> <span data-ttu-id="12cb9-116">Suchen nach Informationen über das lineare Regressionsmodell</span><span class="sxs-lookup"><span data-stu-id="12cb9-116">Finding Information about the Linear Regression Model</span></span>  
 <span data-ttu-id="12cb9-117">Die Struktur eines linearen Regressionsmodells ist äußerst einfach. Das Miningmodell repräsentiert die Daten als einzelnen Knoten, der die Regressionsformel definiert.</span><span class="sxs-lookup"><span data-stu-id="12cb9-117">The structure of a linear regression model is extremely simple: the mining model represents the data as a single node, which defines the regression formula.</span></span> <span data-ttu-id="12cb9-118">Weitere Informationen finden Sie unter [Miningmodellinhalt von logistischen Regressionsmodellen &#40;Analysis Services – Data Mining&#41;](mining-model-content-for-logistic-regression-models.md).</span><span class="sxs-lookup"><span data-stu-id="12cb9-118">For more information, see [Mining Model Content for Logistic Regression Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-logistic-regression-models.md).</span></span>  
  
 [<span data-ttu-id="12cb9-119">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="12cb9-119">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-1-using-the-data-mining-schema-rowset-to-determine-parameters-used-for-a-model"></a><a name="bkmk_Query1"></a> <span data-ttu-id="12cb9-120">Beispielabfrage 1: Verwenden des Data Mining-Schemarowsets zur Ermittlung der für ein Modell verwendeten Parameter</span><span class="sxs-lookup"><span data-stu-id="12cb9-120">Sample Query 1: Using the Data Mining Schema Rowset to Determine Parameters Used for a Model</span></span>  
 <span data-ttu-id="12cb9-121">Metadaten für das Modell finden Sie, indem Sie das Data Mining-Schemarowset abfragen.</span><span class="sxs-lookup"><span data-stu-id="12cb9-121">By querying the data mining schema rowset, you can find metadata about the model.</span></span> <span data-ttu-id="12cb9-122">Dazu gehören beispielsweise das Erstellungsdatum des Modells, das Datum der letzten Verarbeitung, der Name der Miningstruktur, auf der das Modell basiert, und der Name der als vorhersagbares Attribut verwendeten Spalte.</span><span class="sxs-lookup"><span data-stu-id="12cb9-122">This might include when the model was created, when the model was last processed, the name of the mining structure that the model is based on, and the name of the column designated as the predictable attribute.</span></span> <span data-ttu-id="12cb9-123">Sie können auch die Parameter zurückgeben, die beim ersten Erstellen des Modells verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="12cb9-123">You can also return the parameters that were used when the model was first created.</span></span>  
  
```  
SELECT MINING_PARAMETERS   
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'TM_PredictIncome'  
```  
  
 <span data-ttu-id="12cb9-124">Beispielergebnisse:</span><span class="sxs-lookup"><span data-stu-id="12cb9-124">Sample results:</span></span>  
  
|<span data-ttu-id="12cb9-125">MINING_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="12cb9-125">MINING_PARAMETERS</span></span>|  
|------------------------|  
|<span data-ttu-id="12cb9-126">COMPLEXITY_PENALTY=0.9,</span><span class="sxs-lookup"><span data-stu-id="12cb9-126">COMPLEXITY_PENALTY=0.9,</span></span><br /><br /> <span data-ttu-id="12cb9-127">MAXIMUM_INPUT_ATTRIBUTES=255,</span><span class="sxs-lookup"><span data-stu-id="12cb9-127">MAXIMUM_INPUT_ATTRIBUTES=255,</span></span><br /><br /> <span data-ttu-id="12cb9-128">MAXIMUM_OUTPUT_ATTRIBUTES=255,</span><span class="sxs-lookup"><span data-stu-id="12cb9-128">MAXIMUM_OUTPUT_ATTRIBUTES=255,</span></span><br /><br /> <span data-ttu-id="12cb9-129">MINIMUM_SUPPORT=10,</span><span class="sxs-lookup"><span data-stu-id="12cb9-129">MINIMUM_SUPPORT=10,</span></span><br /><br /> <span data-ttu-id="12cb9-130">SCORE_METHOD=4,</span><span class="sxs-lookup"><span data-stu-id="12cb9-130">SCORE_METHOD=4,</span></span><br /><br /> <span data-ttu-id="12cb9-131">SPLIT_METHOD=3,</span><span class="sxs-lookup"><span data-stu-id="12cb9-131">SPLIT_METHOD=3,</span></span><br /><br /> <span data-ttu-id="12cb9-132">FORCE_REGRESSOR=</span><span class="sxs-lookup"><span data-stu-id="12cb9-132">FORCE_REGRESSOR=</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="12cb9-133">Die Parametereinstellung "`FORCE_REGRESSOR =` " gibt an, dass der aktuelle Wert für den FORCE_REGRESSOR-Parameter NULL ist.</span><span class="sxs-lookup"><span data-stu-id="12cb9-133">The parameter setting, "`FORCE_REGRESSOR =` ", indicates that the current value for the FORCE_REGRESSOR parameter is null.</span></span>  
  
 [<span data-ttu-id="12cb9-134">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="12cb9-134">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-2-retrieving-the-regression-formula-for-the-model"></a><a name="bkmk_Query2"></a> <span data-ttu-id="12cb9-135">Beispielabfrage 2: Abrufen der Regressionsformel für das Modell</span><span class="sxs-lookup"><span data-stu-id="12cb9-135">Sample Query 2: Retrieving the Regression Formula for the Model</span></span>  
 <span data-ttu-id="12cb9-136">Die folgende Abfrage gibt den Miningmodellinhalt für ein lineares Regressionsmodell zurück, das mit der Targeted Mailing-Datenquelle erstellt wurde, die bereits im [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md)verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="12cb9-136">The following query returns the mining model content for a linear regression model that was built by using the same Targeted Mailing data source that was used in the [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span></span> <span data-ttu-id="12cb9-137">Dieses Modell sagt das Kundeneinkommen basierend auf dem Alter vorher.</span><span class="sxs-lookup"><span data-stu-id="12cb9-137">This model predicts customer income based on age.</span></span>  
  
 <span data-ttu-id="12cb9-138">Die Abfrage gibt den Inhalt des Knotens zurück, der die Regressionsformel enthält.</span><span class="sxs-lookup"><span data-stu-id="12cb9-138">The query returns the contents of the node that contains the regression formula.</span></span> <span data-ttu-id="12cb9-139">Jede Variable und jeder Koeffizient wird in einer separaten Zeile der geschachtelten NODE_DISTRIBUTION-Tabelle gespeichert.</span><span class="sxs-lookup"><span data-stu-id="12cb9-139">Each variable and coefficient is stored in a separate row of the nested NODE_DISTRIBUTION table.</span></span> <span data-ttu-id="12cb9-140">Wenn Sie die vollständige Regressions Formel anzeigen möchten, verwenden Sie den [Microsoft Tree-Viewer](browse-a-model-using-the-microsoft-tree-viewer.md), klicken Sie auf den Knoten **(alle)** , und öffnen Sie die **Mining Legende**.</span><span class="sxs-lookup"><span data-stu-id="12cb9-140">If you want to view the complete regression formula, use the [Microsoft Tree Viewer](browse-a-model-using-the-microsoft-tree-viewer.md), click the **(All)** node, and open the **Mining Legend**.</span></span>  
  
```  
SELECT FLATTENED NODE_DISTRIBUTION as t  
FROM LR_PredictIncome.CONTENT  
```  
  
> [!NOTE]  
>  <span data-ttu-id="12cb9-141">Wenn Sie auf einzelne Spalten der geschachtelten Tabelle durch Verwenden einer Abfrage wie `SELECT <column name> from NODE_DISTRIBUTION`verweisen, müssen einige Spalten, wie **SUPPORT** oder **PROBABILITY**, in Klammern eingeschlossen werden, um sie von den gleichnamigen reservierten Schlüsselwörtern zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="12cb9-141">If you reference individual columns of the nested table by using a query such as `SELECT <column name> from NODE_DISTRIBUTION`, some columns, such as **SUPPORT** or **PROBABILITY**, must be enclosed in brackets to distinguish them from reserved keywords of the same name.</span></span>  
  
 <span data-ttu-id="12cb9-142">Erwartete Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="12cb9-142">Expected results:</span></span>  
  
|<span data-ttu-id="12cb9-143">T.ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="12cb9-143">t.ATTRIBUTE_NAME</span></span>|<span data-ttu-id="12cb9-144">t.ATTRIBUTE_VALUE</span><span class="sxs-lookup"><span data-stu-id="12cb9-144">t.ATTRIBUTE_VALUE</span></span>|<span data-ttu-id="12cb9-145">t.SUPPORT</span><span class="sxs-lookup"><span data-stu-id="12cb9-145">t.SUPPORT</span></span>|<span data-ttu-id="12cb9-146">t.PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="12cb9-146">t.PROBABILITY</span></span>|<span data-ttu-id="12cb9-147">t.VARIANCE</span><span class="sxs-lookup"><span data-stu-id="12cb9-147">t.VARIANCE</span></span>|<span data-ttu-id="12cb9-148">t.VALUETYPE</span><span class="sxs-lookup"><span data-stu-id="12cb9-148">t.VALUETYPE</span></span>|  
|-----------------------|------------------------|---------------|-------------------|----------------|-----------------|  
|<span data-ttu-id="12cb9-149">Yearly Income</span><span class="sxs-lookup"><span data-stu-id="12cb9-149">Yearly Income</span></span>|<span data-ttu-id="12cb9-150">Missing</span><span class="sxs-lookup"><span data-stu-id="12cb9-150">Missing</span></span>|<span data-ttu-id="12cb9-151">0</span><span class="sxs-lookup"><span data-stu-id="12cb9-151">0</span></span>|<span data-ttu-id="12cb9-152">0.000457142857142857</span><span class="sxs-lookup"><span data-stu-id="12cb9-152">0.000457142857142857</span></span>|<span data-ttu-id="12cb9-153">0</span><span class="sxs-lookup"><span data-stu-id="12cb9-153">0</span></span>|<span data-ttu-id="12cb9-154">1</span><span class="sxs-lookup"><span data-stu-id="12cb9-154">1</span></span>|  
|<span data-ttu-id="12cb9-155">Yearly Income</span><span class="sxs-lookup"><span data-stu-id="12cb9-155">Yearly Income</span></span>|<span data-ttu-id="12cb9-156">57220.8876687257</span><span class="sxs-lookup"><span data-stu-id="12cb9-156">57220.8876687257</span></span>|<span data-ttu-id="12cb9-157">17484</span><span class="sxs-lookup"><span data-stu-id="12cb9-157">17484</span></span>|<span data-ttu-id="12cb9-158">0.999542857142857</span><span class="sxs-lookup"><span data-stu-id="12cb9-158">0.999542857142857</span></span>|<span data-ttu-id="12cb9-159">1041275619.52776</span><span class="sxs-lookup"><span data-stu-id="12cb9-159">1041275619.52776</span></span>|<span data-ttu-id="12cb9-160">3</span><span class="sxs-lookup"><span data-stu-id="12cb9-160">3</span></span>|  
|<span data-ttu-id="12cb9-161">Age</span><span class="sxs-lookup"><span data-stu-id="12cb9-161">Age</span></span>|<span data-ttu-id="12cb9-162">471.687717702463</span><span class="sxs-lookup"><span data-stu-id="12cb9-162">471.687717702463</span></span>|<span data-ttu-id="12cb9-163">0</span><span class="sxs-lookup"><span data-stu-id="12cb9-163">0</span></span>|<span data-ttu-id="12cb9-164">0</span><span class="sxs-lookup"><span data-stu-id="12cb9-164">0</span></span>|<span data-ttu-id="12cb9-165">126.969442359327</span><span class="sxs-lookup"><span data-stu-id="12cb9-165">126.969442359327</span></span>|<span data-ttu-id="12cb9-166">7</span><span class="sxs-lookup"><span data-stu-id="12cb9-166">7</span></span>|  
|<span data-ttu-id="12cb9-167">Age</span><span class="sxs-lookup"><span data-stu-id="12cb9-167">Age</span></span>|<span data-ttu-id="12cb9-168">234.680904692439</span><span class="sxs-lookup"><span data-stu-id="12cb9-168">234.680904692439</span></span>|<span data-ttu-id="12cb9-169">0</span><span class="sxs-lookup"><span data-stu-id="12cb9-169">0</span></span>|<span data-ttu-id="12cb9-170">0</span><span class="sxs-lookup"><span data-stu-id="12cb9-170">0</span></span>|<span data-ttu-id="12cb9-171">0</span><span class="sxs-lookup"><span data-stu-id="12cb9-171">0</span></span>|<span data-ttu-id="12cb9-172">8</span><span class="sxs-lookup"><span data-stu-id="12cb9-172">8</span></span>|  
|<span data-ttu-id="12cb9-173">Age</span><span class="sxs-lookup"><span data-stu-id="12cb9-173">Age</span></span>|<span data-ttu-id="12cb9-174">45.4269617936399</span><span class="sxs-lookup"><span data-stu-id="12cb9-174">45.4269617936399</span></span>|<span data-ttu-id="12cb9-175">0</span><span class="sxs-lookup"><span data-stu-id="12cb9-175">0</span></span>|<span data-ttu-id="12cb9-176">0</span><span class="sxs-lookup"><span data-stu-id="12cb9-176">0</span></span>|<span data-ttu-id="12cb9-177">126.969442359327</span><span class="sxs-lookup"><span data-stu-id="12cb9-177">126.969442359327</span></span>|<span data-ttu-id="12cb9-178">9</span><span class="sxs-lookup"><span data-stu-id="12cb9-178">9</span></span>|  
||<span data-ttu-id="12cb9-179">35793.5477381267</span><span class="sxs-lookup"><span data-stu-id="12cb9-179">35793.5477381267</span></span>|<span data-ttu-id="12cb9-180">0</span><span class="sxs-lookup"><span data-stu-id="12cb9-180">0</span></span>|<span data-ttu-id="12cb9-181">0</span><span class="sxs-lookup"><span data-stu-id="12cb9-181">0</span></span>|<span data-ttu-id="12cb9-182">1012968919.28372</span><span class="sxs-lookup"><span data-stu-id="12cb9-182">1012968919.28372</span></span>|<span data-ttu-id="12cb9-183">11</span><span class="sxs-lookup"><span data-stu-id="12cb9-183">11</span></span>|  
  
 <span data-ttu-id="12cb9-184">In Vergleich dazu wird die Regressionsformel in der **Mininglegende**wie folgt angezeigt:</span><span class="sxs-lookup"><span data-stu-id="12cb9-184">In comparison, in the **Mining Legend**, the regression formula appears as follows:</span></span>  
  
 <span data-ttu-id="12cb9-185">Yearly Income = 57,220.919 + 471.688 \* (Age - 45.427)</span><span class="sxs-lookup"><span data-stu-id="12cb9-185">Yearly Income = 57,220.919 + 471.688 \* (Age - 45.427)</span></span>  
  
 <span data-ttu-id="12cb9-186">In der **Mininglegende**sind einige Zahlen gerundet. Die NODE_DISTRIBUTION-Tabelle und die **Mininglegende** enthalten im Wesentlichen jedoch die gleichen Werte.</span><span class="sxs-lookup"><span data-stu-id="12cb9-186">You can see that in the **Mining Legend**, some numbers are rounded; however, the NODE_DISTRIBUTION table and the **Mining Legend** essentially contain the same values.</span></span>  
  
 <span data-ttu-id="12cb9-187">Die Werte in der VALUETYPE-Spalte geben Aufschluss über die Art der in jeder Zeile enthaltenen Informationen. Dies ist nützlich, wenn Sie die Ergebnisse programmgesteuert verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="12cb9-187">The values in the VALUETYPE column tell you what kind of information is contained in each row, which is useful if you are processing the results programmatically.</span></span> <span data-ttu-id="12cb9-188">In der folgenden Tabelle werden die Werttypen, die für eine lineare Regressionsformel ausgegeben werden, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="12cb9-188">The following table shows the value types that are output for a linear regression formula.</span></span>  
  
|<span data-ttu-id="12cb9-189">VALUETYPE</span><span class="sxs-lookup"><span data-stu-id="12cb9-189">VALUETYPE</span></span>|  
|---------------|  
|<span data-ttu-id="12cb9-190">1 (Missing)</span><span class="sxs-lookup"><span data-stu-id="12cb9-190">1 (Missing)</span></span>|  
|<span data-ttu-id="12cb9-191">3 (Continuous)</span><span class="sxs-lookup"><span data-stu-id="12cb9-191">3 (Continuous)</span></span>|  
|<span data-ttu-id="12cb9-192">7 (Koeffizient)</span><span class="sxs-lookup"><span data-stu-id="12cb9-192">7 (Coefficient)</span></span>|  
|<span data-ttu-id="12cb9-193">8 (Score Gain)</span><span class="sxs-lookup"><span data-stu-id="12cb9-193">8 (Score Gain)</span></span>|  
|<span data-ttu-id="12cb9-194">9 (Statistik)</span><span class="sxs-lookup"><span data-stu-id="12cb9-194">9 (Statistics)</span></span>|  
|<span data-ttu-id="12cb9-195">7 (Koeffizient)</span><span class="sxs-lookup"><span data-stu-id="12cb9-195">7 (Coefficient)</span></span>|  
|<span data-ttu-id="12cb9-196">8 (Score Gain)</span><span class="sxs-lookup"><span data-stu-id="12cb9-196">8 (Score Gain)</span></span>|  
|<span data-ttu-id="12cb9-197">9 (Statistik)</span><span class="sxs-lookup"><span data-stu-id="12cb9-197">9 (Statistics)</span></span>|  
|<span data-ttu-id="12cb9-198">11 (Intercept)</span><span class="sxs-lookup"><span data-stu-id="12cb9-198">11 (Intercept)</span></span>|  
  
 <span data-ttu-id="12cb9-199">Weitere Informationen über die Bedeutung der einzelnen Werttypen für Regressionsmodelle finden Sie unter [Miningmodellinhalt von linearen Regressionsmodellen &#40;Analysis Services – Data Mining&#41;](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="12cb9-199">For more information about the meaning of each value type for regression models, see [Mining Model Content for Linear Regression Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md).</span></span>  
  
 [<span data-ttu-id="12cb9-200">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="12cb9-200">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-3-returning-only-the-coefficient-for-the-model"></a><a name="bkmk_Query3"></a> <span data-ttu-id="12cb9-201">Beispielabfrage 3: Zurückgeben des Koeffizienten für das Modell</span><span class="sxs-lookup"><span data-stu-id="12cb9-201">Sample Query 3: Returning Only the Coefficient for the Model</span></span>  
 <span data-ttu-id="12cb9-202">Mit der VALUETYPE-Enumeration können Sie nur den Koeffizienten für die Regressionsgleichung zurückgeben, wie in der folgenden Abfrage veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="12cb9-202">By using the VALUETYPE enumeration, you can return only the coefficient for the regression equation, as shown in the following query:</span></span>  
  
```  
SELECT FLATTENED MODEL_NAME,  
    (SELECT ATTRIBUTE_VALUE, VALUETYPE  
     FROM NODE_DISTRIBUTION  
     WHERE VALUETYPE = 11)   
AS t  
FROM LR_PredictIncome.CONTENT  
```  
  
 <span data-ttu-id="12cb9-203">Mit dieser Abfrage werden zwei Zeilen zurückgegeben, eine Zeile aus dem Miningmodellinhalt und die Zeile der geschachtelten Tabelle, die den Koeffizienten enthält.</span><span class="sxs-lookup"><span data-stu-id="12cb9-203">This query returns two rows, one from the mining model content, and the row from the nested table that contains the coefficient.</span></span> <span data-ttu-id="12cb9-204">Die Spalte ATTRIBUTE_NAME ist hier nicht eingeschlossen, da sie für den Koeffizienten stets leer ist.</span><span class="sxs-lookup"><span data-stu-id="12cb9-204">The ATTRIBUTE_NAME column is not included here because it is always blank for the coefficient.</span></span>  
  
|<span data-ttu-id="12cb9-205">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="12cb9-205">MODEL_NAME</span></span>|<span data-ttu-id="12cb9-206">t.ATTRIBUTE_VALUE</span><span class="sxs-lookup"><span data-stu-id="12cb9-206">t.ATTRIBUTE_VALUE</span></span>|<span data-ttu-id="12cb9-207">t.VALUETYPE</span><span class="sxs-lookup"><span data-stu-id="12cb9-207">t.VALUETYPE</span></span>|  
|-----------------|------------------------|-----------------|  
|<span data-ttu-id="12cb9-208">LR_PredictIncome</span><span class="sxs-lookup"><span data-stu-id="12cb9-208">LR_PredictIncome</span></span>|||  
|<span data-ttu-id="12cb9-209">LR_PredictIncome</span><span class="sxs-lookup"><span data-stu-id="12cb9-209">LR_PredictIncome</span></span>|<span data-ttu-id="12cb9-210">35793.5477381267</span><span class="sxs-lookup"><span data-stu-id="12cb9-210">35793.5477381267</span></span>|<span data-ttu-id="12cb9-211">11</span><span class="sxs-lookup"><span data-stu-id="12cb9-211">11</span></span>|  
  
 [<span data-ttu-id="12cb9-212">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="12cb9-212">Return to Top</span></span>](#bkmk_top)  
  
## <a name="making-predictions-from-a-linear-regression-model"></a><span data-ttu-id="12cb9-213">Treffen von Vorhersagen aus einem linearen Regressionsmodell</span><span class="sxs-lookup"><span data-stu-id="12cb9-213">Making Predictions from a Linear Regression Model</span></span>  
 <span data-ttu-id="12cb9-214">Mit der Registerkarte Miningmodellvorhersage im Data Mining-Designer können Sie Vorhersageabfragen für lineare Regressionsmodelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="12cb9-214">You can build prediction queries on linear regression models by using the Mining Model Prediction tab in Data Mining Designer.</span></span> <span data-ttu-id="12cb9-215">Der Generator für Vorhersageabfragen ist sowohl in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] als auch in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]verfügbar.</span><span class="sxs-lookup"><span data-stu-id="12cb9-215">The prediction query builder is available in both [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12cb9-216">Abfragen für Regressionsmodelle können Sie auch mit [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Data Mining-Add-Ins für Excel oder [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] Data Mining-Add-Ins für Excel erstellen.</span><span class="sxs-lookup"><span data-stu-id="12cb9-216">You can also create queries on regression models by using the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Data Mining Add-ins for Excel or the [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] Data Mining Add-ins for Excel.</span></span> <span data-ttu-id="12cb9-217">Auch wenn die Data Mining-Add-Ins für Excel keine Regressionsmodelle erstellen, können Sie jedes Miningmodell, das in einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Instanz gespeichert ist, durchsuchen und abfragen.</span><span class="sxs-lookup"><span data-stu-id="12cb9-217">Even though the Data Mining Add-ins for Excel do not create regression models, you can browse and query any mining model that is stored on an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="12cb9-218">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="12cb9-218">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-4-predicting-income-using-a-singleton-query"></a><a name="bkmk_Query4"></a> <span data-ttu-id="12cb9-219">Beispielabfrage 4: Vorhersagen von Einkommen mit einer SINGLETON-Abfrage</span><span class="sxs-lookup"><span data-stu-id="12cb9-219">Sample Query 4: Predicting Income using a Singleton Query</span></span>  
 <span data-ttu-id="12cb9-220">Die einfachste Möglichkeit zum Erstellen einer einzelnen Abfrage für ein Regressionsmodell bietet das Dialogfeld **SINGLETON-Abfrageeingabe** .</span><span class="sxs-lookup"><span data-stu-id="12cb9-220">The easiest way to create a single query on a regression model is by using the **Singleton Query Input** dialog box.</span></span> <span data-ttu-id="12cb9-221">Beispielsweise können Sie die folgende DMX-Abfrage erstellen, indem Sie das entsprechende Regressionsmodell auswählen, **Singleton-Abfrage**auswählen und dann `20` als Wert für **Age**eingeben.</span><span class="sxs-lookup"><span data-stu-id="12cb9-221">For example, you can build the following DMX query by selecting the appropriate regression model, choosing **Singleton Query**, and then typing `20` as the value for **Age**.</span></span>  
  
```  
SELECT [LR_PredictIncome].[Yearly Income]  
From   [LR_PredictIncome]  
NATURAL PREDICTION JOIN  
(SELECT 20 AS [Age]) AS t  
```  
  
 <span data-ttu-id="12cb9-222">Beispielergebnisse:</span><span class="sxs-lookup"><span data-stu-id="12cb9-222">Sample results:</span></span>  
  
|<span data-ttu-id="12cb9-223">Yearly Income</span><span class="sxs-lookup"><span data-stu-id="12cb9-223">Yearly Income</span></span>|  
|-------------------|  
|<span data-ttu-id="12cb9-224">45227.302092176</span><span class="sxs-lookup"><span data-stu-id="12cb9-224">45227.302092176</span></span>|  
  
 [<span data-ttu-id="12cb9-225">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="12cb9-225">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-5-using-prediction-functions-with-a-regression-model"></a><a name="bkmk_Query5"></a> <span data-ttu-id="12cb9-226">Beispielabfrage 5: Verwenden von Vorhersagefunktionen mit einem Regressionsmodell</span><span class="sxs-lookup"><span data-stu-id="12cb9-226">Sample Query 5: Using Prediction Functions with a Regression Model</span></span>  
 <span data-ttu-id="12cb9-227">Sie können viele der Standardvorhersagefunktionen mit linearen Regressionsmodellen verwenden.</span><span class="sxs-lookup"><span data-stu-id="12cb9-227">You can use many of the standard prediction functions with linear regression models.</span></span> <span data-ttu-id="12cb9-228">Im folgenden Beispiel wird veranschaulicht, wie den Vorhersageabfrageergebnissen einige aussagekräftige statistische Daten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="12cb9-228">The following example illustrates how to add some descriptive statistics to the prediction query results.</span></span> <span data-ttu-id="12cb9-229">Aus diesen Ergebnissen ist ersichtlich, dass es eine beträchtliche Abweichung vom Mittelwert für dieses Modell gibt.</span><span class="sxs-lookup"><span data-stu-id="12cb9-229">From these results, you can see that there is considerable deviation from the mean for this model.</span></span>  
  
```  
SELECT  
  ([LR_PredictIncome].[Yearly Income]) as [PredIncome],  
  (PredictStdev([LR_PredictIncome].[Yearly Income])) as [StDev1]  
From  
  [LR_PredictIncome]  
NATURAL PREDICTION JOIN  
(SELECT 20 AS [Age]) AS t  
```  
  
 <span data-ttu-id="12cb9-230">Beispielergebnisse:</span><span class="sxs-lookup"><span data-stu-id="12cb9-230">Sample results:</span></span>  
  
|<span data-ttu-id="12cb9-231">Yearly Income</span><span class="sxs-lookup"><span data-stu-id="12cb9-231">Yearly Income</span></span>|<span data-ttu-id="12cb9-232">StDev1</span><span class="sxs-lookup"><span data-stu-id="12cb9-232">StDev1</span></span>|  
|-------------------|------------|  
|<span data-ttu-id="12cb9-233">45227.302092176</span><span class="sxs-lookup"><span data-stu-id="12cb9-233">45227.302092176</span></span>|<span data-ttu-id="12cb9-234">31827.1726561396</span><span class="sxs-lookup"><span data-stu-id="12cb9-234">31827.1726561396</span></span>|  
  
 [<span data-ttu-id="12cb9-235">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="12cb9-235">Return to Top</span></span>](#bkmk_top)  
  
## <a name="list-of-prediction-functions"></a><span data-ttu-id="12cb9-236">Liste der Vorhersagefunktionen</span><span class="sxs-lookup"><span data-stu-id="12cb9-236">List of Prediction Functions</span></span>  
 <span data-ttu-id="12cb9-237">Alle Algorithmen von [!INCLUDE[msCoName](../../includes/msconame-md.md)] unterstützen einen gemeinsamen Funktionssatz.</span><span class="sxs-lookup"><span data-stu-id="12cb9-237">All [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms support a common set of functions.</span></span> <span data-ttu-id="12cb9-238">Allerdings unterstützt der [!INCLUDE[msCoName](../../includes/msconame-md.md)] Linear Regression-Algorithmus zusätzliche Funktionen, die in der folgenden Tabelle aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="12cb9-238">However, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Linear Regression algorithm supports the additional functions listed in the following table.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="12cb9-239">Vorhersagefunktion</span><span class="sxs-lookup"><span data-stu-id="12cb9-239">Prediction Function</span></span>|<span data-ttu-id="12cb9-240">Verwendung</span><span class="sxs-lookup"><span data-stu-id="12cb9-240">Usage</span></span>|  
|[<span data-ttu-id="12cb9-241">IsDescendant &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="12cb9-241">IsDescendant &#40;DMX&#41;</span></span>](/sql/dmx/isdescendant-dmx)|<span data-ttu-id="12cb9-242">Bestimmt, ob ein Knoten ein untergeordnetes Element eines anderen Knotens im Modell ist.</span><span class="sxs-lookup"><span data-stu-id="12cb9-242">Determines whether one node is a child of another node in the model.</span></span>|  
|[<span data-ttu-id="12cb9-243">IsInNode &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="12cb9-243">IsInNode &#40;DMX&#41;</span></span>](/sql/dmx/isinnode-dmx)|<span data-ttu-id="12cb9-244">Zeigt an, ob der angegebene Knoten den aktuellen Fall enthält.</span><span class="sxs-lookup"><span data-stu-id="12cb9-244">Indicates whether the specified node contains the current case.</span></span>|  
|[<span data-ttu-id="12cb9-245">PredictHistogram &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="12cb9-245">PredictHistogram &#40;DMX&#41;</span></span>](/sql/dmx/predicthistogram-dmx)|<span data-ttu-id="12cb9-246">Gibt einen vorhergesagten Wert oder eine Gruppe von Werten für eine angegebene Spalte zurück.</span><span class="sxs-lookup"><span data-stu-id="12cb9-246">Returns a predicted value, or set of values, for a specified column.</span></span>|  
|[<span data-ttu-id="12cb9-247">PredictNodeId &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="12cb9-247">PredictNodeId &#40;DMX&#41;</span></span>](/sql/dmx/predictnodeid-dmx)|<span data-ttu-id="12cb9-248">Gibt "Node_ID" für jeden Fall zurück.</span><span class="sxs-lookup"><span data-stu-id="12cb9-248">Returns the Node_ID for each case.</span></span>|  
|[<span data-ttu-id="12cb9-249">PredictStdev &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="12cb9-249">PredictStdev &#40;DMX&#41;</span></span>](/sql/dmx/predictstdev-dmx)|<span data-ttu-id="12cb9-250">Gibt die Standardabweichung für den prognostizierten Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="12cb9-250">Returns standard deviation for the predicted value.</span></span>|  
|[<span data-ttu-id="12cb9-251">PredictSupport &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="12cb9-251">PredictSupport &#40;DMX&#41;</span></span>](/sql/dmx/predictsupport-dmx)|<span data-ttu-id="12cb9-252">Gibt den Unterstützungswert für einen bestimmten Status zurück.</span><span class="sxs-lookup"><span data-stu-id="12cb9-252">Returns the support value for a specified state.</span></span>|  
|[<span data-ttu-id="12cb9-253">PredictVariance &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="12cb9-253">PredictVariance &#40;DMX&#41;</span></span>](/sql/dmx/predictvariance-dmx)|<span data-ttu-id="12cb9-254">Gibt die Varianz einer angegebenen Spalte zurück.</span><span class="sxs-lookup"><span data-stu-id="12cb9-254">Returns the variance of a specified column.</span></span>|  
  
 <span data-ttu-id="12cb9-255">Eine Liste der Funktionen, die allen [!INCLUDE[msCoName](../../includes/msconame-md.md)]-Algorithmen gemeinsam sind, finden Sie unter [Data Mining-Algorithmen &#40;Analysis Services – Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="12cb9-255">For a list of the functions that are common to all [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span> <span data-ttu-id="12cb9-256">Weitere Informationen zum Verwenden dieser Funktionen finden Sie unter [Data Mining-Erweiterungen &#40;DMX&#41; – Funktionsreferenz](/sql/dmx/data-mining-extensions-dmx-function-reference).</span><span class="sxs-lookup"><span data-stu-id="12cb9-256">For more information about how to use these functions, see [Data Mining Extensions &#40;DMX&#41; Function Reference](/sql/dmx/data-mining-extensions-dmx-function-reference).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12cb9-257">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="12cb9-257">See Also</span></span>  
 <span data-ttu-id="12cb9-258">[Microsoft Linear Regression-Algorithmus](microsoft-linear-regression-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="12cb9-258">[Microsoft Linear Regression Algorithm](microsoft-linear-regression-algorithm.md) </span></span>  
 <span data-ttu-id="12cb9-259">[Data Mining-Abfragen](data-mining-queries.md) </span><span class="sxs-lookup"><span data-stu-id="12cb9-259">[Data Mining Queries](data-mining-queries.md) </span></span>  
 <span data-ttu-id="12cb9-260">[Technische Referenz für den Microsoft Linear Regression-Algorithmus](microsoft-linear-regression-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="12cb9-260">[Microsoft Linear Regression Algorithm Technical Reference](microsoft-linear-regression-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="12cb9-261">Miningmodellinhalt von linearen Regressionsmodellen &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="12cb9-261">Mining Model Content for Linear Regression Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md)  
  
  
