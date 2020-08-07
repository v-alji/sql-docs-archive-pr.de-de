---
title: Untersuchen des Naive Bayes-Modells (Lernprogramm zu Data Mining-Grundlagen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b06708d5-4477-4a51-bf8d-0b1e3c1f9ebb
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 7a26fa972e1ed50e2f4107026210a5935fcb86d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719111"
---
# <a name="exploring-the-naive-bayes-model-basic-data-mining-tutorial"></a><span data-ttu-id="4a2b1-102">Untersuchen des Naive Bayes-Modells (Lernprogramm zu Data Mining-Grundlagen)</span><span class="sxs-lookup"><span data-stu-id="4a2b1-102">Exploring the Naive Bayes Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="4a2b1-103">Der [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes-Algorithmus bietet mehrere Methoden zum Anzeigen der Interaktion zwischen dem Fahrradkauf und den Eingabe Attributen.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes algorithm provides several methods for displaying the interaction between bike buying and the input attributes.</span></span>  
  
 <span data-ttu-id="4a2b1-104">Der [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes-Viewer bietet die folgenden Registerkarten zur Untersuchung von Naive Bayes-Mining Modellen:</span><span class="sxs-lookup"><span data-stu-id="4a2b1-104">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes Viewer provides the following tabs for use in exploring Naive Bayes mining models:</span></span>  
  
 
  
##  <a name="dependency-network"></a><a name="DependencyNetwork"></a><span data-ttu-id="4a2b1-105">Abhängigkeits Netzwerk</span><span class="sxs-lookup"><span data-stu-id="4a2b1-105">Dependency Network</span></span>  
 <span data-ttu-id="4a2b1-106">Die Registerkarte **Abhängigkeits Netzwerk** funktioniert auf die gleiche Weise wie die Registerkarte **Abhängigkeits Netzwerk** für den Struktur- [!INCLUDE[msCoName](../includes/msconame-md.md)] Viewer.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-106">The **Dependency Network** tab works in the same way as the **Dependency Network** tab for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Tree Viewer.</span></span> <span data-ttu-id="4a2b1-107">Jeder Knoten im Viewer steht für ein Attribut, und die Linien zwischen den Knoten stellen Beziehungen dar.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-107">Each node in the viewer represents an attribute, and the lines between nodes represent relationships.</span></span> <span data-ttu-id="4a2b1-108">In dem Viewer können Sie alle Attribute sehen, die sich auf den Status des vorhersagbaren Attributs Bike Buyer auswirken.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-108">In the viewer, you can see all the attributes that affect the state of the predictable attribute, Bike Buyer.</span></span>  
  
#### <a name="to-explore-the-model-in-the-dependency-network-tab"></a><span data-ttu-id="4a2b1-109">So untersuchen Sie das Modell auf der Registerkarte "Abhängigkeitsnetzwerk"</span><span class="sxs-lookup"><span data-stu-id="4a2b1-109">To explore the model in the Dependency Network tab</span></span>  
  
1.  <span data-ttu-id="4a2b1-110">Verwenden Sie die Liste **Mining Modell** oben auf der Registerkarte **Mining Modell-Viewer** , um zum `TM_NaiveBayes` Modell zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-110">Use the **Mining Model** list at the top of the **Mining Model Viewer** tab to switch to the `TM_NaiveBayes` model.</span></span>  
  
2.  <span data-ttu-id="4a2b1-111">Verwenden Sie die Liste **Viewer** , um zum **Microsoft Naive Bayes-Viewer**zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-111">Use the **Viewer** list to switch to **Microsoft Naive Bayes Viewer**.</span></span>  
  
3.  <span data-ttu-id="4a2b1-112">Klicken Sie `Bike Buyer` auf den Knoten, um seine Abhängigkeiten zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-112">Click the `Bike Buyer` node to identify its dependencies.</span></span>  
  
     <span data-ttu-id="4a2b1-113">Die rosa Schattierung gibt an, dass alle Attribute Auswirkungen auf den Fahrradkauf haben.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-113">The pink shading indicates that all of the attributes have an effect on bike buying.</span></span>  
  
4.  <span data-ttu-id="4a2b1-114">Stellen Sie den Schieberegler ein, um die einflussreichsten Attribute zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-114">Adjust the slider to identify the most influential attribute.</span></span>  
  
     <span data-ttu-id="4a2b1-115">Wenn Sie den Schieberegler nach unten ziehen, werden nur noch diejenigen Attribute angezeigt, welche die stärksten Auswirkungen auf die [Bike Buyer]-Spalte haben.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-115">As you lower the slider, only the attributes that have the greatest effect on the [Bike Buyer] column remain.</span></span> <span data-ttu-id="4a2b1-116">Durch Anpassen des Schiebereglers können Sie herausfinden, dass die einflussreichsten Attribute unter anderem folgende sind: Anzahl der Autos im Besitz, Arbeitsweg und Anzahl der Kinder insgesamt.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-116">By adjusting the slider, you can discover that a few of the most influential attributes are: number of cars owned, commute distance, and total number of children.</span></span>  
 
  
##  <a name="attribute-profiles"></a><a name="AttributeProfiles"></a> <span data-ttu-id="4a2b1-117">Attributprofile</span><span class="sxs-lookup"><span data-stu-id="4a2b1-117">Attribute Profiles</span></span>  
 <span data-ttu-id="4a2b1-118">Auf der Registerkarte **Attribut profile** wird beschrieben, wie sich unterschiedliche Zustände der Eingabe Attribute auf das Ergebnis des vorhersagbaren Attributs auswirken.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-118">The **Attribute Profiles** tab describes how different states of the input attributes affect the outcome of the predictable attribute.</span></span>  
  
#### <a name="to-explore-the-model-in-the-attribute-profiles-tab"></a><span data-ttu-id="4a2b1-119">So untersuchen Sie das Modell auf der Registerkarte "Attributprofile"</span><span class="sxs-lookup"><span data-stu-id="4a2b1-119">To explore the model in the Attribute Profiles tab</span></span>  
  
1.  <span data-ttu-id="4a2b1-120">Vergewissern Sie sich, dass im Feld **vorhersagbare** Felder `Bike Buyer` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-120">In the **Predictable** box, verify that `Bike Buyer` is selected.</span></span>  
  
2.  <span data-ttu-id="4a2b1-121">Wenn die **Mining Legende** die Anzeige der **Attribut profile**blockiert, verschieben Sie Sie nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-121">If the **Mining Legend** is blocking display of the **Attribute profiles**, move it out of the way.</span></span>  
  
3.  <span data-ttu-id="4a2b1-122">Wählen Sie im Feld **Histogrammbalken** den Text **5**aus.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-122">In the **Histogram** bars box, select **5**.</span></span>  
  
     <span data-ttu-id="4a2b1-123">In unserem Modell stellt 5 die maximale Anzahl der Status einer Variablen dar.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-123">In our model, 5 is the maximum number of states for any one variable.</span></span>  
  
     <span data-ttu-id="4a2b1-124">Die Attribute, die sich auf den Status des vorhersagbaren Attributs auswirken, werden zusammen mit den Werten für jeden Status der Eingabeattribute und deren Verteilungen in jedem Status des vorhersagbaren Attributs aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-124">The attributes that affect the state of this predictable attribute are listed together with the values of each state of the input attributes and their distributions in each state of the predictable attribute.</span></span>  
  
4.  <span data-ttu-id="4a2b1-125">Suchen Sie in der Spalte **Attribute** nach **Zahlen Autos im Besitz**von.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-125">In the **Attributes** column, find **Number Cars Owned**.</span></span>  <span data-ttu-id="4a2b1-126">Beachten Sie die Unterschiede in den Histogrammen für Kunden, die ein Fahrrad gekauft haben (Spalte 1) und Kunden, die keinen Kauf getätigt haben (Spalte 0).</span><span class="sxs-lookup"><span data-stu-id="4a2b1-126">Notice the differences in the histograms for bike buyers (column labeled 1) and non-buyers (column labeled 0).</span></span> <span data-ttu-id="4a2b1-127">Personen, die kein oder ein Auto besitzen, kaufen mit größerer Wahrscheinlichkeit ein Fahrrad.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-127">A person with zero or one car is much more likely to buy a bike.</span></span>  
  
5.  <span data-ttu-id="4a2b1-128">Doppelklicken Sie in der Spalte Bike Buyer (Spalte mit der Bezeichnung 1) auf **die Zelle in der Zelle** .</span><span class="sxs-lookup"><span data-stu-id="4a2b1-128">Double-click the **Number Cars Owned** cell in the bike buyer (column labeled 1) column.</span></span>  
  
     <span data-ttu-id="4a2b1-129">Die **Mining Legende** zeigt eine ausführlichere Ansicht an.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-129">The **Mining Legend** displays a more detailed view.</span></span>  
  
  
##  <a name="attribute-characteristics"></a><a name="AttributeCharacteristics"></a><span data-ttu-id="4a2b1-130">Attribut Merkmale</span><span class="sxs-lookup"><span data-stu-id="4a2b1-130">Attribute Characteristics</span></span>  
 <span data-ttu-id="4a2b1-131">Mit der Registerkarte **Attribut Merkmale** können Sie ein Attribut und einen Wert auswählen, um zu sehen, wie häufig Werte für andere Attribute in den ausgewählten Wert Fällen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-131">With the **Attribute Characteristics** tab, you can select an attribute and value to see how frequently values for other attributes appear in the selected value cases.</span></span>  
  
#### <a name="to-explore-the-model-in-the-attribute-characteristics-tab"></a><span data-ttu-id="4a2b1-132">So untersuchen Sie das Modell auf der Registerkarte "Attributmerkmale"</span><span class="sxs-lookup"><span data-stu-id="4a2b1-132">To explore the model in the Attribute Characteristics tab</span></span>  
  
1.  <span data-ttu-id="4a2b1-133">Vergewissern Sie sich, dass in der Liste **Attribut** die Option `Bike Buyer` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-133">In the **Attribute** list, verify that `Bike Buyer` is selected.</span></span>  
  
2.  <span data-ttu-id="4a2b1-134">Legen Sie den **Wert** auf **1**fest.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-134">Set the **Value** to **1**.</span></span>  
  
     <span data-ttu-id="4a2b1-135">Im Viewer sehen Sie, dass Kunden, die keine Kinder zu Hause und einen kurzen Arbeitsweg haben und in Nordamerika leben mit größerer Wahrscheinlichkeit ein Fahrrad kaufen.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-135">In the viewer, you will see that customers who have no children at home, short commutes, and live in the North America region are more likely to buy a bike.</span></span>  
  
  
##  <a name="attribute-discrimination"></a><a name="AttributeDiscrimination"></a><span data-ttu-id="4a2b1-136">Attribut Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="4a2b1-136">Attribute Discrimination</span></span>  
 <span data-ttu-id="4a2b1-137">Mithilfe der Registerkarte **Attribut Unterscheidung** können Sie die Beziehung zwischen zwei diskreten Werten von Bike Einkauf und anderen Attributwerten untersuchen.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-137">With the **Attribute Discrimination** tab, you can investigate the relationship between two discrete values of bike buying and other attribute values.</span></span> <span data-ttu-id="4a2b1-138">Da das `TM_NaiveBayes` Modell nur zwei Zustände aufweist: 1 und 0, müssen Sie keine Änderungen am Viewer vornehmen.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-138">Because the `TM_NaiveBayes` model has only two states, 1 and 0, you do not have to make any changes to the viewer.</span></span>  
  
 <span data-ttu-id="4a2b1-139">Im Viewer können Sie sehen, dass Personen, die keine Autos besitzen, tendenziell Fahrräder kaufen. Personen, die zwei Autos besitzen, kaufen tendenziell keine Fahrräder.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-139">In the viewer, you can see that people who do not own cars tend to buy bicycles, and people who own two cars tend not to buy bicycles.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="4a2b1-140">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="4a2b1-140">Related Tasks</span></span>  
 <span data-ttu-id="4a2b1-141">Die folgenden Themen enthalten Beschreibungen zu den anderen Miningmodellen.</span><span class="sxs-lookup"><span data-stu-id="4a2b1-141">See the following topics to explore the other mining models.</span></span>  
  
-   [<span data-ttu-id="4a2b1-142">Untersuchen des Entscheidungsstruktur Modells &#40;grundlegenden Data Mining-Lernprogramm&#41;</span><span class="sxs-lookup"><span data-stu-id="4a2b1-142">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="4a2b1-143">Erkunden des Clustering-Modells &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="4a2b1-143">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="4a2b1-144">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="4a2b1-144">Next Lesson</span></span>  
 [<span data-ttu-id="4a2b1-145">Lektion 5: Testen von Modellen &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="4a2b1-145">Lesson 5: Testing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-testing-models-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="4a2b1-146">Vorherige Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="4a2b1-146">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="4a2b1-147">Erkunden des Clustering-Modells &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="4a2b1-147">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="4a2b1-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4a2b1-148">See Also</span></span>  
 <span data-ttu-id="4a2b1-149">[Durchsuchen eines Modells mit dem Microsoft Naive Bayes-Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="4a2b1-149">[Browse a Model Using the Microsoft Naive Bayes Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md) </span></span>  
 <span data-ttu-id="4a2b1-150">[Registerkarte Attribut Unterscheidung &#40;Mining Modell-Viewer&#41;](../../2014/analysis-services/attribute-discrimination-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="4a2b1-150">[Attribute Discrimination Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/attribute-discrimination-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="4a2b1-151">[Registerkarte "Attribut profile" &#40;Mining Modell-Viewer&#41;](../../2014/analysis-services/attribute-profiles-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="4a2b1-151">[Attribute Profiles Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/attribute-profiles-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="4a2b1-152">[Registerkarte "Attribut Merkmale" &#40;Mining Modell-Viewer&#41;](../../2014/analysis-services/attribute-characteristics-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="4a2b1-152">[Attribute Characteristics Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/attribute-characteristics-tab-mining-model-viewer.md) </span></span>  
 [<span data-ttu-id="4a2b1-153">Registerkarte Abhängigkeits Netzwerk &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="4a2b1-153">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](../../2014/analysis-services/dependency-network-tab-mining-model-viewer.md)  
  
  
