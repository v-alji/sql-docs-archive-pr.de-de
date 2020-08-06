---
title: Registerkarte "Abhängigkeits Netzwerk" (Mining Modell-Viewer) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.dependencynetwork.f1
ms.assetid: e58ce1b7-20d6-42cb-ade5-916da8471e09
author: minewiskan
ms.author: owend
ms.openlocfilehash: 94ce82524445ffb8999c671c736087362ef0adfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696294"
---
# <a name="dependency-network-tab-mining-model-viewer"></a><span data-ttu-id="a7f45-102">Registerkarte "Abhängigkeitsnetzwerk" (Miningmodell-Viewer)</span><span class="sxs-lookup"><span data-stu-id="a7f45-102">Dependency Network Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="a7f45-103">Die Registerkarte **Abhängigkeitsnetzwerk** bietet eine grafische Sicht aller im Miningmodell enthaltenen Attribute und gibt die Beziehungen zwischen den Attributen an.</span><span class="sxs-lookup"><span data-stu-id="a7f45-103">The **Dependency Net** tab provides a graphical view of all attributes that the mining model contains, and shows how the attributes are related.</span></span>  
  
 <span data-ttu-id="a7f45-104">Die Registerkarte **Abhängigkeitsnetzwerk**  wird für mehrere Typen von Miningmodellen verwendet, darunter Naive Bayes-Modelle, Entscheidungsstrukturmodelle und Zuordnungsmodelle.</span><span class="sxs-lookup"><span data-stu-id="a7f45-104">The **Dependency Net**  tab is used for several types of mining models, including Naïve Bayes models, decision tree models, and association models.</span></span> <span data-ttu-id="a7f45-105">Weitere Informationen zum Interpretieren des Inhalts der Registerkarte **Abhängigkeitsnetzwerk**  im Kontext dieser Modelle finden Sie unter den folgenden Links:</span><span class="sxs-lookup"><span data-stu-id="a7f45-105">For more information about how to interpret the contents of the **Dependency Net**  tab in the context of these models, see the following links:</span></span>  
  
 [<span data-ttu-id="a7f45-106">Durchsuchen eines Modells mit dem Microsoft Struktur-Viewer</span><span class="sxs-lookup"><span data-stu-id="a7f45-106">Browse a Model Using the Microsoft Tree Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-tree-viewer.md)  
  
 [<span data-ttu-id="a7f45-107">Durchsuchen eines Modells mit dem Microsoft Naive Bayes-Viewer</span><span class="sxs-lookup"><span data-stu-id="a7f45-107">Browse a Model Using the Microsoft Naive Bayes Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)  
  
 [<span data-ttu-id="a7f45-108">Modell mit dem Microsoft-Viewer für Zuordnungsregeln durchsuchen</span><span class="sxs-lookup"><span data-stu-id="a7f45-108">Browse a Model Using the Microsoft Association Rules Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)  
  
