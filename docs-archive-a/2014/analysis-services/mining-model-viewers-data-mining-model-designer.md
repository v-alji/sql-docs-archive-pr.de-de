---
title: Mining Modell-Viewer (Modell-Designer für Data Mining) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.viewers.f1
ms.assetid: 4ba391d5-c97b-4848-ba7c-7d096fa4b7dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4cc1c9d72a08ef49ed2f4f466953d2ba61394178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724273"
---
# <a name="mining-model-viewers-data-mining-model-designer"></a><span data-ttu-id="9902f-102">Miningmodell-Viewer (Modell-Designer für Data Mining)</span><span class="sxs-lookup"><span data-stu-id="9902f-102">Mining Model Viewers (Data Mining Model Designer)</span></span>
  <span data-ttu-id="9902f-103">Verwenden Sie die Registerkarte **Miningmodell-Viewer** , um die in einer Miningstruktur enthaltenen Miningmodelle zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="9902f-103">Use the **Mining Model Viewer** tab to explore the mining models that a mining structure contains.</span></span>

 <span data-ttu-id="9902f-104">Wählen Sie erst das Miningmodell und anschließend einen Viewer aus.</span><span class="sxs-lookup"><span data-stu-id="9902f-104">First you select the mining model and then you select a viewer.</span></span> <span data-ttu-id="9902f-105">Für jedes Modell stehen stets zwei Viewer zur Verfügung: ein benutzerdefinierter Viewer, der mehrere Registerkarten umfassen kann, und der generische Viewer.</span><span class="sxs-lookup"><span data-stu-id="9902f-105">Each model always has two viewers available: a custom viewer, which can include multiple tabs, and the generic viewer.</span></span>

 <span data-ttu-id="9902f-106">Eine exemplarische Vorgehensweise zum Verwenden jedes Viewers finden Sie unter [Data Mining-Modell-Viewer](data-mining/data-mining-model-viewers.md).</span><span class="sxs-lookup"><span data-stu-id="9902f-106">For a walkthrough of how to use each viewer, see [Data Mining Model Viewers](data-mining/data-mining-model-viewers.md).</span></span>

## <a name="common-options"></a><span data-ttu-id="9902f-107">Häufige Optionen</span><span class="sxs-lookup"><span data-stu-id="9902f-107">Common Options</span></span>
 <span data-ttu-id="9902f-108">**Viewerinhalt aktualisieren** Lädt das Miningmodell im Viewer neu.</span><span class="sxs-lookup"><span data-stu-id="9902f-108">**Refresh viewer content** Reload the mining model in the viewer.</span></span>

 <span data-ttu-id="9902f-109">**Miningmodell** Wählen Sie ein anzuzeigendes, in der aktuellen Miningstruktur enthaltenes Miningmodell aus.</span><span class="sxs-lookup"><span data-stu-id="9902f-109">**Mining Model** Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="9902f-110">Das Miningmodell wird zuerst im zugeordneten benutzerdefinierten Viewer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="9902f-110">The mining model will first open in its associated custom viewer.</span></span>

 <span data-ttu-id="9902f-111">**Viewer** Wählen Sie den Viewer aus, der zum Durchsuchen des ausgewählten Miningmodells verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9902f-111">**Viewer** Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="9902f-112">Diese Liste enthält die Viewer, die [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] für jedes Mining Modell bereitstellt, den [!INCLUDE[msCoName](../includes/msconame-md.md)] Viewer für Mining Inhalte sowie alle Plug-in-Viewer.</span><span class="sxs-lookup"><span data-stu-id="9902f-112">This list includes the viewers that [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] provides for each mining model, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer, and any plug-in viewers.</span></span>

 <span data-ttu-id="9902f-113">Das folgende Diagramm zeigt einen benutzerdefinierten Viewer und den generischen Viewer für das gleiche Modell an.</span><span class="sxs-lookup"><span data-stu-id="9902f-113">The following diagram shows a custom viewer and the generic viewer for the same model.</span></span>

-   <span data-ttu-id="9902f-114">Das obere Diagramm zeigt den Viewer für ein Miningmodell auf Grundlage des Microsoft Time Series-Algorithmus an.</span><span class="sxs-lookup"><span data-stu-id="9902f-114">The upper diagram shows the viewer for a mining model based on the Microsoft Time Series algorithm.</span></span> <span data-ttu-id="9902f-115">Dieser spezielle benutzerdefinierte Viewer erstellt automatisch ein Diagramm der Zeitreihe und stellt fünf Vorhersagen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="9902f-115">This particular custom viewer automatically creates a graph of the time series and provides five predictions.</span></span>

