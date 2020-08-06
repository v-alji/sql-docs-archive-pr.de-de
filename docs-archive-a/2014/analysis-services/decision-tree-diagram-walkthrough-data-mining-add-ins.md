---
title: Exemplarische Vorgehensweise für das Entscheidungsstruktur Diagramm (Data Mining-Add-Ins) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- shapes, data mining
- diagram, decision tree
- Visio shapes, decision tree
- decision tree [data mining]
ms.assetid: 9566f6a2-c750-4125-ba5e-42c7251a78c7
author: minewiskan
ms.author: owend
ms.openlocfilehash: bbe54db1ab3d00d074917db770a9a731f884f49a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616817"
---
# <a name="decision-tree-diagram-walkthrough--data-mining-add-ins"></a><span data-ttu-id="1ff5f-102">Exemplarische Vorgehensweise für das Entscheidungsstruktur Diagramm (Data Mining-Add-Ins)</span><span class="sxs-lookup"><span data-stu-id="1ff5f-102">Decision Tree Diagram Walkthrough  (Data Mining Add-ins)</span></span>
  <span data-ttu-id="1ff5f-103">Wenn Sie ein Entscheidungsstrukturmodell erstellt haben, können Sie ein benutzerdefiniertes Diagramm in Visio erstellen. Dazu stehen Ihnen die Shapes Entscheidungsstruktur und Abhängigkeitsnetzwerk zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-103">If you have created a decision tree model, you can create a customized diagram in Visio by using either the Decision Tree shape or the Dependency Network shape.</span></span> <span data-ttu-id="1ff5f-104">In diesem Thema werden die Anpassungen beschrieben, die Sie mithilfe der Form **Entscheidungs** Struktur und der folgenden Steuerelemente durchführen können:</span><span class="sxs-lookup"><span data-stu-id="1ff5f-104">This topic describes the customizations you can perform using the **Decision Tree** shape and these controls:</span></span>  
  
-   <span data-ttu-id="1ff5f-105">Rendern von Steuerelementen für das Entscheidungsstrukturdiagramm</span><span class="sxs-lookup"><span data-stu-id="1ff5f-105">Rendering controls for the decision tree diagram</span></span>  
  
     <span data-ttu-id="1ff5f-106">Diese Optionen sind Teil des Entscheidungsstruktur- **Assistenten** , der gestartet wird, wenn Sie eine Form im Visio-Arbeitsbereich ablegen.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-106">These options are part of the **Decision Tree Wizard** that is launched when you drop a shape into the Visio workspace.</span></span>  
  
-   <span data-ttu-id="1ff5f-107">Symbolleiste für **Data Mining-Layout**</span><span class="sxs-lookup"><span data-stu-id="1ff5f-107">**Data Mining Layout** toolbar</span></span>  
  
     <span data-ttu-id="1ff5f-108">Diese Optionen werden dem Visio-Arbeitsbereich hinzugefügt, um Ihnen die Interaktion mit dem Shape zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-108">These options are added to the Visio workspace to help you interact with the shape.</span></span>  
  
## <a name="build-a-decision-tree-diagram"></a><span data-ttu-id="1ff5f-109">Erstellen eines Entscheidungsstrukturdiagramms</span><span class="sxs-lookup"><span data-stu-id="1ff5f-109">Build a Decision Tree Diagram</span></span>  
 <span data-ttu-id="1ff5f-110">Legen Sie die Form Entscheidungsstruktur auf der Visio-Seite ab, um den Assistenten für die **Entscheidungsstruktur Visio-Shape** zu starten und Diagramm Optionen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-110">You drop the Decision Tree shape onto the Visio page to launch the **Decision Tree Visio Shape Wizard** and set diagram options.</span></span>  
  
#### <a name="use-the-decision-tree-wizard"></a><span data-ttu-id="1ff5f-111">Verwenden des Entscheidungsstruktur-Assistenten</span><span class="sxs-lookup"><span data-stu-id="1ff5f-111">Use the Decision Tree Wizard</span></span>  
  
