---
title: Registerkarte "Attribut Merkmale" (Mining Modell-Viewer) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.naivebayse.characteristics.f1
ms.assetid: f0c3350d-84c0-4ab8-9fb8-1527c2647299
author: minewiskan
ms.author: owend
ms.openlocfilehash: b29ba482c21bb674a10bc4c9e6c6eccdf30905dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610378"
---
# <a name="attribute-characteristics-tab-mining-model-viewer"></a><span data-ttu-id="d2035-102">Registerkarte "Attributmerkmale" (Miningmodell-Viewer)</span><span class="sxs-lookup"><span data-stu-id="d2035-102">Attribute Characteristics Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="d2035-103">Im Bereich **Attributmerkmale** können Sie die Beziehungen zwischen Ergebnissen und Eingabeattributen in einem Naive Bayes-Modell untersuchen.</span><span class="sxs-lookup"><span data-stu-id="d2035-103">Use the **Attribute Characteristics** pane to explore the relationships between outcomes and input attributes in a Naïve Bayes model.</span></span> <span data-ttu-id="d2035-104">Sie können den Wert des Zielattributs auswählen und dann eine Liste der Eingabeattribute anzeigen, die die stärksten Auswirkungen auf die Ergebnisse besitzen.</span><span class="sxs-lookup"><span data-stu-id="d2035-104">You can choose the value of the target attribute, and then see a list of the input attributes that have the strongest effect on the outcomes.</span></span>  
  
 <span data-ttu-id="d2035-105">**Weitere Informationen:** [Microsoft Naive Bayes-Algorithmus](data-mining/microsoft-naive-bayes-algorithm.md), [Durchsuchen eines Modells mit dem Microsoft Naive Bayes-Viewer](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="d2035-105">**For More Information:** [Microsoft Naive Bayes Algorithm](data-mining/microsoft-naive-bayes-algorithm.md), [Browse a Model Using the Microsoft Naive Bayes Viewer](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="d2035-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="d2035-106">Options</span></span>  
 <span data-ttu-id="d2035-107">**Viewerinhalt aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="d2035-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="d2035-108">Lädt das Miningmodell im Viewer neu.</span><span class="sxs-lookup"><span data-stu-id="d2035-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="d2035-109">**Mining Modell**</span><span class="sxs-lookup"><span data-stu-id="d2035-109">**Mining Model**</span></span>  
 <span data-ttu-id="d2035-110">Wählen Sie ein anzuzeigendes Miningmodell aus den Modellen in der aktuellen Miningstruktur aus.</span><span class="sxs-lookup"><span data-stu-id="d2035-110">Choose a mining model to view, from the models in the current mining structure.</span></span> <span data-ttu-id="d2035-111">Das Miningmodell wird automatisch in einem benutzerdefinierten Viewer geöffnet, der für den jeweils ausgewählten Typ von Modell am besten geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="d2035-111">The mining model will automatically open in a custom viewer that is best for the particular type of model you chose.</span></span>  
  
 <span data-ttu-id="d2035-112">**Viewer**</span><span class="sxs-lookup"><span data-stu-id="d2035-112">**Viewer**</span></span>  
 <span data-ttu-id="d2035-113">Wählen Sie den Viewer aus, der zum Durchsuchen des ausgewählten Miningmodells verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d2035-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="d2035-114">Für jedes Modell können Sie einen benutzerdefinierten Viewer oder aber den [!INCLUDE[msCoName](../includes/msconame-md.md)] -Viewer für Mininginhalte auswählen.</span><span class="sxs-lookup"><span data-stu-id="d2035-114">For each model, you have the choice of a custom viewer, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="d2035-115">Plug-In-Viewer werden in dieser Liste ebenfalls angezeigt, sofern verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d2035-115">Plug-in viewers also appear in this list if available.</span></span>  
  
 <span data-ttu-id="d2035-116">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="d2035-116">**Attribute**</span></span>  
 <span data-ttu-id="d2035-117">Wählen Sie das vorhersagbare Attribut aus, das Sie analysieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d2035-117">Choose the predictable attribute that you want to analyze.</span></span>  
  
 <span data-ttu-id="d2035-118">**Wert**</span><span class="sxs-lookup"><span data-stu-id="d2035-118">**Value**</span></span>  
 <span data-ttu-id="d2035-119">Wählen Sie einen Status für das unter **Attribut**festgelegte vorhersagbare Attribut aus.</span><span class="sxs-lookup"><span data-stu-id="d2035-119">Choose a state for the predictable attribute that you set in **Attribute**.</span></span> <span data-ttu-id="d2035-120">Da Naive Bayes-Modelle keine stetigen Größen unterstützen, verfügen alle Zielattribute über diskrete oder diskretisierte Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="d2035-120">Because Naïve Bayes models do not support continuous variables, all target attributes have discrete or discretized outcomes.</span></span> <span data-ttu-id="d2035-121">Das Missing-Attribut wird der Liste stets automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d2035-121">The Missing attribute is always automatically added to the list.</span></span>  
  
 <span data-ttu-id="d2035-122">**Merkmale für\<predictable state>**</span><span class="sxs-lookup"><span data-stu-id="d2035-122">**Characteristics for \<predictable state>**</span></span>  
 <span data-ttu-id="d2035-123">Die Grafik enthält die folgenden Spalten, die die Beziehung zwischen den Statuswerten der Eingabeattribute und den Statuswerten des ausgewählten vorhersagbaren Attributs beschreiben.</span><span class="sxs-lookup"><span data-stu-id="d2035-123">The graph contains the following columns, which describe how states of the input attributes are related to the selected predictable attribute state.</span></span>  
  
|<span data-ttu-id="d2035-124">Wert</span><span class="sxs-lookup"><span data-stu-id="d2035-124">Value</span></span>|<span data-ttu-id="d2035-125">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d2035-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d2035-126">**Variable**</span><span class="sxs-lookup"><span data-stu-id="d2035-126">**Variable**</span></span>|<span data-ttu-id="d2035-127">Führt die Eingabeattribute im Miningmodell auf.</span><span class="sxs-lookup"><span data-stu-id="d2035-127">Lists the input attributes in the mining model.</span></span>|  
|<span data-ttu-id="d2035-128">**Werte**</span><span class="sxs-lookup"><span data-stu-id="d2035-128">**Values**</span></span>|<span data-ttu-id="d2035-129">Führt die einzelnen Status des Eingabeattributs in **Variable**auf.</span><span class="sxs-lookup"><span data-stu-id="d2035-129">Lists each state of the input attribute in **Variable**.</span></span>|  
|<span data-ttu-id="d2035-130">**Wahrscheinlichkeit**</span><span class="sxs-lookup"><span data-stu-id="d2035-130">**Probability**</span></span>|<span data-ttu-id="d2035-131">Der Balken stellt die Wahrscheinlichkeit dar, mit der das Attribut und der Wert in dieser Zeile dem ausgewählten Status des ausgewählten vorhersagbaren Attributs entsprechen.</span><span class="sxs-lookup"><span data-stu-id="d2035-131">The bar represents the probability that the attribute and value in that row are associated with the selected state of the predictable attribute.</span></span> <span data-ttu-id="d2035-132">Zeigen Sie mit der Maus auf den Balken, um die Wahrscheinlichkeit als Prozentsatz anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d2035-132">Hover the mouse over the bar to view the probability as a percentage.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d2035-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d2035-133">See Also</span></span>  
 <span data-ttu-id="d2035-134">[Data Mining-Algorithmen &#40;Analysis Services Data Mining-&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="d2035-134">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="d2035-135">[Mining Modell-Viewer &#40;Data Mining-Modell-Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="d2035-135">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="d2035-136">Data Mining-Modell-Viewer</span><span class="sxs-lookup"><span data-stu-id="d2035-136">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
