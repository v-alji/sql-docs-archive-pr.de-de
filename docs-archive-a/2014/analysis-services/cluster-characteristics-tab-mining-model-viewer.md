---
title: Registerkarte "Cluster Merkmale" (Mining Modell-Viewer) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.clustering.characteristics.f1
ms.assetid: 8e33ed1d-1ce4-405d-895b-7e995b2c910d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 959d94767b6cb27d9ebb6e06c592034fca20ac89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610267"
---
# <a name="cluster-characteristics-tab-mining-model-viewer"></a><span data-ttu-id="f4c94-102">Registerkarte "Clustermerkmale" (Miningmodell-Viewer)</span><span class="sxs-lookup"><span data-stu-id="f4c94-102">Cluster Characteristics Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="f4c94-103">Auf der Registerkarte **Clustermerkmale** können Sie die Eigenschaften eines Clusters in einem Clusteringmodell oder die Gruppe aller Fälle im Modell untersuchen.</span><span class="sxs-lookup"><span data-stu-id="f4c94-103">The **Cluster Characteristics** tab lets you explore the characteristics of a cluster in a clustering model, or the set of all cases in the model.</span></span> <span data-ttu-id="f4c94-104">Das Diagramm zeigt die Wichtigkeit jedes Attribut/Wert-Paars als ein Merkmal, das den Cluster definiert, im Vergleich zu anderen Clustern.</span><span class="sxs-lookup"><span data-stu-id="f4c94-104">The graph shows the importance of each attribute-value pair as a characteristic that defines the cluster, in comparison with other clusters.</span></span>  
  
 <span data-ttu-id="f4c94-105">**Weitere Informationen:** [Microsoft Clustering-Algorithmus](data-mining/microsoft-clustering-algorithm.md), [Durchsuchen eines Modells mit dem Microsoft Cluster-Viewer](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="f4c94-105">**For More Information:** [Microsoft Clustering Algorithm](data-mining/microsoft-clustering-algorithm.md), [Browse a Model Using the Microsoft Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="f4c94-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="f4c94-106">Options</span></span>  
 <span data-ttu-id="f4c94-107">**Viewerinhalt aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="f4c94-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="f4c94-108">Lädt das Miningmodell im Viewer neu.</span><span class="sxs-lookup"><span data-stu-id="f4c94-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="f4c94-109">**Mining Modell**</span><span class="sxs-lookup"><span data-stu-id="f4c94-109">**Mining Model**</span></span>  
 <span data-ttu-id="f4c94-110">Wählen Sie ein Miningmodell aus der aktuellen Miningstruktur aus.</span><span class="sxs-lookup"><span data-stu-id="f4c94-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="f4c94-111">Das Miningmodell wird im benutzerdefinierten Viewer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f4c94-111">The mining model will open in the custom viewer.</span></span>  
  
 <span data-ttu-id="f4c94-112">**Viewer**</span><span class="sxs-lookup"><span data-stu-id="f4c94-112">**Viewer**</span></span>  
 <span data-ttu-id="f4c94-113">Wählen Sie den Viewer aus, der zum Durchsuchen des ausgewählten Miningmodells verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f4c94-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="f4c94-114">Sie können den diesem Modelltyp zugeordneten benutzerdefinierten Viewer oder den [!INCLUDE[msCoName](../includes/msconame-md.md)] -Viewer für Mininginhalte verwenden.</span><span class="sxs-lookup"><span data-stu-id="f4c94-114">You can use the custom viewer associated with this model type, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="f4c94-115">Sie können auch alle verfügbaren Plug-In-Viewer verwenden.</span><span class="sxs-lookup"><span data-stu-id="f4c94-115">You can also use any plug-in viewers that are available.</span></span>  
  
 <span data-ttu-id="f4c94-116">**Cluster**</span><span class="sxs-lookup"><span data-stu-id="f4c94-116">**Cluster**</span></span>  
 <span data-ttu-id="f4c94-117">Wählen Sie den anzuzeigenden Cluster aus, oder wählen Sie **Auffüllung (Alle)** aus, um die Verteilung der Attribute für das ganze Modell anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f4c94-117">Choose the cluster you want to view, or choose **Population (All)** to see the distribution of attributes for the model as a whole.</span></span>  
  
 <span data-ttu-id="f4c94-118">**Merkmale für\<cluster>**</span><span class="sxs-lookup"><span data-stu-id="f4c94-118">**Characteristics for \<cluster>**</span></span>  
 <span data-ttu-id="f4c94-119">Das Diagramm enthält die folgenden Spalten, in denen die Merkmale des ausgewählten Clusters beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="f4c94-119">The graph contains the following columns, which describe the characteristics of the selected cluster.</span></span>  
  
|<span data-ttu-id="f4c94-120">Wert</span><span class="sxs-lookup"><span data-stu-id="f4c94-120">Value</span></span>|<span data-ttu-id="f4c94-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f4c94-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f4c94-122">**Variable**</span><span class="sxs-lookup"><span data-stu-id="f4c94-122">**Variable**</span></span>|<span data-ttu-id="f4c94-123">Listet die Attribute aus dem Miningmodell auf, die im ausgewählten Cluster vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f4c94-123">Lists the attributes from the mining model that are found in the selected cluster.</span></span>|  
|<span data-ttu-id="f4c94-124">**Werte**</span><span class="sxs-lookup"><span data-stu-id="f4c94-124">**Values**</span></span>|<span data-ttu-id="f4c94-125">Listet die Werte der aktuellen Attribute auf, die im derzeit ausgewählten Cluster vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f4c94-125">Lists the values of the current attributes that are found in the currently selected cluster.</span></span>|  
|<span data-ttu-id="f4c94-126">**Wahrscheinlichkeit**</span><span class="sxs-lookup"><span data-stu-id="f4c94-126">**Probability**</span></span>|<span data-ttu-id="f4c94-127">Der Balken gibt die Stärke des Attribut/Wert-Paars als kennzeichnendes Merkmal dieses Clusters an.</span><span class="sxs-lookup"><span data-stu-id="f4c94-127">The bar indicates the strength of the attribute-value pair as a distinguishing feature of this cluster.</span></span> <span data-ttu-id="f4c94-128">Wenn Sie mit der Maus auf den Balken zeigen, wird der Wahrscheinlichkeitswert als Prozentsatz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f4c94-128">If you hover the mouse over the bar, you can see the probability value, represented as a percentage.</span></span> <span data-ttu-id="f4c94-129">Dies gibt für diese Attribut/Wert-Kombination in jedem einzelnen Fall die Wahrscheinlichkeit an, dass der Fall in diesen Cluster gehört.</span><span class="sxs-lookup"><span data-stu-id="f4c94-129">What this indicates is, given this attribute and value combination in any particular case, what is the probability that the case would belong in this cluster.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f4c94-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f4c94-130">See Also</span></span>  
 <span data-ttu-id="f4c94-131">[Data Mining-Algorithmen &#40;Analysis Services Data Mining-&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="f4c94-131">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="f4c94-132">[Mining Modell-Viewer &#40;Data Mining-Modell-Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="f4c94-132">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="f4c94-133">Data Mining-Modell-Viewer</span><span class="sxs-lookup"><span data-stu-id="f4c94-133">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
