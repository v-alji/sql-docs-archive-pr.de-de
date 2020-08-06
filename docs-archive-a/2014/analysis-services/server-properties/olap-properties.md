---
title: OLAP-Eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- AggregationPerfLog property
- DefaultPageSizeForProp property
- UseSinglePassForDimSecurityAutoExist property
- DeepCompressValue property
- CacheRowsetRows property
- Income property
- AggregationNewAlgo property
- MemoryAdjustFactor property
- DimensionLatencyAccuracy property
- InitialBonus property
- DefaultPageSizeForDataHeader property
- MaxCPUUsage property
- DistinctBuffer property
- PartitionLatencyAccuracy property
- MaxRetries property
- UseDataCacheRegistryMultiplyKey property
- ConvertDeletedToUnknown property
- DatabaseConnectionPoolMax property
- DataFileInitEnabled property
- DefaultPageSizeForHash property
- MaxRolapOrConditions property
- UseDataCacheFreeLastPageMemory property
- OLAP [Analysis Services], properties
- MapHandleAlgorithm property
- IndexBuildEnabled property
- MaxObjectsInParallel property
- IgnoreNullRolapRows property
- DimensionPropertyCacheSize property
- DefaultRefreshInterval property
- CheckDistinctRecordSortOrder property
- BufferMemoryLimit property
- EnableTableGrouping property
- ExpressNonEmptyUseEnabled property
- CopyLinkedDataCacheAndRegistry property
- UseDataSlice property
- MemoryLimitErrorEnabled property
- Enabled property
- EnableRolapOptimization property
- DatabaseConnectionPoolTimeout property
- UseDataCacheRegistryHashTable property
- AggregationsBuildEnabled property
- Tax property
- DatabaseConnectionPoolGeneralTimeout property
- DefaultPageSizeForString property
- DatabaseConnectionPoolConnectTimeout property
- MinimumBalance property
- OptimizeSchema property
- UseCalculationCacheRegistry property
- MaxTableDepth property
- DataSliceInitEnabled property
- PrefetchLowerGranularities property
- UseVBANet property
- BufferRecordLimit property
- DefaultPageSizeForIndexHeader property
- MaximumBalance property
- CalculationCacheRegistryMaxIterations property
- DefaultDrillthroughMaxRows property
- IndexBuildThreshold property
- UseDataCacheRegistry property
- MemoryAdjustConst property
- ApplyIntersect property
- IndexFileInitEnabled property
- CacheRowsetToDisk property
- DataCacheRegistryMaxIterations property
- AllowSEFiltering property
- ForceMultiPass property
- ApplySubtract property
- IndexUseEnabled property
- AggregationsUseEnabled property
- DataPlacementOptimization property
- UseMaterializedIterators property
- CacheRecordLimit property
- ROLAPDimensionProcessingEffort property
- DefaultPageSizeForIndex property
- EnableRolapDimQueryTableGrouping property
- DimensionPropertyKeyCache property
- SleepIntervalSecs property
- DefaultPageSizeForData property
- MapFormatMask property
- CalculationEvaluationPolicy property
- AggregationMemoryLimitMin property
- RecordsReportGranularity property
- MemoryLimit property
- AggregationMemoryLimitMax property
ms.assetid: 06eb0d78-96c0-42ff-b759-f4c794597c8d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2eb89d318bfdb78935eb4d9f202db11b978c59b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617307"
---
# <a name="olap-properties"></a><span data-ttu-id="11df5-102">OLAP-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="11df5-102">OLAP Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="11df5-103">unterstützt die in den folgenden Tabellen aufgeführten OLAP-Servereigenschaften.</span><span class="sxs-lookup"><span data-stu-id="11df5-103">supports the OLAP server properties listed in the following tables.</span></span> <span data-ttu-id="11df5-104">Weitere Informationen zu zusätzlichen Servereigenschaften und zum Festlegen dieser Eigenschaften finden Sie unter [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="11df5-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="11df5-105">**Gilt für:** Nur mehrdimensionaler Server Modus</span><span class="sxs-lookup"><span data-stu-id="11df5-105">**Applies to:** Multidimensional server mode only</span></span>  
  
