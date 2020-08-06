---
title: Exemplarische Vorgehensweise für das Abhängigkeits Netzwerkdiagramm (Data Mining-Add-Ins) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Visio shapes, dependency network
- shapes, data mining
- shapes, network
- dependencies
- diagram, dependency network
- data mining layout toolbar
- dependency network
ms.assetid: aac732a8-5262-4649-b7d7-3ccf6f9cfa8b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 07f97dac7ffb0211f0ff1e1b58c2e0792d026174
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621728"
---
# <a name="dependency-network-diagram-walkthrough-data-mining-add-ins"></a><span data-ttu-id="a4094-102">Exemplarische Vorgehensweise für das Abhängigkeitsnetzwerkdiagramm (Data Mining-Add-Ins)</span><span class="sxs-lookup"><span data-stu-id="a4094-102">Dependency Network Diagram Walkthrough (Data Mining Add-ins)</span></span>
  <span data-ttu-id="a4094-103">Mehrere verschiedene Data Mining-Modelltypen verwenden ein Netzwerkdiagramm, um Beziehungen in den Daten zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="a4094-103">Several different types of data mining models use a network graph as a way of exploring relationships in the data.</span></span> <span data-ttu-id="a4094-104">Sie können diese Modelle mithilfe der Form **Abhängigkeits Netzwerk** in Visio importieren und das Layout anschließend weiter anpassen und verbessern.</span><span class="sxs-lookup"><span data-stu-id="a4094-104">You can import these models into Visio using the **Dependency Network** shape and then continue to customize and enhance the layout.</span></span> <span data-ttu-id="a4094-105">Die **Data Mining-Shapes für Visio** enthalten die folgenden benutzerdefinierten Steuerelemente zum Arbeiten mit Abhängigkeits Netzwerk Diagrammen:</span><span class="sxs-lookup"><span data-stu-id="a4094-105">The **Data Mining Shapes for Visio** include the following custom controls for working with dependency network diagrams:</span></span>  
  
-   <span data-ttu-id="a4094-106">Rendern von Steuerelementen für das Netzwerkdiagramm</span><span class="sxs-lookup"><span data-stu-id="a4094-106">Rendering controls for the network graph</span></span>  
  
     <span data-ttu-id="a4094-107">Diese Optionen sind Teil des Assistenten, der geöffnet wird, wenn Sie ein Shape auf dem Visio-Arbeitsbereich ablegen.</span><span class="sxs-lookup"><span data-stu-id="a4094-107">These options are part of the wizard that is launched when you drop a shape into the Visio workspace.</span></span>  
  
-   <span data-ttu-id="a4094-108">Symbolleiste für **Data Mining-Layout**</span><span class="sxs-lookup"><span data-stu-id="a4094-108">**Data Mining Layout** toolbar</span></span>  
  
     <span data-ttu-id="a4094-109">Diese Optionen werden dem Visio-Arbeitsbereich hinzugefügt, um Ihnen die Interaktion mit dem Abhängigkeitsnetzwerkdiagramm zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="a4094-109">These options are added to the Visio workspace to help you interact with the dependency network graph.</span></span>  
  
## <a name="build-a-dependency-network-graph"></a><span data-ttu-id="a4094-110">Erstellen eines Abhängigkeitsnetzwerkdiagramms</span><span class="sxs-lookup"><span data-stu-id="a4094-110">Build a Dependency Network Graph</span></span>  
 <span data-ttu-id="a4094-111">Sie können eine Form auf der Visio-Seite ablegen, um den Assistenten für das **Abhängigkeits Netzwerk von Visio** zu starten und Diagramm Optionen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a4094-111">You drop a shape onto the Visio page to launch the **Dependency Net Visio Shape Wizard** and set diagram options.</span></span>  
  
#### <a name="use-the-dependency-net-visio-shape-wizard"></a><span data-ttu-id="a4094-112">Verwenden des "Assistenten für das Abhängigkeitsnetzwerk-Shape in Visio"</span><span class="sxs-lookup"><span data-stu-id="a4094-112">Use the Dependency Net Visio Shape Wizard</span></span>  
  
1.  <span data-ttu-id="a4094-113">Wenn **Microsoft Data Mining-Formen** in der Liste **Shapes** nicht angezeigt werden, klicken Sie auf **Weitere Formen**, wählen Sie **Schablone öffnen**aus, und öffnen Sie die Vorlage aus dem Standard Installationsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a4094-113">If you do not see **Microsoft Data Mining Shapes** in the **Shapes** list, click **More Shapes**, select **Open Stencil**, and open the template from the default installation location.</span></span>  
  
     <span data-ttu-id="a4094-114">\<drive>: \Programme (x85) \Microsoft SQL Server 2012 DM-Add-ins</span><span class="sxs-lookup"><span data-stu-id="a4094-114">\<drive>:\Program files (x85)\Microsoft SQL Server 2012 DM Add-Ins</span></span>  
  
