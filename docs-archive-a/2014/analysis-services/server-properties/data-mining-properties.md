---
title: Data Mining-Eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- ClusterCount property
- AllowedProvidersInOpenRowset property
- MinimumSeriesValue property
- ScoreMethod property
- MinimumImportance property
- ModellingCardinality property
- BrentTolerance property
- ComplexityPenalty property
- MaximumItemsetCount property
- MinimumSupport property
- AllowSessionMiningModels property
- HoldoutPercentage property
- ClusterCountPrior property
- MaximumSequenceStates property
- OptimizedPredictionCount property
- data mining [Analysis Services], properties
- MaximumStates property
- MaximumContinuousInputAttributes property
- MaximumOutputAttributes property
- AllowAdHocOpenRowsetQueries property
- Enabled property
- HistoricModelGap property
- SampleSize property
- MaximumInputAttributes property
- PeriodicityHint property
- MissingValueSubstitution property
- SplitMethod property
- ForceRegressor property
- MaximumBucketsForContinuousSplit property
- MaxConcurrentPredictionQueries property
- MinimumItemsetSize property
- AcyclicGraph property
- HoldoutMethod property
- StoppingTolerance property
- properties [data mining]
- AutoDetectPeriodicity property
- HoldoutTolerance property
- MinimumLeafCases property
- HoldoutSeed property
- MinimumClusterCases property
- ClusterCountDeviation property
- MinimumDependencyProbability property
- ClusteringMethod property
- MaximumItemsetSize property
- HiddenNodeRatio property
- MaximumSeriesValue property
ms.assetid: 9bc9abed-180a-4bd8-b2eb-89c62fa88110
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5ed1c47faafeb0c680e6afb6f8e509c426760da2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727189"
---
# <a name="data-mining-properties"></a><span data-ttu-id="da552-102">Data Mining-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="da552-102">Data Mining Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="da552-103">werden die in den folgenden Tabellen aufgeführten Data Mining-Eigenschaften unterstützt.</span><span class="sxs-lookup"><span data-stu-id="da552-103">supports the data mining server properties listed in the following tables.</span></span> <span data-ttu-id="da552-104">Weitere Informationen zu zusätzlichen Servereigenschaften und zum Festlegen dieser Eigenschaften finden Sie unter [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="da552-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="da552-105">**Gilt für:** Nur mehrdimensionaler Server Modus</span><span class="sxs-lookup"><span data-stu-id="da552-105">**Applies to:** Multidimensional server mode only</span></span>  
  
## <a name="non-specific-category"></a><span data-ttu-id="da552-106">Nicht spezifische Kategorie</span><span class="sxs-lookup"><span data-stu-id="da552-106">Non-Specific Category</span></span>  
 `AllowSessionMiningModels`  
 <span data-ttu-id="da552-107">Eine boolesche Eigenschaft, die anzeigt, ob Sitzungsminingmodelle erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="da552-107">A Boolean property that indicates whether session mining models can be created.</span></span>  
  
 <span data-ttu-id="da552-108">Der Standardwert für diese Eigenschaft ist FALSE. Dies bedeutet, dass keine Sitzungsminingmodelle erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="da552-108">The default value for this property is false, which indicates that session mining models cannot be created.</span></span>  
  
 `AllowAdHocOpenRowsetQueries`  
 <span data-ttu-id="da552-109">Eine boolesche Eigenschaft, die anzeigt, ob Ad-hoc-Abfragen für geöffnete Rowsets zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="da552-109">A Boolean property that indicates whether adhoc open rowset queries are allowed.</span></span>  
  
 <span data-ttu-id="da552-110">Der Standardwert für diese Eigenschaft ist FALSE. Dies bedeutet, dass während einer Sitzung keine Abfragen für geöffnete Rowsets zugelassen sind.</span><span class="sxs-lookup"><span data-stu-id="da552-110">The default value for this property is false, which indicates that open rowset queries are not allowed during a session.</span></span>  
  
 `AllowedProvidersInOpenRowset`  
 <span data-ttu-id="da552-111">Eine Zeichenfolge, die die in einem geöffneten Rowset zulässigen Anbieter identifiziert. Die Zeichenfolge kann aus einer durch Kommas bzw. Semikolons getrennten Liste von Anbieter-ProgIDs oder aus dem Wert [All] bestehen.</span><span class="sxs-lookup"><span data-stu-id="da552-111">A string property that identifies which providers are allowed in an open rowset, consisting of a comma/semi-colon separated list of provider ProgIDs, or else [All].</span></span>  
  
 `MaxConcurrentPredictionQueries`  
 <span data-ttu-id="da552-112">Eine ganze 32-Bit-Zahl mit Vorzeichen, die die maximale Anzahl von gleichzeitigen Vorhersageabfragen definiert.</span><span class="sxs-lookup"><span data-stu-id="da552-112">A signed 32-bit integer property that defines the maximum number of concurrent prediction queries.</span></span>  
  