1.  <span data-ttu-id="1ff5f-112">Wenn **Microsoft Data Mining-Formen** in der Liste **Shapes** nicht angezeigt werden, klicken Sie auf **Weitere Formen**, wählen Sie **Schablone öffnen**aus, und öffnen Sie die Vorlage aus dem Standard Installationsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-112">If you do not see **Microsoft Data Mining Shapes** in the **Shapes** list, click **More Shapes**, select **Open Stencil**, and open the template from the default installation location.</span></span>  
  
     <span data-ttu-id="1ff5f-113">\<drive>: \Programme (x85) \Microsoft SQL Server 2012 DM-Add-ins</span><span class="sxs-lookup"><span data-stu-id="1ff5f-113">\<drive>:\Program files (x85)\Microsoft SQL Server 2012 DM Add-Ins</span></span>  
  
2.  <span data-ttu-id="1ff5f-114">Ziehen Sie die Form **Entscheidungs** Struktur auf die Seite.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-114">Drag the **Decision Tree** shape onto the page.</span></span>  
  
3.  <span data-ttu-id="1ff5f-115">Klicken Sie auf der Willkommensseite des Assistenten für das Entscheidungsstruktur- **Shape in Visio**auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-115">On the welcome page of the **Decision Tree Visio Shape Wizard**, click **Next**.</span></span>  
  
4.  <span data-ttu-id="1ff5f-116">Wählen Sie auf der Seite **Datenquelle auswählen** des **Cluster-Assistenten**eine Verbindung mit einem Server aus, auf [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] dem sich das Modell befindet, das Sie visualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-116">On the **Select a Data Source** page of the **Cluster Wizard**, choose a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that has the model you want to visualize.</span></span>  
  
5.  <span data-ttu-id="1ff5f-117">Wählen Sie ein geeignetes Mining Modell aus, und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-117">Select an appropriate mining model, and click **Next**.</span></span>  
  
     <span data-ttu-id="1ff5f-118">Dieser Diagrammtyp unterstützt Modelle, die mit den Decision Trees oder dem Linear Regression-Algorithmus erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-118">This diagram type supports models created using the Decision Trees or Linear Regression algorithm.</span></span>  
  
6.  <span data-ttu-id="1ff5f-119">Wählen Sie auf der Seite **Entscheidungsstruktur auswählen** eine einzelne Struktur aus, die angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-119">On the **Select Decision Tree** page, choose an individual tree to display.</span></span>  
  
     <span data-ttu-id="1ff5f-120">Eine Struktur modelliert die Interaktionen, die zu einem bestimmten Ergebnis führen, das Sie modelliert haben. Daher können Sie, auch wenn das Modell mehrere Ergebnisse enthält, nur eine Struktur gleichzeitig anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-120">A tree models the interactions that lead to a particular outcome you've modeled; therefore, even if your model contains multiple outcomes, you can display only one tree at a time.</span></span>  
  