2.  <span data-ttu-id="a4094-115">Ziehen Sie die Form **Abhängigkeits Netzwerk** auf die Seite, um den Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="a4094-115">Drag the **Dependency Network** shape onto the page to start the wizard.</span></span> <span data-ttu-id="a4094-116">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a4094-116">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="a4094-117">Klicken Sie auf der Willkommensseite des Assistenten für das **Abhängigkeits Netzwerk-Shape in Visio**auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a4094-117">On the welcome page of the **Dependency Network Visio Shape Wizard**, click **Next**.</span></span>  
  
4.  <span data-ttu-id="a4094-118">Wählen Sie auf der Seite **Datenquelle auswählen** des **Assistenten für das Abhängigkeits Netzwerk-Shape in Visio**eine Verbindung mit einem Server aus, auf [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] dem sich das Modell befindet, das Sie visualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a4094-118">On the **Select a Data Source** page of the **Dependency Network Visio Shape Wizard**, choose a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that has the model you want to visualize.</span></span>  
  
5.  <span data-ttu-id="a4094-119">Wählen Sie ein geeignetes Mining Modell aus, und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a4094-119">Select an appropriate mining model, and click **Next**.</span></span>  
  
     <span data-ttu-id="a4094-120">Zum Auswählen eines geeigneten Modells können Sie den Namen, die Beschreibung, die Spalten und den Typ der Daten im **Eigenschaften** Bereich überprüfen.</span><span class="sxs-lookup"><span data-stu-id="a4094-120">To select an appropriate model, you can review the name, description, columns, and type of data in the **Properties** pane.</span></span>  
  
     <span data-ttu-id="a4094-121">Dieses Shape unterstützt Modelle, die anhand der folgenden Algorithmen erstellt wurden:</span><span class="sxs-lookup"><span data-stu-id="a4094-121">This shape supports models created by using these algorithms:</span></span>  
  
    -   <span data-ttu-id="a4094-122">Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="a4094-122">Naïve Bayes</span></span>  
  
    -   <span data-ttu-id="a4094-123">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="a4094-123">Decision Trees</span></span>  
  
    -   <span data-ttu-id="a4094-124">Zuordnungs Regeln</span><span class="sxs-lookup"><span data-stu-id="a4094-124">Association Rules</span></span>  
  
6.  <span data-ttu-id="a4094-125">Wählen Sie auf der Seite die **Knoten zum Rendering**aus, passen Sie die Größe des Diagramms an, und Filtern Sie optional, um nur bestimmte Knoten einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="a4094-125">On the page, **Select Nodes to Render**, customize the size of the graph, and optionally filter to only include certain nodes.</span></span>  
  
     <span data-ttu-id="a4094-126">Bei einem großen DataSet kann ein Abhängigkeits Diagramm sehr groß werden und viele verbundene Objekte enthalten, die als *Knoten*dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a4094-126">With a large dataset, a dependency graph can become huge, and contain many related objects, represented as *nodes*.</span></span> <span data-ttu-id="a4094-127">Mithilfe dieses Dialogfelds können Sie ein benutzerdefiniertes Netzwerkdiagramm erstellen, das nur die interessanten Knoten enthält.</span><span class="sxs-lookup"><span data-stu-id="a4094-127">By using this dialog box, you can create a custom network graph that includes only the nodes of interest.</span></span>  
  
     <span data-ttu-id="a4094-128">[Kunst Platzhalter]</span><span class="sxs-lookup"><span data-stu-id="a4094-128">[art placeholder]</span></span>  
  
     <span data-ttu-id="a4094-129">**Anzahl der abzurufenden Knoten**</span><span class="sxs-lookup"><span data-stu-id="a4094-129">**Number of nodes to fetch**</span></span>  
     <span data-ttu-id="a4094-130">Falls das Modell weniger Knoten als die angegebene Knotenanzahl enthält, wirkt sich diese Einstellung nicht aus.</span><span class="sxs-lookup"><span data-stu-id="a4094-130">If the model contains fewer than the specified number of nodes, this setting has no effect.</span></span> <span data-ttu-id="a4094-131">Falls das Modell mehr Knoten als die angegebene Anzahl enthält, werden nur die wichtigsten Knoten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a4094-131">If the model contains more nodes than the specified number, only the strongest nodes are displayed.</span></span>  
  
     <span data-ttu-id="a4094-132">**Name enthält**</span><span class="sxs-lookup"><span data-stu-id="a4094-132">**Name contains**</span></span>  
     <span data-ttu-id="a4094-133">Lassen Sie dieses Feld leer, und klicken Sie auf den grünen Pfeil, um alle Knoten im Modell abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a4094-133">Leave this box blank and click the green arrow to retrieve all nodes in the model.</span></span>  
  
     <span data-ttu-id="a4094-134">Alternativ geben Sie eine Zeichenfolge ein und klicken auf den grünen Pfeil, um nur die Knoten zurückzugeben, die die angegebene Zeichenfolge enthalten.</span><span class="sxs-lookup"><span data-stu-id="a4094-134">Or, type a string and click the green arrow to return only those nodes that contain the specified string.</span></span>  
  
     <span data-ttu-id="a4094-135">Die meisten Modelle, die Sie anhand von Beispieldaten erstellen können, sind nicht besonders groß. Erhöhen Sie die Anzahl der Knoten auf 10, und klicken Sie auf den grünen Pfeil, um eine Abfrage auszuführen und eine Liste aller Knoten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a4094-135">Most of the models that you can create with the sample data are not big, so for this example, increase the number of nodes to 10, and then click the green arrow to run a query and get the list of all nodes.</span></span>  
  