## <a name="algorithms-category"></a><span data-ttu-id="da552-113">Algorithmus-Kategorie</span><span class="sxs-lookup"><span data-stu-id="da552-113">Algorithms Category</span></span>  
 `Microsoft_Association_Rules\ Enabled`  
 <span data-ttu-id="da552-114">Eine boolesche Eigenschaft, die anzeigt, ob der Microsoft_Association_Rules-Algorithmus aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="da552-114">A Boolean property that indicates whether the Microsoft_Association_Rules algorithm is enabled.</span></span>  
  
 `Microsoft_Clustering\ Enabled`  
 <span data-ttu-id="da552-115">Eine boolesche Eigenschaft, die anzeigt, ob der Microsoft_Clustering-Algorithmus aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="da552-115">A Boolean property that indicates whether the Microsoft_Clustering algorithm is enabled.</span></span>  
  
 `Microsoft_Decision_Trees\ Enabled`  
 <span data-ttu-id="da552-116">Eine boolesche Eigenschaft, die anzeigt, ob der Microsoft_DecisionTrees-Algorithmus aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="da552-116">A Boolean property that indicates whether the Microsoft_DecisionTrees algorithm is enabled.</span></span>  
  
 `Microsoft_Naive_Bayes\ Enabled`  
 <span data-ttu-id="da552-117">Eine boolesche Eigenschaft, die anzeigt, ob der Microsoft_ Naive_Bayes-Algorithmus aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="da552-117">A Boolean property that indicates whether the Microsoft_ Naive_Bayes algorithm is enabled.</span></span>  
  
 `Microsoft_Neural_Network\ Enabled`  
 <span data-ttu-id="da552-118">Eine boolesche Eigenschaft, die anzeigt, ob der Microsoft_Neural_Network-Algorithmus aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="da552-118">A Boolean property that indicates whether the Microsoft_Neural_Network algorithm is enabled.</span></span>  
  
 `Microsoft_Sequence_Clustering\ Enabled`  
 <span data-ttu-id="da552-119">Eine boolesche Eigenschaft, die anzeigt, ob der Microsoft_Sequence_Clustering-Algorithmus aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="da552-119">A Boolean property that indicates whether the Microsoft_Sequence_Clustering algorithm is enabled.</span></span>  
  
 `Microsoft_Time_Series\ Enabled`  
 <span data-ttu-id="da552-120">Eine boolesche Eigenschaft, die anzeigt, ob der Microsoft_Time_Series-Algorithmus aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="da552-120">A Boolean property that indicates whether the Microsoft_Time_Series algorithm is enabled.</span></span>  
  
 `Microsoft_Linear_Regression\ Enabled`  
 <span data-ttu-id="da552-121">Eine boolesche Eigenschaft, die anzeigt, ob der Microsoft_Linear_Regression-Algorithmus aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="da552-121">A Boolean property that indicates whether the Microsoft_Linear_Regression algorithm is enabled.</span></span>  
  
 `Microsoft_Logistic_Regression\ Enabled`  
 <span data-ttu-id="da552-122">Eine boolesche Eigenschaft, die anzeigt, ob der Microsoft_Logistic_Regression-Algorithmus aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="da552-122">A Boolean property that indicates whether the Microsoft_Logistic_Regression algorithm is enabled.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="da552-123">Zusätzlich zu den Data Mining-Diensten, die auf dem Server verfügbar sind, sind Data Mining-Eigenschaften vorhanden, die das Verhalten bestimmter Algorithmen definieren.</span><span class="sxs-lookup"><span data-stu-id="da552-123">In addition to properties that define the data mining services available on the server, there are data mining properties that define the behavior of specific algorithms.</span></span> <span data-ttu-id="da552-124">Sie konfigurieren diese Eigenschaften, wenn Sie ein einzelnes Data Mining-Modell erstellen, nicht auf Serverebene.</span><span class="sxs-lookup"><span data-stu-id="da552-124">You configure these properties when you create an individual data mining model, not at the server level.</span></span> <span data-ttu-id="da552-125">Weitere Informationen finden Sie unter [Data Mining-Algorithmen &#40;Analysis Services – Data Mining&#41;](../data-mining/data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="da552-125">For more information, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](../data-mining/data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da552-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="da552-126">See Also</span></span>  
 <span data-ttu-id="da552-127">[Physische Architektur &#40;Analysis Services Data Mining-&#41;](../data-mining/physical-architecture-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="da552-127">[Physical Architecture &#40;Analysis Services - Data Mining&#41;](../data-mining/physical-architecture-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="da552-128">[Konfigurieren von Server Eigenschaften in Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="da552-128">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="da552-129">Bestimmen des Servermodus einer Analysis Services-Instanz</span><span class="sxs-lookup"><span data-stu-id="da552-129">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
