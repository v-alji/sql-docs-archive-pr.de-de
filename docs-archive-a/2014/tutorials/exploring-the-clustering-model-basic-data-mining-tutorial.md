---
title: Untersuchen des Clustering-Modells (Lernprogramm zu Data Mining-Grundlagen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ce8aa034-161b-473f-baec-9c29e0a8e5f5
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: cca9d395fece59f607c8faf209128b9d32663a06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726401"
---
# <a name="exploring-the-clustering-model-basic-data-mining-tutorial"></a><span data-ttu-id="ce4cc-102">Untersuchen des Clustering-Modells (Lernprogramm zu Data Mining-Grundlagen)</span><span class="sxs-lookup"><span data-stu-id="ce4cc-102">Exploring the Clustering Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="ce4cc-103">Der [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering-Algorithmus gruppiert Fälle in Clustern, die ähnliche Merkmale aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm groups cases into clusters that contain similar characteristics.</span></span> <span data-ttu-id="ce4cc-104">Diese Gruppierungen eignen sich zum Durchsuchen von Daten, Identifizieren von Datenanomalien und Erstellen von Vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-104">These groupings are useful for exploring data, identifying anomalies in the data, and creating predictions.</span></span>  
  
 <span data-ttu-id="ce4cc-105">Der [!INCLUDE[msCoName](../includes/msconame-md.md)] Cluster-Viewer bietet die folgenden Registerkarten zum Durchsuchen von Clusteringminingmodellen:</span><span class="sxs-lookup"><span data-stu-id="ce4cc-105">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Cluster Viewer provides the following tabs for use in exploring clustering mining models:</span></span>  
  

  
##  <a name="cluster-diagram-tab"></a><a name="ClusterDiagramTab"></a><span data-ttu-id="ce4cc-106">Registerkarte Cluster Diagramm</span><span class="sxs-lookup"><span data-stu-id="ce4cc-106">Cluster Diagram Tab</span></span>  
 <span data-ttu-id="ce4cc-107">Auf der Registerkarte Clusterdiagramm werden alle Cluster in einem Miningmodell angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-107">The Cluster Diagram tab displays all the clusters that are in a mining model.</span></span> <span data-ttu-id="ce4cc-108">Die Linien zwischen den Clustern geben die jeweilige "Nähe" an. Ihre Schattierung hängt davon ab, wie groß die Ähnlichkeit zwischen den Clustern ist.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-108">The lines between the clusters represent "closeness" and are shaded based on how similar the clusters are.</span></span> <span data-ttu-id="ce4cc-109">Die tatsächliche Farbe der einzelnen Cluster gibt die Häufigkeit der Variablen und den Status im Cluster an.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-109">The actual color of each cluster represents the frequency of the variable and the state in the cluster.</span></span>  
  
#### <a name="to-explore-the-model-in-the-cluster-diagram-tab"></a><span data-ttu-id="ce4cc-110">So untersuchen Sie das Modell auf der Registerkarte "Clusterdiagramm"</span><span class="sxs-lookup"><span data-stu-id="ce4cc-110">To explore the model in the Cluster Diagram tab</span></span>  
  
1.  <span data-ttu-id="ce4cc-111">Verwenden Sie die Liste **Mining Modell** oben auf der Registerkarte **Mining Modell-Viewer** , um zum `TM_Clustering` Modell zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-111">Use the **Mining Model** list at the top of the **Mining Model Viewer** tab to switch to the `TM_Clustering` model.</span></span>  
  
2.  <span data-ttu-id="ce4cc-112">Wählen Sie in der Liste **Viewer** den Bereich **Microsoft Cluster-Viewer**aus.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-112">In the **Viewer** list, select **Microsoft Cluster Viewer**.</span></span>  
  
3.  <span data-ttu-id="ce4cc-113">Wählen Sie im Feld **Schattierungs Variable** die Option **Bike Buyer**aus.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-113">In the **Shading Variable** box, select **Bike Buyer**.</span></span>  
  
     <span data-ttu-id="ce4cc-114">Die Standard Variable ist Auffüllung. Sie können **diese jedoch in**jedes beliebige Attribut des Modells ändern, um zu ermitteln, welche Cluster Member mit den gewünschten Attributen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-114">The default variable is **Population**, but you can change this to any attribute in the model, to discover which clusters contain members that have the attributes you want.</span></span>  
  
4.  <span data-ttu-id="ce4cc-115">Wählen Sie im Feld **Status** die Option **1** aus, um die Fälle zu untersuchen, in denen ein Fahrrad gekauft wurde</span><span class="sxs-lookup"><span data-stu-id="ce4cc-115">Select **1** in the **State** box to explore those cases where a bike was purchased.</span></span>  
  
     <span data-ttu-id="ce4cc-116">Die **Dichte** Legende beschreibt die Dichte des Attribut Zustands Paars, das in der Schattierungs Variablen und dem Status ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-116">The **Density** legend describes the density of the attribute state pair selected in the Shading Variable and the State.</span></span> <span data-ttu-id="ce4cc-117">In diesem Beispiel gibt es Aufschluss darüber, dass der Cluster mit der dunkelsten Schattierung über den höchsten Prozentsatz der Fahrrad Käufer verfügt.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-117">In this example it tells us that the clusterwith the darkest shading has the highest percentage of bike buyers.</span></span>  
  
5.  <span data-ttu-id="ce4cc-118">Zeigen Sie mit der Maus auf den Cluster mit der dunkelsten Schattierung.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-118">Pause your mouse over the cluster with the darkest shading.</span></span>  
  
     <span data-ttu-id="ce4cc-119">Eine QuickInfo zeigt den Prozentsatz von Fällen an, die über das Attribut `Bike Buyer = 1` verfügen.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-119">A tooltip displays the percentage of cases that have the attribute, `Bike Buyer = 1`.</span></span>  
  
6.  <span data-ttu-id="ce4cc-120">Wählen Sie den Cluster mit der höchsten Dichte aus, klicken Sie mit der rechten Maustaste auf den Cluster, wählen Sie **Cluster umbenennen** aus, und geben Sie für spätere Identifizierung **Bike Buyers High**</span><span class="sxs-lookup"><span data-stu-id="ce4cc-120">Select the cluster that has the highest density, right-click the cluster, select **Rename Cluster** and type **Bike Buyers High** for later identification.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="ce4cc-121">Suchen Sie den Cluster, der die hellste Schattierung (und die niedrigste Dichte) aufweist.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-121">Find the cluster that has the lightest shading (and the lowest density).</span></span> <span data-ttu-id="ce4cc-122">Klicken Sie mit der rechten Maustaste auf den Cluster, und wählen Sie **Cluster umbenennen** **aus.**</span><span class="sxs-lookup"><span data-stu-id="ce4cc-122">Right-click the cluster, select **Rename Cluster** and type **Bike Buyers Low**.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="ce4cc-123">Klicken Sie auf den Cluster **Fahrrad Käufer hoch** , und ziehen Sie ihn in einen Bereich des Bereichs, in dem Sie eine klare Ansicht der Verbindungen mit den anderen Clustern erhalten.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-123">Click the **Bike Buyers High** cluster and drag it to an area of the pane that will give you a clear view of its connections to the other clusters.</span></span>  
  
     <span data-ttu-id="ce4cc-124">Wenn Sie einen Cluster auswählen, werden die Linien hervorgehoben, die diesen Cluster mit anderen Clustern verbinden, sodass Sie alle Beziehungen dieses Clusters rasch erkennen können.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-124">When you select a cluster, the lines that connect this cluster to other clusters are highlighted, so that you can easily see all the relationships for this cluster.</span></span> <span data-ttu-id="ce4cc-125">Wenn der Cluster nicht ausgewählt ist, können Sie erkennen, wie stark sich die Beziehungen zwischen allen Clustern im Diagramm befinden.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-125">When the cluster is not selected, you can tell by the darkness of the lines how strong the relationships are amongst all the clusters in the diagram.</span></span> <span data-ttu-id="ce4cc-126">Ist die Schattierung schwach oder ist keine Schattierung vorhanden, sind sich die Cluster kaum ähnlich.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-126">If the shading is light or nonexistent, the clusters are not very similar.</span></span>  
  
9. <span data-ttu-id="ce4cc-127">Mithilfe des Schiebereglers links neben dem Netzwerk können Sie schwächere Links herausfiltern und die Cluster mit den engsten Beziehungen finden.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-127">Use the slider to the left of the network, to filter out the weaker links and find the clusters with the closest relationships.</span></span> <span data-ttu-id="ce4cc-128">Die Marketingabteilung von [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] kann ähnliche Cluster kombinieren, um die beste Methode für das Targeted Mailing zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-128">The [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] marketing department might want to combine similar clusters together when determining the best method for delivering the targeted mailing.</span></span>  
  

  
##  <a name="cluster-profiles-tab"></a><a name="ClusterProfilesTab"></a><span data-ttu-id="ce4cc-129">Registerkarte Cluster profile</span><span class="sxs-lookup"><span data-stu-id="ce4cc-129">Cluster Profiles Tab</span></span>  
 <span data-ttu-id="ce4cc-130">Die Registerkarte **Cluster profile** bietet eine allgemeine Ansicht des `TM_Clustering` Modells.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-130">The **Cluster Profiles** tab provides an overall view of the `TM_Clustering` model.</span></span> <span data-ttu-id="ce4cc-131">Die Registerkarte **Cluster profile** enthält eine Spalte für jeden Cluster im Modell.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-131">The **Cluster Profiles** tab contains a column for each cluster in the model.</span></span> <span data-ttu-id="ce4cc-132">In der ersten Spalte werden die Attribute aufgelistet, die mit mindestens einem Cluster verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-132">The first column lists the attributes that are associated with at least one cluster.</span></span> <span data-ttu-id="ce4cc-133">Der Rest des Viewers umfasst die Verteilung der Status eines Attributs für jeden Cluster.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-133">The rest of the viewer contains the distribution of the states of an attribute for each cluster.</span></span> <span data-ttu-id="ce4cc-134">Die Verteilung einer diskreten Variablen wird als farbiger Balken mit der maximalen Anzahl von Balken in der Liste der **Histogrammbalken** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-134">The distribution of a discrete variable is shown as a colored bar with the maximum number of bars displayed in the **Histogram bars** list.</span></span> <span data-ttu-id="ce4cc-135">Kontinuierliche Attribute werden in einem Rautendiagramm angezeigt, das die mittlere und die Standardabweichung in jedem Cluster angibt.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-135">Continuous attributes are displayed with a diamond chart, which represents the mean and standard deviation in each cluster.</span></span>  
  
#### <a name="to-explore-the-model-in-the-cluster-profiles-tab"></a><span data-ttu-id="ce4cc-136">So untersuchen Sie das Modell auf der Registerkarte "Profile"</span><span class="sxs-lookup"><span data-stu-id="ce4cc-136">To explore the model in the Cluster Profiles tab</span></span>  
  
1.  <span data-ttu-id="ce4cc-137">Legen Sie für **Histogrammbalken** den Wert **5**fest.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-137">Set **Histogram** bars to **5**.</span></span>  
  
     <span data-ttu-id="ce4cc-138">In unserem Modell stellt 5 die maximale Anzahl der Status einer Variablen dar.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-138">In our model, 5 is the maximum number of states for any one variable.</span></span>  
  
2.  <span data-ttu-id="ce4cc-139">Wenn die **Mining Legende** die Anzeige der **Attribut profile**blockiert, verschieben Sie Sie nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-139">If the **Mining Legend** blocks the display of the **Attribute profiles**, move it out of the way.</span></span>  
  
3.  <span data-ttu-id="ce4cc-140">Wählen Sie die Spalte **Bike Buyers High** aus, und ziehen Sie diese rechts neben die Spalte **Population** .</span><span class="sxs-lookup"><span data-stu-id="ce4cc-140">Select the **Bike Buyers High** column and drag it to the right of the **Population** column.</span></span>  
  
4.  <span data-ttu-id="ce4cc-141">Wählen Sie die Spalte **Fahrrad Käufer niedrig** aus, und ziehen Sie diese rechts neben die Spalte **Fahrrad Käufer hoch** .</span><span class="sxs-lookup"><span data-stu-id="ce4cc-141">Select the **Bike Buyers Low** column and drag it to the right of the **Bike Buyers High** column.</span></span>  
  
5.  <span data-ttu-id="ce4cc-142">Klicken Sie auf die Spalte **Fahrrad Käufer hoch** .</span><span class="sxs-lookup"><span data-stu-id="ce4cc-142">Click the **Bike Buyers High** column.</span></span>  
  
     <span data-ttu-id="ce4cc-143">Die Spalte **Variablen** wird in der Reihenfolge ihrer Wichtigkeit für diesen Cluster sortiert.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-143">The **Variables** column is sorted in order of importance for that cluster.</span></span> <span data-ttu-id="ce4cc-144">Führen Sie einen Bildlauf durch die Spalte aus, und überprüfen Sie Merkmale des Clusters Fahrradkäufer hoch.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-144">Scroll through the column and review characteristics of the Bike Buyer High cluster.</span></span> <span data-ttu-id="ce4cc-145">Beispielsweise ist hier die Wahrscheinlichkeit eines kurzen Arbeitswegs höher.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-145">For example, they are more likely to have a short commute.</span></span>  
  
6.  <span data-ttu-id="ce4cc-146">Doppelklicken Sie in der Spalte **Fahrrad Käufer hoch** auf die Zelle **Alter** .</span><span class="sxs-lookup"><span data-stu-id="ce4cc-146">Double-click the **Age** cell in the **Bike Buyers High** column.</span></span>  
  
     <span data-ttu-id="ce4cc-147">Die **Mining Legende** zeigt eine ausführlichere Ansicht an, und Sie können den Altersbereich dieser Kunden sowie das mittlere Alter sehen.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-147">The **Mining Legend** displays a more detailed view and you can see the age range of these customers as well as the mean age.</span></span>  
  
7.  <span data-ttu-id="ce4cc-148">Klicken Sie mit der rechten Maustaste auf die Spalte **Fahrrad Käufer niedrig** , und wählen Sie **Spalte ausblenden**.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-148">Right-click the **Bike Buyers Low** column and select **Hide Column**.</span></span>  
  

  
##  <a name="cluster-characteristics-tab"></a><a name="ClusterCharacteristicsTab"></a><span data-ttu-id="ce4cc-149">Registerkarte Cluster Merkmale</span><span class="sxs-lookup"><span data-stu-id="ce4cc-149">Cluster Characteristics Tab</span></span>  
 <span data-ttu-id="ce4cc-150">Auf der Registerkarte **Cluster Merkmale** können Sie die Merkmale eines Clusters ausführlicher untersuchen.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-150">With the **Cluster Characteristics** tab, you can examine in more detail the characteristics that make up a cluster.</span></span> <span data-ttu-id="ce4cc-151">Anstatt die Merkmale aller Cluster (wie auf der Registerkarte Clusterprofile) zu vergleichen, können Sie auch einen Cluster nach dem anderen betrachten.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-151">Instead of comparing the characteristics of all of the clusters (as in the Cluster Profiles tab), you can explore one cluster at a time.</span></span> <span data-ttu-id="ce4cc-152">Wenn Sie z. b. **Bike Buyers High** aus der Liste **Cluster** auswählen, können Sie die Merkmale der Kunden in diesem Cluster sehen.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-152">For example, if you select **Bike Buyers High** from the **Cluster** list, you can see the characteristics of the customers in this cluster.</span></span> <span data-ttu-id="ce4cc-153">Die Anzeige unterscheidet sich zwar vom Viewer für Clusterprofile, die Ergebnisse sind jedoch gleich.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-153">Though the display is different from the Cluster Profiles viewer, the findings are the same.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ce4cc-154">Wenn Sie keinen Anfangswert für **HoldoutSeed**festlegen, variieren die Ergebnisse jedes Mal, wenn Sie das Modell verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-154">Unless you set an initial value for **holdoutseed**, results will vary each time you process the model.</span></span> <span data-ttu-id="ce4cc-155">Weitere Informationen finden Sie unter [HoldoutSeed-Element](https://docs.microsoft.com/bi-reference/assl/properties/holdoutseed-element)</span><span class="sxs-lookup"><span data-stu-id="ce4cc-155">For more information, see [HoldoutSeed Element](https://docs.microsoft.com/bi-reference/assl/properties/holdoutseed-element)</span></span>  
  

  
##  <a name="cluster-discrimination-tab"></a><a name="ClusterDiscriminationTab"></a><span data-ttu-id="ce4cc-156">Registerkarte Cluster Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="ce4cc-156">Cluster Discrimination Tab</span></span>  
 <span data-ttu-id="ce4cc-157">Mithilfe der Registerkarte **Cluster Unterscheidung** können Sie die Merkmale unterscheiden, die einen Cluster von einem anderen Cluster unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-157">With the **Cluster Discrimination** tab, you can explore the characteristics that distinguish one cluster from another.</span></span> <span data-ttu-id="ce4cc-158">Nachdem Sie zwei Cluster ausgewählt haben, eine aus der Liste **Cluster 1** und eine aus der Liste **Cluster 2** , berechnet der Viewer die Unterschiede zwischen den Clustern und zeigt eine Liste der Attribute an, die die Cluster am meisten unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-158">After you select two clusters, one from the **Cluster 1** list, and one from the **Cluster 2** list, the viewer calculates the differences between the clusters and displays a list of the attributes that distinguish the clusters most.</span></span>  
  
#### <a name="to-explore-the-model-in-the-cluster-discrimination-tab"></a><span data-ttu-id="ce4cc-159">So untersuchen Sie das Modell auf der Registerkarte "Clusterunterscheidung"</span><span class="sxs-lookup"><span data-stu-id="ce4cc-159">To explore the model in the Cluster Discrimination tab</span></span>  
  
1.  <span data-ttu-id="ce4cc-160">Wählen Sie im Feld **Cluster 1** die Option **Bike Buyers High**aus.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-160">In the **Cluster 1** box, select **Bike Buyers High**.</span></span>  
  
2.  <span data-ttu-id="ce4cc-161">Wählen Sie im Feld **Cluster 2** die Option **Fahrrad Käufer niedrig**aus.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-161">In the **Cluster 2** box, select **Bike Buyers Low**.</span></span>  
  
3.  <span data-ttu-id="ce4cc-162">Klicken Sie auf **Variablen** , um alphabetisch zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-162">Click **Variables** to sort alphabetically.</span></span>  
  
     <span data-ttu-id="ce4cc-163">Zu den wesentlichen Unterschieden zwischen den Kunden in den Clustern **Fahrrad Käufer niedrig** und **Fahrrad Käufer hoch** gehören Alter, Autobesitz, Anzahl der untergeordneten Elemente und Region.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-163">Some of the more substantial differences among the customers in the **Bike Buyers Low** and **Bike Buyers High** clusters include age, car ownership, number of children, and region.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="ce4cc-164">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="ce4cc-164">Related Tasks</span></span>  
 <span data-ttu-id="ce4cc-165">Die folgenden Themen enthalten Beschreibungen zu den anderen Miningmodellen.</span><span class="sxs-lookup"><span data-stu-id="ce4cc-165">See the following topics to explore the other mining models.</span></span>  
  
-   [<span data-ttu-id="ce4cc-166">Untersuchen des Entscheidungsstruktur Modells &#40;grundlegenden Data Mining-Lernprogramm&#41;</span><span class="sxs-lookup"><span data-stu-id="ce4cc-166">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="ce4cc-167">Untersuchen des Naive Bayes-Modells &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="ce4cc-167">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ce4cc-168">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="ce4cc-168">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ce4cc-169">Untersuchen des Naive Bayes-Modells &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="ce4cc-169">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="ce4cc-170">Vorherige Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="ce4cc-170">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="ce4cc-171">Untersuchen des Entscheidungsstruktur Modells &#40;grundlegenden Data Mining-Lernprogramm&#41;</span><span class="sxs-lookup"><span data-stu-id="ce4cc-171">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="ce4cc-172">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ce4cc-172">See Also</span></span>  
 <span data-ttu-id="ce4cc-173">[Durchsuchen eines Modells mit dem Microsoft Cluster-Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="ce4cc-173">[Browse a Model Using the Microsoft Cluster Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md) </span></span>  
 <span data-ttu-id="ce4cc-174">[Registerkarte Cluster Unterscheidung &#40;Mining Modell-Viewer&#41;](../../2014/analysis-services/cluster-discrimination-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="ce4cc-174">[Cluster Discrimination Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/cluster-discrimination-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="ce4cc-175">[Registerkarte "Cluster profile" &#40;Mining Modell-Viewer&#41;](../../2014/analysis-services/cluster-profiles-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="ce4cc-175">[Cluster Profiles Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/cluster-profiles-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="ce4cc-176">[Registerkarte Cluster Merkmale &#40;Mining Modell-Viewer&#41;](../../2014/analysis-services/cluster-characteristics-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="ce4cc-176">[Cluster Characteristics Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/cluster-characteristics-tab-mining-model-viewer.md) </span></span>  
 [<span data-ttu-id="ce4cc-177">Registerkarte "Cluster Diagramm" &#40;Mining Modell-Viewer&#41;</span><span class="sxs-lookup"><span data-stu-id="ce4cc-177">Cluster Diagram Tab &#40;Mining Model Viewer&#41;</span></span>](../../2014/analysis-services/cluster-diagram-tab-mining-model-viewer.md)  
  
  