## <a name="memory"></a><span data-ttu-id="11df5-106">Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="11df5-106">Memory</span></span>  
 `DefaultPageSizeForData`  
 <span data-ttu-id="11df5-107">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-107">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DefaultPageSizeForDataHeader`  
 <span data-ttu-id="11df5-108">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-108">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DefaultPageSizeForIndex`  
 <span data-ttu-id="11df5-109">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-109">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DefaultPageSizeForIndexHeader`  
 <span data-ttu-id="11df5-110">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-110">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DefaultPageSizeForString`  
 <span data-ttu-id="11df5-111">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-111">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DefaultPageSizeForHash`  
 <span data-ttu-id="11df5-112">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-112">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DefaultPageSizeForProp`  
 <span data-ttu-id="11df5-113">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-113">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="lazyprocessing"></a><span data-ttu-id="11df5-114">LazyProcessing</span><span class="sxs-lookup"><span data-stu-id="11df5-114">LazyProcessing</span></span>  
 `Enabled`  
 <span data-ttu-id="11df5-115">Eine boolesche Eigenschaft, die angibt, ob die verzögerte Aggregationsverarbeitung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="11df5-115">A Boolean property that specifies whether lazy aggregation processing is enabled.</span></span>  
  
 `SleepIntervalSecs`  
 <span data-ttu-id="11df5-116">Eine ganze 32-Bit-Zahl mit Vorzeichen, die das Intervall (in Sekunden) definiert, in dem der Server überprüft, ob Aufträge für eine verzögerte Verarbeitung anstehen.</span><span class="sxs-lookup"><span data-stu-id="11df5-116">A signed 32-bit integer property that defines the interval, in seconds, that the server checks whether there are lazy processing jobs pending.</span></span>  
  
 `MaxCPUUsage`  
 <span data-ttu-id="11df5-117">Eine 64-Bit-Gleitkommazahl mit doppelter Genauigkeit und Vorzeichen, die die maximale CPU-Nutzung für die verzögerte Verarbeitung definiert, ausgedrückt als Prozentsatz.</span><span class="sxs-lookup"><span data-stu-id="11df5-117">A signed 64-bit double-precision floating-point number property that defines maximum CPU usage for lazy processing, expressed as a percentage.</span></span> <span data-ttu-id="11df5-118">Der Server überwacht die durchschnittliche CPU-Nutzung basierend auf Snapshots.</span><span class="sxs-lookup"><span data-stu-id="11df5-118">The server monitors average CPU use based on snapshots.</span></span> <span data-ttu-id="11df5-119">Kurzfristige Überschreitungen dieses Schwellenwerts werden als normales CPU-Verhalten betrachtet.</span><span class="sxs-lookup"><span data-stu-id="11df5-119">It is normal behavior for the CPU to spike above this threshold.</span></span>  
  
 <span data-ttu-id="11df5-120">Der Standardwert für diese Eigenschaft ist 0,5. Bei dieser Einstellung werden maximal 50 % der CPU für die verzögerte Verarbeitung verwendet.</span><span class="sxs-lookup"><span data-stu-id="11df5-120">The default value for this property is 0.5, indicating a maximum of 50% of the CPU will be devoted to lazy processing.</span></span>  
  
 `MaxObjectsInParallel`  
 <span data-ttu-id="11df5-121">Eine ganze 32-Bit-Zahl mit Vorzeichen, die die maximale Anzahl von Partitionen angibt, die gleichzeitig verzögert verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="11df5-121">A signed 32-bit integer property that specifies the maximum number of partitions that can be lazily processed in parallel.</span></span>  
  
 `MaxRetries`  
 <span data-ttu-id="11df5-122">Eine ganze 32-Bit-Zahl mit Vorzeichen, die die Anzahl von Wiederholungen definiert, die bei einem Fehler bei der verzögerten Verarbeitung zulässig sind, bevor ein Fehler ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="11df5-122">A signed 32-bit integer property that defines the number of retries in the event that lazy processing fails before an error is raised.</span></span>  
  