7.  <span data-ttu-id="1ff5f-121">Im Dialogfeld **Entscheidungsstruktur auswählen** können Sie auch diese Renderingoptionen festlegen:</span><span class="sxs-lookup"><span data-stu-id="1ff5f-121">In the **Select Decision Tree** dialog box, you can also set these rendering options:</span></span>  
  
     <span data-ttu-id="1ff5f-122">**Maximale Renderingtiefe**</span><span class="sxs-lookup"><span data-stu-id="1ff5f-122">**Maximum Rendering Depth**</span></span>  
     <span data-ttu-id="1ff5f-123">Mit dieser Option steuern Sie, wie viele Knoten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-123">Use this option to control how many nodes are displayed.</span></span>  
  
     <span data-ttu-id="1ff5f-124">Eine Entscheidungsstruktur kann sehr tief verzweigt sein, sodass das fertige Diagramm möglicherweise nicht auf die Seite passt.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-124">A decision tree might go very deep, creating a diagram that does not fit on the page.</span></span> <span data-ttu-id="1ff5f-125">Verwenden Sie dieses Steuerelement, um die wichtigeren, äußeren linken Knoten zu fokussieren.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-125">Use this control to focus on the leftmost nodes, which are more important.</span></span>  
  
     <span data-ttu-id="1ff5f-126">Standardmäßig werden drei Knotenebenen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-126">The default is three levels of nodes.</span></span>  
  
     <span data-ttu-id="1ff5f-127">**Farbe und Anzeigetext für Werte auswählen**</span><span class="sxs-lookup"><span data-stu-id="1ff5f-127">**Select color and display text for values**</span></span>  
     <span data-ttu-id="1ff5f-128">Wählen Sie die Farbe aus, durch die die einzelnen Ergebnisse dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-128">Choose the color that will represent each one of the outcomes.</span></span> <span data-ttu-id="1ff5f-129">Wenn Sie keine Farben angeben, werden diese automatisch anhand der aktuellen Videodesignfarben generiert.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-129">If you do not specify colors, they are automatically generated using the current video theme colors.</span></span>  
  
8.  <span data-ttu-id="1ff5f-130">Klicken Sie auf **erweitert** , um die folgenden Optionen für die einzelnen Knoten im Entscheidungsstruktur Diagramm anzupassen.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-130">Click **Advanced** to customize the following options for each of the nodes in the decision tree diagram.</span></span>  
  
     <span data-ttu-id="1ff5f-131">**Schattierungs Variable** und **Status**</span><span class="sxs-lookup"><span data-stu-id="1ff5f-131">**Shading Variable** and **State**</span></span>  
     <span data-ttu-id="1ff5f-132">Wählen Sie das Zielergebnis aus, das Sie im Strukturdiagramm anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-132">Choose the target outcome that you want to show in the tree diagram.</span></span>  
  
     <span data-ttu-id="1ff5f-133">**Histogramm anzeigen**</span><span class="sxs-lookup"><span data-stu-id="1ff5f-133">**Show Histogram**</span></span>  
     <span data-ttu-id="1ff5f-134">Fügt jedem Knoten, in dem Definitionsregeln für diesen Knoten angezeigt werden, ein Diagramm hinzu.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-134">Adds a chart to each node that shows the rules that define that node.</span></span>  
  
     <span data-ttu-id="1ff5f-135">**Bezeichnung anzeigen**</span><span class="sxs-lookup"><span data-stu-id="1ff5f-135">**Show Label**</span></span>  
     <span data-ttu-id="1ff5f-136">Fügt dem Histogramm Spaltennamen hinzu.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-136">Adds column names to the histogram.</span></span>  
  
     <span data-ttu-id="1ff5f-137">**Wahrscheinlichkeit anzeigen**</span><span class="sxs-lookup"><span data-stu-id="1ff5f-137">**Show Probability**</span></span>  
     <span data-ttu-id="1ff5f-138">Zeigt die Wahrscheinlichkeit der einzelnen Werte an.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-138">Displays the probability of each value.</span></span>  
  
     <span data-ttu-id="1ff5f-139">**Unterstützung anzeigen**</span><span class="sxs-lookup"><span data-stu-id="1ff5f-139">**Show Support**</span></span>  
     <span data-ttu-id="1ff5f-140">Zeigt die Unterstützung jedes einzelnen Werts an.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-140">Displays the support for each value.</span></span>  
  
     <span data-ttu-id="1ff5f-141">**Fußzeile anzeigen**</span><span class="sxs-lookup"><span data-stu-id="1ff5f-141">**Show Footer**</span></span>  
     <span data-ttu-id="1ff5f-142">Fügt eine Fußzeile hinzu, in der alle angezeigten Werte summiert werden.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-142">Adds a footer that sums all displayed values.</span></span>  
  
     <span data-ttu-id="1ff5f-143">**Kopfzeile anzeigen**</span><span class="sxs-lookup"><span data-stu-id="1ff5f-143">**Show Header**</span></span>  
     <span data-ttu-id="1ff5f-144">Fügt Spaltenüberschriften hinzu.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-144">Adds column headings.</span></span>  
  
     <span data-ttu-id="1ff5f-145">**Status ohne Unterstützung anzeigen**</span><span class="sxs-lookup"><span data-stu-id="1ff5f-145">**Show states with zero support**</span></span>  
     <span data-ttu-id="1ff5f-146">Ermöglicht die Anzeige fehlender Werte.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-146">Lets you display missing values.</span></span>  
  
