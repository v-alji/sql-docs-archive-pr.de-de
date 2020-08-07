---
title: Untersuchen des Entscheidungsstruktur Modells (Lernprogramm zu Data Mining-Grundlagen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2e1472c2-3f3e-4dae-acb3-62fca374d397
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a2c7f063d7cb73cdc431fb1bc94188c9266c10c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719117"
---
# <a name="exploring-the-decision-tree-model-basic-data-mining-tutorial"></a><span data-ttu-id="14302-102">Untersuchen des Entscheidungsstrukturmodells (Lernprogramm zu Data Mining-Grundlagen)</span><span class="sxs-lookup"><span data-stu-id="14302-102">Exploring the Decision Tree Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="14302-103">Durch den [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees-Algorithmus wird anhand der übrigen Spalten im Trainingssatz vorhergesagt, welche Spalten die Entscheidung über den Kauf eines Fahrrads beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="14302-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm predicts which columns influence the decision to purchase a bike based upon the remaining columns in the training set.</span></span>  
  

  
##  <a name="decision-tree-tab"></a><a name="Decision_Tree_Tab"></a><span data-ttu-id="14302-104">Registerkarte Entscheidungsstruktur</span><span class="sxs-lookup"><span data-stu-id="14302-104">Decision Tree Tab</span></span>  
 <span data-ttu-id="14302-105">Auf der Registerkarte **Entscheidungs** Struktur können Sie Entscheidungsbäume für jedes vorhersagbare Attribut im Dataset anzeigen.</span><span class="sxs-lookup"><span data-stu-id="14302-105">On the **Decision Tree** tab, you can view decision trees for every predictable attribute in the dataset.</span></span>  
  
 <span data-ttu-id="14302-106">In diesem Fall prognostiziert das Modell nur eine Spalte Bike Buyer, sodass nur eine Struktur angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="14302-106">In this case, the model predicts only one column, Bike Buyer, so there is only one tree to view.</span></span> <span data-ttu-id="14302-107">Wenn weitere Strukturen vorhanden waren, können **Sie das Struktur** Feld verwenden, um eine andere Struktur auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="14302-107">If there were more trees, you could use the **Tree** box to choose another tree.</span></span>  
  
 <span data-ttu-id="14302-108">Wenn Sie das `TM_Decision_Tree` Modell im Decision Tree-Viewer anzeigen, können Sie die wichtigsten Attribute auf der linken Seite des Diagramms sehen.</span><span class="sxs-lookup"><span data-stu-id="14302-108">As you view the `TM_Decision_Tree` model in the Decision Tree viewer, you can see the most important attributes at the left side of the chart.</span></span> <span data-ttu-id="14302-109">"Am wichtigsten" bedeutet, dass diese Attribute den größten Einfluss auf das Ergebnis haben.</span><span class="sxs-lookup"><span data-stu-id="14302-109">"Most important" means that these attributes have the greatest influence on the outcome.</span></span> <span data-ttu-id="14302-110">Die weiter unten in der Struktur (auf der rechten Diagrammseite) angezeigten Attribute weisen einen geringeren Einfluss auf.</span><span class="sxs-lookup"><span data-stu-id="14302-110">Attributes further down the tree (to the right of the chart) have less of an effect.</span></span>  
  
 <span data-ttu-id="14302-111">In diesem Beispiel ist das Alter der wichtigste Einzelfaktor für die Vorhersage eines Fahrradkaufs.</span><span class="sxs-lookup"><span data-stu-id="14302-111">In this example, age is the single most important factor in predicting bike buying.</span></span> <span data-ttu-id="14302-112">Im Modell werden Kunden nach dem Alter gruppiert, und anschließend wird das nächstwichtigere Attribut für jede Altersgruppe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="14302-112">The model groups customers by age, and then shows the next more important attribute for each age group.</span></span> <span data-ttu-id="14302-113">In der Kundengruppe von 34 bis 40 Jahren ist die Anzahl der Kraftfahrzeuge im Besitz des Kunden nach dem Alter der bedeutendste Vorhersagefaktor.</span><span class="sxs-lookup"><span data-stu-id="14302-113">For example, in the group of customers aged 34 to 40, the number of cars owned is the strongest predictor after age.</span></span>  
  
#### <a name="to-explore-the-model-in-the-decision-tree-tab"></a><span data-ttu-id="14302-114">So untersuchen Sie das Modell auf der Registerkarte "Entscheidungsstruktur"</span><span class="sxs-lookup"><span data-stu-id="14302-114">To explore the model in the Decision Tree tab</span></span>  
  
1.  <span data-ttu-id="14302-115">Wählen Sie im **Data Mining-Designer**die Registerkarte **Mining Modell-Viewer** aus.</span><span class="sxs-lookup"><span data-stu-id="14302-115">Select the **Mining Model Viewer** tab in **Data Mining Designer**.</span></span>  
  
     <span data-ttu-id="14302-116">Standardmäßig wird der Designer mit dem ersten Modell geöffnet, das der Struktur hinzugefügt wurde, in diesem Fall `TM_Decision_Tree` .</span><span class="sxs-lookup"><span data-stu-id="14302-116">By default, the designer opens to the first model that was added to the structure -- in this case, `TM_Decision_Tree`.</span></span>  
  
2.  <span data-ttu-id="14302-117">Mithilfe der Lupensymbole können Sie die Größe der Strukturanzeige einstellen.</span><span class="sxs-lookup"><span data-stu-id="14302-117">Use the magnifying glass buttons to adjust the size of the tree display.</span></span>  
  
     <span data-ttu-id="14302-118">Standardmäßig werden im [!INCLUDE[msCoName](../includes/msconame-md.md)] Struktur-Viewer nur die ersten drei Strukturebenen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="14302-118">By default, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Tree Viewer shows only the first three levels of the tree.</span></span> <span data-ttu-id="14302-119">Umfasst die Struktur weniger als drei Ebenen, zeigt der Viewer nur die vorhandenen Ebenen an.</span><span class="sxs-lookup"><span data-stu-id="14302-119">If the tree contains fewer than three levels, the viewer shows only the existing levels.</span></span> <span data-ttu-id="14302-120">Mit dem Schieberegler **Ebene anzeigen** oder der **Standard Erweiterungs** Liste können Sie weitere Ebenen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="14302-120">You can view more levels by using the **Show Level** slider or the **Default Expansion** list.</span></span>  
  
3.  <span data-ttu-id="14302-121">Folie **zeigt die Ebene** auf den vierten Balken an.</span><span class="sxs-lookup"><span data-stu-id="14302-121">Slide **Show Level** to the fourth bar.</span></span>  
  
4.  <span data-ttu-id="14302-122">Ändern Sie den Wert für **Background** in `1` .</span><span class="sxs-lookup"><span data-stu-id="14302-122">Change the **Background** value to `1`.</span></span>  
  
     <span data-ttu-id="14302-123">Durch Ändern der **Hintergrund** Einstellung können Sie schnell die Anzahl der Fälle in jedem Knoten sehen, die den Zielwert `1` für [Bike Buyer] aufweisen.</span><span class="sxs-lookup"><span data-stu-id="14302-123">By changing the **Background** setting, you can quickly see the number of cases in each node that have the target value of `1` for [Bike Buyer].</span></span> <span data-ttu-id="14302-124">In diesem besonderen Szenario stellt jeder Fall einen Kunden dar.</span><span class="sxs-lookup"><span data-stu-id="14302-124">Remember that in this particular scenario, each case represents a customer.</span></span> <span data-ttu-id="14302-125">Der Wert `1` gibt an, dass der Kunde zuvor ein Fahrrad gekauft hat. der Wert **0** gibt an, dass der Kunde kein Fahrrad gekauft hat.</span><span class="sxs-lookup"><span data-stu-id="14302-125">The value `1` indicates that the customer previously purchased a bike; the value **0** indicates that the customer has not purchased a bike.</span></span> <span data-ttu-id="14302-126">Je dunkler die Schattierung des Knotens ist, desto höher ist der Prozentsatz der Fälle im Knoten mit dem Zielwert.</span><span class="sxs-lookup"><span data-stu-id="14302-126">The darker the shading of the node, the higher the percentage of cases in the node that have the target value.</span></span>  
  
5.  <span data-ttu-id="14302-127">Platzieren Sie den Cursor über dem Knoten mit der Bezeichnung **alle**.</span><span class="sxs-lookup"><span data-stu-id="14302-127">Place your cursor over the node labeled **All**.</span></span> <span data-ttu-id="14302-128">Daraufhin wird eine QuickInfo mit folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="14302-128">An tooltip will display the following information:</span></span>  
  
    -   <span data-ttu-id="14302-129">Gesamtzahl der Fälle</span><span class="sxs-lookup"><span data-stu-id="14302-129">Total number of cases</span></span>  
  
    -   <span data-ttu-id="14302-130">Anzahl der Kunden, die keinen Kauf getätigt haben</span><span class="sxs-lookup"><span data-stu-id="14302-130">Number of non bike buyer cases</span></span>  
  
    -   <span data-ttu-id="14302-131">Anzahl der Kunden, die einen Kauf getätigt haben</span><span class="sxs-lookup"><span data-stu-id="14302-131">Number of bike buyer cases</span></span>  
  
    -   <span data-ttu-id="14302-132">Anzahl der Fälle mit unvollständigen Werten für [Bike Buyer]</span><span class="sxs-lookup"><span data-stu-id="14302-132">Number of cases with missing values for [Bike Buyer]</span></span>  
  
     <span data-ttu-id="14302-133">Sie können den Cursor auch auf einem beliebigen Knoten in der Struktur platzieren, um die Bedingung anzuzeigen, die erforderlich ist, um den Knoten vom vorhergehenden Knoten aus zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="14302-133">Alternately, place your cursor over any node in the tree to see the condition that is required to reach that node from the node that comes before it.</span></span> <span data-ttu-id="14302-134">Sie können dieselben Informationen auch in der **Mining Legende**anzeigen.</span><span class="sxs-lookup"><span data-stu-id="14302-134">You can also view this same information in the **Mining Legend**.</span></span>  
  
6.  <span data-ttu-id="14302-135">Klicken Sie auf den Knoten für **Age >= 34 und < 41**.</span><span class="sxs-lookup"><span data-stu-id="14302-135">Click on the node for **Age >=34 and < 41**.</span></span> <span data-ttu-id="14302-136">Das Histogramm wird als schmaler horizontaler Balken über dem Knoten angezeigt. Es stellt die Verteilung der Kunden in der entsprechenden Altersgruppe dar, die bereits ein Fahrrad gekauft (rosa) bzw. noch kein Fahrrad gekauft haben (blau).</span><span class="sxs-lookup"><span data-stu-id="14302-136">The histogram is displayed as a thin horizontal bar across the node and represents the distribution of customers in this age range who previously did (pink) and did not (blue) purchase a bike.</span></span> <span data-ttu-id="14302-137">Dem Viewer ist zu entnehmen, dass Kunden im Alter von 34 bis 40 Jahren, die ein oder kein Auto besitzen, wahrscheinlich ein Fahrrad kaufen.</span><span class="sxs-lookup"><span data-stu-id="14302-137">The Viewer shows us that customers between the ages of 34 and 40 with one or no cars are likely to purchase a bike.</span></span> <span data-ttu-id="14302-138">Bei einer genaueren Betrachtung stellt sich heraus, dass die Wahrscheinlichkeit, ein Fahrrad zu kaufen, im Alter von 38 bis 40 Jahren am größten ist.</span><span class="sxs-lookup"><span data-stu-id="14302-138">Taking it one step further, we find that the likelihood to purchase a bike increases if the customer is actually age 38 to 40.</span></span>  
  
 <span data-ttu-id="14302-139">Beim Erstellen von Struktur und Modell haben Sie Drillthrough aktiviert. Sie können daher detaillierte Informationen über die Modellfälle und die Miningstruktur einschließlich Spalten abrufen, die nicht Teil des Miningmodells sind (beispielsweise emailAddress, FirstName).</span><span class="sxs-lookup"><span data-stu-id="14302-139">Because you enabled drillthrough when you created the structure and model, you can retrieve detailed information from the model cases and mining structure, including those columns that were not included in the mining model (e.g., emailAddress, FirstName).</span></span>  
  
 <span data-ttu-id="14302-140">Weitere Informationen finden Sie unter [Drillthroughabfragen &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="14302-140">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span></span>  
  
#### <a name="to-drill-through-to-case-data"></a><span data-ttu-id="14302-141">So führen Sie einen Drillthrough zu Falldaten aus</span><span class="sxs-lookup"><span data-stu-id="14302-141">To drill through to case data</span></span>  
  
1.  <span data-ttu-id="14302-142">Klicken Sie mit der rechten Maustaste auf einen Knoten, und wählen Sie **Drillthrough** und dann **nur Modell Spalten**.</span><span class="sxs-lookup"><span data-stu-id="14302-142">Right-click a node, and select **Drill Through** then **Model Columns Only**.</span></span>  
  
     <span data-ttu-id="14302-143">Die Details für die einzelnen Trainingsfälle werden im Arbeitsblattformat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="14302-143">The details for each training case are displayed in spreadsheet format.</span></span> <span data-ttu-id="14302-144">Sie wurden der vTargetMail-Sicht entnommen, die beim Erstellen der Miningstruktur als Falltabelle ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="14302-144">These details come from the vTargetMail view that you selected as the case table when building the mining structure.</span></span>  
  
2.  <span data-ttu-id="14302-145">Klicken Sie mit der rechten Maustaste auf einen Knoten, und wählen Sie **Drillthrough** und dann **Modell-und Struktur Spalten**</span><span class="sxs-lookup"><span data-stu-id="14302-145">Right-click a node, and select **Drill Through** then **Model and Structure Columns**.</span></span>  
  
     <span data-ttu-id="14302-146">Das gleiche Arbeitsblatt wird angezeigt, und die Strukturspalten wurden an das Ende angefügt.</span><span class="sxs-lookup"><span data-stu-id="14302-146">The same spreadsheet displays with the structure columns appended to the end.</span></span>  
  
  
###  <a name="dependency-network-tab"></a><a name="Dependency_Network_Tab"></a><span data-ttu-id="14302-147">Registerkarte Abhängigkeits Netzwerk</span><span class="sxs-lookup"><span data-stu-id="14302-147">Dependency Network Tab</span></span>  
 <span data-ttu-id="14302-148">Auf der Registerkarte **Abhängigkeits Netzwerk** werden die Beziehungen zwischen den Attributen angezeigt, die zur Vorhersagefähigkeit des Mining Modells beitragen.</span><span class="sxs-lookup"><span data-stu-id="14302-148">The **Dependency Network** tab displays the relationships between the attributes that contribute to the predictive ability of the mining model.</span></span> <span data-ttu-id="14302-149">Der Abhängigkeitsnetzwerk-Viewer bestätigt die Erkenntnisse, dass Alter und Region wichtige Faktoren für den Kauf eines Fahrrads darstellen.</span><span class="sxs-lookup"><span data-stu-id="14302-149">The Dependency Network viewer reinforces our findings that Age and Region are important factors in predicting bike buying.</span></span>  
  
##### <a name="to-explore-the-model-in-the-dependency-network-tab"></a><span data-ttu-id="14302-150">So untersuchen Sie das Modell auf der Registerkarte "Abhängigkeitsnetzwerk"</span><span class="sxs-lookup"><span data-stu-id="14302-150">To explore the model in the Dependency Network tab</span></span>  
  
1.  <span data-ttu-id="14302-151">Klicken Sie `Bike Buyer` auf den Knoten, um seine Abhängigkeiten zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="14302-151">Click the `Bike Buyer` node to identify its dependencies.</span></span>  
  
     <span data-ttu-id="14302-152">Der zentrale Knoten des Abhängigkeitsnetzwerks `Bike Buyer` steht für das vorhersagbare Attribut im Miningmodell.</span><span class="sxs-lookup"><span data-stu-id="14302-152">The center node for the dependency network, `Bike Buyer`, represents the predictable attribute in the mining model.</span></span> <span data-ttu-id="14302-153">Im Diagramm werden alle verbundenen Knoten hervorgehoben, die das vorhersagbare Attribut beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="14302-153">The graph highlights any connected nodes that have an effect on the predictable attribute.</span></span>  
  
2.  <span data-ttu-id="14302-154">Passen Sie den Schieberegler **alle Links** an, um das einflussreichste Attribut zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="14302-154">Adjust the **All Links** slider to identify the most influential attribute.</span></span>  
  
     <span data-ttu-id="14302-155">Wenn Sie den Schieberegler nach unten ziehen, werden Attribute, die nur eine schwache Auswirkung auf die Spalte [Bike Buyer] haben, aus dem Diagramm entfernt.</span><span class="sxs-lookup"><span data-stu-id="14302-155">As you drag down the slider, attributes that have only a weak effect on the [Bike Buyer] column are removed from the graph.</span></span> <span data-ttu-id="14302-156">Mithilfe des Reglers können Sie feststellen, dass Alter und Region die wichtigste Faktoren bei der Vorhersage sind, ob ein Kunde ein Fahrrad kauft.</span><span class="sxs-lookup"><span data-stu-id="14302-156">By adjusting the slider, you can discover that Age and Region are the greatest factors in predicting whether someone is a bike buyer.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="14302-157">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="14302-157">Related Tasks</span></span>  
 <span data-ttu-id="14302-158">In den folgenden Themen wird erläutert, wie Daten unter Verwendung anderer Modellarten analysiert werden können.</span><span class="sxs-lookup"><span data-stu-id="14302-158">See these topics to explore the data using the other kinds of models.</span></span>  
  
-   [<span data-ttu-id="14302-159">Erkunden des Clustering-Modells &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="14302-159">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="14302-160">Untersuchen des Naive Bayes-Modells &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="14302-160">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="14302-161">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="14302-161">Next Task in Lesson</span></span>  
 [<span data-ttu-id="14302-162">Erkunden des Clustering-Modells &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="14302-162">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="14302-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="14302-163">See Also</span></span>  
 <span data-ttu-id="14302-164">[Tasks und Anleitungen des Mining Modell-Viewers](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="14302-164">[Mining Model Viewer Tasks and How-tos](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="14302-165">[Registerkarte "Entscheidungsstruktur" &#40;Mining Modell-Viewer&#41;](../../2014/analysis-services/decision-tree-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="14302-165">[Decision Tree Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/decision-tree-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="14302-166">[Registerkarte Abhängigkeits Netzwerk &#40;Mining Modell-Viewer&#41;](../../2014/analysis-services/dependency-network-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="14302-166">[Dependency Network Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/dependency-network-tab-mining-model-viewer.md) </span></span>  
 [<span data-ttu-id="14302-167">Durchsuchen eines Modells mit dem Microsoft Struktur-Viewer</span><span class="sxs-lookup"><span data-stu-id="14302-167">Browse a Model Using the Microsoft Tree Viewer</span></span>](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-tree-viewer.md)  
  
  