## <a name="processplan"></a><span data-ttu-id="11df5-123">ProcessPlan</span><span class="sxs-lookup"><span data-stu-id="11df5-123">ProcessPlan</span></span>  
 `CacheRowsetRows`  
 <span data-ttu-id="11df5-124">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-124">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `CacheRowsetToDisk`  
 <span data-ttu-id="11df5-125">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-125">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DistinctBuffer`  
 <span data-ttu-id="11df5-126">Eine ganze 32-Bit-Zahl mit Vorzeichen, die die Größe eines für Distinct Count Measures verwendeten internen Puffers definiert.</span><span class="sxs-lookup"><span data-stu-id="11df5-126">A signed 32-bit integer property that defines the size of an internal buffer used for distinct counts.</span></span> <span data-ttu-id="11df5-127">Erhöhen Sie diesen Wert, um die Verarbeitung von Distinct Count Measures zu Lasten der CPU-Nutzung zu beschleunigen.</span><span class="sxs-lookup"><span data-stu-id="11df5-127">Increase this value to speed up distinct count processing at the cost of memory use.</span></span>  
  
 `EnableRolapDimQueryTableGrouping`  
 <span data-ttu-id="11df5-128">Eine boolesche Eigenschaft, die angibt, ob für ROLAP-Dimensionen die Tabellengruppierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="11df5-128">A Boolean property that specifies whether table grouping is enabled for ROLAP dimensions.</span></span> <span data-ttu-id="11df5-129">Wenn für diese Eigenschaft TRUE festgelegt ist, werden beim Abfragen von ROLAP-Dimensionen zur Laufzeit vollständige ROLAP-Dimensionstabellen auf einmal abgefragt, statt für jedes Attribut eine eigene Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="11df5-129">If True, when querying ROLAP dimensions at runtime, entire ROLAP dimension tables are queried at once, as opposed to separate queries for each attribute.</span></span>  
  
 `EnableTableGrouping`  
 <span data-ttu-id="11df5-130">Eine boolesche Eigenschaft, die angibt, ob die Tabellengruppierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="11df5-130">A Boolean property that specifies whether table grouping is enabled.</span></span> <span data-ttu-id="11df5-131">Wenn für diese Eigenschaft TRUE festgelegt ist, werden beim Verarbeiten von Dimensionen vollständige Dimensionstabellen auf einmal abgefragt, statt für jedes Attribut eine eigene Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="11df5-131">If True, when processing dimensions, entire dimension tables are queried at once, as opposed to separate queries for each attribute.</span></span>  
  
 `ForceMultiPass`  
 <span data-ttu-id="11df5-132">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-132">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxTableDepth`  
 <span data-ttu-id="11df5-133">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-133">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryAdjustConst`  
 <span data-ttu-id="11df5-134">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-134">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryAdjustFactor`  
 <span data-ttu-id="11df5-135">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-135">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryLimit`  
 <span data-ttu-id="11df5-136">Eine 64-Bit-Gleitkommazahl mit doppelter Genauigkeit und Vorzeichen, die die maximale für die Verarbeitung zugeordnete Menge an Arbeitsspeicher definiert, ausgedrückt als Prozentsatz des physischen Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="11df5-136">A signed 64-bit double-precision floating-point number property that defines the maximum amount of memory to be devoted to processing, expressed as a percentage of physical memory.</span></span>  
  
 <span data-ttu-id="11df5-137">Der Standardwert für diese Eigenschaft ist 65. Dies bedeutet, dass 65 % des physischen Arbeitsspeichers für die Cube- und Dimensionsverarbeitung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="11df5-137">The default value for this property is 65, indicating that 65% of physical memory may be devoted to cube and dimension processing.</span></span>  
  
 `MemoryLimitErrorEnabled`  
 <span data-ttu-id="11df5-138">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-138">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `OptimizeSchema`  
 <span data-ttu-id="11df5-139">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-139">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="proactivecaching"></a><span data-ttu-id="11df5-140">ProactiveCaching</span><span class="sxs-lookup"><span data-stu-id="11df5-140">ProactiveCaching</span></span>  
 `DefaultRefreshInterval`  
 <span data-ttu-id="11df5-141">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-141">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DimensionLatencyAccuracy`  
 <span data-ttu-id="11df5-142">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-142">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `PartitionLatencyAccuracy`  
 <span data-ttu-id="11df5-143">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-143">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="process"></a><span data-ttu-id="11df5-144">Prozess</span><span class="sxs-lookup"><span data-stu-id="11df5-144">Process</span></span>  
 `AggregationMemoryLimitMax`  
 <span data-ttu-id="11df5-145">Eine 64-Bit-Gleitkommazahl mit doppelter Genauigkeit und Vorzeichen, die die maximale für die Aggregationsverarbeitung zugeordnete Menge an Arbeitsspeicher definiert, ausgedrückt als Prozentsatz des physischen Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="11df5-145">A signed 64-bit double-precision floating-point number property that defines the maximum amount of memory that can be devoted to aggregation processing, expressed as a percentage of physical memory.</span></span>  
  
 <span data-ttu-id="11df5-146">Der Standardwert für diese Eigenschaft ist 80. Dies bedeutet, dass 80 % des physischen Arbeitsspeichers für die Aggregationsverarbeitung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="11df5-146">The default value for this property is 80, indicating that 80% of physical memory may be devoted to aggregation processing.</span></span>  
  
 `AggregationMemoryLimitMin`  
 <span data-ttu-id="11df5-147">Eine 64-Bit-Gleitkommazahl mit doppelter Genauigkeit und Vorzeichen, die die minimale für die Aggregationsverarbeitung zugeordnete Menge an Arbeitsspeicher definiert, ausgedrückt als Prozentsatz des physischen Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="11df5-147">A signed 64-bit double-precision floating-point number property that defines the minimum amount of memory that can be devoted to aggregation processing, expressed as a percentage of physical memory.</span></span> <span data-ttu-id="11df5-148">Mit einem höheren Wert kann die Aggregationsverarbeitung zu Lasten der Speicherauslastung beschleunigt werden.</span><span class="sxs-lookup"><span data-stu-id="11df5-148">A larger value may speed up aggregation processing at the cost of memory usage.</span></span>  
  
 <span data-ttu-id="11df5-149">Der Standardwert für diese Eigenschaft ist 10. Dies bedeutet, dass mindestens 10 % des physischen Arbeitsspeichers für die Aggregationsverarbeitung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="11df5-149">The default value for this property is 10, indicating that minimally 10% of physical memory will be devoted to aggregation processing.</span></span>  
  
 `AggregationNewAlgo`  
 <span data-ttu-id="11df5-150">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-150">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `AggregationPerfLog2`  
 <span data-ttu-id="11df5-151">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-151">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `AggregationsBuildEnabled`  
 <span data-ttu-id="11df5-152">Eine boolesche Eigenschaft, die angibt, ob die Aggregationserstellung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="11df5-152">A Boolean property that specifies whether aggregation building is enabled.</span></span> <span data-ttu-id="11df5-153">Hierbei handelt es sich um einen Mechanismus zum Durchführen von Vergleichstests bei der Aggregationserstellung, ohne dass der Aggregationsentwurf geändert werden muss.</span><span class="sxs-lookup"><span data-stu-id="11df5-153">This is a mechanism to benchmark aggregation building without changing aggregation design.</span></span>  
  
 `BufferMemoryLimit`  
 <span data-ttu-id="11df5-154">Eine 64-Bit-Gleitkommazahl mit doppelter Genauigkeit und Vorzeichen, die die Arbeitsspeicherbegrenzung für den Verarbeitungspuffer definiert, ausgedrückt als Prozentsatz des physischen Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="11df5-154">A signed 64-bit double-precision floating-point number property that defines the processing buffer memory limit, expressed as a percent of physical memory.</span></span>  
  
 <span data-ttu-id="11df5-155">Der Standardwert für diese Eigenschaft ist 60. Dies bedeutet, dass für den Pufferspeicher bis zu 60 % des physischen Arbeitsspeichers verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="11df5-155">The default value for this property is 60, which indicates that up to 60% of physical memory can be used for buffer memory.</span></span>  
  
 `BufferRecordLimit`  
 <span data-ttu-id="11df5-156">Eine ganze 32-Bit-Zahl mit Vorzeichen, die die Anzahl von Datensätzen definiert, die bei der Verarbeitung gepuffert werden können.</span><span class="sxs-lookup"><span data-stu-id="11df5-156">A signed 32-bit integer property that defines the number of records that can be buffered during processing.</span></span>  
  
 <span data-ttu-id="11df5-157">Der Standardwert dieser Eigenschaft beträgt 1048576 Datensätze.</span><span class="sxs-lookup"><span data-stu-id="11df5-157">The default value for this property is 1048576 (records).</span></span>  
  
 `CacheRecordLimit`  
 <span data-ttu-id="11df5-158">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-158">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `CheckDistinctRecordSortOrder`  
 <span data-ttu-id="11df5-159">Eine boolesche Eigenschaft, die definiert, ob beim Verarbeiten von Partitionen die Sortierreihenfolge für die Ergebnisse einer Distinct Count-Abfrage sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="11df5-159">A Boolean property that defines if the sort order for the results of a distinct count query are meaningful when processing partitions.</span></span> <span data-ttu-id="11df5-160">TRUE bedeutet, dass die Sortierreihenfolge nicht sinnvoll ist und vom Server überprüft werden muss.</span><span class="sxs-lookup"><span data-stu-id="11df5-160">True indicates the sort order is not meaningful and must be "checked" by the server.</span></span> <span data-ttu-id="11df5-161">Beim Verarbeiten von Partitionen mit Distinct Count Measure wird eine SQL-Abfrage mit ORDER BY gesendet.</span><span class="sxs-lookup"><span data-stu-id="11df5-161">When processing partitions with distinct count measure, query sent to SQL with order-by.</span></span> <span data-ttu-id="11df5-162">Durch Festlegen der Eigenschaft auf FALSE kann die Verarbeitung beschleunigt werden.</span><span class="sxs-lookup"><span data-stu-id="11df5-162">Set to false to speed up processing.</span></span>  
  
 <span data-ttu-id="11df5-163">Der Standardwert für diese Eigenschaft ist TRUE. Dies bedeutet, dass die Sortierreihenfolge nicht sinnvoll ist und überprüft werden muss.</span><span class="sxs-lookup"><span data-stu-id="11df5-163">The default value for this property is True, which indicates that the sort order is not meaningful and must be checked.</span></span>  
  
 `DatabaseConnectionPoolConnectTimeout`  
 <span data-ttu-id="11df5-164">Eine ganze 32-Bit-Zahl mit Vorzeichen, die den beim Öffnen von neuen Verbindungen zu verwendenden Timeoutwert in Sekunden angibt.</span><span class="sxs-lookup"><span data-stu-id="11df5-164">A signed 32-bit integer property that specifies timeout when opening a new connection in seconds.</span></span>  
  
 `DatabaseConnectionPoolGeneralTimeout`  
 <span data-ttu-id="11df5-165">Eine ganze 32-Bit-Zahl mit Vorzeichen, die den Timeoutwert für Datenbankverbindungen bei externen OLE DB-Verbindungen in Sekunden angibt.</span><span class="sxs-lookup"><span data-stu-id="11df5-165">A signed 32-bit integer property that specifies database connection timeout for use with external OLEDB connections in seconds.</span></span>  
  
 `DatabaseConnectionPoolMax`  
 <span data-ttu-id="11df5-166">Eine ganze 32-Bit-Zahl mit Vorzeichen, die die maximale Anzahl von Datenbankverbindungen in einem Pool angibt.</span><span class="sxs-lookup"><span data-stu-id="11df5-166">A signed 32-bit integer property that specifies the maximum number of pooled database connections.</span></span>  
  
 <span data-ttu-id="11df5-167">Der Standardwert für diese Eigenschaft beträgt 50 Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="11df5-167">The default value for this property is 50 (connections).</span></span>  
  
 `DatabaseConnectionPoolTimeout`  
 <span data-ttu-id="11df5-168">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-168">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataFileInitEnabled`  
 <span data-ttu-id="11df5-169">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-169">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataPlacementOptimization`  
 <span data-ttu-id="11df5-170">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-170">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataSliceInitEnabled`  
 <span data-ttu-id="11df5-171">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-171">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DeepCompressValue`  
 <span data-ttu-id="11df5-172">Eine boolesche Eigenschaft für Measures vom Datentyp Double, die angibt, ob Zahlen komprimiert werden können, wodurch sich ein Verlust bei der numerischen Genauigkeit ergibt.</span><span class="sxs-lookup"><span data-stu-id="11df5-172">A Boolean property applying to measures with Double data type that specifies whether numbers can be compressed, causing a loss in numeric precision.</span></span> <span data-ttu-id="11df5-173">Der Wert FALSE zeigt an, dass keine Komprimierung und kein Genauigkeitsverlust stattfinden.</span><span class="sxs-lookup"><span data-stu-id="11df5-173">A value of False indicates no compression and no precision loss.</span></span>  
  
 <span data-ttu-id="11df5-174">Der Standardwert für diese Eigenschaft ist TRUE. Hiermit wird angezeigt, dass die Komprimierung aktiviert ist und ein Genauigkeitsverlust auftreten kann.</span><span class="sxs-lookup"><span data-stu-id="11df5-174">The default value for this property is True, which indicates that compression is enabled and precision will be lost.</span></span>  
  
 `DimensionPropertyKeyCache`  
 <span data-ttu-id="11df5-175">Eine boolesche Eigenschaft, die angibt, ob die Dimensionseigenschaftenschlüssel zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="11df5-175">A Boolean property that specifies whether dimension property keys are cached.</span></span> <span data-ttu-id="11df5-176">Bei nicht eindeutigen Schlüsseln muss diese Eigenschaft auf TRUE festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="11df5-176">Must be set to True if keys are non-unique.</span></span>  
  
 `IndexBuildEnabled`  
 <span data-ttu-id="11df5-177">Eine boolesche Eigenschaft, die angibt, ob nach der Verarbeitung Indizes erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="11df5-177">A Boolean property that specifies whether indexes are built upon processing.</span></span> <span data-ttu-id="11df5-178">Diese Eigenschaft ist für Vergleichstests und Informationszwecke vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="11df5-178">This property is for benchmarking and informational purposes.</span></span>  
  
 `IndexBuildThreshold`  
 <span data-ttu-id="11df5-179">Eine ganze 32-Bit-Zahl mit Vorzeichen, die einen Schwellenwert für die Zeilenanzahl angibt, unter dem keine Indizes für Partitionen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="11df5-179">A signed 32-bit integer property that specifies a row count threshold below which indexes will not be built for partitions.</span></span>  
  
 <span data-ttu-id="11df5-180">Der Standardwert dieser Eigenschaft beträgt 4096 Zeilen.</span><span class="sxs-lookup"><span data-stu-id="11df5-180">The default value for this property is 4096 (rows).</span></span>  
  
 `IndexFileInitEnabled`  
 <span data-ttu-id="11df5-181">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-181">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MapFormatMask`  
 <span data-ttu-id="11df5-182">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-182">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `RecordsReportGranularity`  
 <span data-ttu-id="11df5-183">Eine ganze 32-Bit-Zahl mit Vorzeichen, die angibt, wie oft (in Zeilen) der Server während der Verarbeitung Ablaufverfolgungsereignisse aufzeichnet.</span><span class="sxs-lookup"><span data-stu-id="11df5-183">A signed 32-bit integer property that specifies how often the server records Trace events during processing, in rows.</span></span>  
  
 <span data-ttu-id="11df5-184">Der Standardwert für diese Eigenschaft ist 1000. Dies bedeutet, dass einmal pro 1000 Zeilen ein Ablaufverfolgungsereignis aufgezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="11df5-184">The default value for this property is 1000, which indicates that a Trace event is logged once every 1000 rows.</span></span>  
  
 `ROLAPDimensionProcessingEffort`  
 <span data-ttu-id="11df5-185">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-185">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="query"></a><span data-ttu-id="11df5-186">Abfrage</span><span class="sxs-lookup"><span data-stu-id="11df5-186">Query</span></span>  
 `AggregationsUseEnabled`  
 <span data-ttu-id="11df5-187">Eine boolesche Eigenschaft, die definiert, ob zur Laufzeit gespeicherte Aggregationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="11df5-187">A Boolean property that defines whether stored aggregations are used at runtime.</span></span> <span data-ttu-id="11df5-188">Diese Eigenschaft lässt zu, dass Aggregationen für Informationszwecke oder Vergleichstests ohne Ändern des Aggregationsentwurfs oder erneutes Verarbeiten deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="11df5-188">This property allows aggregations to be disabled without changing the aggregation design or re-processing, for informational and benchmarking purposes.</span></span>  
  
 <span data-ttu-id="11df5-189">Der Standardwert für diese Eigenschaft ist TRUE. Dies bedeutet, dass Aggregationen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="11df5-189">The default value for this property is True, indicating that aggregations are enabled.</span></span>  
  
 `AllowSEFiltering`  
 <span data-ttu-id="11df5-190">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-190">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `CalculationCacheRegistryMaxIterations`  
 <span data-ttu-id="11df5-191">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-191">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `CalculationEvaluationPolicy`  
 <span data-ttu-id="11df5-192">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-192">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ConvertDeletedToUnknown`  
 <span data-ttu-id="11df5-193">Eine boolesche Eigenschaft, die angibt, ob gelöschte Dimensionselemente in Unbekannt konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="11df5-193">A Boolean property that specifies whether deleted dimension members are converted to Unknown member.</span></span>  
  
 `CopyLinkedDataCacheAndRegistry`  
 <span data-ttu-id="11df5-194">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-194">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCacheRegistryMaxIterations`  
 <span data-ttu-id="11df5-195">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-195">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DefaultDrillthroughMaxRows`  
 <span data-ttu-id="11df5-196">Eine ganze 32-Bit-Zahl mit Vorzeichen, die die maximale Anzahl von Zeilen angibt, die von einer Drillthroughabfrage zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="11df5-196">A signed 32-bit integer property that specifies the maximum number of rows that will return from a drill-through query.</span></span>  
  
 <span data-ttu-id="11df5-197">Der Standardwert dieser Eigenschaft beträgt 10000 Zeilen.</span><span class="sxs-lookup"><span data-stu-id="11df5-197">The default value for this property is 10000 (rows).</span></span>  
  
 `DimensionPropertyCacheSize`  
 <span data-ttu-id="11df5-198">Eine Eigenschaft für eine ganze 32-Bit-Zahl mit Vorzeichen, die den Arbeitsspeicher (in Bytes) angibt, der zum Zwischenspeichern von Dimensionselementen aus einer Abfrage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="11df5-198">A signed 32-bit integer property that specifies the amount of memory (in bytes) used to cache dimension members used in a query.</span></span>  
  
 <span data-ttu-id="11df5-199">Der Standardwert ist 4.000.000 Bytes (4 MB) pro Attributhierarchie und pro aktiver Abfrage.</span><span class="sxs-lookup"><span data-stu-id="11df5-199">The default is 4,000,000 bytes (or 4 MB) per attribute hierarchy, per active query.</span></span> <span data-ttu-id="11df5-200">Der Standardwert gewährleistet eine ausgewogene Cachegröße für Lösungen, die typische Hierarchien enthalten.</span><span class="sxs-lookup"><span data-stu-id="11df5-200">The default value provides a well-balanced cache size for solutions having typical hierarchies.</span></span> <span data-ttu-id="11df5-201">Dimensionen, die über eine sehr große Anzahl von Elementen (im Millionenbereich) oder über verschachtelte Hierarchien verfügen, erzielen eine bessere Leistung, wenn Sie diesen Wert erhöhen.</span><span class="sxs-lookup"><span data-stu-id="11df5-201">However, dimensions with a very large number of members (in the millions) or deep hierarchies perform better if you increase this value.</span></span>  
  
 <span data-ttu-id="11df5-202">Die Vergrößerung des Cachespeichers kann folgende Auswirkungen haben:</span><span class="sxs-lookup"><span data-stu-id="11df5-202">Implications of increasing cache size:</span></span>  
  