-   <span data-ttu-id="9902f-116">Das niedrigere Modell zeigt das gleiche Modell mit dem **Microsoft Generic Content Tree Viewer**.</span><span class="sxs-lookup"><span data-stu-id="9902f-116">The lower diagram shows the same model displayed using the **Microsoft Generic Content Tree Viewer**.</span></span> <span data-ttu-id="9902f-117">Dieser Viewer präsentiert den Inhalt des Miningmodells nach einem standardisierten Schema.</span><span class="sxs-lookup"><span data-stu-id="9902f-117">This viewer presents the contents of the mining model according to a standardized schema.</span></span> <span data-ttu-id="9902f-118">Weitere Informationen finden Sie unter [Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="9902f-118">For more information, see [Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](microsoft-generic-content-tree-viewer-data-mining.md).</span></span>

 <span data-ttu-id="9902f-119">![Übersicht über den Data Mining-Modell-Designer](media/generic-mining-model-tab1.gif "Übersicht über den Data Mining-Modell-Designer")</span><span class="sxs-lookup"><span data-stu-id="9902f-119">![Overview of mining model designer](media/generic-mining-model-tab1.gif "Overview of mining model designer")</span></span>

## <a name="viewers-and-their-components"></a><span data-ttu-id="9902f-120">Viewer und ihre Komponenten</span><span class="sxs-lookup"><span data-stu-id="9902f-120">Viewers and Their Components</span></span>
 <span data-ttu-id="9902f-121">Abhängig vom Modell, das Sie auswählen, wird ein anderer benutzerdefinierter Viewer angezeigt, der an den Algorithmus angepasst wurde, mit dem Sie das ausgewählte Data Mining-Modell erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="9902f-121">Depending on the model that you select, you will see a different custom viewer, tailored to the algorithm that you used to create the selected data mining model.</span></span> <span data-ttu-id="9902f-122">Jeder benutzerdefinierte Viewer verfügt über mehrere Tools und Dialogfelder zum Untersuchen der Statistiken und Muster im Modell.</span><span class="sxs-lookup"><span data-stu-id="9902f-122">Each custom viewer has a variety of tools and dialog boxes for helping you explore the statistics and patterns in the model.</span></span>

 <span data-ttu-id="9902f-123">Die folgende Liste beschreibt die Optionen in jeden der benutzerdefinierten Viewer.</span><span class="sxs-lookup"><span data-stu-id="9902f-123">The following list describes the options in each of the custom viewers.</span></span>

### <a name="microsoft-association-rules-algorithm"></a><span data-ttu-id="9902f-124">Microsoft Association Rules-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="9902f-124">Microsoft Association Rules Algorithm</span></span>

-   [<span data-ttu-id="9902f-125">Modell mit dem Microsoft-Viewer für Zuordnungsregeln durchsuchen</span><span class="sxs-lookup"><span data-stu-id="9902f-125">Browse a Model Using the Microsoft Association Rules Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)

    -   [<span data-ttu-id="9902f-126">Registerkarte "Itemsets" &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-126">Itemsets Tab &#40;Mining Model Viewer&#41;</span></span>](itemsets-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="9902f-127">Registerkarte "Regeln" &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-127">Rules Tab &#40;Mining Model Viewer&#41;</span></span>](rules-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="9902f-128">Registerkarte Abhängigkeits Netzwerk &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-128">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

### <a name="microsoft-clustering-algorithm"></a><span data-ttu-id="9902f-129">Microsoft Clustering-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="9902f-129">Microsoft Clustering Algorithm</span></span>

-   [<span data-ttu-id="9902f-130">Durchsuchen eines Modells mit dem Microsoft Cluster-Viewer</span><span class="sxs-lookup"><span data-stu-id="9902f-130">Browse a Model Using the Microsoft Cluster Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)

    -   [<span data-ttu-id="9902f-131">Registerkarte "Cluster Diagramm" &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-131">Cluster Diagram Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-diagram-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="9902f-132">Registerkarte "Cluster profile" &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-132">Cluster Profiles Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-profiles-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="9902f-133">Registerkarte Cluster Merkmale &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-133">Cluster Characteristics Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-characteristics-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="9902f-134">Registerkarte Cluster Unterscheidung &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-134">Cluster Discrimination Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-discrimination-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="9902f-135">Mining Legende (Dialog Feld) &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-135">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

### <a name="microsoft-decision-tree-algorithm"></a><span data-ttu-id="9902f-136">Microsoft Decision Tree-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="9902f-136">Microsoft Decision Tree Algorithm</span></span>

-   [<span data-ttu-id="9902f-137">Durchsuchen eines Modells mit dem Microsoft Struktur-Viewer</span><span class="sxs-lookup"><span data-stu-id="9902f-137">Browse a Model Using the Microsoft Tree Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-tree-viewer.md)

    -   [<span data-ttu-id="9902f-138">Registerkarte "Entscheidungsstruktur" &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-138">Decision Tree Tab &#40;Mining Model Viewer&#41;</span></span>](decision-tree-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="9902f-139">Registerkarte Abhängigkeits Netzwerk &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-139">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="9902f-140">Mining Legende (Dialog Feld) &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-140">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

### <a name="microsoft-linear-regression-algorithm"></a><span data-ttu-id="9902f-141">Microsoft Linear Regression-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="9902f-141">Microsoft Linear Regression Algorithm</span></span>

-   [<span data-ttu-id="9902f-142">Modell mit dem Microsoft-Viewer für neuronale Netzwerke durchsuchen</span><span class="sxs-lookup"><span data-stu-id="9902f-142">Browse a Model Using the Microsoft Neural Network Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)

    -   [<span data-ttu-id="9902f-143">Registerkarte "Entscheidungsstruktur" &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-143">Decision Tree Tab &#40;Mining Model Viewer&#41;</span></span>](decision-tree-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="9902f-144">Registerkarte Abhängigkeits Netzwerk &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-144">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="9902f-145">Mining Legende (Dialog Feld) &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-145">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

### <a name="microsoft-logistic-regression-algorithm"></a><span data-ttu-id="9902f-146">Microsoft Logistic Regression-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="9902f-146">Microsoft Logistic Regression Algorithm</span></span>

-   [<span data-ttu-id="9902f-147">Modell mit dem Microsoft-Viewer für neuronale Netzwerke durchsuchen</span><span class="sxs-lookup"><span data-stu-id="9902f-147">Browse a Model Using the Microsoft Neural Network Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)

### <a name="microsoft-nave-bayes-algorithm"></a><span data-ttu-id="9902f-148">Microsoft Naive Bayes-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="9902f-148">Microsoft Naïve Bayes Algorithm</span></span>

-   [<span data-ttu-id="9902f-149">Durchsuchen eines Modells mit dem Microsoft Naive Bayes-Viewer</span><span class="sxs-lookup"><span data-stu-id="9902f-149">Browse a Model Using the Microsoft Naive Bayes Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)

    -   [<span data-ttu-id="9902f-150">Registerkarte Abhängigkeits Netzwerk &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-150">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="9902f-151">Registerkarte "Attribut profile" &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-151">Attribute Profiles Tab &#40;Mining Model Viewer&#41;</span></span>](attribute-profiles-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="9902f-152">Registerkarte "Attribut Merkmale" &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-152">Attribute Characteristics Tab &#40;Mining Model Viewer&#41;</span></span>](attribute-characteristics-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="9902f-153">Registerkarte Attribut Unterscheidung &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-153">Attribute Discrimination Tab &#40;Mining Model Viewer&#41;</span></span>](attribute-discrimination-tab-mining-model-viewer.md)

### <a name="microsoft-neural-network-algorithm"></a><span data-ttu-id="9902f-154">Microsoft Neural Network Algorithm</span><span class="sxs-lookup"><span data-stu-id="9902f-154">Microsoft Neural Network Algorithm</span></span>

-   [<span data-ttu-id="9902f-155">Modell mit dem Microsoft-Viewer für neuronale Netzwerke durchsuchen</span><span class="sxs-lookup"><span data-stu-id="9902f-155">Browse a Model Using the Microsoft Neural Network Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)

    -   [<span data-ttu-id="9902f-156">Registerkarte Abhängigkeits Netzwerk &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-156">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="9902f-157">&#40;Mining Modell-Viewer für neuronale Netzwerke&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-157">Neural Network &#40;Mining Model Viewer&#41;</span></span>](neural-network-mining-model-viewer.md)

    -   [<span data-ttu-id="9902f-158">Dialog Feld "Knoten suchen" &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-158">Find Node Dialog Box &#40;Mining Model Viewer&#41;</span></span>](find-node-dialog-box-mining-model-viewer.md)

### <a name="microsoft-sequence-clustering-algorithm"></a><span data-ttu-id="9902f-159">Microsoft Sequence Clustering-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="9902f-159">Microsoft Sequence Clustering Algorithm</span></span>

-   [<span data-ttu-id="9902f-160">Durchsuchen eines Modells mit dem Microsoft Sequenzcluster-Viewer</span><span class="sxs-lookup"><span data-stu-id="9902f-160">Browse a Model Using the Microsoft Sequence Cluster Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)

    -   [<span data-ttu-id="9902f-161">Registerkarte "Sequenz Cluster/Cluster Diagramm" &#40;Mining Modell-Viewer</span><span class="sxs-lookup"><span data-stu-id="9902f-161">Sequence Clustering Cluster Diagram Tab &#40;Mining Model Viewer</span></span>](sequence-clustering-cluster-diagram-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="9902f-162">Registerkarte "Sequenz Cluster-Cluster profile" &#40;Mining Modell-Viewer</span><span class="sxs-lookup"><span data-stu-id="9902f-162">Sequence Clustering Cluster Profiles Tab &#40;Mining Model Viewer</span></span>](sequence-clustering-cluster-profiles-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="9902f-163">Registerkarte "Sequenz Cluster/Cluster Merkmale" &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-163">Sequence Clustering Cluster Characteristics Tab &#40;Mining Model Viewer&#41;</span></span>](sequence-clustering-cluster-characteristics-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="9902f-164">Registerkarte "Sequenz Cluster/Cluster Unterscheidung" &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-164">Sequence Clustering Cluster Discrimination Tab &#40;Mining Model Viewer&#41;</span></span>](sequence-clustering-cluster-discrimination-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="9902f-165">Registerkarte "Sequenz Cluster/Cluster Übergang" &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-165">Sequence Clustering Cluster Transition Tab &#40;Mining Model Viewer&#41;</span></span>](sequence-clustering-cluster-transition-tab-mining-model-viewer.md)

### <a name="microsoft-time-series-algorithm"></a><span data-ttu-id="9902f-166">Microsoft Time Series-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="9902f-166">Microsoft Time Series Algorithm</span></span>

-   [<span data-ttu-id="9902f-167">Durchsuchen eines Modells mit Microsoft Time Series-Viewer</span><span class="sxs-lookup"><span data-stu-id="9902f-167">Browse a Model Using the Microsoft Time Series Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-time-series-viewer.md)

    -   [<span data-ttu-id="9902f-168">Registerkarte "Modell" &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-168">Model Tab &#40;Mining Model Viewers&#41;</span></span>](model-tab-mining-model-viewers.md)

    -   [<span data-ttu-id="9902f-169">Registerkarte "Diagramm" &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-169">Chart Tab &#40;Mining Model Viewers&#41;</span></span>](chart-tab-mining-model-viewers.md)

    -   [<span data-ttu-id="9902f-170">Mining Legende (Dialog Feld) &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="9902f-170">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

## <a name="see-also"></a><span data-ttu-id="9902f-171">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9902f-171">See Also</span></span>
 <span data-ttu-id="9902f-172">[Mining Modelle Ansicht &#40;Data Mining-Modell-Designer&#41;](mining-models-view-data-mining-model-designer.md) [Mining Strukturansicht &#40;Data Mining-Modell-Designer&#41;](mining-structure-view-data-mining-model-designer.md) [Mining Genauigkeits Diagramm-Designer &#40;Data Mining&#41;](mining-accuracy-chart-designer-data-mining.md) [Vorhersage Abfrage-Generator &#40;Data Mining&#41;](prediction-query-builder-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="9902f-172">[Mining Models View &#40;Data Mining Model Designer&#41;](mining-models-view-data-mining-model-designer.md) [Mining Structure View &#40;Data Mining Model Designer&#41;](mining-structure-view-data-mining-model-designer.md) [Mining Accuracy Chart Designer &#40;Data Mining&#41;](mining-accuracy-chart-designer-data-mining.md) [Prediction Query Builder &#40;Data Mining&#41;](prediction-query-builder-data-mining.md)</span></span>


