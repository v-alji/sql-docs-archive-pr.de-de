---
title: Verarbeiten von Objekten (XMLA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- errors [XML for Analysis]
- objects [XML for Analysis]
- XML for Analysis, objects
- XMLA, partitions
- partitions [Analysis Services], XML for Analysis
- XML for Analysis, partitions
- writeback [Analysis Services], XML for Analysis
- out-of-line bindings
- processing objects [XML for Analysis]
- XMLA, objects
ms.assetid: a65b3249-303d-49c6-98af-6ac6eed11a03
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e59c7953ae8fc7d3cfceafa7b0e9d8c7186daf8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723186"
---
# <a name="processing-objects-xmla"></a><span data-ttu-id="befe4-102">Verarbeiten von Objekten (XMLA)</span><span class="sxs-lookup"><span data-stu-id="befe4-102">Processing Objects (XMLA)</span></span>
  <span data-ttu-id="befe4-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ist die Verarbeitung der Schritt oder eine Reihe von Schritten, durch die Daten in Informationen für Geschäftsanalysen umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="befe4-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], processing is the step or series of steps that turn data into information for business analysis.</span></span> <span data-ttu-id="befe4-104">Die Verarbeitung ist je nach Objekttyp unterschiedlich, aber immer Teil einer Umwandlung von Daten in Informationen.</span><span class="sxs-lookup"><span data-stu-id="befe4-104">Processing is different depending on the type of object, but processing is always part of turning data into information.</span></span>  
  
 <span data-ttu-id="befe4-105">Zum Verarbeiten eines [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Objekts können Sie den [Process](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/process-element-xmla) -Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="befe4-105">To process an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] object, you can use the [Process](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/process-element-xmla) command.</span></span> <span data-ttu-id="befe4-106">Der Befehl `Process` kann die folgenden Objekte auf einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Instanz verarbeiten:</span><span class="sxs-lookup"><span data-stu-id="befe4-106">The `Process` command can process the following objects on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance:</span></span>  
  
-   <span data-ttu-id="befe4-107">Cubes</span><span class="sxs-lookup"><span data-stu-id="befe4-107">Cubes</span></span>  
  
-   <span data-ttu-id="befe4-108">Datenbanken</span><span class="sxs-lookup"><span data-stu-id="befe4-108">Databases</span></span>  
  
-   <span data-ttu-id="befe4-109">Dimensionen</span><span class="sxs-lookup"><span data-stu-id="befe4-109">Dimensions</span></span>  
  
-   <span data-ttu-id="befe4-110">Measuregruppen</span><span class="sxs-lookup"><span data-stu-id="befe4-110">Measure groups</span></span>  
  
-   <span data-ttu-id="befe4-111">Miningmodelle</span><span class="sxs-lookup"><span data-stu-id="befe4-111">Mining models</span></span>  
  
-   <span data-ttu-id="befe4-112">Miningstrukturen</span><span class="sxs-lookup"><span data-stu-id="befe4-112">Mining structures</span></span>  
  
-   <span data-ttu-id="befe4-113">Partitionen</span><span class="sxs-lookup"><span data-stu-id="befe4-113">Partitions</span></span>  
  
 <span data-ttu-id="befe4-114">Um die Verarbeitung von Objekten zu kontrollieren, verfügt der Befehl `Process` über verschiedene Eigenschaften, die festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="befe4-114">To control the processing of objects, the `Process` command has various properties that can be set.</span></span> <span data-ttu-id="befe4-115">Der `Process`-Befehl verfügt über Eigenschaften, die kontrollieren, wie viel Verarbeitung stattfinden wird, welche Objekte verarbeitet werden, ob Out-of-Line-Bindungen zum Einsatz kommen, wie Fehler gehandhabt und wie Rückschreibetabellen verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="befe4-115">The `Process` command has properties that control: how much processing will be done, which objects will be processed, whether to use out-of-line bindings, how to handle errors, and how to manage writeback tables.</span></span>  
  