-   <span data-ttu-id="11df5-203">Die Kosten der Arbeitsspeichernutzung erhöhen sich, wenn Sie dem Dimensionscache die Nutzung einer größeren Arbeitsspeichermenge erlauben.</span><span class="sxs-lookup"><span data-stu-id="11df5-203">Memory utilization costs increase when you allow more memory to be used by the dimension cache.</span></span> <span data-ttu-id="11df5-204">Die tatsächliche Nutzung hängt von der Abfrageausführung ab.</span><span class="sxs-lookup"><span data-stu-id="11df5-204">Actual usage depends on query execution.</span></span> <span data-ttu-id="11df5-205">Nicht alle Abfragen verwenden den zulässigen Höchstwert.</span><span class="sxs-lookup"><span data-stu-id="11df5-205">Not all queries will use the allowable maximum.</span></span>  
  
     <span data-ttu-id="11df5-206">Der von diesen Cachespeichern genutzte Arbeitsspeicher gilt als nicht verkleinerbar und wird bei der Berechnung von **TotalMemoryLimit**berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="11df5-206">Note that the memory used by these caches is considered nonshrinkable and will be included when accounting against the **TotalMemoryLimit**.</span></span>  
  
-   <span data-ttu-id="11df5-207">Wirkt sich auf alle Datenbanken auf dem Server aus.</span><span class="sxs-lookup"><span data-stu-id="11df5-207">Affects all databases on the server.</span></span> <span data-ttu-id="11df5-208">**DimensionPropertyCachesize** ist eine serverweite Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="11df5-208">**DimensionPropertyCachesize** is a server-wide property.</span></span> <span data-ttu-id="11df5-209">Wenn Sie diese Eigenschaft ändern, wirkt sich dies auf alle Datenbanken aus, die auf der aktuellen Instanz ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="11df5-209">Changing this property affects all databases running on the current instance.</span></span>  
  
 <span data-ttu-id="11df5-210">Schätzen der Anforderungen für den Dimensionscache:</span><span class="sxs-lookup"><span data-stu-id="11df5-210">Approach for estimating dimension cache requirements:</span></span>  
  
