---
title: Registerkarte "Attribut Unterscheidung" (Mining Modell-Viewer) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.naivebayse.discrimination.f1
ms.assetid: 68323f23-121e-44fc-be85-6f9915d6d3c7
author: minewiskan
ms.author: owend
ms.openlocfilehash: a8b0d4bc99b1c8f1c5de0269312f02eeb09df022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610373"
---
# <a name="attribute-discrimination-tab-mining-model-viewer"></a><span data-ttu-id="fdf10-102">Registerkarte "Attributunterscheidung" (Miningmodell-Viewer)</span><span class="sxs-lookup"><span data-stu-id="fdf10-102">Attribute Discrimination Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="fdf10-103">Mithilfe der Registerkarte **Attributunterscheidung** können Sie die Status der Eingabeattribute vergleichen und anzeigen, in welcher Beziehung sie zum Ausgabeattribut stehen.</span><span class="sxs-lookup"><span data-stu-id="fdf10-103">Use the **Attribute Discrimination** tab to compare the states of the input attributes and see how they are related to the outcome attribute.</span></span> <span data-ttu-id="fdf10-104">Die Attributwerte, die für die größte Differenz zwischen den beiden ausgewählten vorhersagbaren Attributstatus sorgen, werden zuerst aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="fdf10-104">The attribute values that make the most difference between the two selected predictable attribute states are listed first.</span></span>  
  
 <span data-ttu-id="fdf10-105">**Weitere Informationen:** [Microsoft Naive Bayes-Algorithmus](data-mining/microsoft-naive-bayes-algorithm.md), [Durchsuchen eines Modells mit dem Microsoft Naive Bayes-Viewer](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="fdf10-105">**For More Information:** [Microsoft Naive Bayes Algorithm](data-mining/microsoft-naive-bayes-algorithm.md), [Browse a Model Using the Microsoft Naive Bayes Viewer](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="fdf10-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="fdf10-106">Options</span></span>  
 <span data-ttu-id="fdf10-107">**Viewerinhalt aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="fdf10-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="fdf10-108">Lädt das Miningmodell im Viewer neu.</span><span class="sxs-lookup"><span data-stu-id="fdf10-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="fdf10-109">**Mining Modell**</span><span class="sxs-lookup"><span data-stu-id="fdf10-109">**Mining Model**</span></span>  
 <span data-ttu-id="fdf10-110">Wählen Sie ein Miningmodell aus der aktuellen Miningstruktur aus.</span><span class="sxs-lookup"><span data-stu-id="fdf10-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="fdf10-111">Das Miningmodell wird automatisch im richtigen benutzerdefinierten Viewer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="fdf10-111">The mining model automatically opens in the correct custom viewer.</span></span>  
  
 <span data-ttu-id="fdf10-112">**Viewer**</span><span class="sxs-lookup"><span data-stu-id="fdf10-112">**Viewer**</span></span>  
 <span data-ttu-id="fdf10-113">Wählen Sie den Viewer aus, der zum Durchsuchen des ausgewählten Miningmodells verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fdf10-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="fdf10-114">Für jedes Modell können Sie entweder den benutzerdefinierten Viewer oder den [!INCLUDE[msCoName](../includes/msconame-md.md)] -Viewer für Mininginhalte auswählen.</span><span class="sxs-lookup"><span data-stu-id="fdf10-114">For each model, you can choose either the custom viewer, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="fdf10-115">Sie können auch Plug-In-Viewer verwenden, falls diese verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="fdf10-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="fdf10-116">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="fdf10-116">**Attribute**</span></span>  
 <span data-ttu-id="fdf10-117">Wählen Sie ein vorhersagbares Attribut aus.</span><span class="sxs-lookup"><span data-stu-id="fdf10-117">Choose a predictable attribute.</span></span>  
  
 <span data-ttu-id="fdf10-118">**Wert 1**</span><span class="sxs-lookup"><span data-stu-id="fdf10-118">**Value 1**</span></span>  
 <span data-ttu-id="fdf10-119">Wählen Sie einen Status des vorhersagbaren Attributs aus, der mit dem in **Wert 2**enthaltenen Wert verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="fdf10-119">Choose a state of the predictable attribute to compare to the state that is contained in **Value 2**.</span></span>  
  
 <span data-ttu-id="fdf10-120">**Wert 2**</span><span class="sxs-lookup"><span data-stu-id="fdf10-120">**Value 2**</span></span>  
 <span data-ttu-id="fdf10-121">Wählen Sie einen Status des vorhersagbaren Attributs aus, der mit dem in **Wert 1**enthaltenen Wert verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="fdf10-121">Select a state of the predictable attribute to compare to the state that is contained in **Value 1**.</span></span> <span data-ttu-id="fdf10-122">Sie können auch **alle anderen Zustände** auswählen, um den Wert in **Wert 1** mit seinem Komplement zu vergleichen, d. h. alle anderen Werte außer Wert 1.</span><span class="sxs-lookup"><span data-stu-id="fdf10-122">You can also select **All Other States** to compare the value in **Value 1** with its complement-that is, all other values except Value 1.</span></span>  
  
 <span data-ttu-id="fdf10-123">**Unterscheidungs Ergebnisse für \<Value 1> und\<Value 2>**</span><span class="sxs-lookup"><span data-stu-id="fdf10-123">**Discrimination scores for \<Value 1> and \<Value 2>**</span></span>  
 <span data-ttu-id="fdf10-124">Das Diagramm enthält die folgenden Spalten, in denen beschrieben wird, in welcher Beziehung das Zielattribut zu den spezifischen Status des Eingabeattributs steht.</span><span class="sxs-lookup"><span data-stu-id="fdf10-124">The graph contains the following columns, which describe how the target attribute is related to specific states of the input attribute.</span></span>  
  
|<span data-ttu-id="fdf10-125">Wert</span><span class="sxs-lookup"><span data-stu-id="fdf10-125">Value</span></span>|<span data-ttu-id="fdf10-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fdf10-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fdf10-127">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="fdf10-127">**Attributes**</span></span>|<span data-ttu-id="fdf10-128">Ein Eingabeattribut im Miningmodell.</span><span class="sxs-lookup"><span data-stu-id="fdf10-128">An input attribute in the mining model.</span></span>|  
|<span data-ttu-id="fdf10-129">**Werte**</span><span class="sxs-lookup"><span data-stu-id="fdf10-129">**Values**</span></span>|<span data-ttu-id="fdf10-130">Ein Status des Attributs, das unter **Attribute**aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="fdf10-130">A state of the attribute that is listed in **Attributes**.</span></span>|  
|<span data-ttu-id="fdf10-131">**Günstige\<Value 1>**</span><span class="sxs-lookup"><span data-stu-id="fdf10-131">**Favors \<Value 1>**</span></span>|<span data-ttu-id="fdf10-132">Der Balken gibt an, ob das aktuelle Attribut und der aktuelle Wert das in **Wert 1**ausgewählte Zielergebnis begünstigen.</span><span class="sxs-lookup"><span data-stu-id="fdf10-132">The bar indicates whether the current attribute and value favor the target outcome selected in **Value 1**.</span></span>|  
|<span data-ttu-id="fdf10-133">**Günstige\<Value 2>**</span><span class="sxs-lookup"><span data-stu-id="fdf10-133">**Favors \<Value 2>**</span></span>|<span data-ttu-id="fdf10-134">Der Balken gibt an, ob das aktuelle Attribut und der aktuelle Wert das in **Wert 2**ausgewählte Zielergebnis begünstigen.</span><span class="sxs-lookup"><span data-stu-id="fdf10-134">The bar indicates whether the current attribute and value favor the target outcome selected in **Value 2**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fdf10-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fdf10-135">See Also</span></span>  
 <span data-ttu-id="fdf10-136">[Data Mining-Algorithmen &#40;Analysis Services Data Mining-&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="fdf10-136">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="fdf10-137">[Mining Modell-Viewer &#40;Data Mining-Modell-Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="fdf10-137">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="fdf10-138">Data Mining-Modell-Viewer</span><span class="sxs-lookup"><span data-stu-id="fdf10-138">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
