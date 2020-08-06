---
title: Exemplarische Vorgehensweise zum Cluster Diagramm (Data Mining-Add-Ins) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Visio shapes, cluster
- diagram, cluster
- shapes, data mining
- shapes, cluster
- data mining layout toolbar
ms.assetid: 761bef6a-37d4-4b19-944e-f2aadc75a242
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44ee8cce3cd2498d765c9b69e7f352b49cb0f115
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615688"
---
# <a name="cluster-diagram-walkthrough-data-mining-add-ins"></a><span data-ttu-id="01272-102">Exemplarische Vorgehensweise für das Clusterdiagramm (Data Mining-Add-Ins)</span><span class="sxs-lookup"><span data-stu-id="01272-102">Cluster Diagram Walkthrough (Data Mining Add-ins)</span></span>
  <span data-ttu-id="01272-103">Nachdem Sie ein Clusteringmodell erstellt haben, können Sie es mithilfe der Form **Cluster** in Visio importieren und das Layout anschließend weiter anpassen und verbessern.</span><span class="sxs-lookup"><span data-stu-id="01272-103">After you have created a clustering model, you can import it into Visio using the **Cluster** shape and then continue to customize and enhance the layout.</span></span> <span data-ttu-id="01272-104">Die **Data Mining-Shapes für Visio** enthalten die folgenden benutzerdefinierten Steuerelemente zum Arbeiten mit Data Mining Diagrammen:</span><span class="sxs-lookup"><span data-stu-id="01272-104">The **Data Mining Shapes for Visio** include the following custom controls for working with data mining diagrams:</span></span>  
  
-   <span data-ttu-id="01272-105">Rendern von Steuerelementen für das Clusterdiagramm</span><span class="sxs-lookup"><span data-stu-id="01272-105">Rendering controls for the cluster diagram</span></span>  
  
     <span data-ttu-id="01272-106">Diese Optionen sind Teil des **Cluster-Assistenten** , der gestartet wird, wenn Sie eine Form im Visio-Arbeitsbereich ablegen.</span><span class="sxs-lookup"><span data-stu-id="01272-106">These options are part of the **Cluster Wizard** that is launched when you drop a shape into the Visio workspace.</span></span>  
  
-   <span data-ttu-id="01272-107">Symbolleiste für **Data Mining-Layout**</span><span class="sxs-lookup"><span data-stu-id="01272-107">**Data Mining Layout** toolbar</span></span>  
  
     <span data-ttu-id="01272-108">Diese Optionen werden dem Visio-Arbeitsbereich hinzugefügt, um Ihnen die Interaktion mit dem Data Mining-Shape zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="01272-108">These options are added to the Visio workspace to help you interact with the data mining shape.</span></span> <span data-ttu-id="01272-109">Die Optionen unterscheiden sich je nach Typ des verwendeten Data Mining-Modells.</span><span class="sxs-lookup"><span data-stu-id="01272-109">The options are different depending on which type of data mining model you are using.</span></span>  
  
