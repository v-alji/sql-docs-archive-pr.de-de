---
title: Beispiele für Zuordnungs Modell Abfragen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- itemsets [Analysis Services]
- association algorithms [Analysis Services]
- rules [Data Mining]
- association rules
- content queries [DMX]
ms.assetid: 68b39f5c-c439-44ac-8046-6f2d36649059
author: minewiskan
ms.author: owend
ms.openlocfilehash: a19eb2302639c7f13d48a8778969bbeca4fee18d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621748"
---
# <a name="association-model-query-examples"></a><span data-ttu-id="29c9e-102">Beispiele für Zuordnungsmodellabfragen</span><span class="sxs-lookup"><span data-stu-id="29c9e-102">Association Model Query Examples</span></span>
  <span data-ttu-id="29c9e-103">Beim Erstellen einer Abfrage für ein Data Mining-Modell können Sie entweder eine Inhaltsabfrage oder eine Vorhersageabfrage auswählen. Die Inhaltsabfrage liefert Details über die während der Analyse ermittelten Regeln und Itemsets. Die Vorhersageabfrage nimmt hingegen Vorhersagen anhand der in den Daten gefundenen Zuordnungen vor.</span><span class="sxs-lookup"><span data-stu-id="29c9e-103">When you create a query against a data mining model, you can create either a content query, which provides details about the rules and itemsets discovered during analysis, or you can create a prediction query, which uses the associations discovered in the data to make predictions.</span></span> <span data-ttu-id="29c9e-104">Für ein Zuordnungsmodell basieren Vorhersagen üblicherweise auf Regeln und können für Empfehlungen verwendet werden. Bei Abfragen des Inhalts wird hingegen die Beziehung zwischen Itemsets analysiert.</span><span class="sxs-lookup"><span data-stu-id="29c9e-104">For an association model, predictions typically are based on rules, and can be used to make recommendations, whereas queries on content typically explore the relationship among itemsets.</span></span> <span data-ttu-id="29c9e-105">Sie können auch Metadaten über das Modell abrufen.</span><span class="sxs-lookup"><span data-stu-id="29c9e-105">You can also retrieve metadata about the model.</span></span>  
  
 <span data-ttu-id="29c9e-106">In diesem Abschnitt wird erklärt, wie diese Art von Abfragen für Modelle erstellt werden, die auf dem [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules-Algorithmus basieren.</span><span class="sxs-lookup"><span data-stu-id="29c9e-106">This section explains how to create these kinds of queries for models that are based on the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules algorithm.</span></span>  
  
 <span data-ttu-id="29c9e-107">**Inhaltsabfragen**</span><span class="sxs-lookup"><span data-stu-id="29c9e-107">**Content Queries**</span></span>  
  
 [<span data-ttu-id="29c9e-108">Abrufen von Modellmetadaten-Daten mithilfe von DMX</span><span class="sxs-lookup"><span data-stu-id="29c9e-108">Getting model metadata data by using DMX</span></span>](#bkmk_Query1)  
  
 [<span data-ttu-id="29c9e-109">Abrufen von Metadaten aus dem Schemarowset</span><span class="sxs-lookup"><span data-stu-id="29c9e-109">Getting metadata from the schema rowset</span></span>](#bkmk_Query2)  
  
 [<span data-ttu-id="29c9e-110">Abrufen der ursprünglichen Parameter für das Modell</span><span class="sxs-lookup"><span data-stu-id="29c9e-110">Retrieving the original parameters for the model</span></span>](#bkmk_Query3)  
  
 [<span data-ttu-id="29c9e-111">Abrufen einer Liste von Itemsets und Produkten</span><span class="sxs-lookup"><span data-stu-id="29c9e-111">Retrieving a list of itemsets and products</span></span>](#bkmk_Query4)  
  
 [<span data-ttu-id="29c9e-112">Zurückgeben der obersten 10 Itemsets</span><span class="sxs-lookup"><span data-stu-id="29c9e-112">Returning the top 10 itemsets</span></span>](#bkmk_Query5)  
  
 <span data-ttu-id="29c9e-113">**Vorhersageabfragen**</span><span class="sxs-lookup"><span data-stu-id="29c9e-113">**Prediction Queries**</span></span>  
  
 [<span data-ttu-id="29c9e-114">Vorhersagen von verknüpften Elementen</span><span class="sxs-lookup"><span data-stu-id="29c9e-114">Predicting associated items</span></span>](#bkmk_Query6)  
  
 [<span data-ttu-id="29c9e-115">Bestimmen von Vertrauen für verwandte Itemsets</span><span class="sxs-lookup"><span data-stu-id="29c9e-115">Determining confidence for related itemsets</span></span>](#bkmk_Query7)  
  
##  <a name="finding-information-about-the-model"></a><a name="bkmk_top2"></a><span data-ttu-id="29c9e-116">Suchen nach Informationen über das Modell</span><span class="sxs-lookup"><span data-stu-id="29c9e-116">Finding Information about the Model</span></span>  
 <span data-ttu-id="29c9e-117">Alle Miningmodelle machen den vom Algorithmus erfassten Inhalt nach einem standardisierten Schema verfügbar. Dieses Schema wird als Miningmodell-Schemarowset bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="29c9e-117">All mining models expose the content learned by the algorithm according to a standardized schema, which is named the mining model schema rowset.</span></span> <span data-ttu-id="29c9e-118">Abfragen für das Miningmodell-Schemarowset können Sie entweder mithilfe von DMX-Anweisungen oder mit gespeicherten [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Prozeduren erstellen.</span><span class="sxs-lookup"><span data-stu-id="29c9e-118">You can create queries against the mining model schema rowset either by using Data Mining Extensions (DMX) statements, or by using [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stored procedures.</span></span> <span data-ttu-id="29c9e-119">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]können Sie die Schemarowsets mit einer SQL-ähnlichen Syntax auch direkt als Systemtabellen abfragen.</span><span class="sxs-lookup"><span data-stu-id="29c9e-119">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can also query the schema rowsets directly as system tables, by using a SQL-like syntax.</span></span>  
  
###  <a name="sample-query-1-getting-model-metadata-by-using-dmx"></a><a name="bkmk_Query1"></a><span data-ttu-id="29c9e-120">Beispiel Abfrage 1: erhalten von Modell Metadaten mithilfe von DMX</span><span class="sxs-lookup"><span data-stu-id="29c9e-120">Sample Query 1: Getting Model Metadata by Using DMX</span></span>  
 <span data-ttu-id="29c9e-121">Die folgende Abfrage gibt grundlegende Metadaten über das Zuordnungsmodell `Association`zurück, wie Name des Modells, die Datenbank, in der das Modell gespeichert ist, und die Anzahl der untergeordneten Knoten im Modell.</span><span class="sxs-lookup"><span data-stu-id="29c9e-121">The following query returns basic metadata about the association model, `Association`, such as the name of the model, the database where the model is stored, and the number of child nodes in the model.</span></span> <span data-ttu-id="29c9e-122">Diese Abfrage ruft die Metadaten mithilfe einer DMX-Inhaltsabfrage vom übergeordneten Knoten des Modells ab:</span><span class="sxs-lookup"><span data-stu-id="29c9e-122">This query uses a DMX content query to retrieve the metadata from the parent node of the model:</span></span>  
  
```  
SELECT MODEL_CATALOG, MODEL_NAME, NODE_CAPTION,   
NODE_SUPPORT, [CHILDREN_CARDINALITY], NODE_DESCRIPTION  
FROM Association.CONTENT  
WHERE NODE_TYPE = 1  
```  
  
> [!NOTE]  
>  <span data-ttu-id="29c9e-123">Setzen Sie den Namen der Spalte CHILDREN_CARDINALITY in Klammern, um ihn von dem gleichnamigen reservierten MDX-Schlüsselwort zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="29c9e-123">You must enclose the name of the column, CHILDREN_CARDINALITY, in brackets to distinguish it from the MDX reserved keyword of the same name.</span></span>  
  
 <span data-ttu-id="29c9e-124">Beispielergebnisse:</span><span class="sxs-lookup"><span data-stu-id="29c9e-124">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="29c9e-125">MODEL_CATALOG</span><span class="sxs-lookup"><span data-stu-id="29c9e-125">MODEL_CATALOG</span></span>|<span data-ttu-id="29c9e-126">Zuordnungstest</span><span class="sxs-lookup"><span data-stu-id="29c9e-126">Association Test</span></span>|  
|<span data-ttu-id="29c9e-127">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="29c9e-127">MODEL_NAME</span></span>|<span data-ttu-id="29c9e-128">Zuordnung</span><span class="sxs-lookup"><span data-stu-id="29c9e-128">Association</span></span>|  
|<span data-ttu-id="29c9e-129">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="29c9e-129">NODE_CAPTION</span></span>|<span data-ttu-id="29c9e-130">Modell für Zuordnungsregeln</span><span class="sxs-lookup"><span data-stu-id="29c9e-130">Association Rules Model</span></span>|  
|<span data-ttu-id="29c9e-131">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="29c9e-131">NODE_SUPPORT</span></span>|<span data-ttu-id="29c9e-132">14879</span><span class="sxs-lookup"><span data-stu-id="29c9e-132">14879</span></span>|  
|<span data-ttu-id="29c9e-133">CHILDREN_CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="29c9e-133">CHILDREN_CARDINALITY</span></span>|<span data-ttu-id="29c9e-134">942</span><span class="sxs-lookup"><span data-stu-id="29c9e-134">942</span></span>|  
|<span data-ttu-id="29c9e-135">NODE_DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="29c9e-135">NODE_DESCRIPTION</span></span>|<span data-ttu-id="29c9e-136">Modell für Zuordnungsregeln; ITEMSET_COUNT=679; RULE_COUNT=263; MIN_SUPPORT=14; MAX_SUPPORT=4334; MIN_ITEMSET_SIZE=0; MAX_ITEMSET_SIZE=3; MIN_PROBABILITY=0.400390625; MAX_PROBABILITY=1; MIN_LIFT=0.14309369632511; MAX_LIFT=1.95758227647523</span><span class="sxs-lookup"><span data-stu-id="29c9e-136">Association Rules Model; ITEMSET_COUNT=679; RULE_COUNT=263; MIN_SUPPORT=14; MAX_SUPPORT=4334; MIN_ITEMSET_SIZE=0; MAX_ITEMSET_SIZE=3; MIN_PROBABILITY=0.400390625; MAX_PROBABILITY=1; MIN_LIFT=0.14309369632511; MAX_LIFT=1.95758227647523</span></span>|  
  
 <span data-ttu-id="29c9e-137">Eine Definition der Bedeutung dieser Spalten in einem Zuordnungsmodell finden Sie unter [Miningmodellinhalt von Zuordnungsmodellen &#40;Analysis Services – Data Mining&#41;](mining-model-content-for-association-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="29c9e-137">For a definition of what these columns mean in an association model, see [Mining Model Content for Association Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-association-models-analysis-services-data-mining.md).</span></span>  
  
 [<span data-ttu-id="29c9e-138">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="29c9e-138">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-2-getting-additional-metadata-from-the-schema-rowset"></a><a name="bkmk_Query2"></a><span data-ttu-id="29c9e-139">Beispiel Abfrage 2: erhalten zusätzlicher Metadaten aus dem Schemarowset</span><span class="sxs-lookup"><span data-stu-id="29c9e-139">Sample Query 2: Getting Additional Metadata from the Schema Rowset</span></span>  
 <span data-ttu-id="29c9e-140">Durch Abfragen des Data Mining-Schemarowsets erhalten Sie dieselben Informationen wie bei einer DMX-Inhaltsabfrage.</span><span class="sxs-lookup"><span data-stu-id="29c9e-140">By querying the data mining schema rowset, you can find the same information that is returned in a DMX content query.</span></span> <span data-ttu-id="29c9e-141">Das Schemarowset bietet jedoch einige zusätzliche Spalten, wie das Datum der letzten Modellverarbeitung, die Miningstruktur und den Namen der als vorhersagbares Attribut verwendeten Spalte.</span><span class="sxs-lookup"><span data-stu-id="29c9e-141">However, the schema rowset provides some additional columns, such as the date the model was last processed, the mining structure, and the name of the column used as the predictable attribute.</span></span>  
  
```  
SELECT MODEL_CATALOG, MODEL_NAME, SERVICE_NAME, PREDICTION_ENTITY,   
MINING_STRUCTURE, LAST_PROCESSED  
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'Association'  
```  
  
 <span data-ttu-id="29c9e-142">Beispielergebnisse:</span><span class="sxs-lookup"><span data-stu-id="29c9e-142">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="29c9e-143">MODEL_CATALOG</span><span class="sxs-lookup"><span data-stu-id="29c9e-143">MODEL_CATALOG</span></span>|<span data-ttu-id="29c9e-144">Adventure Works DW Multidimensional 2012</span><span class="sxs-lookup"><span data-stu-id="29c9e-144">Adventure Works DW Multidimensional 2012</span></span>|  
|<span data-ttu-id="29c9e-145">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="29c9e-145">MODEL_NAME</span></span>|<span data-ttu-id="29c9e-146">Zuordnung</span><span class="sxs-lookup"><span data-stu-id="29c9e-146">Association</span></span>|  
|<span data-ttu-id="29c9e-147">SERVICE_NAME</span><span class="sxs-lookup"><span data-stu-id="29c9e-147">SERVICE_NAME</span></span>|<span data-ttu-id="29c9e-148">Modell für Zuordnungsregeln</span><span class="sxs-lookup"><span data-stu-id="29c9e-148">Association Rules Model</span></span>|  
|<span data-ttu-id="29c9e-149">PREDICTION_ENTITY</span><span class="sxs-lookup"><span data-stu-id="29c9e-149">PREDICTION_ENTITY</span></span>|<span data-ttu-id="29c9e-150">v Assoc Seq Line Items</span><span class="sxs-lookup"><span data-stu-id="29c9e-150">v Assoc Seq Line Items</span></span>|  
|<span data-ttu-id="29c9e-151">MINING_STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="29c9e-151">MINING_STRUCTURE</span></span>|<span data-ttu-id="29c9e-152">Zuordnung</span><span class="sxs-lookup"><span data-stu-id="29c9e-152">Association</span></span>|  
|<span data-ttu-id="29c9e-153">LAST_PROCESSED</span><span class="sxs-lookup"><span data-stu-id="29c9e-153">LAST_PROCESSED</span></span>|<span data-ttu-id="29c9e-154">9/29/2007 10:21:24 PM</span><span class="sxs-lookup"><span data-stu-id="29c9e-154">9/29/2007 10:21:24 PM</span></span>|  
  
 [<span data-ttu-id="29c9e-155">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="29c9e-155">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-3-retrieving-original-parameters-for-model"></a><a name="bkmk_Query3"></a><span data-ttu-id="29c9e-156">Beispiel Abfrage 3: Abrufen von ursprünglichen Parametern für das Modell</span><span class="sxs-lookup"><span data-stu-id="29c9e-156">Sample Query 3: Retrieving Original Parameters for Model</span></span>  
 <span data-ttu-id="29c9e-157">Die folgende Abfrage gibt eine einzelne Spalte mit Details über die Parametereinstellungen zurück, die beim Erstellen des Modells verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="29c9e-157">The following query returns a single column that contains details about the parameter settings that were used when the model was created.</span></span>  
  
```  
SELECT MINING_PARAMETERS   
from $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'Association'  
```  
  
 <span data-ttu-id="29c9e-158">Beispielergebnisse:</span><span class="sxs-lookup"><span data-stu-id="29c9e-158">Example results:</span></span>  
  
 <span data-ttu-id="29c9e-159">MAXIMUM_ITEMSET_COUNT=200000, MAXIMUM_ITEMSET_SIZE=3, MAXIMUM_SUPPORT=1, MINIMUM_SUPPORT=9.40923449156529E-04, MINIMUM_IMPORTANCE=-999999999,MINIMUM_ITEMSET_SIZE=0, MINIMUM_PROBABILITY=0.4</span><span class="sxs-lookup"><span data-stu-id="29c9e-159">MAXIMUM_ITEMSET_COUNT=200000,MAXIMUM_ITEMSET_SIZE=3,MAXIMUM_SUPPORT=1,MINIMUM_SUPPORT=9.40923449156529E-04,MINIMUM_IMPORTANCE=-999999999,MINIMUM_ITEMSET_SIZE=0,MINIMUM_PROBABILITY=0.4</span></span>  
  
 [<span data-ttu-id="29c9e-160">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="29c9e-160">Return to Top</span></span>](#bkmk_top2)  
  
## <a name="finding-information-about-rules-and-itemsets"></a><span data-ttu-id="29c9e-161">Suchen nach Informationen über Regeln und Itemsets</span><span class="sxs-lookup"><span data-stu-id="29c9e-161">Finding Information about Rules and Itemsets</span></span>  
 <span data-ttu-id="29c9e-162">Ein Zuordnungsmodell dient im Wesentlichen zwei Zwecken: dem Finden von Informationen über häufig vorhandene Itemsets und dem Extrahieren von Details über bestimmte Regeln und Itemsets.</span><span class="sxs-lookup"><span data-stu-id="29c9e-162">There are two common uses of an association model: to discover information about frequent itemsets, and to extract details about particular rules and itemsets.</span></span> <span data-ttu-id="29c9e-163">Sie können beispielsweise eine Liste der Regeln extrahieren, die als besonders interessant eingestuft wurden, oder eine Liste mit den gängigsten Itemsets erstellen.</span><span class="sxs-lookup"><span data-stu-id="29c9e-163">For example, you might want to extract a list of rules that were scored as being especially interesting, or create a list of the most common itemsets.</span></span> <span data-ttu-id="29c9e-164">Diese Informationen rufen Sie mit einer DMX-Inhaltsabfrage ab.</span><span class="sxs-lookup"><span data-stu-id="29c9e-164">You retrieve such information by using a DMX content query.</span></span> <span data-ttu-id="29c9e-165">Sie können auch mithilfe des **Microsoft Association Viewer**nach diesen Informationen suchen.</span><span class="sxs-lookup"><span data-stu-id="29c9e-165">You can also browse this information by using the **Microsoft Association Viewer**.</span></span>  
  
###  <a name="sample-query-4-retrieving-list-of-itemsets-and-products"></a><a name="bkmk_Query4"></a> <span data-ttu-id="29c9e-166">Beispiel Abfrage 4: Abrufen der Liste von Itemsets und Produkten</span><span class="sxs-lookup"><span data-stu-id="29c9e-166">Sample Query 4: Retrieving List of Itemsets and Products</span></span>  
 <span data-ttu-id="29c9e-167">Mit folgender Abfrage werden alle Itemsets sowie eine geschachtelte Tabelle abgerufen, in der die in den einzelnen Itemsets enthaltenen Produkte aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="29c9e-167">The following query retrieves all of the itemsets, together with a nested table that lists the products included in each itemset.</span></span> <span data-ttu-id="29c9e-168">Die Spalte NODE_NAME enthält die eindeutige ID des Itemsets innerhalb des Modells, während die Spalte NODE_CAPTION eine Textbeschreibung der Elemente zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="29c9e-168">The NODE_NAME column contains the unique ID of the itemset within the model, whereas the NODE_CAPTION provides a text description of the items.</span></span> <span data-ttu-id="29c9e-169">In diesem Beispiel wird die geschachtelte Tabelle vereinfacht, sodass ein Itemset, das zwei Produkte enthält, zwei Zeilen in den Ergebnissen generiert.</span><span class="sxs-lookup"><span data-stu-id="29c9e-169">In this example, the nested table is flattened, so that an itemset that contains two products generates two rows in the results.</span></span> <span data-ttu-id="29c9e-170">Sie können das FLATTENED-Schlüsselwort auslassen, wenn der Client hierarchische Daten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="29c9e-170">You can omit the FLATTENED keyword if your client supports hierarchical data.</span></span>  
  
```  
SELECT FLATTENED NODE_NAME, NODE_CAPTION,  
NODE_PROBABILITY, NODE_SUPPORT,  
(SELECT ATTRIBUTE_NAME FROM NODE_DISTRIBUTION) as PurchasedProducts  
FROM Association.CONTENT  
WHERE NODE_TYPE = 7  
```  
  
 <span data-ttu-id="29c9e-171">Beispielergebnisse:</span><span class="sxs-lookup"><span data-stu-id="29c9e-171">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="29c9e-172">NODE_NAME</span><span class="sxs-lookup"><span data-stu-id="29c9e-172">NODE_NAME</span></span>|<span data-ttu-id="29c9e-173">37</span><span class="sxs-lookup"><span data-stu-id="29c9e-173">37</span></span>|  
|<span data-ttu-id="29c9e-174">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="29c9e-174">NODE_CAPTION</span></span>|<span data-ttu-id="29c9e-175">Sport-100 = Existing</span><span class="sxs-lookup"><span data-stu-id="29c9e-175">Sport-100 = Existing</span></span>|  
|<span data-ttu-id="29c9e-176">NODE_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="29c9e-176">NODE_PROBABILITY</span></span>|<span data-ttu-id="29c9e-177">0.291283016331743</span><span class="sxs-lookup"><span data-stu-id="29c9e-177">0.291283016331743</span></span>|  
|<span data-ttu-id="29c9e-178">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="29c9e-178">NODE_SUPPORT</span></span>|<span data-ttu-id="29c9e-179">4334</span><span class="sxs-lookup"><span data-stu-id="29c9e-179">4334</span></span>|  
|<span data-ttu-id="29c9e-180">PURCHASEDPRODUCTS.ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="29c9e-180">PURCHASEDPRODUCTS.ATTRIBUTE_NAME</span></span>|<span data-ttu-id="29c9e-181">v Assoc Seq Line Items(Sport-100)</span><span class="sxs-lookup"><span data-stu-id="29c9e-181">v Assoc Seq Line Items(Sport-100)</span></span>|  
  
 [<span data-ttu-id="29c9e-182">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="29c9e-182">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-5-returning-top-10-itemsets"></a><a name="bkmk_Query5"></a><span data-ttu-id="29c9e-183">Beispiel Abfrage 5: Zurückgeben der obersten 10 Itemsets</span><span class="sxs-lookup"><span data-stu-id="29c9e-183">Sample Query 5: Returning Top 10 Itemsets</span></span>  
 <span data-ttu-id="29c9e-184">Dieses Beispiel zeigt, wie einige der Gruppierungs- und Anordnungsfunktionen, die von DMX standardmäßig bereitgestellt werden, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="29c9e-184">This example demonstrates how to use some of the grouping and ordering functions that DMX provides by default.</span></span> <span data-ttu-id="29c9e-185">Die Abfrage gibt die obersten 10 Itemsets zurück, wenn diese entsprechend der Unterstützung für jeden Knoten angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="29c9e-185">The query returns the top 10 itemsets when ordered by the support for each node.</span></span> <span data-ttu-id="29c9e-186">Die Ergebnisse müssen nicht explizit wie in Transact-SQL gruppiert werden. Sie können in jeder Abfrage nur eine Aggregatfunktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="29c9e-186">Note that you do not need to explicitly group the results, as you would in Transact-SQL; however, you can use only one aggregate function in each query.</span></span>  
  
```  
SELECT TOP 10 (NODE_SUPPORT),NODE_NAME, NODE_CAPTION  
FROM Association.CONTENT  
WHERE NODE_TYPE = 7  
```  
  
 <span data-ttu-id="29c9e-187">Beispielergebnisse:</span><span class="sxs-lookup"><span data-stu-id="29c9e-187">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="29c9e-188">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="29c9e-188">NODE_SUPPORT</span></span>|<span data-ttu-id="29c9e-189">4334</span><span class="sxs-lookup"><span data-stu-id="29c9e-189">4334</span></span>|  
|<span data-ttu-id="29c9e-190">NODE_NAME</span><span class="sxs-lookup"><span data-stu-id="29c9e-190">NODE_NAME</span></span>|<span data-ttu-id="29c9e-191">37</span><span class="sxs-lookup"><span data-stu-id="29c9e-191">37</span></span>|  
|<span data-ttu-id="29c9e-192">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="29c9e-192">NODE_CAPTION</span></span>|<span data-ttu-id="29c9e-193">Sport-100 = Existing</span><span class="sxs-lookup"><span data-stu-id="29c9e-193">Sport-100 = Existing</span></span>|  
  
 [<span data-ttu-id="29c9e-194">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="29c9e-194">Return to Top</span></span>](#bkmk_top2)  
  
## <a name="making-predictions-using-the-model"></a><span data-ttu-id="29c9e-195">Treffen von Vorhersagen mit dem Modell</span><span class="sxs-lookup"><span data-stu-id="29c9e-195">Making Predictions using the Model</span></span>  
 <span data-ttu-id="29c9e-196">Ein Zuordnungsregelnmodell wird häufig zum Generieren von Empfehlungen verwendet, die auf in den Itemsets gefundenen Korrelationen basieren.</span><span class="sxs-lookup"><span data-stu-id="29c9e-196">An association rules model is often used to generate recommendations, which are based on correlations discovered in the itemsets.</span></span> <span data-ttu-id="29c9e-197">Wenn Sie eine Vorhersageabfrage auf Basis eines Modells für Zuordnungsregeln erstellen, werden die Regeln im Modell üblicherweise verwendet, um Vermutungen basierend auf neuen Daten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="29c9e-197">Therefore, when you create a prediction query based on an association rules model, you are typically using the rules in the model to make guesses based on new data.</span></span>  <span data-ttu-id="29c9e-198">[PredictAssociation &#40;DMX&#41;](/sql/dmx/predictassociation-dmx) werden Empfehlungen zurückgegeben. Diese Funktion besitzt mehrere Argumente, mit denen Sie Abfrageergebnisse anpassen können.</span><span class="sxs-lookup"><span data-stu-id="29c9e-198">[PredictAssociation &#40;DMX&#41;](/sql/dmx/predictassociation-dmx) is the function that returns recommendations, and has several arguments that you can use to customize the query results.</span></span>  
  
 <span data-ttu-id="29c9e-199">Ein anderes Beispiel für den sinnvollen Einsatz von Abfragen bei einem Zuordnungsmodell ist die Rückgabe des Vertrauenswerts für verschiedene Regeln und Itemsets, sodass Sie die Effektivität verschiedener Cross-Selling-Strategien vergleichen können.</span><span class="sxs-lookup"><span data-stu-id="29c9e-199">Another example of where queries on an association model might be useful is to return the confidence for various rules and itemsets so that you can compare the effectiveness of different cross-sell strategies.</span></span> <span data-ttu-id="29c9e-200">In den folgenden Beispielen wird gezeigt, wie derartige Abfragen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="29c9e-200">The following examples illustrate how to create such queries.</span></span>  
  
###  <a name="sample-query-6-predicting-associated-items"></a><a name="bkmk_Query6"></a><span data-ttu-id="29c9e-201">Beispiel Abfrage 6: Vorhersagen von zugeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="29c9e-201">Sample Query 6: Predicting Associated Items</span></span>  
 <span data-ttu-id="29c9e-202">In diesem Beispiel wird das im [Data Mining-Tutorial für Fortgeschrittene &#40;Analysis Services – Data Mining&#41;](../../tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) erstellte Zuordnungsmodell verwendet.</span><span class="sxs-lookup"><span data-stu-id="29c9e-202">This example uses the Association model created in the [Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span></span> <span data-ttu-id="29c9e-203">Es zeigt, wie Sie eine Vorhersageabfrage erstellen, die Aufschluss darüber gibt, welche Produkte Sie einem Kunden empfehlen sollten, der ein bestimmtes Produkt gekauft hat.</span><span class="sxs-lookup"><span data-stu-id="29c9e-203">It demonstrates how to create a prediction query that tells you what products to recommend to a customer who has purchased a particular product.</span></span> <span data-ttu-id="29c9e-204">Dieser Abfragetyp, bei dem Sie mithilfe einer `SELECT...UNION`-Anweisung Werte für das Modell bereitstellen, wird als SINGLETON-Abfrage bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="29c9e-204">This type of query, where you provide values to the model in a `SELECT...UNION` statement, is called a singleton query.</span></span> <span data-ttu-id="29c9e-205">Da es sich bei der vorhersagbaren Spalte des Modells, die den neuen Werten entspricht, um eine geschachtelte Tabelle handelt, müssen Sie eine `SELECT`-Klausel verwenden, um den neuen Wert der geschachtelten Tabellenspalte zuzuordnen, `[Model]` und eine weitere `SELECT`-Klausel, um die geschachtelte Tabellenspalte der Spalte auf Fallebene `[v Assoc Seq Line Items]` zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="29c9e-205">Because the predictable model column that corresponds to the new values is a nested table, you must use one `SELECT` clause to map the new value to the nested table column, `[Model]`, and another `SELECT` clause to map the nested table column to the case-level column, `[v Assoc Seq Line Items]`.</span></span> <span data-ttu-id="29c9e-206">Durch Hinzufügen des Schlüsselworts INCLUDE-STATISTICS zur Abfrage können Sie die Wahrscheinlichkeit und die Unterstützung für die Empfehlungen sehen.</span><span class="sxs-lookup"><span data-stu-id="29c9e-206">Adding the keyword INCLUDE-STATISTICS to the query lets you see the probability and support for the recommendations.</span></span>  
  
```  
SELECT PredictAssociation([Association].[vAssocSeqLineItems],INCLUDE_STATISTICS, 3)  
FROM [Association]  
NATURAL PREDICTION JOIN   
(SELECT  
(SELECT 'Classic Vest' as [Model])  
AS [v Assoc Seq Line Items])  
AS t  
```  
  
 <span data-ttu-id="29c9e-207">Beispielergebnisse:</span><span class="sxs-lookup"><span data-stu-id="29c9e-207">Example results:</span></span>  
  
|<span data-ttu-id="29c9e-208">Modell</span><span class="sxs-lookup"><span data-stu-id="29c9e-208">Model</span></span>|<span data-ttu-id="29c9e-209">$SUPPORT</span><span class="sxs-lookup"><span data-stu-id="29c9e-209">$SUPPORT</span></span>|<span data-ttu-id="29c9e-210">$PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="29c9e-210">$PROBABILITY</span></span>|<span data-ttu-id="29c9e-211">$ADJUSTEDPROBABILITY</span><span class="sxs-lookup"><span data-stu-id="29c9e-211">$ADJUSTEDPROBABILITY</span></span>|  
|-----------|--------------|------------------|--------------------------|  
|<span data-ttu-id="29c9e-212">Sport-100</span><span class="sxs-lookup"><span data-stu-id="29c9e-212">Sport-100</span></span>|<span data-ttu-id="29c9e-213">4334</span><span class="sxs-lookup"><span data-stu-id="29c9e-213">4334</span></span>|<span data-ttu-id="29c9e-214">0.291283</span><span class="sxs-lookup"><span data-stu-id="29c9e-214">0.291283</span></span>|<span data-ttu-id="29c9e-215">0.252696</span><span class="sxs-lookup"><span data-stu-id="29c9e-215">0.252696</span></span>|  
|<span data-ttu-id="29c9e-216">Water Bottle</span><span class="sxs-lookup"><span data-stu-id="29c9e-216">Water Bottle</span></span>|<span data-ttu-id="29c9e-217">2866</span><span class="sxs-lookup"><span data-stu-id="29c9e-217">2866</span></span>|<span data-ttu-id="29c9e-218">0.19262</span><span class="sxs-lookup"><span data-stu-id="29c9e-218">0.19262</span></span>|<span data-ttu-id="29c9e-219">0.175205</span><span class="sxs-lookup"><span data-stu-id="29c9e-219">0.175205</span></span>|  
|<span data-ttu-id="29c9e-220">Patchkit</span><span class="sxs-lookup"><span data-stu-id="29c9e-220">Patch kit</span></span>|<span data-ttu-id="29c9e-221">2113</span><span class="sxs-lookup"><span data-stu-id="29c9e-221">2113</span></span>|<span data-ttu-id="29c9e-222">0.142012</span><span class="sxs-lookup"><span data-stu-id="29c9e-222">0.142012</span></span>|<span data-ttu-id="29c9e-223">0.132389</span><span class="sxs-lookup"><span data-stu-id="29c9e-223">0.132389</span></span>|  
  
 [<span data-ttu-id="29c9e-224">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="29c9e-224">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-7-determining-confidence-for-related-itemsets"></a><a name="bkmk_Query7"></a><span data-ttu-id="29c9e-225">Beispiel Abfrage 7: Bestimmen von Vertrauen für verwandte Itemsets</span><span class="sxs-lookup"><span data-stu-id="29c9e-225">Sample Query 7: Determining Confidence for Related Itemsets</span></span>  
 <span data-ttu-id="29c9e-226">Während Regeln nützlich sind, um Empfehlungen zu generieren, sind Itemsets eher für eine tiefer gehende Analyse der Muster im Dataset interessant.</span><span class="sxs-lookup"><span data-stu-id="29c9e-226">Whereas rules are useful for generating recommendations, itemsets are more interesting for deeper analysis of the patterns in the data set.</span></span> <span data-ttu-id="29c9e-227">Wenn Sie beispielsweise mit den Empfehlungen, die von der vorherigen Beispielabfrage zurückgegeben wurden, nicht zufrieden sind, können Sie andere Itemsets, die das Produkt A enthalten, prüfen. So können Sie sich ein Bild machen, ob Produkt A ein Zubehör ist, das eher zusammen mit beliebigen anderen Produkten gekauft wird, oder ob Produkt A eng mit dem Kauf bestimmter Produkte verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="29c9e-227">For example, if you were not satisfied with the recommendation that are returned by the previous sample query, you could examine other itemsets that contain Product A, to can get a better idea of whether Product A is an accessory that people tend to buy with all kinds of products, or whether A is strongly correlated with purchases of particular products.</span></span> <span data-ttu-id="29c9e-228">Die einfachste Möglichkeit zur Prüfung dieser Beziehungen besteht darin, die Itemsets im [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Viewer zu filtern. Sie können die gleichen Informationen jedoch auch mit einer Abfrage abrufen.</span><span class="sxs-lookup"><span data-stu-id="29c9e-228">The easiest way to explore these relationships is by filtering the itemsets in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Viewer; however, you can retrieve the same information with a query.</span></span>  
  
 <span data-ttu-id="29c9e-229">Mit der folgenden Beispielabfrage werden alle Itemsets zurückgegeben, die das Element "Water Bottle" enthalten, einschließlich des einzelnen Elements "Water bottle".</span><span class="sxs-lookup"><span data-stu-id="29c9e-229">The following sample query returns all itemsets that include the Water Bottle item, including the single item Water bottle.</span></span>  
  
```  
SELECT TOP 100 FROM   
(  
SELECT FLATTENED NODE_CAPTION, NODE_SUPPORT,   
(SELECT ATTRIBUTE_NAME from NODE_DISTRIBUTION  
WHERE ATTRIBUTE_NAME = 'v Assoc Seq Line Items(Water Bottle)') as D  
FROM Association.CONTENT  
WHERE NODE_TYPE = 7  
) AS Items  
WHERE [D.ATTRIBUTE_NAME] <> NULL  
ORDER BY NODE_SUPPORT DESC  
```  
  
 <span data-ttu-id="29c9e-230">Beispielergebnisse:</span><span class="sxs-lookup"><span data-stu-id="29c9e-230">Example results:</span></span>  
  
|<span data-ttu-id="29c9e-231">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="29c9e-231">NODE_CAPTION</span></span>|<span data-ttu-id="29c9e-232">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="29c9e-232">NODE_SUPPORT</span></span>|<span data-ttu-id="29c9e-233">D.ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="29c9e-233">D.ATTRIBUTE_NAME</span></span>|  
|-------------------|-------------------|-----------------------|  
|<span data-ttu-id="29c9e-234">Water Bottle = Existing</span><span class="sxs-lookup"><span data-stu-id="29c9e-234">Water Bottle = Existing</span></span>|<span data-ttu-id="29c9e-235">2866</span><span class="sxs-lookup"><span data-stu-id="29c9e-235">2866</span></span>|<span data-ttu-id="29c9e-236">v Assoc Seq Line Items(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="29c9e-236">v Assoc Seq Line Items(Water Bottle)</span></span>|  
|<span data-ttu-id="29c9e-237">Mountain Bottle Cage = Existing, Water Bottle = Existing</span><span class="sxs-lookup"><span data-stu-id="29c9e-237">Mountain Bottle Cage = Existing, Water Bottle = Existing</span></span>|<span data-ttu-id="29c9e-238">1.136</span><span class="sxs-lookup"><span data-stu-id="29c9e-238">1136</span></span>|<span data-ttu-id="29c9e-239">v Assoc Seq Line Items(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="29c9e-239">v Assoc Seq Line Items(Water Bottle)</span></span>|  
|<span data-ttu-id="29c9e-240">Road Bottle Cage = Existing, Water Bottle = Existing</span><span class="sxs-lookup"><span data-stu-id="29c9e-240">Road Bottle Cage = Existing, Water Bottle = Existing</span></span>|<span data-ttu-id="29c9e-241">1068</span><span class="sxs-lookup"><span data-stu-id="29c9e-241">1068</span></span>|<span data-ttu-id="29c9e-242">v Assoc Seq Line Items(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="29c9e-242">v Assoc Seq Line Items(Water Bottle)</span></span>|  
|<span data-ttu-id="29c9e-243">Water Bottle = Existing, Sport-100 = Existing</span><span class="sxs-lookup"><span data-stu-id="29c9e-243">Water Bottle = Existing, Sport-100 = Existing</span></span>|<span data-ttu-id="29c9e-244">734</span><span class="sxs-lookup"><span data-stu-id="29c9e-244">734</span></span>|<span data-ttu-id="29c9e-245">v Assoc Seq Line Items(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="29c9e-245">v Assoc Seq Line Items(Water Bottle)</span></span>|  
  
 <span data-ttu-id="29c9e-246">Mit dieser Abfrage werden die Zeilen der geschachtelten Tabelle zurückgegeben, die den Kriterien entsprechen, sowie alle Zeilen der Außen- oder Falltabelle.</span><span class="sxs-lookup"><span data-stu-id="29c9e-246">This query returns both the rows from the nested table that match the criteria, and all the rows from the outside or case table.</span></span> <span data-ttu-id="29c9e-247">Daher müssen Sie eine Bedingung hinzufügen, mit der die Falltabellenzeilen mit einem NULL-Wert für den Zielattributnamen entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="29c9e-247">Therefore, you must add a condition that eliminates the case table rows that have a null value for the target attribute name.</span></span>  
  
 [<span data-ttu-id="29c9e-248">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="29c9e-248">Return to Top</span></span>](#bkmk_top2)  
  
## <a name="function-list"></a><span data-ttu-id="29c9e-249">Funktionsliste</span><span class="sxs-lookup"><span data-stu-id="29c9e-249">Function List</span></span>  
 <span data-ttu-id="29c9e-250">Alle Algorithmen von [!INCLUDE[msCoName](../../includes/msconame-md.md)] unterstützen einen gemeinsamen Funktionssatz.</span><span class="sxs-lookup"><span data-stu-id="29c9e-250">All [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms support a common set of functions.</span></span> <span data-ttu-id="29c9e-251">Der [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association-Algorithmus unterstützt jedoch zusätzliche Funktionen, die in der folgenden Tabelle aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="29c9e-251">However, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association algorithm supports the additional functions listed in the following table.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="29c9e-252">Vorhersagefunktion</span><span class="sxs-lookup"><span data-stu-id="29c9e-252">Prediction Function</span></span>|<span data-ttu-id="29c9e-253">Verwendung</span><span class="sxs-lookup"><span data-stu-id="29c9e-253">Usage</span></span>|  
|[<span data-ttu-id="29c9e-254">IsDescendant &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="29c9e-254">IsDescendant &#40;DMX&#41;</span></span>](/sql/dmx/isdescendant-dmx)|<span data-ttu-id="29c9e-255">Bestimmt, ob ein Knoten ein untergeordnetes Element eines anderen Knotens im Diagramm für neuronale Netzwerke ist.</span><span class="sxs-lookup"><span data-stu-id="29c9e-255">Determines whether one node is a child of another node in the neural network graph.</span></span>|  
|[<span data-ttu-id="29c9e-256">IsInNode &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="29c9e-256">IsInNode &#40;DMX&#41;</span></span>](/sql/dmx/isinnode-dmx)|<span data-ttu-id="29c9e-257">Zeigt an, ob der angegebene Knoten den aktuellen Fall enthält.</span><span class="sxs-lookup"><span data-stu-id="29c9e-257">Indicates whether the specified node contains the current case.</span></span>|  
|[<span data-ttu-id="29c9e-258">PredictAdjustedProbability &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="29c9e-258">PredictAdjustedProbability &#40;DMX&#41;</span></span>](/sql/dmx/predictadjustedprobability-dmx)|<span data-ttu-id="29c9e-259">Gibt die gewichtete Wahrscheinlichkeit zurück.</span><span class="sxs-lookup"><span data-stu-id="29c9e-259">Returns the weighted probability.</span></span>|  
|[<span data-ttu-id="29c9e-260">PredictAssociation &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="29c9e-260">PredictAssociation &#40;DMX&#41;</span></span>](/sql/dmx/predictassociation-dmx)|<span data-ttu-id="29c9e-261">Sagt eine Mitgliedschaft in einem assoziativen Dataset voraus.</span><span class="sxs-lookup"><span data-stu-id="29c9e-261">Predicts membership in an associative dataset.</span></span>|  
|[<span data-ttu-id="29c9e-262">PredictHistogram &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="29c9e-262">PredictHistogram &#40;DMX&#41;</span></span>](/sql/dmx/predicthistogram-dmx)|<span data-ttu-id="29c9e-263">Gibt eine Tabelle mit Werten zurück, die sich auf den aktuellen vorhergesagten Wert beziehen.</span><span class="sxs-lookup"><span data-stu-id="29c9e-263">Returns a table of values related to the current predicted value.</span></span>|  
|[<span data-ttu-id="29c9e-264">PredictNodeId &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="29c9e-264">PredictNodeId &#40;DMX&#41;</span></span>](/sql/dmx/predictnodeid-dmx)|<span data-ttu-id="29c9e-265">Gibt "Node_ID" für jeden Fall zurück.</span><span class="sxs-lookup"><span data-stu-id="29c9e-265">Returns the Node_ID for each case.</span></span>|  
|[<span data-ttu-id="29c9e-266">PredictProbability &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="29c9e-266">PredictProbability &#40;DMX&#41;</span></span>](/sql/dmx/predictprobability-dmx)|<span data-ttu-id="29c9e-267">Gibt die Wahrscheinlichkeit für den vorhergesagten Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="29c9e-267">Returns probability for the predicted value.</span></span>|  
|[<span data-ttu-id="29c9e-268">PredictSupport &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="29c9e-268">PredictSupport &#40;DMX&#41;</span></span>](/sql/dmx/predictsupport-dmx)|<span data-ttu-id="29c9e-269">Gibt den Unterstützungswert für einen bestimmten Status zurück.</span><span class="sxs-lookup"><span data-stu-id="29c9e-269">Returns the support value for a specified state.</span></span>|  
|[<span data-ttu-id="29c9e-270">PredictVariance &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="29c9e-270">PredictVariance &#40;DMX&#41;</span></span>](/sql/dmx/predictvariance-dmx)|<span data-ttu-id="29c9e-271">Gibt die Varianz für den vorhergesagten Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="29c9e-271">Returns variance for the predicted value.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="29c9e-272">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="29c9e-272">See Also</span></span>  
 <span data-ttu-id="29c9e-273">[Microsoft Association-Algorithmus](microsoft-association-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="29c9e-273">[Microsoft Association Algorithm](microsoft-association-algorithm.md) </span></span>  
 <span data-ttu-id="29c9e-274">[Technische Referenz für den Microsoft Association-Algorithmus](microsoft-association-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="29c9e-274">[Microsoft Association Algorithm Technical Reference](microsoft-association-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="29c9e-275">Miningmodellinhalt von Zuordnungsmodellen &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="29c9e-275">Mining Model Content for Association Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-model-content-for-association-models-analysis-services-data-mining.md)  
  
  