7.  <span data-ttu-id="a4094-136">Klicken Sie auf **erweitert** , um Schattierungs-und Shape-Optionen für das Diagramm festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a4094-136">Click **Advanced** to set shading and shape options for the graph.</span></span>  
  
8.  <span data-ttu-id="a4094-137">Klicken Sie auf schließen, um das Dialogfeld **Erweiterte** Optionen zu **Schließen** , und klicken Sie auf **Fertig** stellen, um das Diagramm zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a4094-137">Click **Close** to exit the **Advanced** options dialog box, and then click **Finish** to create the graph.</span></span>  
  
## <a name="explore-and-modify-the-finished-diagram"></a><span data-ttu-id="a4094-138">Durchsuchen und Ändern des fertigen Diagramms</span><span class="sxs-lookup"><span data-stu-id="a4094-138">Explore and Modify the Finished Diagram</span></span>  
 <span data-ttu-id="a4094-139">Nachdem das Abhängigkeitsnetzwerkdiagramm von Visio erstellt wurde, können Sie anhand der Visio-Funktionen weitere Änderungen und Verbesserungen am Diagramm vornehmen.</span><span class="sxs-lookup"><span data-stu-id="a4094-139">After Visio has created the network dependency graph, you can continue to modify and enhance the graph by using the features in Visio.</span></span>  
  
 <span data-ttu-id="a4094-140">Die folgende Abbildung zeigt das Standardlayout eines Abhängigkeitsnetzwerkdiagramms.</span><span class="sxs-lookup"><span data-stu-id="a4094-140">The following graphic shows the default layout of a dependency network graph.</span></span>  
  
 <span data-ttu-id="a4094-141">[Kunst Platzhalter]</span><span class="sxs-lookup"><span data-stu-id="a4094-141">[art placeholder]</span></span>  
  
1.  <span data-ttu-id="a4094-142">Verwenden Sie das Steuerelement **schwenken und Zoomen** im **Aufgaben** Bereich des Menübands **Ansicht Ansicht** , um sich auf einen Bereich des Diagramms zu konzentrieren und das Diagramm zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="a4094-142">Use the **Pan and Zoom** control, in the **Task Pane** area of the Visio **View** ribbon, to focus on a section of the graph and move around the diagram.</span></span>  
  
2.  <span data-ttu-id="a4094-143">Experimentieren Sie mit verschiedenen Diagramm Layouts, die von der Visio **-Seite für neulayoutseiten** bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a4094-143">Experiment with different graph layouts provided by the Visio **Re-Layout Page** option.</span></span>  
  