1.  <span data-ttu-id="11df5-211">Beginnen Sie, indem Sie die Größe um einen sehr hohen Wert erhöhen. So stellen Sie fest, ob sich die Vergrößerung des Dimensionscaches vorteilhaft auswirkt.</span><span class="sxs-lookup"><span data-stu-id="11df5-211">Start by increasing the size by a large number to determine whether there is a benefit to increasing the dimension cache size.</span></span> <span data-ttu-id="11df5-212">Beispielsweise können Sie den Standardwert in einem ersten Schritt verdoppeln.</span><span class="sxs-lookup"><span data-stu-id="11df5-212">For example, you might want to double the default value as an initial step.</span></span>  
  
2.  <span data-ttu-id="11df5-213">Wenn sich eine Leistungsverbesserung abzeichnet, verringern Sie den Wert schrittweise, bis Sie ein ausgewogenes Verhältnis zwischen Leistung und Arbeitsspeicherauslastung erreichen.</span><span class="sxs-lookup"><span data-stu-id="11df5-213">If a performance improvement is evident, incrementally reduce the value until you reach a balance between performance and memory utilization.</span></span>  
  
 `ExpressNonEmptyUseEnabled`  
 <span data-ttu-id="11df5-214">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-214">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `IgnoreNullRolapRows`  
 <span data-ttu-id="11df5-215">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-215">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `IndexUseEnabled`  
 <span data-ttu-id="11df5-216">Eine boolesche Eigenschaft, die definiert, ob zur Laufzeit Indizes verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="11df5-216">A Boolean property that defines whether indexes are used at runtime.</span></span> <span data-ttu-id="11df5-217">Diese Eigenschaft ist für Informationszwecke und zum Durchführen von Vergleichstests vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="11df5-217">This property is for informational and benchmarking purposes.</span></span>  
  
 `MapHandleAlgorithm`  
 <span data-ttu-id="11df5-218">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-218">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxRolapOrConditions`  
 <span data-ttu-id="11df5-219">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-219">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `UseCalculationCacheRegistry`  
 <span data-ttu-id="11df5-220">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-220">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `UseDataCacheFreeLastPageMemory`  
 <span data-ttu-id="11df5-221">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-221">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `UseDataCacheRegistry`  
 <span data-ttu-id="11df5-222">Eine boolesche Eigenschaft, die angibt, ob die Datencacheregistrierung für die Zwischenspeicherung von Abfragergebnissen (jedoch nicht für berechnete Ergebnisse) aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="11df5-222">A Boolean property that specifies whether to enable the data cache registry, where query results are cached (though not calculated results).</span></span>  
  
 `UseDataCacheRegistryHashTable`  
 <span data-ttu-id="11df5-223">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-223">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `UseDataCacheRegistryMultiplyKey`  
 <span data-ttu-id="11df5-224">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-224">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `UseDataSlice`  
 <span data-ttu-id="11df5-225">Eine boolesche Eigenschaft, die definiert, ob zur Laufzeit für die Abfrageoptimierung Datenslices der Partition verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="11df5-225">A Boolean property that defines whether to use partition data slices at runtime for query optimization.</span></span> <span data-ttu-id="11df5-226">Diese Eigenschaft ist für Vergleichstests und Informationszwecke vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="11df5-226">This property is for benchmarking and informational purposes.</span></span>  
  
 `UseMaterializedIterators`  
 <span data-ttu-id="11df5-227">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-227">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `UseSinglePassForDimSecurityAutoExist`  
 <span data-ttu-id="11df5-228">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-228">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `UseVBANet`  
 <span data-ttu-id="11df5-229">Eine boolesche Eigenschaft, die definiert, ob für benutzerdefinierte Funktionen die VBA .net-Assembly verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="11df5-229">A Boolean property that defines whether to use the VBA .net assembly for user-defined functions.</span></span>  
  
 `CalculationPrefetchLocality\ ApplyIntersect`  
 <span data-ttu-id="11df5-230">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-230">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `CalculationPrefetchLocality\ ApplySubtract`  
 <span data-ttu-id="11df5-231">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-231">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `CalculationPrefetchLocality\ PrefetchLowerGranularities`  
 <span data-ttu-id="11df5-232">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-232">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\  CachedPageAlloc\ Income`  
 <span data-ttu-id="11df5-233">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-233">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\  CachedPageAlloc\ InitialBonus`  
 <span data-ttu-id="11df5-234">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-234">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\  CachedPageAlloc\ MaximumBalance`  
 <span data-ttu-id="11df5-235">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-235">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\  CachedPageAlloc\ MinimumBalance`  
 <span data-ttu-id="11df5-236">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-236">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\  CachedPageAlloc\ Tax`  
 <span data-ttu-id="11df5-237">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-237">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\CellStore\ Income`  
 <span data-ttu-id="11df5-238">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-238">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\CellStore\ InitialBonus`  
 <span data-ttu-id="11df5-239">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-239">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\CellStore\ MaximumBalance`  
 <span data-ttu-id="11df5-240">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-240">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\CellStore\ MinimumBalance`  
 <span data-ttu-id="11df5-241">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-241">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\CellStore\ Tax`  
 <span data-ttu-id="11df5-242">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-242">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\ MemoryModel \ Income`  
 <span data-ttu-id="11df5-243">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-243">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\ MemoryModel \ InitialBonus`  
 <span data-ttu-id="11df5-244">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-244">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\ MemoryModel \ MaximumBalance`  
 <span data-ttu-id="11df5-245">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-245">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\ MemoryModel \ MinimumBalance`  
 <span data-ttu-id="11df5-246">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-246">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\ MemoryModel\ Tax`  
 <span data-ttu-id="11df5-247">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-247">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="jobs"></a><span data-ttu-id="11df5-248">Aufträge</span><span class="sxs-lookup"><span data-stu-id="11df5-248">Jobs</span></span>  
 `ProcessAggregation\ MemoryModel\ Income`  
 <span data-ttu-id="11df5-249">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-249">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ MemoryModel\ InitialBonus`  
 <span data-ttu-id="11df5-250">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-250">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ MemoryModel\ MaximumBalance`  
 <span data-ttu-id="11df5-251">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-251">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ MemoryModel\ MinimumBalance`  
 <span data-ttu-id="11df5-252">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-252">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ MemoryModel\ Tax`  
 <span data-ttu-id="11df5-253">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-253">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessPartition\ Income`  
 <span data-ttu-id="11df5-254">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-254">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessPartition \ InitialBonus`  
 <span data-ttu-id="11df5-255">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-255">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessPartition \ MaximumBalance`  
 <span data-ttu-id="11df5-256">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-256">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessPartition \ MinimumBalance`  
 <span data-ttu-id="11df5-257">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-257">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessPartition \ Tax`  
 <span data-ttu-id="11df5-258">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-258">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessProperty\ Income`  
 <span data-ttu-id="11df5-259">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-259">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessProperty\ InitialBonus`  
 <span data-ttu-id="11df5-260">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-260">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessProperty\ MaximumBalance`  
 <span data-ttu-id="11df5-261">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-261">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessProperty\ MinimumBalance`  
 <span data-ttu-id="11df5-262">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-262">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessProperty\ Tax`  
 <span data-ttu-id="11df5-263">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="11df5-263">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11df5-264">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="11df5-264">See Also</span></span>  
 <span data-ttu-id="11df5-265">[Konfigurieren von Server Eigenschaften in Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="11df5-265">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="11df5-266">Bestimmen des Servermodus einer Analysis Services-Instanz</span><span class="sxs-lookup"><span data-stu-id="11df5-266">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
