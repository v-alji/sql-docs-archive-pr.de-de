---
title: Durchsuchen eines Clustering-Modells | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- mining models, viewing
- clustering [data mining]
- mining model, clustering
ms.assetid: 7f3f0949-d791-403a-88e2-54cb1a803dae
author: minewiskan
ms.author: owend
ms.openlocfilehash: f1d508603acd29fde981bddc5642b54ca9413f5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610333"
---
# <a name="browsing-a-clustering-model"></a><span data-ttu-id="54359-102">Durchsuchen eines Clustermodells</span><span class="sxs-lookup"><span data-stu-id="54359-102">Browsing a Clustering Model</span></span>
  <span data-ttu-id="54359-103">Wenn Sie ein Clustering-Modell mithilfe von **Durchsuchen**öffnen, wird das Modell in einem interaktiven Viewer angezeigt, der dem Clustering-Viewer in ähnelt [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="54359-103">When you open a clustering model using **Browse**, the model is displayed in an interactive viewer, similar to the clustering viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="54359-104">Die Viewer unterstützt Sie dabei, die erstellten Cluster zu untersuchen und die Clustermerkmale zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="54359-104">The viewer helps you explore the clusters that were created, and understand cluster characteristics.</span></span> <span data-ttu-id="54359-105">Darüber hinaus können Sie einzelne Segmente mit anderen Segmenten oder mit der Grundgesamtheit vergleichen und die Unterschiede untersuchen.</span><span class="sxs-lookup"><span data-stu-id="54359-105">You can also compare and contrast individual segments with other segments or with the population.</span></span>  
  
##  <a name="explore-the-model"></a><a name="BKMK_Tabs"></a><span data-ttu-id="54359-106">Untersuchen des Modells</span><span class="sxs-lookup"><span data-stu-id="54359-106">Explore the Model</span></span>  
 <span data-ttu-id="54359-107">Das Fenster **Durchsuchen** enthält die folgenden Tools, die Ihnen helfen, Ihr Clustering-Modell zu verstehen und die Attribute der zugrunde liegenden Datengruppen zu untersuchen:</span><span class="sxs-lookup"><span data-stu-id="54359-107">The **Browse** window includes the following tools to help you understand your clustering model and explore the attributes of the underlying data groups:</span></span>  
  
-   [<span data-ttu-id="54359-108">Clusterdiagramm</span><span class="sxs-lookup"><span data-stu-id="54359-108">Cluster Diagram</span></span>](#BKMK_ClusterDiagram)  
  
-   [<span data-ttu-id="54359-109">Clusterprofile</span><span class="sxs-lookup"><span data-stu-id="54359-109">Cluster Profiles</span></span>](#BKMK_ClusterProfiles)  
  
-   [<span data-ttu-id="54359-110">Cluster Merkmale</span><span class="sxs-lookup"><span data-stu-id="54359-110">Cluster Characteristics</span></span>](#BKMK_ClusterCharacteristics)  
  
-   [<span data-ttu-id="54359-111">Clusterunterscheidung</span><span class="sxs-lookup"><span data-stu-id="54359-111">Cluster Discrimination</span></span>](#BKMK_ClusterDiscrimination)  
  
 <span data-ttu-id="54359-112">Um mit einem Clustering-Modell zu experimentieren, können Sie die Beispiel Daten auf der Registerkarte Training der Beispiel Daten-Arbeitsmappe verwenden und ein Clustering-Modell mithilfe des [Cluster-Assistenten &#40;Data Mining-Add-Ins für Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) und alle Standardeinstellungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="54359-112">To experiment with a clustering model, you can use the sample data on the Training tab of the sample data workbook, and build a clustering model using [Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) and all the defaults.</span></span>  
  
###  <a name="cluster-diagram"></a><a name="BKMK_ClusterDiagram"></a><span data-ttu-id="54359-113">Cluster Diagramm</span><span class="sxs-lookup"><span data-stu-id="54359-113">Cluster Diagram</span></span>  
 <span data-ttu-id="54359-114">Auf der Registerkarte **Cluster Diagramm** werden alle Cluster in einem Mining Modell angezeigt.</span><span class="sxs-lookup"><span data-stu-id="54359-114">The **Cluster Diagram** tab displays all the clusters that are in a mining model.</span></span> <span data-ttu-id="54359-115">Hier sehen Sie, wie viele verschiedene Gruppierungen im Dataset enthalten sind und wie nah oder weit sie voneinander entfernt liegen.</span><span class="sxs-lookup"><span data-stu-id="54359-115">Here you can see how many different groupings were found in your data set, and how near or far they are from each other.</span></span>  
  
##### <a name="explore-the-cluster-diagram"></a><span data-ttu-id="54359-116">Untersuchen des Clusterdiagramms</span><span class="sxs-lookup"><span data-stu-id="54359-116">Explore the cluster diagram</span></span>  
  
1.  <span data-ttu-id="54359-117">Klicken Sie auf Cluster 1 im Diagramm.</span><span class="sxs-lookup"><span data-stu-id="54359-117">Click Cluster 1 in the diagram.</span></span>  
  
     <span data-ttu-id="54359-118">Sie können beobachten, wie sich die grauen Linien, die alle Cluster verbinden, ändern. Die Linien, die zum ausgewählten Cluster führen, sind in hellem Blau hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="54359-118">Note how the gray lines connecting all clusters change so that lines leading to the selected cluster are highlighted in bright blue.</span></span>  
  
     <span data-ttu-id="54359-119">![Clusterdiagramm-Intro](media/dm13-cluster-diagram-intro.gif "Clusterdiagramm-Intro")</span><span class="sxs-lookup"><span data-stu-id="54359-119">![cluster diagram intro](media/dm13-cluster-diagram-intro.gif "cluster diagram intro")</span></span>  
  
     <span data-ttu-id="54359-120">Anhand der Stärke der Linie, die einen Cluster mit einem anderen verbindet, können Sie die Ähnlichkeit der Cluster ableiten.</span><span class="sxs-lookup"><span data-stu-id="54359-120">The intensity of the line that connects one cluster to another represents the strength of the similarity of the clusters.</span></span> <span data-ttu-id="54359-121">Ist die Schattierung schwach oder ist keine Schattierung vorhanden, sind sich die Cluster kaum ähnlich.</span><span class="sxs-lookup"><span data-stu-id="54359-121">If the shading is light or nonexistent, the clusters are not very similar.</span></span> <span data-ttu-id="54359-122">Je stärker die Linie ist, desto größer ist die Ähnlichkeit zwischen den beiden Clustern.</span><span class="sxs-lookup"><span data-stu-id="54359-122">As the line becomes darker, it indicates that the similarity between the two clusters is stronger.</span></span>  
  
2.  <span data-ttu-id="54359-123">Klicken und ziehen Sie den Schieberegler zur linken Seite des Clusterdiagramms, um die Anzahl der Linien anzupassen, die im Viewer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="54359-123">Click and drag the slider to the left of the cluster diagram, to adjust how many lines the viewer shows.</span></span>  
  
     <span data-ttu-id="54359-124">Wenn Sie den Schieberegler nach unten ziehen, werden nur die stärksten Verbindungslinien zwischen Clustern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="54359-124">When you drag the slider down, only the strongest links between clusters are shown.</span></span> <span data-ttu-id="54359-125">So können Sie verwandte Gruppen leichter fokussieren.</span><span class="sxs-lookup"><span data-stu-id="54359-125">This helps you focus on related groups.</span></span>  
  
3.  <span data-ttu-id="54359-126">Beachten Sie das Steuerelement **Schattierungs Variable** in der oberen rechten Ecke des Fensters **Cluster Diagramm** .</span><span class="sxs-lookup"><span data-stu-id="54359-126">Notice the **Shading Variable** control in the upper right corner of the **Cluster Diagram** window.</span></span>  
  
     <span data-ttu-id="54359-127">Standardmäßig ist es auf **Population**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="54359-127">By default, it is set to **Population**.</span></span> <span data-ttu-id="54359-128">Das bedeutet, dass die Cluster mit der dunkleren Schattierung größere Unterstützung erhalten.</span><span class="sxs-lookup"><span data-stu-id="54359-128">What this means is that the darker clusters have greater support.</span></span>  
  
4.  <span data-ttu-id="54359-129">Platzieren Sie den Cursor auf einem beliebigen Cluster.</span><span class="sxs-lookup"><span data-stu-id="54359-129">Pause over any cluster with the cursor.</span></span>  
  
     <span data-ttu-id="54359-130">Eine QuickInfo wird angezeigt, in der die Auffüllung des Clusters enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="54359-130">A ToolTip is displayed that contains the population of that cluster.</span></span>  
  
5.  <span data-ttu-id="54359-131">Klicken Sie nun auf die Dropdown Liste **Schattierungs Variable** , und wählen Sie die **Alter** -Variable aus.</span><span class="sxs-lookup"><span data-stu-id="54359-131">Now, click the **Shading Variable** dropdown list and choose the **Age** variable.</span></span> <span data-ttu-id="54359-132">Wie Sie dies tun, wird eine Liste von Werten im Textfeld **Status** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="54359-132">As you do so, a list of values appears in the **State** text box.</span></span>  
  
     <span data-ttu-id="54359-133">Die als Eingabe für dieses Modell verwendete Spalte Alter enthält fortlaufende numerische Werte, zu Clusteringzwecken werden die Zahlen vom Algorithmus jedoch immer diskretisiert.</span><span class="sxs-lookup"><span data-stu-id="54359-133">The Age column used as input to this model contains continuous numeric values, but for the purpose of clustering, the algorithm always discretizes numbers.</span></span> <span data-ttu-id="54359-134">Hier können Sie die vom Algorithmus erstellten Behälter oder Gruppen anzeigen, z. b. "sehr niedrig ( \<=27)" and "Very High (> = 63)".</span><span class="sxs-lookup"><span data-stu-id="54359-134">Here you can see the bins, or groups that the algorithm created, such as "Very Low (\<=27)" and "Very High (>=63)".</span></span>  
  
6.  <span data-ttu-id="54359-135">Wählen Sie in der Dropdown Liste **Status** die Option **sehr hoch** aus, und sehen Sie sich an, wie sich das Diagramm</span><span class="sxs-lookup"><span data-stu-id="54359-135">From the **State** dropdown lists, select **Very High** and see how the diagram changes.</span></span>  
  
     <span data-ttu-id="54359-136">Indem Sie die Schattierungsvariable ändern, erkennen Sie auf einen Blick, welche Cluster mehr und welche nur wenige Kunden dieser Altersgruppe enthalten.</span><span class="sxs-lookup"><span data-stu-id="54359-136">By changing the shading variable, you can see at a glance which clusters contain more of this targeted age group, and which clusters contain very few customers in this age group.</span></span>  
  
     <span data-ttu-id="54359-137">![Ändern des Clusterdiagramms zur Anzeige des Alters](media/dm13-cluster-diagramshadebyage.gif "Ändern des Clusterdiagramms zur Anzeige des Alters")</span><span class="sxs-lookup"><span data-stu-id="54359-137">![Modify the cluster diagram to show age](media/dm13-cluster-diagramshadebyage.gif "Modify the cluster diagram to show age")</span></span>  
  
     <span data-ttu-id="54359-138">Je stärker die Schattierung, desto größer ist der Anteil der Zielattribut- und Werteverteilung des Clusters.</span><span class="sxs-lookup"><span data-stu-id="54359-138">The darker the shading, the larger the proportion of the target attribute and value distribution that cluster.</span></span>  
  
7.  <span data-ttu-id="54359-139">Suchen Sie den Cluster, der als dunkel schattiert ist, wenn die **Schattierungs Variable** auf Age >65 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="54359-139">Locate the cluster that is shaded darkest when the **Shading Variable** is set to Age >65.</span></span>  
  
     <span data-ttu-id="54359-140">Zeigen Sie mit der Maus auf den Cluster.</span><span class="sxs-lookup"><span data-stu-id="54359-140">Hover the mouse over the cluster.</span></span>  
  
     <span data-ttu-id="54359-141">Der in der QuickInfo angezeigte Wert zeigt jetzt die Grundgesamtheit der Kunden in diesem Cluster an, die älter als 65 sind.</span><span class="sxs-lookup"><span data-stu-id="54359-141">The value displayed in the ToolTip now shows you the population of customers in this cluster who are over 65.</span></span>  
  
8.  <span data-ttu-id="54359-142">Klicken Sie mit der rechten Maustaste auf den Cluster und wählen Sie **Cluster umbenennen**</span><span class="sxs-lookup"><span data-stu-id="54359-142">Right-click the cluster and select **Rename Cluster**.</span></span> <span data-ttu-id="54359-143">Geben Sie einen neuen beschreibenden Namen ein, z. b. **über 65**.</span><span class="sxs-lookup"><span data-stu-id="54359-143">Type a new name that is descriptive, such as **Over 65**.</span></span> <span data-ttu-id="54359-144">Der neue Name wird mit dem Modell auf dem Server gespeichert und kann zum Identifizieren des Clusters in den anderen Clusteringsichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="54359-144">The new name is saved with the model to the server and can be used for identifying the cluster in the other clustering views.</span></span>  
  
 [<span data-ttu-id="54359-145">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="54359-145">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="cluster-profiles"></a><a name="BKMK_ClusterProfiles"></a><span data-ttu-id="54359-146">Cluster profile</span><span class="sxs-lookup"><span data-stu-id="54359-146">Cluster Profiles</span></span>  
 <span data-ttu-id="54359-147">Auf der Registerkarte **Cluster profile** können Sie die Zusammensetzung aller Cluster auf einen Blick vergleichen.</span><span class="sxs-lookup"><span data-stu-id="54359-147">The **Cluster Profiles** tab lets you compare the makeup of all clusters at a glance.</span></span> <span data-ttu-id="54359-148">Dies ist ein guter Ausgangspunkt, um sich mit dem Modell vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="54359-148">This is a good place to start when you are getting familiar with the model.</span></span> <span data-ttu-id="54359-149">Diese Ansicht ist auch später hilfreich, wenn Sie einen bestimmten Cluster untersuchen und zu dem Schluss kommen, dass Sie verwandte Cluster suchen müssen.</span><span class="sxs-lookup"><span data-stu-id="54359-149">This view is also useful later on, if you have been exploring a particular cluster and decide you need to find related ones.</span></span>  
  
 <span data-ttu-id="54359-150">**Cluster profile** bieten Ihnen außerdem einen guten Überblick darüber, wie sich die Cluster voneinander unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="54359-150">**Cluster Profiles** also gives you a good overview of how the clusters are different from each other.</span></span> <span data-ttu-id="54359-151">Daher kann es praktisch sein, jedem Cluster mithilfe dieser Ansicht einen aussagekräftigen Namen zu geben.</span><span class="sxs-lookup"><span data-stu-id="54359-151">Therefore, you might find it convenient to use this view to give each cluster a descriptive name.</span></span>  
  
##### <a name="explore-the-cluster-profiles"></a><span data-ttu-id="54359-152">Untersuchen der Clusterprofile</span><span class="sxs-lookup"><span data-stu-id="54359-152">Explore the cluster profiles</span></span>  
  
1.  <span data-ttu-id="54359-153">Klicken Sie in der Spalte **Zustände** auf die Zelle für die Berufe, um die Liste aller Werte für den Beruf anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="54359-153">Click the cell for Occupations, in the **States** column, to see the list of all values for Occupation.</span></span>  
  
2.  <span data-ttu-id="54359-154">Platzieren Sie jetzt den Cursor in den Clusterprofilen auf Beruf.</span><span class="sxs-lookup"><span data-stu-id="54359-154">Now move the cursor over Occupation in the cluster profiles.</span></span>  
  
     <span data-ttu-id="54359-155">Die QuickInfo zeigt die Verteilung von Berufen in diesem Cluster an.</span><span class="sxs-lookup"><span data-stu-id="54359-155">The ToolTip shows the distribution of occupations in that cluster.</span></span>  
  
     <span data-ttu-id="54359-156">![Anzeigen ausführlicher Werte in QuickInfos oder in der Legende](media/dm13-cluster-profile-age-tooltip.gif "Anzeigen ausführlicher Werte in QuickInfos oder in der Legende")</span><span class="sxs-lookup"><span data-stu-id="54359-156">![View detailed values in Tooltips or in Legend](media/dm13-cluster-profile-age-tooltip.gif "View detailed values in Tooltips or in Legend")</span></span>  
  
     <span data-ttu-id="54359-157">Beachten Sie, dass in einigen Clustern (z. b. in der Grafik) die Liste der Berufe nicht fertiggestellt ist und einige Berufe durch die Bezeichnung **ersetzt werden.**</span><span class="sxs-lookup"><span data-stu-id="54359-157">Notice that, in some clusters (such as the one in the graphic), the list of occupations is not complete, and some occupations are replaced with the label, **Other**.</span></span>  
  
     <span data-ttu-id="54359-158">Dieses Verhalten ist programmbedingt, da es schwierig sein kann, den Unterschied zwischen vielen kleinen Balken im Histogramm auszumachen.</span><span class="sxs-lookup"><span data-stu-id="54359-158">This is by design, because it can be hard to tell the difference between many small bars in a histogram.</span></span> <span data-ttu-id="54359-159">Standardmäßig werden nur die wichtigsten Balken beibehalten, und die restlichen Balken werden in einem grauen **anderen** Bucket zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="54359-159">By default only the bars of highest importance are retained, and the remaining bars are grouped together into a gray **Other** bucket.</span></span>  
  
     <span data-ttu-id="54359-160">Um die Anzahl der in einem Histogramm sichtbaren Balken zu ändern, verwenden Sie die Option **Histogrammbalken**.</span><span class="sxs-lookup"><span data-stu-id="54359-160">To change the number of bars that are visible in any histogram, use the option **Histogram bars**.</span></span>  
  
3.  <span data-ttu-id="54359-161">Beachten Sie, dass die Spalte " **Age** " von anderen abweicht.</span><span class="sxs-lookup"><span data-stu-id="54359-161">Note that the **Age** column looks different from the others.</span></span> <span data-ttu-id="54359-162">Klicken Sie auf die Raute im Diagramm, durch das das Alter dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="54359-162">Click the diamond in the chart used to represent Age.</span></span>  
  
     <span data-ttu-id="54359-163">Die Spalte Alter enthielt ursprünglich nur fortlaufende Zahlen.</span><span class="sxs-lookup"><span data-stu-id="54359-163">The column Age originally contained only continuous numbers.</span></span> <span data-ttu-id="54359-164">Der Clusteringalgorithmus erfordert diskrete Werte. Folglich wurden die numerischen Werte in der Spalte Alter – basierend auf der Werteverteilung – unter einer eingeschränkten Anzahl von Altersgruppen gruppiert.</span><span class="sxs-lookup"><span data-stu-id="54359-164">The clustering algorithm requires discrete values, so it grouped the numeric values in the Age column into a limited number of age groups, based on the distribution of values.</span></span>  
  
4.  <span data-ttu-id="54359-165">Klicken Sie auf eines der Rautendiagramme in einem Clusterprofil.</span><span class="sxs-lookup"><span data-stu-id="54359-165">Click one of the diamond charts in a cluster profile.</span></span>  
  
     <span data-ttu-id="54359-166">Diese Rautendiagramme werden nur angezeigt, wenn die Quelldaten fortlaufende numerische Werte enthalten.</span><span class="sxs-lookup"><span data-stu-id="54359-166">These diamond charts are displayed only when the source data uses continuous numeric values.</span></span> <span data-ttu-id="54359-167">Die Rautendiagramme stellen einige aussagekräftige Statistiken bereit, einschließlich der mittleren und Standardabweichung dieses Werts in den einzelnen Clustern:</span><span class="sxs-lookup"><span data-stu-id="54359-167">The diamond charts provide some useful descriptive statistics, including the mean and standard deviation for that value in each cluster:</span></span>  
  
    -   <span data-ttu-id="54359-168">Die Linie im Rautendiagramm stellt den Wertebereich für das Attribut dar.</span><span class="sxs-lookup"><span data-stu-id="54359-168">The line in the diamond chart represents the range of values for the attribute.</span></span> <span data-ttu-id="54359-169">Die Werte werden auch in der Spalte **Zustände** auf der linken Seite des **Profil** Diagramms angezeigt.</span><span class="sxs-lookup"><span data-stu-id="54359-169">The values are also shown in the **States** column at the left of the **Profiles** chart.</span></span>  
  
    -   <span data-ttu-id="54359-170">Der Mittelpunkt der Raute orientiert sich am Mittelwert des Knotens.</span><span class="sxs-lookup"><span data-stu-id="54359-170">The center of the diamond is positioned at the mean for the node.</span></span>  
  
    -   <span data-ttu-id="54359-171">Die Breite der Raute gibt die Varianz des Attributs in diesem Knoten an.</span><span class="sxs-lookup"><span data-stu-id="54359-171">The width of the diamond represents the variance of the attribute at that node.</span></span> <span data-ttu-id="54359-172">Eine schlankere Raute sagt also aus, dass mithilfe des Knotens eine genauere Vorhersage getroffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="54359-172">Therefore, a thinner diamond indicates that the node can create a more accurate prediction.</span></span>  
  
5.  <span data-ttu-id="54359-173">Um mehr Platz im Diagramm zu schaffen, klicken Sie mit der rechten Maustaste auf einen Cluster, den Sie nicht sofort anzeigen müssen, und wählen Sie **Spalte ausblenden**aus.</span><span class="sxs-lookup"><span data-stu-id="54359-173">To make more room in the graph, right-click a cluster you don't need to view right away, and select **Hide Column**.</span></span> <span data-ttu-id="54359-174">Dadurch wird die Spalte nicht aus dem Modell gelöscht, sondern nur vorübergehend reduziert.</span><span class="sxs-lookup"><span data-stu-id="54359-174">This doesn't delete it from the model, just collapses the column temporarily.</span></span>  
  
     <span data-ttu-id="54359-175">Zum Anzeigen von Clustern, die Sie ausgeblendet haben, können Sie auf den Spalten Rand klicken und ihn ziehen oder den Cluster Namen aus der Liste, **Weitere Cluster**auswählen.</span><span class="sxs-lookup"><span data-stu-id="54359-175">To view clusters that you've hidden, you can click and drag the column edge, or select the cluster name from the list, **More clusters**.</span></span>  
  
6.  <span data-ttu-id="54359-176">Führen Sie in der Attributliste einen Bildlauf bis Bike Buyer durch, und suchen Sie dann den Cluster, der den höchsten Prozentsatz an Ja-Werten aufweist.</span><span class="sxs-lookup"><span data-stu-id="54359-176">Scroll down the attribute list till you find Bike Buyer, and then find the cluster that has the highest percentage of Yes values.</span></span>  
  
     <span data-ttu-id="54359-177">Klicken Sie mit der rechten Maustaste auf die Spaltenüberschrift des Clusters, den Sie umbenennen möchten, und wählen Sie **Cluster umbenennen** **aus.**</span><span class="sxs-lookup"><span data-stu-id="54359-177">Right-click the column heading for the cluster that you want to rename, select **Rename cluster**, and type **Bike Buyers**.</span></span>  
  
     <span data-ttu-id="54359-178">Der neue Clustername wird in allen Ansichten und auf dem Server beibehalten, bis Sie das Modell erneut verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="54359-178">The new cluster name is persisted in all views, and on the server, until you reprocess the model.</span></span>  
  
     <span data-ttu-id="54359-179">![Umbenennen von Clusters zur einfacheren Verwendung des Diagramms](media/dm13-cluster-rename.gif "Umbenennen von Clusters zur einfacheren Verwendung des Diagramms")</span><span class="sxs-lookup"><span data-stu-id="54359-179">![Rename clusters to make chart easier to use](media/dm13-cluster-rename.gif "Rename clusters to make chart easier to use")</span></span>  
  
 <span data-ttu-id="54359-180">**Tipps**</span><span class="sxs-lookup"><span data-stu-id="54359-180">**Tips**</span></span>  
  
-   <span data-ttu-id="54359-181">Klicken Sie auf eine Spaltenüberschrift, um die Attribute nach der Reihenfolge der Wichtigkeit für diesen Cluster zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="54359-181">Click a column heading to sort the attributes in order of importance for that cluster.</span></span>  
  
-   <span data-ttu-id="54359-182">Ziehen Sie die Spalten, um sie im Viewer neu anzuordnen.</span><span class="sxs-lookup"><span data-stu-id="54359-182">Drag columns to reorder them in the viewer.</span></span>  
  
-   <span data-ttu-id="54359-183">Klicken Sie im Diagramm Profile auf eine beliebige Zelle, um ausführliche Statistiken in der **Mining Legende**anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="54359-183">Click any cell in the profiles chart to view detailed statistics in the **Mining Legend**.</span></span>  
  
-   <span data-ttu-id="54359-184">Klicken Sie mit der rechten Maustaste auf eine beliebige Zelle, und wählen Sie **Drillthrough Modell Spalten** aus, um die zugrunde liegenden Daten in einem neuen Arbeitsblatt in Excel auszugeben</span><span class="sxs-lookup"><span data-stu-id="54359-184">Right-click any cell and select **Drillthrough model columns** to output the underlying data to a new worksheet in Excel.</span></span>  
  
-   <span data-ttu-id="54359-185">Klicken Sie mit der rechten Maustaste auf die Spaltenüberschrift des Clusters, und wählen Sie **Drillthrough für Strukturdaten** aus, um ausführliche Informationen über die Cluster Mitglieder zu erhalten, die nicht im Modell enthalten waren</span><span class="sxs-lookup"><span data-stu-id="54359-185">Right-click the cluster's column heading and select **Drillthrough to structure data** to get detailed information about the cluster members that wasn't included in the model.</span></span>  
  
     <span data-ttu-id="54359-186">Wenn Sie z. b. die Profilerstellung für Kunden durchlaufen, können Sie die Kontaktinformationen in den zugrunde liegenden Daten (der Mining Struktur) belassen, aber nicht in das Modell einschließen, da dies für die Analyse nicht nützlich ist.</span><span class="sxs-lookup"><span data-stu-id="54359-186">For example, if you are profiling customers, you might leave the contact information in the underlying data (the mining structure) but not include it in the model, because it's not useful for analysis.</span></span> <span data-ttu-id="54359-187">Nachdem die Kunden den Clustern zugewiesen wurden, können Sie die detaillierten Daten jedoch mithilfe eines Drillthrough-Vorgangs anzeigen.</span><span class="sxs-lookup"><span data-stu-id="54359-187">However, after customers have been assigned to clusters, you can view the detailed data by using drillthrough.</span></span>  
  
 [<span data-ttu-id="54359-188">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="54359-188">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="cluster-characteristics"></a><a name="BKMK_ClusterCharacteristics"></a> <span data-ttu-id="54359-189">Clustermerkmale</span><span class="sxs-lookup"><span data-stu-id="54359-189">Cluster Characteristics</span></span>  
 <span data-ttu-id="54359-190">In der Ansicht Clustermerkmale können Sie einen einzelnen Cluster gründlich untersuchen, um herauszufinden, durch welche Attribute diese Datengruppe am stärksten charakterisiert wird.</span><span class="sxs-lookup"><span data-stu-id="54359-190">The Cluster Characteristics view lets you really explore a single cluster, to find which attributes most strongly characterize this group of data.</span></span>  
  
##### <a name="explore-the-cluster-characteristics"></a><span data-ttu-id="54359-191">Untersuchen der Clustermerkmale</span><span class="sxs-lookup"><span data-stu-id="54359-191">Explore the cluster characteristics</span></span>  
  
1.  <span data-ttu-id="54359-192">Wählen Sie den Cluster **über 65** aus der Liste **Cluster** aus.</span><span class="sxs-lookup"><span data-stu-id="54359-192">Select the **Over 65** cluster from the **Cluster** list.</span></span>  
  
     <span data-ttu-id="54359-193">Nachdem Sie einen Cluster ausgewählt haben, können Sie die Merkmale dieses Clusters eingehend untersuchen.</span><span class="sxs-lookup"><span data-stu-id="54359-193">After you select a cluster, you can see in detail the characteristics that make up that specific cluster.</span></span>  
  
     <span data-ttu-id="54359-194">Die im Cluster enthaltenen Attribute werden in den **Variablen** -Spalten und der Status der aufgelisteten Attribute in der **Werte** -Spalte aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="54359-194">The attributes that the cluster contains are listed in the **Variables** columns, and the state of the listed attribute is listed in the **Values** column.</span></span>  
  
     <span data-ttu-id="54359-195">Attribut Zustände werden in der Reihenfolge ihrer Wichtigkeit aufgeführt, und zwar zusammen mit ihrer Wahrscheinlichkeit in diesem Cluster, dargestellt als farbiger Balken in der **Wahrscheinlichkeits** Spalte.</span><span class="sxs-lookup"><span data-stu-id="54359-195">Attribute states are listed in order of importance, accompanied by their probability in this cluster, represented as a colored bar in the **Probability** column.</span></span>  
  
     <span data-ttu-id="54359-196">![Merkmale eines Clusteringmodells](media/dm13-cluster-characteristics.gif "Merkmale eines Clusteringmodells")</span><span class="sxs-lookup"><span data-stu-id="54359-196">![Characteristics of a clustering model](media/dm13-cluster-characteristics.gif "Characteristics of a clustering model")</span></span>  
  
2.  <span data-ttu-id="54359-197">Klicken Sie auf die Spalte **Variablen** , um nach Attribut zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="54359-197">Click the **Variables** column to sort by attribute.</span></span>  
  
     <span data-ttu-id="54359-198">Indem Sie die Sortierungsvariable ändern, können Sie leichter erkennen, wie Werte für Variablen, z. B. Einkommen oder Autobesitz, in der Gruppe verteilt sind.</span><span class="sxs-lookup"><span data-stu-id="54359-198">By changing the sort variable, you can more easily see how values for variables such as income or car ownership are distributed in the group.</span></span>  
  
3.  <span data-ttu-id="54359-199">Klicken Sie **auf nach Excel kopieren**.</span><span class="sxs-lookup"><span data-stu-id="54359-199">Click **Copy to Excel**.</span></span>  
  
     <span data-ttu-id="54359-200">Der Arbeitsmappe wird ein neues Arbeitsblatt hinzugefügt, das die Merkmale des ausgewählten Clusters enthält.</span><span class="sxs-lookup"><span data-stu-id="54359-200">A new worksheet is added to your workbook that contains the characteristics of the selected cluster.</span></span>  
  
4.  <span data-ttu-id="54359-201">Wählen Sie nun einen anderen Cluster aus der Liste **Bike Buyers**aus.</span><span class="sxs-lookup"><span data-stu-id="54359-201">Now choose a different cluster from the list, **Bike Buyers**.</span></span>  
  
5.  <span data-ttu-id="54359-202">Klicken Sie **auf nach Excel kopieren**.</span><span class="sxs-lookup"><span data-stu-id="54359-202">Click **Copy to Excel**.</span></span>  
  
     <span data-ttu-id="54359-203">Das neue Clustermerkmaldiagramm wird auf einem eigenen Arbeitsblatt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="54359-203">Note that the new cluster characteristics chart is added on its own worksheet.</span></span> <span data-ttu-id="54359-204">Sie können Sie auf das gleiche Arbeitsblatt wie das andere Profil verschieben, um Sie leichter vergleichen zu können, was Sie im nächsten Schritt tun werden.</span><span class="sxs-lookup"><span data-stu-id="54359-204">You can move it onto the same worksheet as the other profile to make it easier to compare them, which you'll do in the next step.</span></span>  
  
 <span data-ttu-id="54359-205">**Tipps**</span><span class="sxs-lookup"><span data-stu-id="54359-205">**Tips**</span></span>  
  
-   <span data-ttu-id="54359-206">Beachten Sie, dass das primäre Merkmal des Kunden im over 65-Cluster darin besteht, dass Sie Ihr Produkt nicht kaufen!</span><span class="sxs-lookup"><span data-stu-id="54359-206">Note that the primary characteristic of the customer in the Over 65 cluster is that they don't buy your product!</span></span> <span data-ttu-id="54359-207">Wenn Sie wissen möchten, warum das so ist, können Sie die Cluster durchsuchen und Gruppen vergleichen. Oder Sie erstellen ein verwandtes Modell mithilfe eines Algorithmus, der sich für die Untersuchung von Ursachen und Ergebnissen eignet, z. B. ein Entscheidungsstrukturmodell oder ein Naïve Bayes-Modell.</span><span class="sxs-lookup"><span data-stu-id="54359-207">If you want to know why this is so, you can browse clusters and compare groups, or you might create a related model using an algorithm that is good at exploring causes and outcomes, such as a decision tree model or a Naïve Bayes model.</span></span>  
  
-   <span data-ttu-id="54359-208">Wenn Sie eine vollständige Liste der Attribute und Wahrscheinlichkeitswerte für diesen Cluster (oder alle Cluster) abrufen möchten, können Sie eine Abfrage erstellen.</span><span class="sxs-lookup"><span data-stu-id="54359-208">If you want to get a complete list of attributes and probabilities for this cluster (or all clusters) you can create a query.</span></span> <span data-ttu-id="54359-209">Beispiele für Abfragen für Clustering-Modelle finden Sie unter [Beispiele für Clustering-Modell Abfragen](data-mining/clustering-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="54359-209">For examples of queries on clustering models, see [Clustering Model Query Examples](data-mining/clustering-model-query-examples.md).</span></span>  
  
 [<span data-ttu-id="54359-210">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="54359-210">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="cluster-discrimination"></a><a name="BKMK_ClusterDiscrimination"></a><span data-ttu-id="54359-211">Cluster Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="54359-211">Cluster Discrimination</span></span>  
 <span data-ttu-id="54359-212">Sie können die Registerkarte **Cluster Unterscheidung** verwenden, um Attribute zwischen zwei Clustern oder zwischen einem Cluster und allen anderen Fällen im DataSet zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="54359-212">You use the **Cluster Discrimination** tab to compare attributes between two clusters, or between a cluster and all the other cases in the data set.</span></span>  
  
 <span data-ttu-id="54359-213">Um die Features dieses Viewers hervorzuheben, vergleichen wir ihn mit den parallelen Tabellen in Excel, die Sie basierend auf der Ansicht **Cluster Merkmale** erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="54359-213">To highlight the features of this viewer, we'll compare it to the side-by-side tables in Excel that you created based on the **Cluster Characteristics** view.</span></span>  
  
##### <a name="explore-cluster-discrimination"></a><span data-ttu-id="54359-214">Untersuchen der Clusterunterscheidung</span><span class="sxs-lookup"><span data-stu-id="54359-214">Explore cluster discrimination</span></span>  
  
1.  <span data-ttu-id="54359-215">Verwenden Sie die Listen **Cluster 1** und **Cluster 2** , um die zu vergleichenden Cluster auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="54359-215">Use the **Cluster 1** and **Cluster 2** lists to select the clusters to compare.</span></span>  
  
    -   <span data-ttu-id="54359-216">Wählen Sie für Cluster 1 Über 65 aus.</span><span class="sxs-lookup"><span data-stu-id="54359-216">For Cluster 1, select Over 65.</span></span>  
  
    -   <span data-ttu-id="54359-217">Wählen Sie für Cluster 2 Bike Buyers aus.</span><span class="sxs-lookup"><span data-stu-id="54359-217">For Cluster 2, select Bike Buyers.</span></span>  
  
     <span data-ttu-id="54359-218">Der Vergleich sollte ähnlich wie in der folgenden Grafik aussehen.</span><span class="sxs-lookup"><span data-stu-id="54359-218">The comparison should look similar to the following graphic.</span></span>  
  
     <span data-ttu-id="54359-219">![Vergleichen von Clustern in einem Modell](media/dm13-cluster-compareclusters.gif "Vergleichen von Clustern in einem Modell")</span><span class="sxs-lookup"><span data-stu-id="54359-219">![comparing clusters in a model](media/dm13-cluster-compareclusters.gif "comparing clusters in a model")</span></span>  
  
     <span data-ttu-id="54359-220">Beachten Sie, dass der **Cluster** Unterscheidungs-Viewer im Bereich komplexe Abfragen an den Data Mining-Server sendet, um die Attribute zu extrahieren, die bei der Unterscheidung zwischen den beiden Gruppen am wichtigsten sind, sodass zwei Kunden Sätze einfacher verglichen werden können.</span><span class="sxs-lookup"><span data-stu-id="54359-220">Note that, under the covers, the **Cluster Discrimination** viewer sends complex queries to the data mining server, to extract the attributes that are most important in distinguishing between the two groups, making it easier to compare two sets of customers.</span></span>  
  
2.  <span data-ttu-id="54359-221">Klicken Sie auf eine der Spalten **begünstigt...** .</span><span class="sxs-lookup"><span data-stu-id="54359-221">Click either of the **Favors...** columns.</span></span>  
  
     <span data-ttu-id="54359-222">Der Balken rechts neben der Attribut- und Werteliste zeigt, welchen Funktionen oder Werte das wichtigste Merkmal des ausgewählten Clusters sind.</span><span class="sxs-lookup"><span data-stu-id="54359-222">The bar to the right of the attribute and value list shows which features or values are most important as a characteristic of the selected cluster.</span></span>  
  
3.  <span data-ttu-id="54359-223">Vergleichen Sie die Listen jetzt in Excel.</span><span class="sxs-lookup"><span data-stu-id="54359-223">Now compare the lists in Excel.</span></span>  
  
     <span data-ttu-id="54359-224">![Abhängigkeitsnetzwerkdiagramm für ein Zuordnungsmodell](media/dm13-comparing-profiles-in-excel.gif "Abhängigkeitsnetzwerkdiagramm für ein Zuordnungsmodell")</span><span class="sxs-lookup"><span data-stu-id="54359-224">![Dependency network graph for an association model](media/dm13-comparing-profiles-in-excel.gif "Dependency network graph for an association model")</span></span>  
  
     <span data-ttu-id="54359-225">Da die zugrunde liegenden Statistik, die zur Darstellung der Grafik im Viewer verwendet wurde, in Excel in Tabellenform gespeichert wird, können Sie die tatsächlichen Wahrscheinlichkeitswerte filtern, sortieren und anzeigen.</span><span class="sxs-lookup"><span data-stu-id="54359-225">Because the underlying statistics that were used to build the image in the viewer are saved to Excel as tables, you can filter and sort, and view the actual probability values.</span></span>  
  
     <span data-ttu-id="54359-226">Zusätzlich zur Verwendung von Excel wird empfohlen, den Cluster-Viewer für Visio auszuprobieren, mit dem Sie nicht nur Datenpunkte anzeigen, sondern die Grafik auch umfassend ändern und verbessern können.</span><span class="sxs-lookup"><span data-stu-id="54359-226">In addition to using Excel, we recommend that you try the cluster viewer for Visio, which also allows you to not just view data points but also extensively modify and enhance the graph.</span></span> <span data-ttu-id="54359-227">Weitere Informationen finden Sie unter Exemplarische Vorgehensweise für das [Cluster Diagramm &#40;Data Mining-Add-ins&#41;](cluster-diagram-walkthrough-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="54359-227">For more information, see [Cluster Diagram Walkthrough &#40;Data Mining Add-ins&#41;](cluster-diagram-walkthrough-data-mining-add-ins.md).</span></span>  
  
 <span data-ttu-id="54359-228">**Tipps**</span><span class="sxs-lookup"><span data-stu-id="54359-228">**Tips**</span></span>  
  
 <span data-ttu-id="54359-229">Nachdem Sie einige Einblicke in Kundengruppen erhalten haben, verwenden Sie das [Was-wäre-wenn-Szenario &#40;Tabellenanalyse Tools für Excel&#41;](what-if-scenario-table-analysis-tools-for-excel.md) oder das [zielsuchszenario &#40;Tabellenanalyse Tools für Excel-&#41;](goal-seek-scenario-table-analysis-tools-for-excel.md) Tools, um Faktoren im Modell zu untersuchen, die möglicherweise geändert werden, um das Ergebnis zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="54359-229">After getting some insights into groups of customers, try using the [What-If Scenario &#40;Table Analysis Tools for Excel&#41;](what-if-scenario-table-analysis-tools-for-excel.md) or [Goal Seek Scenario &#40;Table Analysis Tools for Excel&#41;](goal-seek-scenario-table-analysis-tools-for-excel.md) tools, to explore factors in the model that might be changed to affect the outcome.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54359-230">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="54359-230">See Also</span></span>  
 <span data-ttu-id="54359-231">[Durchsuchen von Modellen in Excel &#40;SQL Server Data Mining-Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="54359-231">[Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="54359-232">Cluster-Assistent &#40;Data Mining-Add-Ins für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="54359-232">Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](cluster-wizard-data-mining-add-ins-for-excel.md)  
  
  