## <a name="build-a-cluster-diagram"></a><span data-ttu-id="01272-110">Erstellen eines Clusterdiagramms</span><span class="sxs-lookup"><span data-stu-id="01272-110">Build a Cluster Diagram</span></span>  
 <span data-ttu-id="01272-111">Durch diese exemplarische Vorgehensweise wird veranschaulicht, wie Sie ein Clusteringdiagramm in Visio erstellen und anpassen.</span><span class="sxs-lookup"><span data-stu-id="01272-111">This walkthrough demonstrates how to build and customize a clustering diagram in Visio.</span></span>  
  
 <span data-ttu-id="01272-112">Zum Ausführen der Schritte sollten Sie bereits über ein Clusteringmodell verfügen.</span><span class="sxs-lookup"><span data-stu-id="01272-112">To follow along, you should have a clustering model already available.</span></span> <span data-ttu-id="01272-113">Wenn Sie nicht über ein Modell verfügen, verwenden Sie den Assistenten [&#40;Data Mining-Add-Ins für Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) , und erstellen Sie ein Modell mit dem Trainings Dataset in der Beispiel Arbeitsmappe, wobei alle Standardwerte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="01272-113">If you do not have a model, use the [Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) wizard and create a model using the Training data set in the sample workbook, using all the defaults.</span></span>  
  
#### <a name="use-the-cluster-visio-shape-wizard"></a><span data-ttu-id="01272-114">Verwenden des Assistenten für das Cluster-Shape in Visio</span><span class="sxs-lookup"><span data-stu-id="01272-114">Use the Cluster Visio Shape Wizard</span></span>  
  
1.  <span data-ttu-id="01272-115">Wenn **Microsoft Data Mining-Formen** in der Liste **Shapes** nicht angezeigt werden, klicken Sie auf **Weitere Formen**, wählen Sie **Schablone öffnen**aus, und öffnen Sie die Vorlage aus dem Standard Installationsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="01272-115">If you do not see **Microsoft Data Mining Shapes** in the **Shapes** list, click **More Shapes**, select **Open Stencil**, and open the template from the default installation location.</span></span>  
  
     <span data-ttu-id="01272-116">\<drive>: \Programme\Microsoft SQL Server 2012 DM-Add-ins</span><span class="sxs-lookup"><span data-stu-id="01272-116">\<drive>:\Program files\Microsoft SQL Server 2012 DM Add-Ins</span></span>  
  
2.  <span data-ttu-id="01272-117">Ziehen Sie die Form " **Cluster** " auf die Seite.</span><span class="sxs-lookup"><span data-stu-id="01272-117">Drag the **Cluster** shape onto the page.</span></span>  
  
3.  <span data-ttu-id="01272-118">Klicken Sie auf der Willkommensseite des Assistenten für das **Cluster-Shape in Visio**auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="01272-118">On the welcome page of the **Cluster Visio Shape Wizard**, click **Next**.</span></span>  
  
4.  <span data-ttu-id="01272-119">Wählen Sie auf der Seite **Datenquelle auswählen** des **Cluster-Assistenten**eine Verbindung mit einem- [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Server aus, der die Data Mining Modelle enthält, die Sie visualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="01272-119">On the **Select a Data Source** page of the **Cluster Wizard**, choose a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that contains the data mining models you want to visualize.</span></span>  
  
5.  <span data-ttu-id="01272-120">Wählen Sie ein geeignetes Mining Modell aus, und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="01272-120">Select an appropriate mining model, and click **Next**.</span></span>  
  
     <span data-ttu-id="01272-121">Um sicherzustellen, dass Sie ein Clusteringmodell auswählen, überprüfen Sie die Beschreibung im Bereich " **Eigenschaften** ".</span><span class="sxs-lookup"><span data-stu-id="01272-121">To make sure you choose a clustering model, review the description in the **Properties** pane.</span></span>  
  
6.  <span data-ttu-id="01272-122">Wenn die Verbindung erfolgreich hergestellt wurde, legen Sie auf der Seite **Optionen für Cluster Diagramm**fest, welche Art von Cluster Diagramm in die Visio-Präsentation aufgenommen werden soll:</span><span class="sxs-lookup"><span data-stu-id="01272-122">If the connection is successful, on the page, **Options for cluster diagram**, you decide which type of cluster diagram to include in your Visio presentation:</span></span>  
  
     <span data-ttu-id="01272-123">**Nur Cluster-Shapes anzeigen**</span><span class="sxs-lookup"><span data-stu-id="01272-123">**Show cluster shapes only**</span></span>  
     <span data-ttu-id="01272-124">Mit dieser Option erstellen Sie ein einfaches Clusterdiagramm, in dem jeder Cluster durch ein Rechteck oder ein anderes Shape Ihrer Wahl dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="01272-124">This option creates a simple cluster diagram, with each cluster represented by a rectangle or other shape you choose</span></span>  
  
     <span data-ttu-id="01272-125">**Cluster mit Merkmaldiagramm anzeigen**</span><span class="sxs-lookup"><span data-stu-id="01272-125">**Show clusters with characteristics chart**</span></span>  
     <span data-ttu-id="01272-126">Mit dieser Option erstellen Sie das gleiche Diagramm wie oben. In diesem Fall enthalten die Shapes jedoch Histogramme, die die Merkmale des Clusters beschreiben.</span><span class="sxs-lookup"><span data-stu-id="01272-126">This option creates the same chart as above, but inside the shapes are histograms that describe the characteristics of the cluster.</span></span>  
  
     <span data-ttu-id="01272-127">![Beispiel des Clustermerkmal-Diagramms in Visio](media/dm13-visio-cluster-samplecharshape.gif "Beispiel des Clustermerkmal-Diagramms in Visio")</span><span class="sxs-lookup"><span data-stu-id="01272-127">![Example of cluster characteristics chart in Visio](media/dm13-visio-cluster-samplecharshape.gif "Example of cluster characteristics chart in Visio")</span></span>  
  
     <span data-ttu-id="01272-128">**Cluster mit Unterscheidungsdiagramm anzeigen**</span><span class="sxs-lookup"><span data-stu-id="01272-128">**Show clusters with discrimination chart**</span></span>  
     <span data-ttu-id="01272-129">Mit dieser Option erstellen Sie ebenfalls ein Clusterdiagramm. In diesem Fall werden jedoch die Merkmale des aktuellen Clusters aufgeführt, die sich am stärksten von den anderen Clustern unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="01272-129">This option creates the same chart as the cluster diagram, but instead lists the characteristics of the current cluster that most strongly distinguish it from other clusters.</span></span>  
  
     <span data-ttu-id="01272-130">Sie können auch zu einem anderen Diagrammtyp wechseln, nachdem das Diagramm vom Assistenten erstellt wurde. Klicken Sie dazu mit der rechten Maustaste auf einen Cluster, und wählen Sie einen neuen Diagrammtyp aus.</span><span class="sxs-lookup"><span data-stu-id="01272-130">You can switch to another chart type after the wizard has built the diagram, by right-clicking a cluster and selecting a new chart type.</span></span> <span data-ttu-id="01272-131">Wählen Sie vorerst die Option **Cluster mit Merkmalen anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="01272-131">For now, choose the option, **Show clusters with characteristics chart**.</span></span>  
  
7.  <span data-ttu-id="01272-132">Belassen Sie die Option **Anzahl von Zeilen im Diagramm**5.</span><span class="sxs-lookup"><span data-stu-id="01272-132">Leave the option, **Number of rows in the chart**, as 5.</span></span>  
  
     <span data-ttu-id="01272-133">Mit dieser Option wird die Anzahl der Cluster im Modell nicht geändert. die Anzahl der Attribute, die als Funktionen der einzelnen Cluster angezeigt werden können, wird einfach eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="01272-133">This option doesn't change the number of clusters in the model; it simply limits the number of attributes that can be displayed as features of each cluster.</span></span>  
  
     <span data-ttu-id="01272-134">Die Option fungiert jedoch als Filter für die Diagramm Daten, sodass Sie die Anzahl der Elemente später nicht mehr erhöhen können.</span><span class="sxs-lookup"><span data-stu-id="01272-134">However, the option acts as a filter on the chart data, so you can't increase the number of items later.</span></span>  
  
8.  <span data-ttu-id="01272-135">Klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="01272-135">Click **Advanced**.</span></span>  
  
     <span data-ttu-id="01272-136">Im Dialogfeld **Cluster Optionen** passen Sie die visuelle Darstellung von Formen an, die im Diagramm verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="01272-136">The **Cluster Options** dialog box is where you customize the visual appearance of shapes used in the diagram.</span></span> <span data-ttu-id="01272-137">Sie können die im Diagramm verwendeten Farben und das für die Cluster verwendete Shape ändern.</span><span class="sxs-lookup"><span data-stu-id="01272-137">You can change the colors used in the graph, and the shape used for clusters.</span></span>  
  
     <span data-ttu-id="01272-138">Das Steuerelement für **Schattierungs Variablen** funktioniert nicht in Office 2013.</span><span class="sxs-lookup"><span data-stu-id="01272-138">The **Shading Variable** control does not work in Office 2013.</span></span>  
  
     <span data-ttu-id="01272-139">![Klicken auf "Erweitert", um Shape-Farben auszuwählen](media/dm13-visio-clusteroptions-advanced.gif "Klicken auf "Erweitert", um Shape-Farben auszuwählen")</span><span class="sxs-lookup"><span data-stu-id="01272-139">![click Advanced to choose shape colors](media/dm13-visio-clusteroptions-advanced.gif "click Advanced to choose shape colors")</span></span>  
  
     <span data-ttu-id="01272-140">**Tipp:** Einige Farben können später mithilfe von Visio-Designs und Steuerelementen zum Bearbeiten von Formen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="01272-140">**Tip:** Some colors can be altered later by using Visio themes and shape editing controls.</span></span> <span data-ttu-id="01272-141">Ein Teil dieser Farbauswahl wird jedoch von Visio-Designs überschrieben. Aus diesem Grund wird empfohlen, mit den Standardfarben zu beginnen und die Änderungen schrittweise vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="01272-141">However, Visio themes will also override some of these color selections, so we recommend starting with the default colors and gradually applying changes.</span></span>  
  
9. <span data-ttu-id="01272-142">Klicken Sie auf **Fertig** stellen, um das Diagramm zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="01272-142">Click **Finish** to create the graph.</span></span>  
  
     <span data-ttu-id="01272-143">Der Assistent ruft Informationen aus dem Data Mining-Modell ab, rendert die Shapes und füllt jeden Cluster mit Attributen und Werten auf.</span><span class="sxs-lookup"><span data-stu-id="01272-143">The wizard retrieves information from the data mining model, renders the shapes, and populates each cluster with attributes and values.</span></span>  
  
     <span data-ttu-id="01272-144">![ein Abhängigkeitsnetzwerk](media/dm13-visiodepnet-defaultgraph.gif "ein Abhängigkeitsnetzwerk")</span><span class="sxs-lookup"><span data-stu-id="01272-144">![a dependency network](media/dm13-visiodepnet-defaultgraph.gif "a dependency network")</span></span>  
  
## <a name="explore-and-modify-the-finished-diagram"></a><span data-ttu-id="01272-145">Durchsuchen und Ändern des fertigen Diagramms</span><span class="sxs-lookup"><span data-stu-id="01272-145">Explore and Modify the Finished Diagram</span></span>  
 <span data-ttu-id="01272-146">Nachdem das Diagramm vollständig erstellt wurde, können Sie dessen Erscheinungsbild, wie im folgenden Beispiel beschrieben, mithilfe von Visio-Steuerelementen anpassen.</span><span class="sxs-lookup"><span data-stu-id="01272-146">After the diagram is complete, you can continue to customize the appearance using the Visio controls, as shown in the following example.</span></span>  
  
 <span data-ttu-id="01272-147">![Mithilfe von Visio angepasstes Clusterdiagramm](media/dm13-visio-clustercomplete1.gif "Mithilfe von Visio angepasstes Clusterdiagramm")</span><span class="sxs-lookup"><span data-stu-id="01272-147">![cluster diagram customized using Visio](media/dm13-visio-clustercomplete1.gif "cluster diagram customized using Visio")</span></span>  
  
 <span data-ttu-id="01272-148">Alle grundlegenden Cluster-Shapes werden vom Assistenten generiert. Verwenden Sie die folgenden Tools zum Aktualisieren und Personalisieren des Diagramms:</span><span class="sxs-lookup"><span data-stu-id="01272-148">All of the basic cluster shapes are generated by the wizard; use the following tools to update and personalize the diagram:</span></span>  
  
1.  <span data-ttu-id="01272-149">Ziehen Sie den Schieberegler in das Steuerelement **Cluster Optionen** , um schwächere Beziehungen herauszufiltern und das Diagramm zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="01272-149">Drag the slider in the **Cluster Options** control, to filter out weaker relationships and simplify the diagram.</span></span>  
  
2.  <span data-ttu-id="01272-150">Verwenden Sie die Option für die Visio **-neulayoutseite** , um mit unterschiedlichen Cluster Layouts zu experimentieren.</span><span class="sxs-lookup"><span data-stu-id="01272-150">Use the Visio **Re-Layout Page** option to experiment with different cluster layouts.</span></span>  
  
3.  <span data-ttu-id="01272-151">Verwenden Sie die Option **Connectors** auf der Registerkarte **Entwurf** , um den connectorstil so zu ändern, dass Zeilen vom überschreiten von Clustern bleiben.</span><span class="sxs-lookup"><span data-stu-id="01272-151">Use the **Connectors** option on the **Design** tab to change the connector style to keep lines from crossing over clusters.</span></span>  
  
4.  <span data-ttu-id="01272-152">Klicken Sie auf das Menüband **Add-ins** , und zeigen Sie dann eine der benutzerdefinierten Symbolleisten an, die für die Arbeit mit Data Mining Diagrammen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="01272-152">Click the **Add-Ins** ribbon, and then display one of the custom toolbars used for working with data mining diagrams:</span></span>  
  
     <span data-ttu-id="01272-153">**Layout**</span><span class="sxs-lookup"><span data-stu-id="01272-153">**Layout**</span></span>  
     <span data-ttu-id="01272-154">Optimiert die Anordnung der Cluster, sodass sie auf die aktuelle Seite passen.</span><span class="sxs-lookup"><span data-stu-id="01272-154">Optimizes the arrangement of clusters to fit in the current page.</span></span>  
  
     <span data-ttu-id="01272-155">**Größe der Seite ändern**</span><span class="sxs-lookup"><span data-stu-id="01272-155">**Resize Page**</span></span>  
     <span data-ttu-id="01272-156">Dieses Steuerelement war für frühere HTML-Versionen vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="01272-156">This control was intended for earlier HTML versions.</span></span> <span data-ttu-id="01272-157">Verwenden Sie stattdessen Steuerungselemente zur Anpassung der Visio-Seitengröße.</span><span class="sxs-lookup"><span data-stu-id="01272-157">Use the Visio page resizing controls instead.</span></span>  
  
     <span data-ttu-id="01272-158">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="01272-158">**Description**</span></span>  
     <span data-ttu-id="01272-159">Wenn ein Cluster ausgewählt ist, klicken Sie auf diese Option, um Details zum Cluster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="01272-159">If a cluster is selected, click this option to display details about the cluster.</span></span>  
  
     <span data-ttu-id="01272-160">![Klicken auf "Beschreibung", um Details zum Cluster abzurufen](media/dm13-visio-cluster-description-control.gif "Klicken auf "Beschreibung", um Details zum Cluster abzurufen")</span><span class="sxs-lookup"><span data-stu-id="01272-160">![click Description to get details about the cluster](media/dm13-visio-cluster-description-control.gif "click Description to get details about the cluster")</span></span>  
  
     <span data-ttu-id="01272-161">**Kantenstärke**</span><span class="sxs-lookup"><span data-stu-id="01272-161">**Edge Strength**</span></span>  
     <span data-ttu-id="01272-162">Zeigt Vertrauensergebnisse für die Linien an, die die Cluster verbinden.</span><span class="sxs-lookup"><span data-stu-id="01272-162">Displays confidence scores on the lines connecting clusters.</span></span>  
  
     <span data-ttu-id="01272-163">Wenn Sie eine spezielle Formatierung anwenden, die von der standardmäßig generierten Formatierung des Assistenten abweicht (einschließlich einiger Hintergründe), sind diese Zahlen u. U. nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="01272-163">However, if you apply any special formatting other than the default generated by the wizard, including some backgrounds, these numbers might not be visible.</span></span>  
  
     <span data-ttu-id="01272-164">**Schieberegler**</span><span class="sxs-lookup"><span data-stu-id="01272-164">**Slider**</span></span>  
     <span data-ttu-id="01272-165">Filtert die Linien zwischen den Clustern.</span><span class="sxs-lookup"><span data-stu-id="01272-165">Filters the lines between clusters.</span></span> <span data-ttu-id="01272-166">Wenn Sie den Schieberegler verschieben, werden alle Zuordnungen bis auf die wichtigsten entfernt.</span><span class="sxs-lookup"><span data-stu-id="01272-166">Moving the slider up removes all but the most important associations.</span></span>  
  
     <span data-ttu-id="01272-167">**Schattierung**</span><span class="sxs-lookup"><span data-stu-id="01272-167">**Shading**</span></span>  
     <span data-ttu-id="01272-168">Dieses Steuerelement funktioniert nicht in Office 2013.</span><span class="sxs-lookup"><span data-stu-id="01272-168">This control does not work in Office 2013.</span></span>  
  
5.  <span data-ttu-id="01272-169">Verwenden Sie das Steuerelement **schwenken und Zoomen** im **Aufgaben** Bereich des Menübands **Ansicht Ansicht** , um sich auf eine Gruppe von Clustern zu konzentrieren und das Diagramm zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="01272-169">Use the **Pan and Zoom** control, in the **Task Pane** area of the Visio **View** ribbon, to focus on a set of clusters and move around the diagram.</span></span>  
  
6.  <span data-ttu-id="01272-170">Klicken Sie mit der rechten Maustaste auf einen beliebigen Cluster, um die Optionen für das Cluster-Shape anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="01272-170">Right-click any cluster to see options specific to the cluster shape:</span></span>  
  
    -   <span data-ttu-id="01272-171">Ändern Sie das Diagrammformat.</span><span class="sxs-lookup"><span data-stu-id="01272-171">Change the chart style.</span></span>  
  
    -   <span data-ttu-id="01272-172">Flügen Sie ein Clustermerkmaldiagramm hinzu.</span><span class="sxs-lookup"><span data-stu-id="01272-172">Add a cluster characteristics chart.</span></span>  
  
    -   <span data-ttu-id="01272-173">Fügen Sie ein Clusterunterscheidungsdiagramm hinzu.</span><span class="sxs-lookup"><span data-stu-id="01272-173">Add a cluster discrimination chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01272-174">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="01272-174">See Also</span></span>  
 [<span data-ttu-id="01272-175">Problembehandlung bei Visio Data Mining-Diagrammen &#40;SQL Server Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="01272-175">Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;</span></span>](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md)  
  
  