3.  <span data-ttu-id="a4094-144">Klicken Sie auf das Menüband **Add-ins** , und zeigen Sie dann eine der benutzerdefinierten Symbolleisten an, die für die Arbeit mit Data Mining Diagrammen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="a4094-144">Click the **Add-Ins** ribbon, and then display one of the custom toolbars used for working with data mining diagrams:</span></span>  
  
     <span data-ttu-id="a4094-145">**Layout**</span><span class="sxs-lookup"><span data-stu-id="a4094-145">**Layout**</span></span>  
     <span data-ttu-id="a4094-146">Optimiert das Layout von Knoten auf dem Zeichenblatt und ändert die Anzeige so, dass alle Knoten sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="a4094-146">Optimizes the layout of nodes on the page, and changes the view so that all nodes are visible.</span></span>  
  
     <span data-ttu-id="a4094-147">**Größe der Seite ändern**</span><span class="sxs-lookup"><span data-stu-id="a4094-147">**Resize Page**</span></span>  
     <span data-ttu-id="a4094-148">Ändert die Zeichenblattgröße so, dass alle Knoten sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="a4094-148">Changes the size of the page so that all nodes are visible.</span></span>  
  
     <span data-ttu-id="a4094-149">**Kantenstärke**</span><span class="sxs-lookup"><span data-stu-id="a4094-149">**Edge Strength**</span></span>  
     <span data-ttu-id="a4094-150">Blendet die Anzeige der Kantenstärke für das gesamte Diagramm ein/aus.</span><span class="sxs-lookup"><span data-stu-id="a4094-150">Toggles display of edge strength for the entire graph.</span></span> <span data-ttu-id="a4094-151">Eine Kante ist eine Verbindung zwischen Knoten.</span><span class="sxs-lookup"><span data-stu-id="a4094-151">An edge is a connection between nodes.</span></span> <span data-ttu-id="a4094-152">Sie können das Schieberegler-Steuerelement verwenden, um schwache Verbindungen herauszufiltern.</span><span class="sxs-lookup"><span data-stu-id="a4094-152">You can use the slider control to filter out connections that are not strong.</span></span>  
  
     <span data-ttu-id="a4094-153">**Schieberegler**</span><span class="sxs-lookup"><span data-stu-id="a4094-153">**Slider**</span></span>  
     <span data-ttu-id="a4094-154">Mit dem **Schieberegler** können Sie die Stärke der Beziehungen steuern, die im Abhängigkeits Netzwerkdiagramm angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a4094-154">The **Slider** helps you control the strength of the relationships that are displayed in the dependency network diagram.</span></span>  
  
     <span data-ttu-id="a4094-155">Jeder Knoten im Diagramm stellt einen Status dar.</span><span class="sxs-lookup"><span data-stu-id="a4094-155">Each node in the graph represents a state.</span></span> <span data-ttu-id="a4094-156">Ein Pfeil stellt einen Übergang zwischen zwei Status dar, und die Wahrscheinlichkeit, dass dieser einem Übergang zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a4094-156">An arrow represents a transition between two states and the probability that is associated with the transition.</span></span> <span data-ttu-id="a4094-157">Zum Verringern der Anzahl von Knoten im Diagramm bewegen Sie die Schiebereglerleiste nach oben.</span><span class="sxs-lookup"><span data-stu-id="a4094-157">To reduce the number of nodes in the graph, move the slider bar up.</span></span>  
  
     <span data-ttu-id="a4094-158">Zum Erhöhen der Anzahl von Knoten im Diagramm bewegen Sie die Schiebereglerleiste nach unten.</span><span class="sxs-lookup"><span data-stu-id="a4094-158">To increase the number of nodes in the graph, move the slider bar down.</span></span>  
  
     <span data-ttu-id="a4094-159">**Elemente hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="a4094-159">**Add Items**</span></span>  
     <span data-ttu-id="a4094-160">Öffnet das Dialogfeld **zu Rendering-Knoten auswählen** , sodass Sie neue Knoten auswählen können, die dem Diagramm hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a4094-160">Opens the **Select Nodes to Render** dialog box so that you can select new nodes to add to the graph.</span></span>  
  
4.  <span data-ttu-id="a4094-161">Sie können Diagramme so einfach oder komplex gestalten, wie Sie möchten, und Anmerkungen hinzufügen, während Sie mit dem Modell verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="a4094-161">You can make the graphs as simple or elaborate as you like, and add annotations, while staying connected to the model.</span></span>  
  
     <span data-ttu-id="a4094-162">[ art placeholder]</span><span class="sxs-lookup"><span data-stu-id="a4094-162">[ art placeholder]</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="a4094-163">Die Hervorhebung abhängiger Knoten und andere Kontextmenüoptionen, die in früheren Versionen des Add-Ins verfügbar waren, sind in Office 2013 nicht funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="a4094-163">Highlighting of dependent nodes and other shortcut menu options that were available in previous versions of the Add-Ins do not work in Office 2013.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4094-164">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a4094-164">See Also</span></span>  
 [<span data-ttu-id="a4094-165">Problembehandlung bei Visio Data Mining-Diagrammen &#40;SQL Server Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="a4094-165">Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;</span></span>](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md)  
  
  
