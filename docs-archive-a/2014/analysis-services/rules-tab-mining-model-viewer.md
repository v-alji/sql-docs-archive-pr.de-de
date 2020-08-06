---
title: Registerkarte "Regeln" (Mining Modell-Viewer) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.associationrules.rules.f1
ms.assetid: 705d5492-b58f-45d9-94d7-ed57b7025823
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0d86931865fd9352074669de93b14dacfc84537
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610127"
---
# <a name="rules-tab-mining-model-viewer"></a><span data-ttu-id="7b1d1-102">Registerkarte "Regeln" (Miningmodell-Viewer)</span><span class="sxs-lookup"><span data-stu-id="7b1d1-102">Rules Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="7b1d1-103">Im Bereich **Regeln** in einem Zuordnungsmodell können Sie die Regeln anzeigen, die vom Algorithmus aus den Daten extrahiert wurden.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-103">Use the **Rules** pane in an association model to view the rules that the algorithm extracted from the data.</span></span> <span data-ttu-id="7b1d1-104">Regeln beschreiben, in welcher Beziehung Elemente zueinander stehen, und können zum Erstellen von Empfehlungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-104">Rules describe how items are related to each other, and can be used to create recommendations.</span></span>  
  
 <span data-ttu-id="7b1d1-105">Mit den Optionen im Viewer können Sie die Anzahl der im Viewer angezeigten Regeln filtern.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-105">You can use the options in the viewer to filter the number of rules that are displayed in the viewer.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="7b1d1-106">Standardmäßig werden nur die Regeln im Viewer angezeigt, die über dem in **Minimale Wahrscheinlichkeit** definierten Schwellenwert für die Wahrscheinlichkeit liegen.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-106">By default, only the rules that are above the probability threshold defined in **Minimum probability** are displayed in the viewer.</span></span> <span data-ttu-id="7b1d1-107">Dieser Wert kann im Viewer nicht verringert werden, da der Wahrscheinlichkeitsschwellenwert für Regelausgaben beim Erstellen des Modells bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-107">You cannot make this value any smaller by using the viewer, because the probability threshold for rule output is determined when the model is created.</span></span> <span data-ttu-id="7b1d1-108">Weitere Informationen finden Sie unter [Technische Referenz für den Microsoft Association-Algorithmus](data-mining/microsoft-association-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="7b1d1-108">For more information, see [Microsoft Association Algorithm Technical Reference](data-mining/microsoft-association-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="7b1d1-109">**Weitere Informationen:** [Microsoft Association-Algorithmus](data-mining/microsoft-association-algorithm.md), [Modell mit dem Microsoft-Viewer für Zuordnungsregeln durchsuchen](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="7b1d1-109">**For More Information:** [Microsoft Association Algorithm](data-mining/microsoft-association-algorithm.md), [Browse a Model Using the Microsoft Association Rules Viewer](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="7b1d1-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="7b1d1-110">Options</span></span>  
 <span data-ttu-id="7b1d1-111">**Viewerinhalt aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="7b1d1-111">**Refresh viewer content**</span></span>  
 <span data-ttu-id="7b1d1-112">Lädt das Miningmodell im Viewer neu.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-112">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="7b1d1-113">**Mining Modell**</span><span class="sxs-lookup"><span data-stu-id="7b1d1-113">**Mining Model**</span></span>  
 <span data-ttu-id="7b1d1-114">Wählen Sie ein anzuzeigendes, in der aktuellen Miningstruktur enthaltenes Miningmodell aus.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-114">Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="7b1d1-115">Das Miningmodell wird im dazugehörigen Viewer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-115">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="7b1d1-116">**Viewer**</span><span class="sxs-lookup"><span data-stu-id="7b1d1-116">**Viewer**</span></span>  
 <span data-ttu-id="7b1d1-117">Wählen Sie einen Viewer aus, mit dem das ausgewählte Miningmodell angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-117">Choose a viewer to use to view the selected mining model.</span></span> <span data-ttu-id="7b1d1-118">Sie können für jedes Miningmodell den benutzerdefinierten Viewer oder den **Microsoft Generic Content Tree Viewer**verwenden.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-118">You can use the custom viewer for each mining model, or the **Microsoft Generic Content Tree Viewer**.</span></span> <span data-ttu-id="7b1d1-119">Sie können auch Plug-In-Viewer verwenden, falls diese verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-119">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="7b1d1-120">**Minimale Wahrscheinlichkeit**</span><span class="sxs-lookup"><span data-stu-id="7b1d1-120">**Minimum probability**</span></span>  
 <span data-ttu-id="7b1d1-121">Ändern Sie diesen Wert, um die erforderliche minimale Wahrscheinlichkeit festzulegen, damit eine Regel im Viewer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-121">Change this value to set the minimum probability required for a rule to be displayed in the viewer.</span></span> <span data-ttu-id="7b1d1-122">Wenn Sie den Wert für die Wahrscheinlichkeit erhöhen, wird die Anzahl der angezeigten Regeln verringert.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-122">Increasing the value for probability will reduce the number of rules that are displayed.</span></span>  
  
 <span data-ttu-id="7b1d1-123">**Minimale Wichtigkeit**</span><span class="sxs-lookup"><span data-stu-id="7b1d1-123">**Minimum importance**</span></span>  
 <span data-ttu-id="7b1d1-124">Ändern Sie diesen Wert, um die erforderliche minimale Wichtigkeit festzulegen, damit eine Regel im Viewer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-124">Change this value to set the minimum importance required for a rule to be displayed in the viewer.</span></span> <span data-ttu-id="7b1d1-125">Wenn Sie den Wert für die Wichtigkeit erhöhen, wird die Anzahl der angezeigten Regeln verringert.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-125">Increasing the value for importance will reduce the number of rules that are displayed.</span></span>  
  
 <span data-ttu-id="7b1d1-126">**Filterregel**</span><span class="sxs-lookup"><span data-stu-id="7b1d1-126">**Filter Rule**</span></span>  
 <span data-ttu-id="7b1d1-127">Geben Sie einen Zeichenfolgenwert ein, um die Anzahl der im Viewer angezeigten Regeln zu filtern.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-127">Type a string value to filter the number of rules that appear in the viewer.</span></span>  
  
 <span data-ttu-id="7b1d1-128">Sie können auch reguläre .NET-Ausdrücke als Filterkriterien eingeben.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-128">You can also type .NET regular expressions as filter criteria.</span></span> <span data-ttu-id="7b1d1-129">Der folgende Ausdruck gibt z. B. alle Regeln zurück, die 'Road Bottle Cage' auf der linken Seite der Regel enthalten:</span><span class="sxs-lookup"><span data-stu-id="7b1d1-129">For example, the following expression returns all rules that contain 'Road Bottle Cage' on the left side of the rule:</span></span>  
  
 `\bRoad\b.\bBottle\b.\bCage\b.*->.*`  
  
 <span data-ttu-id="7b1d1-130">Beachten Sie, dass Sie die Sicht möglicherweise aktualisieren müssen, damit die Filterkriterien angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-130">Note that you might need to refresh the view to see the filter criteria apply.</span></span> <span data-ttu-id="7b1d1-131">Sie können auch die Option **Langen Namen anzeigen** aktivieren und deaktivieren, um die Liste zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-131">You can also toggle the **Show long name** option on and off to refresh the list.</span></span>  
  
 <span data-ttu-id="7b1d1-132">Standardmäßig wird ein Filterkriterium auf den vollständigen Namen der Attribut/Wert-Kombination angewendet. Wenn Sie nur den Attributnamen anzeigen, ist daher möglicherweise nicht gleich erkennbar, dass das Filterkriterium richtig angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-132">By default the filter criteria applies to the full name of the attribute-value combination; therefore, if you are viewing the attribute name only, it might not be obvious that the filter criteria has applied correctly.</span></span> <span data-ttu-id="7b1d1-133">Wählen Sie in der Dropdownliste **Anzeigen** die Option **Attributnamen und Wert anzeigen**aus, und überprüfen Sie, ob die Liste der Itemsets richtig gefiltert wurde.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-133">Use the **Show** dropdown list to select **Show attribute name and value**, and verify that the list of itemsets is filtered correctly.</span></span>  
  
 <span data-ttu-id="7b1d1-134">**Anzeigen**</span><span class="sxs-lookup"><span data-stu-id="7b1d1-134">**Show**</span></span>  
 <span data-ttu-id="7b1d1-135">Passen Sie an, wie die Regel im Viewer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-135">Adjust the way that the rule is displayed in the viewer.</span></span> <span data-ttu-id="7b1d1-136">Sie können eine der drei folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="7b1d1-136">You can select one of the three following options:</span></span>  
  
