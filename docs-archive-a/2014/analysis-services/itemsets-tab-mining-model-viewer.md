---
title: Registerkarte "Itemsets" (Mining Modell-Viewer) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.associationrules.itemsets.f1
ms.assetid: 95b2b805-b142-4064-9c80-4b1b3fe2fe63
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b99b62b01b196fd62e1ef264e530487018f6a60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610161"
---
# <a name="itemsets-tab-mining-model-viewer"></a><span data-ttu-id="691d3-102">Registerkarte "Itemsets" (Miningmodell-Viewer)</span><span class="sxs-lookup"><span data-stu-id="691d3-102">Itemsets Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="691d3-103">Im Bereich **Itemsets** werden die häufig in einem Miningmodell für Zuordnungsregeln enthaltenen Itemsets angezeigt.</span><span class="sxs-lookup"><span data-stu-id="691d3-103">You can use the **Itemsets** pane to view the frequent itemsets that an association rules mining model contains.</span></span> <span data-ttu-id="691d3-104">Da ein Zuordnungsmodell viele Itemsets enthalten kann, werden im Viewer Steuerelemente bereitgestellt, mit denen Sie die im Viewer angezeigten Itemsets filtern können.</span><span class="sxs-lookup"><span data-stu-id="691d3-104">Because an association model can contain many itemsets, controls are provided in the viewer to help you filter the itemsets that are displayed in the viewer.</span></span>  
  
 <span data-ttu-id="691d3-105">**Weitere Informationen:** [Microsoft Association-Algorithmus](data-mining/microsoft-association-algorithm.md), [Modell mit dem Microsoft-Viewer für Zuordnungsregeln durchsuchen](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="691d3-105">**For More Information:** [Microsoft Association Algorithm](data-mining/microsoft-association-algorithm.md), [Browse a Model Using the Microsoft Association Rules Viewer](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="691d3-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="691d3-106">Options</span></span>  
 <span data-ttu-id="691d3-107">**Viewerinhalt aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="691d3-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="691d3-108">Lädt das Miningmodell im Viewer neu.</span><span class="sxs-lookup"><span data-stu-id="691d3-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="691d3-109">**Mining Modell**</span><span class="sxs-lookup"><span data-stu-id="691d3-109">**Mining Model**</span></span>  
 <span data-ttu-id="691d3-110">Wählen Sie ein anzuzeigendes, in der aktuellen Miningstruktur enthaltenes Miningmodell aus.</span><span class="sxs-lookup"><span data-stu-id="691d3-110">Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="691d3-111">Das Miningmodell wird im dazugehörigen Viewer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="691d3-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="691d3-112">**Viewer**</span><span class="sxs-lookup"><span data-stu-id="691d3-112">**Viewer**</span></span>  
 <span data-ttu-id="691d3-113">Wählen Sie einen Viewer aus, mit dem das ausgewählte Miningmodell angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="691d3-113">Choose a viewer to use to view the selected mining model.</span></span> <span data-ttu-id="691d3-114">Sie können entweder den benutzerdefinierten Viewer für Zuordnungsmodelle oder den [!INCLUDE[msCoName](../includes/msconame-md.md)] Generic Content Tree Viewer verwenden.</span><span class="sxs-lookup"><span data-stu-id="691d3-114">You can use either the custom viewer for association models, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Generic Content Tree viewer.</span></span> <span data-ttu-id="691d3-115">Sie können auch Plug-In-Viewer verwenden, falls diese verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="691d3-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="691d3-116">**Minimaler Unterstützungswert**</span><span class="sxs-lookup"><span data-stu-id="691d3-116">**Minimum support**</span></span>  
 <span data-ttu-id="691d3-117">Ändern Sie diesen Wert, um den Unterstützungswert festzulegen, den ein Itemset enthalten muss, um im Viewer angezeigt zu werden.</span><span class="sxs-lookup"><span data-stu-id="691d3-117">Change this value to set the minimum support that an itemset must contain to appear in the viewer.</span></span> <span data-ttu-id="691d3-118">Der Standardwert, der beim ersten Öffnen des Modells angezeigt wird, wird vom Modell berechnet, Sie können ihn jedoch ändern, um mehr oder weniger Itemsets anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="691d3-118">The default value that is displayed when you first open the model is calculated by the model, but you can change it to see more or fewer itemsets.</span></span>  
  
 <span data-ttu-id="691d3-119">**Mindestgröße des Itemsets**</span><span class="sxs-lookup"><span data-stu-id="691d3-119">**Minimum itemset size**</span></span>  
 <span data-ttu-id="691d3-120">Ändern Sie diesen Wert, um die Mindestanzahl von Elementen festzulegen, die in einem Itemset enthalten sein müssen, bevor das Itemset im Viewer angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="691d3-120">Change this value to set the minimum number of items that must be included in an itemset before the itemset can be displayed in the viewer.</span></span>  
  
 <span data-ttu-id="691d3-121">**Filteritemset**</span><span class="sxs-lookup"><span data-stu-id="691d3-121">**Filter Itemset**</span></span>  
 <span data-ttu-id="691d3-122">Geben Sie einen Zeichenfolgenwert ein, um die Anzahl der im Viewer angezeigten Itemsets zu filtern.</span><span class="sxs-lookup"><span data-stu-id="691d3-122">Type a string value to filter the number of itemsets that appear in the viewer.</span></span>  
  
 <span data-ttu-id="691d3-123">Sie können auch reguläre .NET-Ausdrücke als Filterkriterien eingeben.</span><span class="sxs-lookup"><span data-stu-id="691d3-123">You can also type .NET regular expressions as filter criteria.</span></span> <span data-ttu-id="691d3-124">Der folgende Ausdruck gibt z. B. alle Itemsets zurück, die 'Road Bottle Cage' enthalten:</span><span class="sxs-lookup"><span data-stu-id="691d3-124">For example, the following expression returns all itemsets that contain 'Road Bottle Cage':</span></span>  
  
 `\bRoad\b.\bBottle\b.\bCage\b.*`  
  
 <span data-ttu-id="691d3-125">Beachten Sie, dass Sie die Sicht möglicherweise aktualisieren müssen, damit die Filterkriterien angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="691d3-125">Note that you might need to refresh the view to see the filter criteria apply.</span></span> <span data-ttu-id="691d3-126">Sie können auch die Option **Langen Namen anzeigen** aktivieren und deaktivieren, um die Liste zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="691d3-126">You can also toggle the **Show long name** option on and off to refresh the list.</span></span>  
  
 <span data-ttu-id="691d3-127">Standardmäßig wird ein Filterkriterium auf den vollständigen Namen der Attribut/Wert-Kombination angewendet. Wenn Sie nur den Attributnamen anzeigen, ist daher möglicherweise nicht gleich erkennbar, dass das Filterkriterium richtig angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="691d3-127">By default the filter criteria applies to the full name of the attribute-value combination; therefore, if you are viewing the attribute name only, it might not be obvious that the filter criteria has applied correctly.</span></span> <span data-ttu-id="691d3-128">Wählen Sie in der Dropdownliste **Anzeigen** die Option **Attributnamen und Wert anzeigen**aus, und überprüfen Sie, ob die Liste der Itemsets richtig gefiltert wurde.</span><span class="sxs-lookup"><span data-stu-id="691d3-128">Use the **Show** dropdown list to select **Show attribute name and value**, and verify that the list of itemsets is filtered correctly.</span></span>  
  
 <span data-ttu-id="691d3-129">**Anzeigen**</span><span class="sxs-lookup"><span data-stu-id="691d3-129">**Show**</span></span>  
 <span data-ttu-id="691d3-130">Passen Sie an, wie das Itemset im Viewer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="691d3-130">Adjust how the itemset is displayed in the viewer.</span></span> <span data-ttu-id="691d3-131">Sie können eine der drei folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="691d3-131">You can select one of the three following options:</span></span>  
  
-   <span data-ttu-id="691d3-132">Attributnamen und Wert anzeigen</span><span class="sxs-lookup"><span data-stu-id="691d3-132">Show attribute name and value</span></span>  
  
-   <span data-ttu-id="691d3-133">Nur Attributwert anzeigen</span><span class="sxs-lookup"><span data-stu-id="691d3-133">Show attribute value only</span></span>  
  
-   <span data-ttu-id="691d3-134">Nur Attributnamen anzeigen</span><span class="sxs-lookup"><span data-stu-id="691d3-134">Show attribute name only</span></span>  
  
 <span data-ttu-id="691d3-135">Beachten Sie, dass mit dieser Option das Modell nicht erneut abgefragt wird. Es werden nur die Attribute oder Werte gefiltert, die angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="691d3-135">Note that this option does not requery the model; it only filters the attributes or values that are displayed.</span></span>  
  
 <span data-ttu-id="691d3-136">**Langen Namen anzeigen**</span><span class="sxs-lookup"><span data-stu-id="691d3-136">**Show long name**</span></span>  
 <span data-ttu-id="691d3-137">Wählen Sie diese Option aus, um den vollständigen Namen des Itemsets anzuzeigen, wie er im Miningmodellinhalt angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="691d3-137">Select this option to display the full name of the itemset as it appears in the mining model content.</span></span>  
  
 <span data-ttu-id="691d3-138">**Maximale Zeilenanzahl**</span><span class="sxs-lookup"><span data-stu-id="691d3-138">**Maximum rows**</span></span>  
 <span data-ttu-id="691d3-139">Beschränkt die Anzahl der Itemsets, die im Viewer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="691d3-139">Limit the number of itemsets that are displayed in the viewer.</span></span> <span data-ttu-id="691d3-140">Standardmäßig werden Itemsets in absteigender Reihenfolge nach Unterstützung sortiert, durch Verringern dieses Werts wird die Liste daher auf die häufigsten Itemsets eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="691d3-140">By default, itemsets are ordered by support in descending order, so lowering this value restricts the list to the most common itemsets.</span></span>  
  
 <span data-ttu-id="691d3-141">**Unterstützung**</span><span class="sxs-lookup"><span data-stu-id="691d3-141">**Support**</span></span>  
 <span data-ttu-id="691d3-142">Zeigt den Unterstützungswert der einzelnen Itemsets an.</span><span class="sxs-lookup"><span data-stu-id="691d3-142">Displays the support for each itemset.</span></span>  
  
 <span data-ttu-id="691d3-143">**Größe**</span><span class="sxs-lookup"><span data-stu-id="691d3-143">**Size**</span></span>  
 <span data-ttu-id="691d3-144">Zeigt an, wie viele Elemente in jedem Itemset vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="691d3-144">Displays the number of items that exist in each itemset.</span></span>  
  
 <span data-ttu-id="691d3-145">**Itemset**</span><span class="sxs-lookup"><span data-stu-id="691d3-145">**Itemset**</span></span>  
 <span data-ttu-id="691d3-146">Zeigt die Beschreibung für jedes Itemset an.</span><span class="sxs-lookup"><span data-stu-id="691d3-146">Displays the description of each itemset.</span></span> <span data-ttu-id="691d3-147">Standardmäßig werden Itemsets als durch Trennzeichen getrennte Liste von Attributen und ihren Werten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="691d3-147">By default, itemsets are presented as a comma-delimited list of attributes and their values.</span></span> <span data-ttu-id="691d3-148">Mit der Option **Anzeigen** können Sie ändern, wie sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="691d3-148">You can change the way they are displayed by using the **Show** option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="691d3-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="691d3-149">See Also</span></span>  
 <span data-ttu-id="691d3-150">[Data Mining-Algorithmen &#40;Analysis Services Data Mining-&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="691d3-150">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="691d3-151">[Mining Modell-Viewer &#40;Data Mining-Modell-Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="691d3-151">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="691d3-152">Data Mining-Modell-Viewer</span><span class="sxs-lookup"><span data-stu-id="691d3-152">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