## <a name="options"></a><span data-ttu-id="a7f45-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="a7f45-109">Options</span></span>  
 <span data-ttu-id="a7f45-110">**Viewerinhalt aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="a7f45-110">**Refresh viewer content**</span></span>  
 <span data-ttu-id="a7f45-111">Lädt das Miningmodell im Viewer neu.</span><span class="sxs-lookup"><span data-stu-id="a7f45-111">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="a7f45-112">**Mining Modell**</span><span class="sxs-lookup"><span data-stu-id="a7f45-112">**Mining Model**</span></span>  
 <span data-ttu-id="a7f45-113">Wählen Sie ein anzuzeigendes Miningmodell aus der aktuellen Miningstruktur aus.</span><span class="sxs-lookup"><span data-stu-id="a7f45-113">Choose a mining model to view, from those in the current mining structure.</span></span> <span data-ttu-id="a7f45-114">Das Miningmodell wird in einem benutzerdefinierten Viewer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a7f45-114">The mining model will open in a custom viewer.</span></span> <span data-ttu-id="a7f45-115">Der jeweils für ein Modell verwendete Typ von benutzerdefiniertem Viewer wird durch den Algorithmus bestimmt, mit dem Sie das Modell erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a7f45-115">The type of custom viewer that is used for each model is determined by the algorithm that you used to create the model.</span></span>  
  
 <span data-ttu-id="a7f45-116">**Viewer**</span><span class="sxs-lookup"><span data-stu-id="a7f45-116">**Viewer**</span></span>  
 <span data-ttu-id="a7f45-117">Wählen Sie den Viewer aus, der zum Durchsuchen des ausgewählten Miningmodells verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a7f45-117">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="a7f45-118">Für jedes Modell können Sie den benutzerdefinierten Viewer verwenden, der für das betreffende Miningmodell bereitgestellt wird, oder aber den [!INCLUDE[msCoName](../includes/msconame-md.md)] -Viewer für Mininginhalte.</span><span class="sxs-lookup"><span data-stu-id="a7f45-118">For each model, you can use either the custom viewer is provided for each mining model, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="a7f45-119">Sie können auch Plug-In-Viewer verwenden, falls diese verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a7f45-119">You can also use plug-in viewers if available.</span></span> <span data-ttu-id="a7f45-120">Der Microsoft Generic Content Tree Viewer kann mit allen Modellen verwendet werden, wobei der Modellinhalt in einer HTML-Tabelle dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="a7f45-120">The Microsoft Content Tree Viewer can be used with all models, and represents the model content in an HTML table.</span></span>  
  
 <span data-ttu-id="a7f45-121">**Vergrößern**</span><span class="sxs-lookup"><span data-stu-id="a7f45-121">**Zoom In**</span></span>  
 <span data-ttu-id="a7f45-122">Vergrößern Sie die Ansicht des Diagramms, damit Sie die Attribute detaillierter einsehen können.</span><span class="sxs-lookup"><span data-stu-id="a7f45-122">Zoom in to the diagram, so that you can see the attributes in more detail.</span></span>  
  
 <span data-ttu-id="a7f45-123">**Verkleinern**</span><span class="sxs-lookup"><span data-stu-id="a7f45-123">**Zoom Out**</span></span>  
 <span data-ttu-id="a7f45-124">Verkleinern Sie das Diagramm, damit Sie mehr Attribute und die Links zwischen diesen einsehen können.</span><span class="sxs-lookup"><span data-stu-id="a7f45-124">Zoom out from the diagram, so that you can see more attributes and the links between them.</span></span>  
  
 <span data-ttu-id="a7f45-125">**Diagrammsicht kopieren**</span><span class="sxs-lookup"><span data-stu-id="a7f45-125">**Copy Graph View**</span></span>  
 <span data-ttu-id="a7f45-126">Kopiert den sichtbaren Abschnitt des Diagramms in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="a7f45-126">Copy the visible section of the diagram to the clipboard.</span></span>  
  
 <span data-ttu-id="a7f45-127">**Gesamtes Diagramm kopieren**</span><span class="sxs-lookup"><span data-stu-id="a7f45-127">**Copy Entire Graph**</span></span>  
 <span data-ttu-id="a7f45-128">Kopiert das gesamte Diagramm in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="a7f45-128">Copy the complete diagram to the clipboard.</span></span>  
  
 <span data-ttu-id="a7f45-129">**Links**</span><span class="sxs-lookup"><span data-stu-id="a7f45-129">**Links**</span></span>  
 <span data-ttu-id="a7f45-130">Passt die Anzahl der im Viewer angezeigten Links (Ränder) und Knoten an, indem der Schieberegler rechts neben den Attributen verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="a7f45-130">Adjust how many links (edges) and nodes the viewer shows by adjusting the slider to the right of the attributes.</span></span> <span data-ttu-id="a7f45-131">Durch Ziehen des Schiebereglers nach unten wird der Schwellenwert erhöht, sodass nur die stärksten Links angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a7f45-131">Dragging the slider bar down increases the threshold value, so that only the strongest links are shown.</span></span> <span data-ttu-id="a7f45-132">Bei jedem Modelltyp wird ein etwas anderer Wert verwendet, um die Links im Diagramm darzustellen:</span><span class="sxs-lookup"><span data-stu-id="a7f45-132">For each model type, a slightly different value is used to represent the links in the graph:</span></span>  
  
-   <span data-ttu-id="a7f45-133">In einem **Entscheidungsstrukturmodell** stellen die Ränder die prognostizierte Stärke der Verbindung dar, die teilweise vom Teilungsergebnis abhängt.</span><span class="sxs-lookup"><span data-stu-id="a7f45-133">In a **decision tree** model, the edges represent the predictive strength of the connection, determined partly by the split score.</span></span>  
  
-   <span data-ttu-id="a7f45-134">In einem **Naive Bayes-Modell** können die Links zwischen zwei Knoten in beide Richtungen verlaufen: Knoten A kann Knoten B vorhersagen und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="a7f45-134">In a **Naïve Bayes** model, the links between two nodes can go either way: that is, node A can predict the node B, and vice versa.</span></span> <span data-ttu-id="a7f45-135">Das dem Rand zugeordnete Ergebnis stellt die prognostizierte Stärke der Verbindung dar.</span><span class="sxs-lookup"><span data-stu-id="a7f45-135">The score associated with the edge represents the predictive strength of the connection.</span></span>  
  
-   <span data-ttu-id="a7f45-136">In einem **Zuordnungsmodell**stellen die Ränder zwischen Knoten das Wichtigkeitsergebnis der Regel dar, die zwei Itemsets verbindet.</span><span class="sxs-lookup"><span data-stu-id="a7f45-136">In an **association model**, the edges between nodes represent the importance score of the rule that connects two itemsets.</span></span>  
  
 <span data-ttu-id="a7f45-137">Allgemeine gilt für alle Modelltypen: je stärker der Link, desto stärker ist auch die prognostizierte Beziehung zwischen den beiden Attributen.</span><span class="sxs-lookup"><span data-stu-id="a7f45-137">A general rule for all model types is that the stronger the link, the stronger the predictive relationship between the two attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7f45-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a7f45-138">See Also</span></span>  
 <span data-ttu-id="a7f45-139">[Data Mining-Algorithmen &#40;Analysis Services Data Mining-&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="a7f45-139">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="a7f45-140">[Mining Modell-Viewer &#40;Data Mining-Modell-Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="a7f45-140">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="a7f45-141">Data Mining-Modell-Viewer</span><span class="sxs-lookup"><span data-stu-id="a7f45-141">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