-   <span data-ttu-id="7b1d1-137">Attributnamen und Wert anzeigen</span><span class="sxs-lookup"><span data-stu-id="7b1d1-137">Show the attribute name and value</span></span>  
  
-   <span data-ttu-id="7b1d1-138">Nur Attributwert anzeigen</span><span class="sxs-lookup"><span data-stu-id="7b1d1-138">Show the attribute value only</span></span>  
  
-   <span data-ttu-id="7b1d1-139">Nur Attributnamen anzeigen</span><span class="sxs-lookup"><span data-stu-id="7b1d1-139">Show the attribute name only</span></span>  
  
 <span data-ttu-id="7b1d1-140">**Langen Namen anzeigen**</span><span class="sxs-lookup"><span data-stu-id="7b1d1-140">**Show long name**</span></span>  
 <span data-ttu-id="7b1d1-141">Zeigt den vollständigen Namen der Regel so an, wie er im Inhalt des Miningmodells enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-141">Show the full name of the rule as it appears in the mining model content.</span></span>  
  
 <span data-ttu-id="7b1d1-142">**Maximale Zeilenanzahl**</span><span class="sxs-lookup"><span data-stu-id="7b1d1-142">**Maximum rows**</span></span>  
 <span data-ttu-id="7b1d1-143">Beschränkt die Anzahl der Regeln, die im Viewer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-143">Limit the number of rules that are displayed in the viewer.</span></span>  
  
 <span data-ttu-id="7b1d1-144">**Wahrscheinlichkeit**</span><span class="sxs-lookup"><span data-stu-id="7b1d1-144">**Probability**</span></span>  
 <span data-ttu-id="7b1d1-145">In dieser Spalte im Diagramm wird die Wahrscheinlichkeit für jede Regel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-145">This column in the chart displays the probability for each rule.</span></span>  
  
 <span data-ttu-id="7b1d1-146">Sie können auf die Spaltenüberschrift klicken, um nach Wahrscheinlichkeit zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-146">You can click the column heading to sort by probability.</span></span>  
  
 <span data-ttu-id="7b1d1-147">**Wichtigkeit**</span><span class="sxs-lookup"><span data-stu-id="7b1d1-147">**Importance**</span></span>  
 <span data-ttu-id="7b1d1-148">In dieser Spalte im Diagramm wird die Wichtigkeit für jede Regel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-148">This column in the chart displays the importance for each rule.</span></span>  
  
 <span data-ttu-id="7b1d1-149">Sie können auf die Spaltenüberschrift klicken, um nach Wichtigkeit zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-149">You can click the column heading to sort by importance.</span></span>  
  
 <span data-ttu-id="7b1d1-150">**Regel**</span><span class="sxs-lookup"><span data-stu-id="7b1d1-150">**Rule**</span></span>  
 <span data-ttu-id="7b1d1-151">In dieser Spalte im Diagramm wird die Textbeschreibung für jede Regel angezeigt, dabei wird das mit den Optionen **Anzeigen** und **Langen Namen anzeigen**angegebene Format verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-151">This column in the chart displays the text description for each rule, according to the format specified by using the options, **Show** and **Show long name**.</span></span>  
  
 <span data-ttu-id="7b1d1-152">Sie können auf die Spaltenüberschrift klicken, um nach dem Text der Regel zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="7b1d1-152">You can click the column heading to sort by the text of the rule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b1d1-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7b1d1-153">See Also</span></span>  
 <span data-ttu-id="7b1d1-154">[Data Mining-Algorithmen &#40;Analysis Services Data Mining-&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="7b1d1-154">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="7b1d1-155">[Mining Modell-Viewer &#40;Data Mining-Modell-Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="7b1d1-155">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="7b1d1-156">Data Mining-Modell-Viewer</span><span class="sxs-lookup"><span data-stu-id="7b1d1-156">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