## <a name="specifying-processing-options"></a><span data-ttu-id="befe4-116">Angeben von Verarbeitungsoptionen</span><span class="sxs-lookup"><span data-stu-id="befe4-116">Specifying Processing Options</span></span>  
 <span data-ttu-id="befe4-117">Die [Type](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/type-element-xmla) -Eigenschaft des- `Process` Befehls gibt die Verarbeitungsoption an, die bei der Verarbeitung des-Objekts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="befe4-117">The [Type](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/type-element-xmla) property of the `Process` command specifies the processing option to use when processing the object.</span></span> <span data-ttu-id="befe4-118">Weitere Informationen zu Verarbeitungsoptionen finden Sie unter [Verarbeitungsoptionen und -einstellungen &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="befe4-118">For more information about processing options, see [Processing Options and Settings &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md).</span></span>  
  
 <span data-ttu-id="befe4-119">In der folgenden Tabelle werden die Konstanten der Eigenschaft `Type` und die verschiedenen Objekte, die über die Konstanten verarbeitet werden können, aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="befe4-119">The following table lists the constants for the `Type` property and the various objects that can be processed using each constant.</span></span>  
  
|<span data-ttu-id="befe4-120">`Type`-Wert</span><span class="sxs-lookup"><span data-stu-id="befe4-120">`Type` value</span></span>|<span data-ttu-id="befe4-121">Anwendbare Objekte</span><span class="sxs-lookup"><span data-stu-id="befe4-121">Applicable objects</span></span>|  
|--------------------|------------------------|  
|<span data-ttu-id="befe4-122">*ProcessFull*</span><span class="sxs-lookup"><span data-stu-id="befe4-122">*ProcessFull*</span></span>|<span data-ttu-id="befe4-123">Cube, Datenbank, Dimension, Measuregruppe, Miningmodell, Miningstruktur, Partition</span><span class="sxs-lookup"><span data-stu-id="befe4-123">Cube, database, dimension, measure group, mining model, mining structure, partition</span></span>|  
|<span data-ttu-id="befe4-124">*ProcessAdd*</span><span class="sxs-lookup"><span data-stu-id="befe4-124">*ProcessAdd*</span></span>|<span data-ttu-id="befe4-125">Dimension, Partition</span><span class="sxs-lookup"><span data-stu-id="befe4-125">Dimension, partition</span></span>|  
|<span data-ttu-id="befe4-126">*ProcessUpdate*</span><span class="sxs-lookup"><span data-stu-id="befe4-126">*ProcessUpdate*</span></span>|<span data-ttu-id="befe4-127">Dimension</span><span class="sxs-lookup"><span data-stu-id="befe4-127">Dimension</span></span>|  
|<span data-ttu-id="befe4-128">*ProcessIndexes*</span><span class="sxs-lookup"><span data-stu-id="befe4-128">*ProcessIndexes*</span></span>|<span data-ttu-id="befe4-129">Dimension, Cube, Measuregruppe, Partition</span><span class="sxs-lookup"><span data-stu-id="befe4-129">Dimension, cube, measure group, partition</span></span>|  
|<span data-ttu-id="befe4-130">*ProcessData*</span><span class="sxs-lookup"><span data-stu-id="befe4-130">*ProcessData*</span></span>|<span data-ttu-id="befe4-131">Dimension, Cube, Measuregruppe, Partition</span><span class="sxs-lookup"><span data-stu-id="befe4-131">Dimension, cube, measure group, partition</span></span>|  
|<span data-ttu-id="befe4-132">*ProcessDefault*</span><span class="sxs-lookup"><span data-stu-id="befe4-132">*ProcessDefault*</span></span>|<span data-ttu-id="befe4-133">Cube, Datenbank, Dimension, Measuregruppe, Miningmodell, Miningstruktur, Partition</span><span class="sxs-lookup"><span data-stu-id="befe4-133">Cube, database, dimension, measure group, mining model, mining structure, partition</span></span>|  
|<span data-ttu-id="befe4-134">*ProcessClear*</span><span class="sxs-lookup"><span data-stu-id="befe4-134">*ProcessClear*</span></span>|<span data-ttu-id="befe4-135">Cube, Datenbank, Dimension, Measuregruppe, Miningmodell, Miningstruktur, Partition</span><span class="sxs-lookup"><span data-stu-id="befe4-135">Cube, database, dimension, measure group, mining model, mining structure, partition</span></span>|  
|<span data-ttu-id="befe4-136">*ProcessStructure*</span><span class="sxs-lookup"><span data-stu-id="befe4-136">*ProcessStructure*</span></span>|<span data-ttu-id="befe4-137">Cube, Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="befe4-137">Cube, mining structure</span></span>|  
|<span data-ttu-id="befe4-138">*ProcessClearStructureOnly*</span><span class="sxs-lookup"><span data-stu-id="befe4-138">*ProcessClearStructureOnly*</span></span>|<span data-ttu-id="befe4-139">Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="befe4-139">Mining structure</span></span>|  
|<span data-ttu-id="befe4-140">*ProcessScriptCache*</span><span class="sxs-lookup"><span data-stu-id="befe4-140">*ProcessScriptCache*</span></span>|<span data-ttu-id="befe4-141">Cube</span><span class="sxs-lookup"><span data-stu-id="befe4-141">Cube</span></span>|  
  
 <span data-ttu-id="befe4-142">Weitere Informationen zum Verarbeiten von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Objekten finden Sie unter mehr [dimensionale Modell Objekt Verarbeitung](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="befe4-142">For more information about processing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Multidimensional Model Object Processing](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
## <a name="specifying-objects-to-be-processed"></a><span data-ttu-id="befe4-143">Angeben zu verarbeitender Objekte</span><span class="sxs-lookup"><span data-stu-id="befe4-143">Specifying Objects to be Processed</span></span>  
 <span data-ttu-id="befe4-144">Die [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) -Eigenschaft des- `Process` Befehls enthält den Objekt Bezeichner des zu verarbeitenden Objekts.</span><span class="sxs-lookup"><span data-stu-id="befe4-144">The [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `Process` command contains the object identifier of the object to be processed.</span></span> <span data-ttu-id="befe4-145">In einem `Process`-Befehl kann nur ein Objekt angegeben werden. Allerdings führt die Verarbeitung eines Objekts auch zur Verarbeitung aller untergeordneten Objekte.</span><span class="sxs-lookup"><span data-stu-id="befe4-145">Only one object can be specified in a `Process` command, but processing an object also processes any child objects.</span></span> <span data-ttu-id="befe4-146">Beispielsweise werden bei der Verarbeitung einer Measuregruppe in einem Cube alle Partitionen für diese Measuregruppe verarbeitet, während bei der Verarbeitung einer Datenbank alle Objekte, die in der Datenbank enthalten sind, verarbeitet werden, einschließlich Cubes, Dimensionen und Miningstrukturen.</span><span class="sxs-lookup"><span data-stu-id="befe4-146">For example, processing a measure group in a cube processes all the partitions for that measure group, while processing a database processes all the objects, including cubes, dimensions, and mining structures, that are contained by the database.</span></span>  
  
 <span data-ttu-id="befe4-147">Wenn Sie das `ProcessAffectedObjects`-Attribut des `Process`-Befehls auf True setzen, werden alle verwandten Objekte, die von der Verarbeitung des angegebenen Objekts betroffen sind, ebenfalls verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="befe4-147">If you set the `ProcessAffectedObjects` attribute of the `Process` command to true, any related object affected by processing the specified object is also processed.</span></span> <span data-ttu-id="befe4-148">Wenn beispielsweise eine Dimension inkrementell mithilfe der Verarbeitungsoption *ProcessUpdate* im Befehl aktualisiert wird `Process` , wird jede Partition, deren Aggregationen aufgrund von hinzugefügten oder gelöschten Membern ungültig werden, auch von verarbeitet, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Wenn `ProcessAffectedObjects` auf true festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="befe4-148">For example, if a dimension is incrementally updated by using the *ProcessUpdate* processing option in the `Process` command, any partition whose aggregations are invalidated because of members being added or deleted is also processed by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] if `ProcessAffectedObjects` is set to true.</span></span> <span data-ttu-id="befe4-149">In diesem Fall kann ein einzelner `Process`-Befehl mehrere Objekte auf einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Instanz verarbeiten, aber [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] bestimmt, welche Objekte neben dem einzelnen, im `Process`-Befehl angegebenen Objekt ebenfalls verarbeitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="befe4-149">In this case, a single `Process` command can process multiple objects on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, but [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] determines which objects besides the single object specified in the `Process` command must also be processed.</span></span>  
  
 <span data-ttu-id="befe4-150">Allerdings können Sie über die `Process`-Befehle in einem `Batch`-Befehl mehrere Objekte, einschließlich Dimensionen, gleichzeitig verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="befe4-150">However, you can process multiple objects, such as dimensions, at the same time by using multiple `Process` commands within a `Batch` command.</span></span> <span data-ttu-id="befe4-151">Batchvorgänge bieten eine präzisere Kontrolle über die serielle oder parallele Verarbeitung von Objekten auf einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Instanz, als es die Verwendung des `ProcessAffectedObjects`-Attributs tut, und ermöglicht es Ihnen, Ihren Verarbeitungsansatz für größere [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Datenbanken zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="befe4-151">Batch operations provide a finer level of control for serial or parallel processing of objects on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance than using the `ProcessAffectedObjects` attribute, and let you to tune your processing approach for larger [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases.</span></span> <span data-ttu-id="befe4-152">Weitere Informationen zum Ausführen von Batch Vorgängen finden Sie unter Ausführen von Batch Vorgängen [&#40;XMLA&#41;](performing-batch-operations-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="befe4-152">For more information about performing batch operations, see [Performing Batch Operations &#40;XMLA&#41;](performing-batch-operations-xmla.md).</span></span>  
  
## <a name="specifying-out-of-line-bindings"></a><span data-ttu-id="befe4-153">Angeben von Out-of-Line-Bindungen</span><span class="sxs-lookup"><span data-stu-id="befe4-153">Specifying Out-of-Line Bindings</span></span>  
 <span data-ttu-id="befe4-154">Wenn der `Process` Befehl nicht in einem Befehl enthalten ist `Batch` , können Sie optional out-of-Line-Bindungen in den Eigenschaften [Bindungen](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/bindings-element-xmla), [DataSource](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla)und [DataSourceView](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/datasourceview-element-xmla) des `Process` Befehls für die zu verarbeitenden Objekte angeben.</span><span class="sxs-lookup"><span data-stu-id="befe4-154">If the `Process` command is not contained by a `Batch` command, you can optionally specify out-of-line bindings in the [Bindings](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/bindings-element-xmla), [DataSource](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla), and [DataSourceView](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/datasourceview-element-xmla) properties of the `Process` command for the objects to be processed.</span></span> <span data-ttu-id="befe4-155">Out-of-Line-Bindungen sind Verweise auf Datenquellen, Datenquellensichten und andere Objekte, in denen die Bindungen nur während der Ausführung des `Process`-Befehls existieren, und die vorhandene Bindungen, die dem zu verarbeitenden Objekt zugeordnet sind, überschreiben.</span><span class="sxs-lookup"><span data-stu-id="befe4-155">Out-of-line bindings are references to data sources, data source views, and other objects in which the binding exists only during the execution of the `Process` command, and which override any existing bindings associated with the objects being processed.</span></span> <span data-ttu-id="befe4-156">Wenn keine Out-of-Line-Bindungen angegeben sind, werden die Bindungen verwendet, die aktuell dem zu verarbeitenden Objekt zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="befe4-156">If out-of-line bindings are not specified, the bindings currently associated with the objects to be processed are used.</span></span>  
  
 <span data-ttu-id="befe4-157">Out-of-Line-Bindungen werden in den folgenden Situationen verwendet:</span><span class="sxs-lookup"><span data-stu-id="befe4-157">Out-of-line bindings are used in the following circumstances:</span></span>  
  
-   <span data-ttu-id="befe4-158">Inkrementelle Verarbeitung einer Partition, bei der eine alternative Faktentabelle oder ein Filter auf der vorhandenen Faktentabelle angegeben sein muss, um sicherzustellen, dass die Zeilen nicht zweimal gezählt werden.</span><span class="sxs-lookup"><span data-stu-id="befe4-158">Incrementally processing a partition, in which an alternative fact table or a filter on the existing fact table must be specified to make sure that rows are not counted twice.</span></span>  
  
-   <span data-ttu-id="befe4-159">Verwenden eines Datenfluss Tasks in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] zum Bereitstellen von Daten bei der Verarbeitung einer Dimension, eines Mining Modells oder einer Partition.</span><span class="sxs-lookup"><span data-stu-id="befe4-159">Using a data flow task in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to provide data while processing a dimension, mining model, or partition.</span></span>  
  
 <span data-ttu-id="befe4-160">Out-of-Line-Bindungen werden als Teil der Analysis Services Scripting Language (ASSL) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="befe4-160">Out-of-line bindings are described as part of the Analysis Services Scripting Language (ASSL).</span></span> <span data-ttu-id="befe4-161">Weitere Informationen zu out-of-Line-Bindungen in ASSL finden Sie unter [Datenquellen und Bindungen &#40;mehrdimensionalen SSAS-&#41;](../multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="befe4-161">For more information about out-of-line bindings in ASSL, see [Data Sources and Bindings &#40;SSAS Multidimensional&#41;](../multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).</span></span>  
  
### <a name="incrementally-updating-partitions"></a><span data-ttu-id="befe4-162">Inkrementelles Update von Partitionen</span><span class="sxs-lookup"><span data-stu-id="befe4-162">Incrementally Updating Partitions</span></span>  
 <span data-ttu-id="befe4-163">Das inkrementelle Update einer bereits verarbeiteten Partition erfordert in der Regel eine Out-of-Line-Bindung, da die für die Partition angegebene Bindung auf Faktentabellendaten verweist, die bereits in der Partition aggregiert wurden.</span><span class="sxs-lookup"><span data-stu-id="befe4-163">Incrementally updating an already processed partition typically requires an out-of-line binding because the binding specified for the partition references fact table data already aggregated within the partition.</span></span> <span data-ttu-id="befe4-164">Bei der inkrementellen Aktualisierung einer bereits verarbeiteten Partition über den Befehl `Process` führt  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="befe4-164">When incrementally updating an already processed partition by using the `Process` command, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] performs the following actions:</span></span>  
  
-   <span data-ttu-id="befe4-165">Erstellt eine temporäre Partition mit einer Struktur, die mit der Struktur der Partition identisch ist, die inkrementell aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="befe4-165">Creates a temporary partition with a structure identical to that of the partition to be incrementally updated.</span></span>  
  
-   <span data-ttu-id="befe4-166">Verarbeitet die temporäre Partition über die im `Process`-Befehl angegebene Out-of-Line-Bindung.</span><span class="sxs-lookup"><span data-stu-id="befe4-166">Processes the temporary partition, using the out-of-line binding specified in the `Process` command.</span></span>  
  
-   <span data-ttu-id="befe4-167">Führt die temporäre Partition mit der vorhandenen, ausgewählten Partition zusammen.</span><span class="sxs-lookup"><span data-stu-id="befe4-167">Merges the temporary partition with the existing selected partition.</span></span>  
  
 <span data-ttu-id="befe4-168">Weitere Informationen zum Zusammenführen von Partitionen mithilfe von XML for Analysis (XMLA) finden Sie unter Zusammenführen von [Partitionen &#40;XMLA&#41;](merging-partitions-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="befe4-168">For more information about merging partitions using XML for Analysis (XMLA), see [Merging Partitions &#40;XMLA&#41;](merging-partitions-xmla.md).</span></span>  
  
## <a name="handling-processing-errors"></a><span data-ttu-id="befe4-169">Behandeln von Verarbeitungsfehlern</span><span class="sxs-lookup"><span data-stu-id="befe4-169">Handling Processing Errors</span></span>  
 <span data-ttu-id="befe4-170">Mit der [ErrorConfiguration](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/errorconfiguration-element-xmla) -Eigenschaft des- `Process` Befehls können Sie angeben, wie Fehler behandelt werden sollen, die bei der Verarbeitung eines Objekts aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="befe4-170">The [ErrorConfiguration](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/errorconfiguration-element-xmla) property of the `Process` command lets you specify how to handle errors encountered while processing an object.</span></span> <span data-ttu-id="befe4-171">Beispielsweise ermittelt [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] bei der Verarbeitung einer Dimension einen doppelten Wert in der Schlüsselspalte des Schlüsselattributs.</span><span class="sxs-lookup"><span data-stu-id="befe4-171">For example, while processing a dimension, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] encounters a duplicate value in the key column of the key attribute.</span></span> <span data-ttu-id="befe4-172">Da Attributschlüssel eindeutig sein müssen, verwirft [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] die doppelten Datensätze.</span><span class="sxs-lookup"><span data-stu-id="befe4-172">Because attribute keys must be unique, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] discards the duplicate records.</span></span> <span data-ttu-id="befe4-173">Basierend auf der [KeyDuplicate](https://docs.microsoft.com/bi-reference/assl/properties/keyduplicate-element-assl) -Eigenschaft `ErrorConfiguration` von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] könnte Folgendes:</span><span class="sxs-lookup"><span data-stu-id="befe4-173">Based on the [KeyDuplicate](https://docs.microsoft.com/bi-reference/assl/properties/keyduplicate-element-assl) property of `ErrorConfiguration`, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] could:</span></span>  
  
-   <span data-ttu-id="befe4-174">den Fehler ignorieren und die Verarbeitung der Dimension fortsetzen;</span><span class="sxs-lookup"><span data-stu-id="befe4-174">Ignore the error and continue processing the dimension.</span></span>  
  
-   <span data-ttu-id="befe4-175">eine Meldung ausgeben, die besagt, dass [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] einen doppelten Schlüssel ermittelt hat und die Verarbeitung fortgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="befe4-175">Return a message that states [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] encountered a duplicate key and continue processing.</span></span>  
  
 <span data-ttu-id="befe4-176">Es gibt viele ähnliche Bedingungen, für die `ErrorConfiguration` Optionen während eines `Process`-Befehls bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="befe4-176">There are many similar conditions for which `ErrorConfiguration` provides options during a `Process` command.</span></span>  
  
## <a name="managing-writeback-tables"></a><span data-ttu-id="befe4-177">Verwalten von Rückschreibetabellen</span><span class="sxs-lookup"><span data-stu-id="befe4-177">Managing Writeback Tables</span></span>  
 <span data-ttu-id="befe4-178">Wenn der `Process`-Befehl eine Partition mit Schreibzugriff oder einen Cube oder eine Measuregruppe für eine derartige Partition entdeckt, die noch nicht vollständig verarbeitet ist, besteht möglicherweise noch keine Rückschreibetabelle für diese Partition.</span><span class="sxs-lookup"><span data-stu-id="befe4-178">If the `Process` command encounters a write-enabled partition, or a cube or measure group for such a partition, that is not already fully processed, a writeback table may not already exist for that partition.</span></span> <span data-ttu-id="befe4-179">Die Eigenschaft " [schreitebacktablecreation](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/writebacktablecreation-element-xmla) " des `Process` Befehls bestimmt, ob [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] eine Rück schreibe Tabelle erstellen soll.</span><span class="sxs-lookup"><span data-stu-id="befe4-179">The [WritebackTableCreation](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/writebacktablecreation-element-xmla) property of the `Process` command determines whether [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] should create a writeback table.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="befe4-180">Beispiele</span><span class="sxs-lookup"><span data-stu-id="befe4-180">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="befe4-181">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="befe4-181">Description</span></span>  
 <span data-ttu-id="befe4-182">Im folgenden Beispiel wird die [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)][!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Beispieldatenbank vollständig verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="befe4-182">The following example fully processes the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] sample [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
### <a name="code"></a><span data-ttu-id="befe4-183">Code</span><span class="sxs-lookup"><span data-stu-id="befe4-183">Code</span></span>  
  
```  
<Process xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Object>  
    <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
  </Object>  
  <Type>ProcessFull</Type>  
  <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
</Process>  
```  
  
### <a name="description"></a><span data-ttu-id="befe4-184">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="befe4-184">Description</span></span>  
 <span data-ttu-id="befe4-185">Im folgenden Beispiel wird die **Internet_Sales_2004** Partition in der **Internet Sales** -Measure-Gruppe des **Adventure Works DW** -Cubes in der-Beispieldatenbank inkrementell verarbeitet [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="befe4-185">The following example incrementally processes the **Internet_Sales_2004** partition in the **Internet Sales** measure group of the **Adventure Works DW** cube in the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] sample [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="befe4-186">Der `Process` Befehl fügt Aggregationen für Bestelldaten nach dem 31. Dezember 2006 zur Partition hinzu, indem eine Out-of-Line-Abfrage Bindung in der- `Bindings` Eigenschaft des-Befehls verwendet wird `Process` , um die Fakten Tabellenzeilen abzurufen, aus denen Aggregationen generiert werden, die der Partition hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="befe4-186">The `Process` command is adding aggregations for order dates later than December 31, 2006 to the partition by using an out-of-line query binding in the `Bindings` property of the `Process` command to retrieve the fact table rows from which to generate aggregations to add to the partition.</span></span>  
  
### <a name="code"></a><span data-ttu-id="befe4-187">Code</span><span class="sxs-lookup"><span data-stu-id="befe4-187">Code</span></span>  
  
```  
<Process ProcessAffectedObjects="true" xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Object>  
    <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
    <CubeID>Adventure Works DW</CubeID>  
    <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
    <PartitionID>Internet_Sales_2006</PartitionID>  
  </Object>  
  <Bindings>  
    <Binding>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2006</PartitionID>  
      <Source xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="QueryBinding">  
        <DataSourceID>Adventure Works DW</DataSourceID>  
        <QueryDefinition>  
          SELECT  
            [dbo].[FactInternetSales].[ProductKey],  
            [dbo].[FactInternetSales].[OrderDateKey],  
            [dbo].[FactInternetSales].[DueDateKey],  
            [dbo].[FactInternetSales].[ShipDateKey],   
            [dbo].[FactInternetSales].[CustomerKey],   
            [dbo].[FactInternetSales].[PromotionKey],  
            [dbo].[FactInternetSales].[CurrencyKey],  
            [dbo].[FactInternetSales].[SalesTerritoryKey],  
            [dbo].[FactInternetSales].[SalesOrderNumber],  
            [dbo].[FactInternetSales].[SalesOrderLineNumber],  
            [dbo].[FactInternetSales].[RevisionNumber],  
            [dbo].[FactInternetSales].[OrderQuantity],  
            [dbo].[FactInternetSales].[UnitPrice],  
            [dbo].[FactInternetSales].[ExtendedAmount],  
            [dbo].[FactInternetSales].[UnitPriceDiscountPct],  
            [dbo].[FactInternetSales].[DiscountAmount],  
            [dbo].[FactInternetSales].[ProductStandardCost],  
            [dbo].[FactInternetSales].[TotalProductCost],  
            [dbo].[FactInternetSales].[SalesAmount],  
            [dbo].[FactInternetSales].[TaxAmt],  
            [dbo].[FactInternetSales].[Freight],  
            [dbo].[FactInternetSales].[CarrierTrackingNumber],  
            [dbo].[FactInternetSales].[CustomerPONumber]  
          FROM [dbo].[FactInternetSales]  
          WHERE OrderDateKey > '1280'  
        </QueryDefinition>  
      </Source>  
    </Binding>  
  </Bindings>  
  <Type>ProcessAdd</Type>  
  <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
</Process>  
```  
  
  
