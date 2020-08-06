---
title: Anzeigen der Formel für ein Zeitreihen Modell (Data Mining) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], how-to topics
- ARTXP
- time series algorithms [Analysis Services]
- ARIMA
- time series [Analysis Services]
- Time Series Viewer [Analysis Services]
ms.assetid: 825ef719-2f44-4979-be01-5a81f54e1a53
author: minewiskan
ms.author: owend
ms.openlocfilehash: eff61c469d34f084e6a0eb11c49a1c37c7cc97c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608076"
---
# <a name="view-the-formula-for-a-time-series-model-data-mining"></a><span data-ttu-id="214b2-102">Anzeigen der Formel für ein Zeitreihenmodell (Data Mining)</span><span class="sxs-lookup"><span data-stu-id="214b2-102">View the Formula for a Time Series Model (Data Mining)</span></span>
  <span data-ttu-id="214b2-103">Der [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series-Viewer inData Mining-Designer bietet die einfachste Möglichkeit, die Details der in einem Zeitreihen Modell verwendeten Regressionsgleichung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="214b2-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series viewer inData Mining Designer provides the easiest way to view the details of the regression equation used in a time series model.</span></span>  
  
 <span data-ttu-id="214b2-104">Sie können die Regressionsformel für ein Zeitreihenmodell extrahieren, indem Sie den Modellinhalt abfragen.</span><span class="sxs-lookup"><span data-stu-id="214b2-104">You can extract the regression formula for a time series model by querying the model content.</span></span> <span data-ttu-id="214b2-105">Zum Anzeigen der vollständigen ARTxp-oder ARIMA-Formel empfiehlt es sich jedoch, die **Mining Legende** des [Microsoft Time Series-Viewers](browse-a-model-using-the-microsoft-time-series-viewer.md)zu verwenden, in der alle Konstanten in einem lesbaren Format dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="214b2-105">However, to view the complete ARTXP or ARIMA formula, we recommend that you use the **Mining Legend** of the [Microsoft Time Series Viewer](browse-a-model-using-the-microsoft-time-series-viewer.md), which presents all the constants in a readable format.</span></span>  
  
 <span data-ttu-id="214b2-106">Wenn Sie ein gemischtes Modell erstellen, werden die ARIMA- und die ARTXP-Analyse in separaten Strukturen erstellt. Sie sind am Stammknoten miteinander verknüpft, der das Modell darstellt.</span><span class="sxs-lookup"><span data-stu-id="214b2-106">If you create a mixed model, the ARIMA and ARTXP analyses are created in separate trees, joined at the root node representing the model.</span></span> <span data-ttu-id="214b2-107">Die Strukturen der ARIMA- und der ARTXP-Struktur unterscheiden sich stark.</span><span class="sxs-lookup"><span data-stu-id="214b2-107">The structures of the ARIMA and ARTXP trees are very different.</span></span> <span data-ttu-id="214b2-108">Zum Beispiel ist die ARTXP-Struktur tatsächlich eine Baumstruktur (wie eine Entscheidungsstruktur), wohingegen die ARIMA-Struktur eine Reihe von gleitenden Durchschnitten darstellt.</span><span class="sxs-lookup"><span data-stu-id="214b2-108">For example, the ARTXP tree is in fact a tree structure, like a decision tree, whereas the ARIMA tree represents a series of moving averages.</span></span> <span data-ttu-id="214b2-109">Obwohl die beiden Darstellungen der Übersichtlichkeit halber in einem Modell gezeigt werden, müssen Sie sie dennoch als zwei unabhängige Modelle behandeln.</span><span class="sxs-lookup"><span data-stu-id="214b2-109">Therefore, although the two representations are presented in one model for convenience, they should be treated as two independent models.</span></span> <span data-ttu-id="214b2-110">Die Gleichungen sind auch völlig unterschiedlich und können nicht kombiniert oder verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="214b2-110">The equations are also completely different and cannot be combined or compared.</span></span>  
  
 <span data-ttu-id="214b2-111">Sie können Zeitreihen Modelle auch mit dem [Microsoft Generic Content Tree Viewer](../microsoft-generic-content-tree-viewer-data-mining.md)anzeigen.</span><span class="sxs-lookup"><span data-stu-id="214b2-111">You can also view time series models by using the [Microsoft Generic Content Tree Viewer](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span> <span data-ttu-id="214b2-112">Weitere Informationen zum Inhalt eines Zeitreihen Modells finden Sie unter [Mining Modell Inhalt von Zeitreihen Modellen &#40;Analysis Services Data Mining-&#41;](mining-model-content-for-time-series-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="214b2-112">For more information about the content of a time series model, see [Mining Model Content for Time Series Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-time-series-models-analysis-services-data-mining.md).</span></span>  
  
### <a name="to-view-the-artxp-regression-formula-for-a-time-series-model"></a><span data-ttu-id="214b2-113">So zeigen Sie die ARTXP-Regressionsformel für ein Zeitreihenmodell an</span><span class="sxs-lookup"><span data-stu-id="214b2-113">To view the ARTXP regression formula for a time series model</span></span>  
  
1.  <span data-ttu-id="214b2-114">Wählen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]das Zeitreihenmodell aus, das Sie anzeigen möchten, und klicken Sie auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="214b2-114">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the time series model that you want to view, and click **Browse**.</span></span>  
  
     <span data-ttu-id="214b2-115">– oder –</span><span class="sxs-lookup"><span data-stu-id="214b2-115">-- or --</span></span>  
  
     <span data-ttu-id="214b2-116">Wählen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das Zeitreihenmodell aus, und klicken Sie dann auf die Registerkarte **Miningmodell-Viewer** .</span><span class="sxs-lookup"><span data-stu-id="214b2-116">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the time series model, and then click the **Mining Model Viewer** tab.</span></span>  
  
2.  <span data-ttu-id="214b2-117">Klicken Sie auf die Registerkarte **Model** .</span><span class="sxs-lookup"><span data-stu-id="214b2-117">Click the **Model** tab.</span></span>  
  
3.  <span data-ttu-id="214b2-118">Wenn das Modell mehrere Strukturen enthält, wählen Sie aus der Dropdownliste **Struktur** eine einzelne Struktur aus.</span><span class="sxs-lookup"><span data-stu-id="214b2-118">If the model contains multiple trees, select a single tree from the **Tree** drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="214b2-119">Ein Modell hat stets mehrere Strukturen, wenn mehr als eine Datenreihe vorliegt.</span><span class="sxs-lookup"><span data-stu-id="214b2-119">A model will always have multiple trees if you have more than one data series.</span></span> <span data-ttu-id="214b2-120">Sie sehen jedoch im **Time Series-Viewer** nicht so viele Strukturen wie im [Microsoft Generic Content Tree Viewer](../microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="214b2-120">However, you will not see as many trees in the **Time Series viewer** as you will see in the [Microsoft Generic Content Tree Viewer](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span> <span data-ttu-id="214b2-121">Der Grund hierfür liegt darin, dass der Time Series-Viewer die ARIMA- und ARTXP-Informationen für jede Datenreihe zu einer einzelnen Darstellung kombiniert.</span><span class="sxs-lookup"><span data-stu-id="214b2-121">That is because the Time Series viewer combines the ARIMA and ARTXP information for each data series into a single representation.</span></span>  
  
4.  <span data-ttu-id="214b2-122">Klicken Sie auf einen Blattknoten in der Struktur.</span><span class="sxs-lookup"><span data-stu-id="214b2-122">Click any leaf node in the tree.</span></span>  
  
     <span data-ttu-id="214b2-123">Knoten, die als **Datenreihe** bezeichnet werden, sind immer Blattknoten und können eine Gleichung enthalten.</span><span class="sxs-lookup"><span data-stu-id="214b2-123">Nodes that are labeled as **Data Series** are always leaf nodes and can contain an equation.</span></span> <span data-ttu-id="214b2-124">Wenn ein **(Alle)** -Knoten keine untergeordneten Knoten besitzt, kann er ebenfalls eine Gleichung enthalten.</span><span class="sxs-lookup"><span data-stu-id="214b2-124">If an **(All)** node has no child nodes, it can also contain an equation.</span></span>  
  
5.  <span data-ttu-id="214b2-125">Wenn die **Mininglegende** nicht verfügbar ist, klicken Sie mit der rechten Maustaste auf den Knoten, und wählen Sie **Legende anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="214b2-125">If the **Mining Legend** is not available, right-click the node, and select **Show Legend**.</span></span>  
  
     <span data-ttu-id="214b2-126">Die ARTXP-Formel wird in der ersten Hälfte der **Mininglegende**als **Strukturknotenformel**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="214b2-126">The ARTXP formula is displayed in the first half of the **Mining Legend**, as the **Tree node equation**.</span></span>  
  
### <a name="to-view-the-arima-formula-for-a-time-series-model"></a><span data-ttu-id="214b2-127">So zeigen Sie die ARTxp-Formel für ein Zeitreihenmodell an</span><span class="sxs-lookup"><span data-stu-id="214b2-127">To view the ARIMA formula for a time series model</span></span>  
  
1.  <span data-ttu-id="214b2-128">Wählen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]das Zeitreihenmodell aus, das Sie anzeigen möchten, und klicken Sie auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="214b2-128">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the time series model that you want to view, and click **Browse**.</span></span>  
  
     <span data-ttu-id="214b2-129">– oder –</span><span class="sxs-lookup"><span data-stu-id="214b2-129">-- or --</span></span>  
  
     <span data-ttu-id="214b2-130">Wählen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das Zeitreihenmodell aus, und klicken Sie dann auf die Registerkarte **Miningmodell-Viewer** .</span><span class="sxs-lookup"><span data-stu-id="214b2-130">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the time series model, and then click the **Mining Model Viewer** tab.</span></span>  
  
2.  <span data-ttu-id="214b2-131">Klicken Sie auf die Registerkarte **Model** .</span><span class="sxs-lookup"><span data-stu-id="214b2-131">Click the **Model** tab.</span></span>  
  
3.  <span data-ttu-id="214b2-132">Wenn das Modell mehrere Strukturen enthält, wählen Sie aus der Dropdownliste **Struktur** eine einzelne Struktur aus.</span><span class="sxs-lookup"><span data-stu-id="214b2-132">If the model contains multiple trees, select a single tree from the **Tree** drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="214b2-133">Das Modell hat stets mehrere Strukturen, wenn Sie mehr als eine Datenreihe einschließen.</span><span class="sxs-lookup"><span data-stu-id="214b2-133">The model will always have multiple trees if you include more than one data series.</span></span>  
  
4.  <span data-ttu-id="214b2-134">Klicken Sie auf einen Knoten in der Struktur.</span><span class="sxs-lookup"><span data-stu-id="214b2-134">Click any node in the tree.</span></span>  
  
     <span data-ttu-id="214b2-135">Die ARIMA-Formel wird in der zweiten Hälfte der **Mininglegende**als **ARIMA-Formel**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="214b2-135">The ARIMA formula is displayed in the second half of the **Mining Legend**, as the **ARIMA equation**.</span></span>  
  
5.  <span data-ttu-id="214b2-136">Wenn die **Mininglegende** nicht verfügbar ist, klicken Sie mit der rechten Maustaste auf den Knoten, und wählen Sie **Legende anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="214b2-136">If the **Mining Legend** is not available, right-click the node, and select **Show Legend**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="214b2-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="214b2-137">See Also</span></span>  
 <span data-ttu-id="214b2-138">[Tasks und Anleitungen des Mining Modell-Viewers](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="214b2-138">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="214b2-139">[Durchsuchen eines Modells mit dem Microsoft Time Series-Viewer](browse-a-model-using-the-microsoft-time-series-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="214b2-139">[Browse a Model Using the Microsoft Time Series Viewer](browse-a-model-using-the-microsoft-time-series-viewer.md) </span></span>  
 [<span data-ttu-id="214b2-140">Abfragebeispiel Zeitreihenmodell</span><span class="sxs-lookup"><span data-stu-id="214b2-140">Time Series Model Query Examples</span></span>](time-series-model-query-examples.md)  
  
  
