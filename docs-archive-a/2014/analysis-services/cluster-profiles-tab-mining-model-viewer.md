---
title: Registerkarte "Cluster profile" (Mining Modell-Viewer) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.clustering.profiles.f1
ms.assetid: 1ebafa1f-74e9-4c05-b278-a690fa8543bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: a7ec1ce5b5204ae81a9313ca7b7e5df58c98c5da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615685"
---
# <a name="cluster-profiles-tab-mining-model-viewer"></a><span data-ttu-id="75c5a-102">Registerkarte "Clusterprofile" (Miningmodell-Viewer)</span><span class="sxs-lookup"><span data-stu-id="75c5a-102">Cluster Profiles Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="75c5a-103">Auf der Registerkarte **Clusterprofile** erhalten Sie einen Überblick über die vom Algorithmus in einem Clustermodell erkannten Cluster.</span><span class="sxs-lookup"><span data-stu-id="75c5a-103">Use the **Cluster Profiles** tab for an overall view of the clusters that the algorithm discovered within a clustering model.</span></span> <span data-ttu-id="75c5a-104">Die Registerkarte zeigt jedes Attribut zusammen mit der Verteilung des Attributs in jedem Cluster an.</span><span class="sxs-lookup"><span data-stu-id="75c5a-104">The tab displays each attribute, together with the distribution of the attribute in each cluster.</span></span>  
  
 <span data-ttu-id="75c5a-105">**Weitere Informationen:** [Microsoft Clustering-Algorithmus](data-mining/microsoft-clustering-algorithm.md), [Durchsuchen eines Modells mit dem Microsoft Cluster-Viewer](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="75c5a-105">**For More Information:** [Microsoft Clustering Algorithm](data-mining/microsoft-clustering-algorithm.md), [Browse a Model Using the Microsoft Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="75c5a-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="75c5a-106">Options</span></span>  
 <span data-ttu-id="75c5a-107">**Viewerinhalt aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="75c5a-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="75c5a-108">Lädt das Miningmodell im Viewer neu.</span><span class="sxs-lookup"><span data-stu-id="75c5a-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="75c5a-109">**Mining Modell**</span><span class="sxs-lookup"><span data-stu-id="75c5a-109">**Mining Model**</span></span>  
 <span data-ttu-id="75c5a-110">Wählen Sie ein Miningmodell aus der aktuellen Miningstruktur aus.</span><span class="sxs-lookup"><span data-stu-id="75c5a-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="75c5a-111">Das Miningmodell wird im dazugehörigen Viewer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="75c5a-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="75c5a-112">**Viewer**</span><span class="sxs-lookup"><span data-stu-id="75c5a-112">**Viewer**</span></span>  
 <span data-ttu-id="75c5a-113">Wählen Sie einen Viewer aus, mit dem das ausgewählte Miningmodell angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="75c5a-113">Choose a viewer to use to view the selected mining model.</span></span> <span data-ttu-id="75c5a-114">Sie können den benutzerdefinierten Viewer für das Miningmodell oder den [!INCLUDE[msCoName](../includes/msconame-md.md)] -Viewer für Mininginhalte verwenden.</span><span class="sxs-lookup"><span data-stu-id="75c5a-114">You can use the custom viewer for the mining model, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="75c5a-115">Sie können auch Plug-In-Viewer verwenden, falls diese verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="75c5a-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="75c5a-116">**Legende anzeigen**</span><span class="sxs-lookup"><span data-stu-id="75c5a-116">**Show Legend**</span></span>  
 <span data-ttu-id="75c5a-117">Wählen Sie diese Option zum Anzeigen eines Schlüssels aus, der die Zuordnung von Farben im Viewer zu Werten in der Spalte **Status** anzeigt.</span><span class="sxs-lookup"><span data-stu-id="75c5a-117">Select this option to display a key that shows the mapping of colors in the viewer to values in the **States** column.</span></span>  
  
 <span data-ttu-id="75c5a-118">**Histogrammbalken**</span><span class="sxs-lookup"><span data-stu-id="75c5a-118">**Histogram Bars**</span></span>  
 <span data-ttu-id="75c5a-119">Ändern Sie diesen Wert, um zu steuern, wie viele Status in jedem Histogramm eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="75c5a-119">Change this value to control how many states are included in each histogram.</span></span> <span data-ttu-id="75c5a-120">Wenn mehr Status vorhanden sind, als Sie für die Anzeige ausgewählt haben, werden die Status mit der höchsten Wahrscheinlichkeit im Histogramm angezeigt, und die restlichen Status werden unter **Sonstige**gruppiert.</span><span class="sxs-lookup"><span data-stu-id="75c5a-120">If there are more states than you choose to display, the states with the highest probability are shown in the histogram, and the remaining states are grouped together into **Other**.</span></span>  
  
 <span data-ttu-id="75c5a-121">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="75c5a-121">**Attributes**</span></span>  
 <span data-ttu-id="75c5a-122">Listet die Spalten im Clusteringmodell auf.</span><span class="sxs-lookup"><span data-stu-id="75c5a-122">Lists the columns that are in the clustering model.</span></span> <span data-ttu-id="75c5a-123">Die Histogramme für jedes Attribut zeigen an, wie das Attribut in den vom Algorithmus identifizierten Clustern verteilt ist.</span><span class="sxs-lookup"><span data-stu-id="75c5a-123">The histograms for each attribute show how the attribute is distributed among the clusters identified by the algorithm.</span></span>  
  
 <span data-ttu-id="75c5a-124">**Status**</span><span class="sxs-lookup"><span data-stu-id="75c5a-124">**States**</span></span>  
 <span data-ttu-id="75c5a-125">Stellt einen Schlüssel bereit, der angibt, durch welche Farben die einzelnen Status in der entsprechenden Clusterreihe dargestellt werden, oder einen Schieberegler mit einer Raute, mit dem die Verteilung von kontinuierlichen numerischen Werten angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="75c5a-125">Provides a key that either denotes what color represents each state in the corresponding row of clusters, or a slider with diamond that indicates the distribution of continuous numeric values.</span></span> <span data-ttu-id="75c5a-126">Sie können diese Spalte mit dem Kontrollkästchen **Legende anzeigen** ein- und ausblenden.</span><span class="sxs-lookup"><span data-stu-id="75c5a-126">You can show or hide this column by using the **Show Legend** check box.</span></span>  
  
 <span data-ttu-id="75c5a-127">**Clusterprofile**</span><span class="sxs-lookup"><span data-stu-id="75c5a-127">**Cluster Profiles**</span></span>  
 <span data-ttu-id="75c5a-128">Dieser Abschnitt enthält eine Spalte für jeden Cluster im Modell.</span><span class="sxs-lookup"><span data-stu-id="75c5a-128">This section contains a column for each cluster in the model.</span></span> <span data-ttu-id="75c5a-129">Für jedes Attribut wird im Histogramm die Verteilung der Werte im Attribut nur für diesen Cluster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="75c5a-129">For each attribute, the histogram shows the distribution of the values in the attribute for just that cluster.</span></span> <span data-ttu-id="75c5a-130">Das Diagramm enthält auch eine Spalte für **Auffüllung**, bei der ebenfalls mit Histogrammen die Verteilung der Werte für jedes Attribut angezeigt wird, dies jedoch für alle Fälle im Modell.</span><span class="sxs-lookup"><span data-stu-id="75c5a-130">The chart also has a column for **Population**, which also uses histograms to display the distribution of values for each attribute, but for all cases in the model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75c5a-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="75c5a-131">See Also</span></span>  
 <span data-ttu-id="75c5a-132">[Data Mining-Algorithmen &#40;Analysis Services Data Mining-&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="75c5a-132">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="75c5a-133">[Mining Modell-Viewer &#40;Data Mining-Modell-Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="75c5a-133">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="75c5a-134">Data Mining-Modell-Viewer</span><span class="sxs-lookup"><span data-stu-id="75c5a-134">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
