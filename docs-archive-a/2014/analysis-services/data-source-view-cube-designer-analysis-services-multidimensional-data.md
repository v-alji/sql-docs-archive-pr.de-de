---
title: Datenquellen Sicht (Registerkarte Cubestruktur, Cube-Designer) (Analysis Services-Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.cubebuilder.datasourcepane.f1
ms.assetid: 1e39c910-5c10-4624-be27-ca02a461b46b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8c949eaa17ec9d8bf585a5d595f31779382c41ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716996"
---
# <a name="data-source-view-cube-structure-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="72d50-102">Datenquellensicht (Registerkarte 'Cubestruktur', Cube-Designer) (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="72d50-102">Data Source View (Cube Structure Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="72d50-103">Im Bereich **Datenquellensicht** können Sie Tabellen und Spalten aus der Datenquellensicht anzeigen, die dem ausgewählten Cube zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="72d50-103">Use the **Data Source View** pane to view tables and columns from the data source view associated with the selected cube.</span></span> <span data-ttu-id="72d50-104">In diesem Bereich können Sie Measuregruppen und Measures erstellen, indem Sie Spalten aus dem Bereich **Datenquellensicht** in den Bereich **Measures** ziehen.</span><span class="sxs-lookup"><span data-stu-id="72d50-104">This pane is used to create measure groups and measures by dragging columns from the **Data Source View** pane to the **Measures** pane.</span></span>  
  
## <a name="options"></a><span data-ttu-id="72d50-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="72d50-105">Options</span></span>  
 <span data-ttu-id="72d50-106">**Datenquellensicht**</span><span class="sxs-lookup"><span data-stu-id="72d50-106">**Data Source View**</span></span>  
 <span data-ttu-id="72d50-107">Zeigt die dem ausgewählten Cube zugeordnete Datenquellensicht an.</span><span class="sxs-lookup"><span data-stu-id="72d50-107">Displays the data source view associated with the selected cube.</span></span>  
  
 <span data-ttu-id="72d50-108">**(Viewpoint verschieben)**</span><span class="sxs-lookup"><span data-stu-id="72d50-108">**(Move viewpoint)**</span></span>  
 <span data-ttu-id="72d50-109">Klicken Sie auf die rechte untere Ecke des Bereichs zwischen die Bildlaufleisten, um einen Teil des Bereichs **Datenquellensicht** auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="72d50-109">Click the lower right corner of the pane, between the scrollbars, to select an area of the **Data Source View** pane to view.</span></span>  
  
## <a name="diagram-context-menu"></a><span data-ttu-id="72d50-110">Diagramm (Kontextmenü)</span><span class="sxs-lookup"><span data-stu-id="72d50-110">Diagram Context Menu</span></span>  
 <span data-ttu-id="72d50-111">Wenn Sie mit der rechten Maustaste auf den Diagrammhintergrund im Bereich **Datenquellensicht** klicken, wird ein Kontextmenü angezeigt, das die folgenden Optionen enthält:</span><span class="sxs-lookup"><span data-stu-id="72d50-111">The following options are available in the context menu displayed by right-clicking the diagram background of the **Data Source View** pane:</span></span>  
  
 <span data-ttu-id="72d50-112">**Show Tables**</span><span class="sxs-lookup"><span data-stu-id="72d50-112">**Show Tables**</span></span>  
 <span data-ttu-id="72d50-113">Zeigt das Dialogfeld **Tabelle anzeigen** an.</span><span class="sxs-lookup"><span data-stu-id="72d50-113">Displays the **Show Table** dialog box.</span></span> <span data-ttu-id="72d50-114">Weitere Informationen zum Dialogfeld **Tabelle anzeigen** finden Sie unter [Dialogfeld „Tabelle anzeigen“ &#40;Analysis Services – Mehrdimensionale Daten&#41;](show-table-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="72d50-114">For more information about the **Show Table** dialog box, see [Show Table Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](show-table-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="72d50-115">**Alle Tabellen anzeigen**</span><span class="sxs-lookup"><span data-stu-id="72d50-115">**Show All Tables**</span></span>  
 <span data-ttu-id="72d50-116">Zeigt in dem Bereich alle in der Datenquellensicht enthaltenen Tabellen an, die dem Cube zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="72d50-116">Displays in the pane all tables included in the data source view associated with the cube.</span></span>  
  
 <span data-ttu-id="72d50-117">**Nur verwendete Tabellen anzeigen**</span><span class="sxs-lookup"><span data-stu-id="72d50-117">**Show Only Used Tables**</span></span>  
 <span data-ttu-id="72d50-118">Zeigt in dem Bereich nur die Tabellen aus der zugeordneten Datenquellensicht an, die vom Cube verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="72d50-118">Displays in the pane only those tables used by the cube from the associated data source view.</span></span>  
  
 <span data-ttu-id="72d50-119">**Anzeigen Amen anzeigen**</span><span class="sxs-lookup"><span data-stu-id="72d50-119">**Show Friendly Names**</span></span>  
 <span data-ttu-id="72d50-120">Wählen Sie diese Option aus, um für die Objekte im Bereich die Anzeigenamen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="72d50-120">Selects to show friendly names for the objects in the pane.</span></span>  
  
 <span data-ttu-id="72d50-121">**Alles markieren**</span><span class="sxs-lookup"><span data-stu-id="72d50-121">**Select All**</span></span>  
 <span data-ttu-id="72d50-122">Wählt alle Objekte im Bereich aus.</span><span class="sxs-lookup"><span data-stu-id="72d50-122">Selects all of the objects in the pane.</span></span>  
  
 <span data-ttu-id="72d50-123">**Tabelle suchen**</span><span class="sxs-lookup"><span data-stu-id="72d50-123">**Find Table**</span></span>  
 <span data-ttu-id="72d50-124">Zeigt das Dialogfeld **Tabelle suchen** an.</span><span class="sxs-lookup"><span data-stu-id="72d50-124">Displays the **Find Table** dialog box.</span></span> <span data-ttu-id="72d50-125">Weitere Informationen zum Dialogfeld **Tabelle suchen** finden Sie unter [Dialogfeld „Tabelle suchen“ &#40;Analysis Services – Mehrdimensionale Daten&#41;](find-table-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="72d50-125">For more information about the **Find Table** dialog box, see [Find Table Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](find-table-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="72d50-126">**Tabellen anordnen**</span><span class="sxs-lookup"><span data-stu-id="72d50-126">**Arrange Tables**</span></span>  
 <span data-ttu-id="72d50-127">Ordnet die Objekte im Bereich in dem Layout an, das durch das Auswählen von **Zu diagonalem Layout wechseln** oder **Zu rechteckigem Layout wechseln**angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="72d50-127">Arranges the objects in the pane according to the layout specified by selecting either **Switch to Diagonal Layout** or **Switch to Rectangular Layout**.</span></span>  
  
 <span data-ttu-id="72d50-128">**Zu diagonalem Layout wechseln**</span><span class="sxs-lookup"><span data-stu-id="72d50-128">**Switch to Diagonal Layout**</span></span>  
 <span data-ttu-id="72d50-129">Mit dieser Option werden die Objekte diagonal angeordnet.</span><span class="sxs-lookup"><span data-stu-id="72d50-129">Select to arrange objects in a diagonal pattern.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="72d50-130">Diese Option wird nur angezeigt, wenn **Zu rechteckigem Layout wechseln** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="72d50-130">This option is displayed only if **Switch to Rectangular Layout** is selected.</span></span>  
  
 <span data-ttu-id="72d50-131">**Zu rechteckigem Layout wechseln**</span><span class="sxs-lookup"><span data-stu-id="72d50-131">**Switch to Rectangular Layout**</span></span>  
 <span data-ttu-id="72d50-132">Mit dieser Option werden die Objekte in einem Rechteckmuster angeordnet.</span><span class="sxs-lookup"><span data-stu-id="72d50-132">Select to arrange objects in a rectangular pattern.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="72d50-133">Diese Option wird nur angezeigt, wenn **Zu diagonalem Layout wechseln** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="72d50-133">This option is displayed only if **Switch to Diagonal Layout** is selected.</span></span>  
  
 <span data-ttu-id="72d50-134">**Datenquellensicht bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="72d50-134">**Edit Data Source View**</span></span>  
 <span data-ttu-id="72d50-135">Zeigt den Datenquellensicht-Designer für die dem Objekt zugeordnete Datenquellensicht an.</span><span class="sxs-lookup"><span data-stu-id="72d50-135">Displays Data Source View Designer for the data source view associated with the object.</span></span> <span data-ttu-id="72d50-136">Weitere Informationen zum Datenquellensicht-Designer finden Sie unter [Datenquellensicht-Designer &#40;Analysis Services – Mehrdimensionale Daten&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="72d50-136">For more information about Data Source View Designer, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="72d50-137">**Datenquellensicht anzeigen in**</span><span class="sxs-lookup"><span data-stu-id="72d50-137">**Show Data Source View In**</span></span>  
 <span data-ttu-id="72d50-138">Wählen Sie eine der folgenden Optionen aus, um zwischen den folgenden Anzeigemodi für den Bereich **Datenquellensicht** zu wechseln:</span><span class="sxs-lookup"><span data-stu-id="72d50-138">Select one of the following options to toggle between viewing the **Data Source View** pane in the following modes:</span></span>  
  
-   <span data-ttu-id="72d50-139">Diagramm</span><span class="sxs-lookup"><span data-stu-id="72d50-139">Diagram</span></span>  
  
     <span data-ttu-id="72d50-140">Zeigt ein Diagramm mit Tabellen und Spalten an, die dem aktuellen Cube zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="72d50-140">Displays a diagram of the tables and columns associated with the current cube.</span></span>  
  
-   <span data-ttu-id="72d50-141">Struktur</span><span class="sxs-lookup"><span data-stu-id="72d50-141">Tree</span></span>  
  
     <span data-ttu-id="72d50-142">Zeigt eine Strukturansicht mit Tabellen und Spalten an, die dem aktuellen Cube zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="72d50-142">Displays a tree view containing the tables and columns associated with the current cube.</span></span>  
  
 <span data-ttu-id="72d50-143">**Diagramm kopieren von**</span><span class="sxs-lookup"><span data-stu-id="72d50-143">**Copy Diagram From**</span></span>  
 <span data-ttu-id="72d50-144">Wählen Sie eines der Diagramme aus der Datenquellensicht aus, die dem Cube zugeordnet ist, um es im Bereich **Datenquellensicht** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="72d50-144">Select one of the diagrams included in the data source view associated with the cube to display it in the **Data Source View** pane.</span></span>  
  
 <span data-ttu-id="72d50-145">**Zoom**</span><span class="sxs-lookup"><span data-stu-id="72d50-145">**Zoom**</span></span>  
 <span data-ttu-id="72d50-146">Wählen Sie eine verfügbare Zoomoption aus.</span><span class="sxs-lookup"><span data-stu-id="72d50-146">Select an available zoom option.</span></span>  
  
 <span data-ttu-id="72d50-147">**Eigenschaften**</span><span class="sxs-lookup"><span data-stu-id="72d50-147">**Properties**</span></span>  
 <span data-ttu-id="72d50-148">Zeigt das Fenster **Eigenschaften** für die Datenquellensicht in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] an, die dem Cube zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="72d50-148">Displays the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] for the data source view associated with the cube.</span></span>  
  
## <a name="table-context-menu"></a><span data-ttu-id="72d50-149">Tabelle (Kontextmenü)</span><span class="sxs-lookup"><span data-stu-id="72d50-149">Table Context Menu</span></span>  
 <span data-ttu-id="72d50-150">Wenn Sie mit der rechten Maustaste auf den Namen einer Tabelle oder einer Sicht im Bereich **Datenquellensicht** klicken, wird ein Kontextmenü angezeigt, das die folgenden Optionen enthält:</span><span class="sxs-lookup"><span data-stu-id="72d50-150">The following options are available in the context menu displayed by right-clicking the name of a table or view in the **Data Source View** pane:</span></span>  
  
 <span data-ttu-id="72d50-151">**Verknüpfte Tabellen anzeigen**</span><span class="sxs-lookup"><span data-stu-id="72d50-151">**Show Related Tables**</span></span>  
 <span data-ttu-id="72d50-152">Zeigt die Tabellen im Bereich an, die mit der in der Datenquellensicht ausgewählten Tabelle verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="72d50-152">Displays in the pane the tables related to the selected table in the data source view.</span></span>  
  
 <span data-ttu-id="72d50-153">**Tabelle ausblenden**</span><span class="sxs-lookup"><span data-stu-id="72d50-153">**Hide Table**</span></span>  
 <span data-ttu-id="72d50-154">Entfernt die Tabelle aus dem Bereich.</span><span class="sxs-lookup"><span data-stu-id="72d50-154">Removes the table from the pane.</span></span>  
  
 <span data-ttu-id="72d50-155">**Daten durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="72d50-155">**Explore Data**</span></span>  
 <span data-ttu-id="72d50-156">Zeigen Sie das Dialogfeld **Daten durchsuchen** für die ausgewählte Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="72d50-156">Display the **Explore Data** dialog box for the selected table.</span></span>  
  
 <span data-ttu-id="72d50-157">**Datenquellensicht bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="72d50-157">**Edit Data Source View**</span></span>  
 <span data-ttu-id="72d50-158">Zeigt den Datenquellensicht-Designer für die Datenquellensicht an, die die ausgewählte Tabelle enthält.</span><span class="sxs-lookup"><span data-stu-id="72d50-158">Displays Data Source View Designer for the data source view that contains the selected table.</span></span> <span data-ttu-id="72d50-159">Weitere Informationen zum Datenquellensicht-Designer finden Sie unter [Datenquellensicht-Designer &#40;Analysis Services – Mehrdimensionale Daten&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="72d50-159">For more information about Data Source View Designer, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="72d50-160">**Neue Measuregruppe aus Tabelle**</span><span class="sxs-lookup"><span data-stu-id="72d50-160">**New Measure Group from Table**</span></span>  
 <span data-ttu-id="72d50-161">Definiert auf Grundlage der ausgewählten Tabelle eine neue Measuregruppe im Bereich **Measures** .</span><span class="sxs-lookup"><span data-stu-id="72d50-161">Defines a new measure group in the **Measures** pane based on the selected table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="72d50-162">Diese Option ist nur verfügbar, wenn noch keine Measuregruppe im Bereich **Measures** auf die Tabelle verweist.</span><span class="sxs-lookup"><span data-stu-id="72d50-162">This option is enabled only if the table is not yet referenced by a measure group in the **Measures** pane.</span></span>  
  
 <span data-ttu-id="72d50-163">**Eigenschaften**</span><span class="sxs-lookup"><span data-stu-id="72d50-163">**Properties**</span></span>  
 <span data-ttu-id="72d50-164">Zeigt in **das Fenster** Eigenschaften [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] für die ausgewählte Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="72d50-164">Displays the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] for the selected table.</span></span>  
  
## <a name="column-context-menu"></a><span data-ttu-id="72d50-165">Spalte (Kontextmenü)</span><span class="sxs-lookup"><span data-stu-id="72d50-165">Column Context Menu</span></span>  
 <span data-ttu-id="72d50-166">Wenn Sie mit der rechten Maustaste auf den Namen einer Spalte in einer Tabelle oder einer Sicht im Bereich **Datenquellensicht** klicken, wird ein Kontextmenü angezeigt, das die folgenden Optionen enthält:</span><span class="sxs-lookup"><span data-stu-id="72d50-166">The following options are available in the context menu displayed by right-clicking the name of a column in a table or view in the **Data Source View** pane:</span></span>  
  
 <span data-ttu-id="72d50-167">**Neues Measure aus Spalte**</span><span class="sxs-lookup"><span data-stu-id="72d50-167">**New Measure from Column**</span></span>  
 <span data-ttu-id="72d50-168">Definiert auf Grundlage der ausgewählten Spalte eine neue Measuregruppe im Bereich **Measures** .</span><span class="sxs-lookup"><span data-stu-id="72d50-168">Defines a new measure in the **Measures** pane based on the selected column.</span></span>  
  
 <span data-ttu-id="72d50-169">**Daten durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="72d50-169">**Explore Data**</span></span>  
 <span data-ttu-id="72d50-170">Zeigt das Dialogfeld **Daten durchsuchen** für die Tabelle mit der ausgewählten Spalte an.</span><span class="sxs-lookup"><span data-stu-id="72d50-170">Display the **Explore Data** dialog box for the table that contains the selected column.</span></span>  
  
 <span data-ttu-id="72d50-171">**Datenquellensicht bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="72d50-171">**Edit Data Source View**</span></span>  
 <span data-ttu-id="72d50-172">Zeigt den Datenquellensicht-Designer für die Datenquellensicht an, die die ausgewählte Spalte enthält.</span><span class="sxs-lookup"><span data-stu-id="72d50-172">Displays Data Source View Designer for the data source view that contains the selected column.</span></span> <span data-ttu-id="72d50-173">Weitere Informationen zum Datenquellensicht-Designer finden Sie unter [Datenquellensicht-Designer &#40;Analysis Services – Mehrdimensionale Daten&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="72d50-173">For more information about Data Source View Designer, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="72d50-174">**Eigenschaften**</span><span class="sxs-lookup"><span data-stu-id="72d50-174">**Properties**</span></span>  
 <span data-ttu-id="72d50-175">Zeigt in **das Fenster** Eigenschaften [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] für die ausgewählte Spalte an.</span><span class="sxs-lookup"><span data-stu-id="72d50-175">Displays the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] for the selected column.</span></span>  
  
## <a name="relationship-context-menu"></a><span data-ttu-id="72d50-176">Beziehung (Kontextmenü)</span><span class="sxs-lookup"><span data-stu-id="72d50-176">Relationship Context Menu</span></span>  
 <span data-ttu-id="72d50-177">Die folgenden Optionen sind im Kontextmenü verfügbar, das angezeigt wird, wenn Sie im Bereich **Datenquellensicht** mit der rechten Maustaste auf eine Beziehung klicken:</span><span class="sxs-lookup"><span data-stu-id="72d50-177">The following options are available in the context menu displayed by right-clicking a relationship in the **Data Source View** pane:</span></span>  
  
 <span data-ttu-id="72d50-178">**Datenquellensicht bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="72d50-178">**Edit Data Source View**</span></span>  
 <span data-ttu-id="72d50-179">Zeigt den Datenquellensicht-Designer für die Datenquellensicht an, die die ausgewählte Beziehung enthält.</span><span class="sxs-lookup"><span data-stu-id="72d50-179">Displays Data Source View Designer for the data source view that contains the selected relationship.</span></span> <span data-ttu-id="72d50-180">Weitere Informationen zum Datenquellensicht-Designer finden Sie unter [Datenquellensicht-Designer &#40;Analysis Services – Mehrdimensionale Daten&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="72d50-180">For more information about Data Source View Designer, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="72d50-181">**Eigenschaften**</span><span class="sxs-lookup"><span data-stu-id="72d50-181">**Properties**</span></span>  
 <span data-ttu-id="72d50-182">Zeigt in **das Fenster** Eigenschaften [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] für die ausgewählte Beziehung an.</span><span class="sxs-lookup"><span data-stu-id="72d50-182">Displays the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] for the selected relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72d50-183">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="72d50-183">See Also</span></span>  
 <span data-ttu-id="72d50-184">[Symbolleiste &#40;Registerkarte "Cubestruktur", Cube-Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;](toolbar-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="72d50-184">[Toolbar &#40;Cube Structure Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="72d50-185">[Measures &#40;Registerkarte "Cubestruktur", Cube-Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;](measures-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="72d50-185">[Measures &#40;Cube Structure Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](measures-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="72d50-186">[Dimensionen &#40;Registerkarte "Cubestruktur", Cube-Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;](dimensions-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="72d50-186">[Dimensions &#40;Cube Structure Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](dimensions-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="72d50-187">Cubestruktur &#40;Cube-Designer-&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="72d50-187">Cube Structure &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](cube-structure-cube-designer-analysis-services-multidimensional-data.md)  
  
  