9. <span data-ttu-id="1ff5f-147">Klicken Sie auf **Fertig** stellen, um das Diagramm zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-147">Click **Finish** to create the graph.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="1ff5f-148">In einigen Umgebungen kann es vorkommen, dass Verbinder in Office 2013 nicht gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-148">In some environments, connectors in the chart might fail to render in Office 2013.</span></span>  
  
## <a name="explore-and-modify-the-finished-diagram"></a><span data-ttu-id="1ff5f-149">Durchsuchen und Ändern des fertigen Diagramms</span><span class="sxs-lookup"><span data-stu-id="1ff5f-149">Explore and Modify the Finished Diagram</span></span>  
 <span data-ttu-id="1ff5f-150">Nachdem Sie den Assistenten für das Entscheidungsstruktur- **Shape in Visio**abgeschlossen haben, wird von Visio ein Strukturdiagramm auf der Seite erstellt, das die Regeln grafisch anzeigt, die zum vorhergesagten Ergebnis führen.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-150">After you have completed the **Decision Tree Visio Shape Wizard**, Visio creates a tree diagram on the page that graphically displays the rules that lead to the predicted outcome.</span></span>  
  
 <span data-ttu-id="1ff5f-151">Anhand der folgenden Steuerelemente für Entscheidungsstrukturdiagramme können Sie weitere Änderungen am Shape vornehmen:</span><span class="sxs-lookup"><span data-stu-id="1ff5f-151">You can continue to modify the shape by using the following controls for decision tree diagrams:</span></span>  
  
#### <a name="using-the-decision-tree-option-menus"></a><span data-ttu-id="1ff5f-152">Verwenden der Menüs mit Entscheidungsstrukturoptionen</span><span class="sxs-lookup"><span data-stu-id="1ff5f-152">Using the decision tree option menus</span></span>  
  
1.  <span data-ttu-id="1ff5f-153">Klicken Sie auf das Menüband **Add-ins** , und zeigen Sie dann eine der benutzerdefinierten Symbolleisten an, die für die Arbeit mit Data Mining Diagrammen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="1ff5f-153">Click the **Add-Ins** ribbon, and then display one of the custom toolbars used for working with data mining diagrams:</span></span>  
  
     <span data-ttu-id="1ff5f-154">**Layout**</span><span class="sxs-lookup"><span data-stu-id="1ff5f-154">**Layout**</span></span>  
     <span data-ttu-id="1ff5f-155">Optimiert die Anordnung der Struktur, sodass sie auf die aktuelle Seite passt.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-155">Optimizes the arrangement of the tree to fit the current page.</span></span>  
  
     <span data-ttu-id="1ff5f-156">**Größe der Seite ändern**</span><span class="sxs-lookup"><span data-stu-id="1ff5f-156">**Resize Page**</span></span>  
     <span data-ttu-id="1ff5f-157">Dieses Steuerelement war für frühere HTML-Versionen vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-157">This control was intended for earlier HTML versions.</span></span> <span data-ttu-id="1ff5f-158">Verwenden Sie stattdessen die Steuerelemente für die Anpassung von Visio-Seiten,</span><span class="sxs-lookup"><span data-stu-id="1ff5f-158">Use the Visio page resizing controls instead,</span></span>  
  
     <span data-ttu-id="1ff5f-159">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1ff5f-159">**Description**</span></span>  
     <span data-ttu-id="1ff5f-160">Wenn ein Strukturknoten ausgewählt ist, klicken Sie auf diese Option, um die Details der im Knoten enthaltenen Fälle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-160">When a node of the tree is selected, click this option to display details about the cases in the node.</span></span>  
  
2.  <span data-ttu-id="1ff5f-161">Verwenden Sie die Option **neulayoutseite** im Visio-Menüband **Design** , um mit verschiedenen Struktur Layouts zu experimentieren.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-161">Use the **Re-Layout Page** option in the Visio **Design** ribbon to experiment with different tree layouts.</span></span>  
  
3.  <span data-ttu-id="1ff5f-162">Verwenden Sie die Option **Connectors** auf der Registerkarte **Entwurf** , um die Connectors zu ändern, die zwischen den Knoten in der Struktur verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-162">Use the **Connectors** option on the **Design** tab to change the connectors used between nodes in the tree.</span></span>  
  
4.  <span data-ttu-id="1ff5f-163">Verwenden Sie das Steuerelement **schwenken und Zoomen** im **Aufgaben** Bereich des Menübands **Ansicht Ansicht** , um sich auf einen bestimmten Bereich des Diagramms zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-163">Use the **Pan and Zoom** control, in the **Task Pane** area of the Visio **View** ribbon, to focus on a particular area of the diagram.</span></span>  
  
5.  <span data-ttu-id="1ff5f-164">Klicken Sie mit der rechten Maustaste auf einen beliebigen Strukturknoten, und wählen Sie im Kontextmenü spezifische Optionen für Entscheidungsstrukturdiagramme aus:</span><span class="sxs-lookup"><span data-stu-id="1ff5f-164">Right-click any node in the tree, and choose from these shortcut menu options specific to decision tree diagrams:</span></span>  
  
     <span data-ttu-id="1ff5f-165">**Zeichenblattlayout verbessern**</span><span class="sxs-lookup"><span data-stu-id="1ff5f-165">**Improve Page Layout**</span></span>  
     <span data-ttu-id="1ff5f-166">Verteilt die Knoten gleichmäßig auf dem Zeichenblatt und passt die Seitenansicht so an, dass alle Knoten sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-166">Distributes the nodes evenly on the page and adjusts the page view to see all nodes.</span></span>  
  
     <span data-ttu-id="1ff5f-167">**Untergeordnete Elemente auf neues Zeichenblatt verschieben**</span><span class="sxs-lookup"><span data-stu-id="1ff5f-167">**Move Children to New Page**</span></span>  
     <span data-ttu-id="1ff5f-168">Verschiebt die untergeordneten Elemente des aktuell ausgewählten Knotens auf eine neue Seite.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-168">Moves the children of the currently selected node to a new page.</span></span>  
  
     <span data-ttu-id="1ff5f-169">**Untergeordnete Knoten reduzieren**</span><span class="sxs-lookup"><span data-stu-id="1ff5f-169">**Collapse Child Nodes**</span></span>  
     <span data-ttu-id="1ff5f-170">Blendet die untergeordneten Elemente des aktuell ausgewählten Knotens aus.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-170">Hides the children of the currently selected node.</span></span>  
  
     <span data-ttu-id="1ff5f-171">**Untergeordnete Knoten erweitern**</span><span class="sxs-lookup"><span data-stu-id="1ff5f-171">**Expand Child Nodes**</span></span>  
     <span data-ttu-id="1ff5f-172">Blendet untergeordnete Elemente des ausgewählten Knotens wieder ein.</span><span class="sxs-lookup"><span data-stu-id="1ff5f-172">Displays the children of the currently selected node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ff5f-173">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ff5f-173">See Also</span></span>  
 [<span data-ttu-id="1ff5f-174">Problembehandlung bei Visio Data Mining-Diagrammen &#40;SQL Server Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="1ff5f-174">Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;</span></span>](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md)  
  
  
