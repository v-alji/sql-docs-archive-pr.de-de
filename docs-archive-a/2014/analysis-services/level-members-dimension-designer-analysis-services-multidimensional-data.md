---
title: Ebene und Elemente (Registerkarte ' Browser ', Dimensions-Designer) (Analysis Services-Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.browsertab.levelsandmembers.f1
ms.assetid: 3f61e384-5b4e-4480-a7ed-b408de2fdea7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 21680f00b82b5410e2c7a67122fdcfeb78c999dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727265"
---
# <a name="level-and-members-browser-tab-dimension-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="50213-102">Ebenen und Elemente (Registerkarte 'Browser', Dimensions-Designer) (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="50213-102">Level and Members (Browser Tab, Dimension Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="50213-103">In diesem Bereich können Sie die Elemente der aktuell ausgewählten Hierarchie und Sprache durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="50213-103">Use this pane to browse the members of the currently selected hierarchy and language.</span></span> <span data-ttu-id="50213-104">Verwenden Sie die Optionen **Hierarchie** und **Sprache** im Bereich **Symbolleiste** , um eine zu durchsuchende Hierarchie oder Sprache auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="50213-104">To select a hierarchy or language to browse, use the **Hierarchy** and **Language** options on the **Toolbar** pane.</span></span> <span data-ttu-id="50213-105">Weitere Informationen zum Symbolleistenbereich finden Sie unter [Toolbar &#40;Browser Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="50213-105">For more information about the Toolbar pane, see [Toolbar &#40;Browser Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="writeback-mode"></a><span data-ttu-id="50213-106">Rückschreibemodus</span><span class="sxs-lookup"><span data-stu-id="50213-106">Writeback Mode</span></span>  
 <span data-ttu-id="50213-107">Die Funktionalität dieses Bereichs ändert sich, wenn der Rückschreibemodus aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="50213-107">The functionality of this pane changes if writeback mode is enabled.</span></span> <span data-ttu-id="50213-108">Für die ausgewählte Dimension muss der Schreibzugriff aktiviert sein (anders ausgedrückt, die `WriteEnabled`-Eigenschaft der Dimension muss auf den Wert True festgelegt sein), und die Dimension muss für eine [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Instanz bereitgestellt werden, damit der Rückschreibemodus aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="50213-108">The selected dimension must be write-enabled (in other words, the `WriteEnabled` property of the dimension must be set to true) and the dimension must be deployed to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance in order to enable writeback mode.</span></span>  
  
 <span data-ttu-id="50213-109">Sie können entweder die Option **Rückschreiben** aus dem Bereich **Symbolleiste** auswählen oder mit der rechten Maustaste auf den Bereich **Ebene und Elemente** klicken und aus dem Kontextmenü die Option **Rückschreiben** auswählen, um den Rückschreibemodus zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="50213-109">To enable writeback mode, you can either select **Writeback** from the **Toolbar** pane, or right-click the **Level and Members** pane and select **Writeback** from the context menu.</span></span>  
  
 <span data-ttu-id="50213-110">Wenn der Rückschreibemodus aktiviert ist, können Sie die folgenden zusätzlichen Aktionen im Bereich \*\*\*\* für Ebene und Elemente ausführen:</span><span class="sxs-lookup"><span data-stu-id="50213-110">If writeback mode is enabled, you can perform the following additional actions in the **Level and Members** pane:</span></span>  
  
|<span data-ttu-id="50213-111">Folgendes ist zu erledigen</span><span class="sxs-lookup"><span data-stu-id="50213-111">To do</span></span>|<span data-ttu-id="50213-112">Funktion</span><span class="sxs-lookup"><span data-stu-id="50213-112">Perform</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="50213-113">Erstellen gleichgeordneter und untergeordneter Elemente innerhalb der ausgewählten Hierarchie</span><span class="sxs-lookup"><span data-stu-id="50213-113">Create sibling and child members within the selected hierarchy.</span></span>|<span data-ttu-id="50213-114">Klicken Sie mit der rechten Maustaste auf das ausgewählte Element, und wählen Sie aus dem Kontextmenü entweder **Gleichgeordnetes Element erstellen**aus, um ein gleichgeordnetes Element zu erstellen, oder **Untergeordnetes Element erstellen**, um ein untergeordnetes Element zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="50213-114">Right-click the selected member and select either **Create Sibling**, to create a sibling member, or **Create Child**, to create a child member, from the context menu.</span></span>|  
|<span data-ttu-id="50213-115">Verschieben eines ausgewählten Elements in der Hierarchie nach oben oder nach unten</span><span class="sxs-lookup"><span data-stu-id="50213-115">Move a selected member up or down the hierarchy.</span></span>|<span data-ttu-id="50213-116">Ziehen Sie das ausgewählte Element entweder auf das entsprechende über- bzw. untergeordnete Element, oder klicken Sie auf **Einzug vergrößern** bzw. **Einzug verkleinern** im Bereich **Symbolleiste** , um das ausgewählte Element in den Ebenen der Hierarchie noch oben bzw. unten zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="50213-116">Either drag the selected member to the appropriate parent or child member, or click **Increase Indent** or **Decrease Indent** on the **Toolbar** pane to move the selected member up or down the levels of the hierarchy.</span></span>|  
|<span data-ttu-id="50213-117">Umbenennen eines ausgewählten Elements</span><span class="sxs-lookup"><span data-stu-id="50213-117">Rename a selected member.</span></span>|<span data-ttu-id="50213-118">Klicken Sie entweder mit der rechten Maustaste auf das ausgewählte Element, und wählen Sie die Option **Umbenennen**aus, oder klicken Sie auf ein bereits ausgewähltes Element.</span><span class="sxs-lookup"><span data-stu-id="50213-118">Either right-click the selected member and select **Rename**, or click an already-selected member.</span></span>|  
|<span data-ttu-id="50213-119">Bearbeiten der Werte von Elementeigenschaften</span><span class="sxs-lookup"><span data-stu-id="50213-119">Edit member property values</span></span>|<span data-ttu-id="50213-120">Doppelklicken Sie auf den Wert in der ausgewählten Elementeigenschaft für das ausgewählte Element, um den Wert zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="50213-120">Double-click the value in the selected member property for the selected member to edit the value.</span></span>|  
  
## <a name="options"></a><span data-ttu-id="50213-121">Tastatur</span><span class="sxs-lookup"><span data-stu-id="50213-121">Options</span></span>  
 <span data-ttu-id="50213-122">**Aktuelle Ebene**</span><span class="sxs-lookup"><span data-stu-id="50213-122">**Current level**</span></span>  
 <span data-ttu-id="50213-123">Zeigt die Ebene an, zu der das aktuell ausgewählte Element unter **Struktur** gehört.</span><span class="sxs-lookup"><span data-stu-id="50213-123">Displays the level to which the currently selected member in **Tree** belongs.</span></span>  
  
 <span data-ttu-id="50213-124">**Linde**</span><span class="sxs-lookup"><span data-stu-id="50213-124">**Tree**</span></span>  
 <span data-ttu-id="50213-125">Zeigt die Elemente der aktuell ausgewählten Hierarchie und Sprache an.</span><span class="sxs-lookup"><span data-stu-id="50213-125">Displays the members of the currently selected hierarchy and language.</span></span>  
  
 <span data-ttu-id="50213-126">Wenn Elementeigenschaften aus der Option **Elementeigenschaften** des Symbolleistenbereichs ausgewählt werden, wird jede Elementeigenschaft als eine Spalte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="50213-126">If member properties are selected from the **Member Properties** option of the Toolbar pane, each member property is displayed as a column.</span></span>  
  
 <span data-ttu-id="50213-127">Wenn der Rückschreibemodus aktiviert ist, wird für jede Schlüsselspalte, der das Schlüsselattribut in der Dimension zugeordnet ist, eine Spalte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="50213-127">If writeback mode is enabled, one column for each key column associated with the key attribute in the dimension is displayed.</span></span>  
  
## <a name="context-menu"></a><span data-ttu-id="50213-128">Kontextmenü</span><span class="sxs-lookup"><span data-stu-id="50213-128">Context Menu</span></span>  
 <span data-ttu-id="50213-129">Die folgenden Optionen sind im Kontextmenü verfügbar, das durch Klicken mit der rechten Maustaste auf einen beliebigen Teil des Bereichs **Ebene und Elemente** für das ausgewählte Element angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="50213-129">The following options are available in the context menu displayed by right-clicking any part of the **Level and Members** pane for the selected member:</span></span>  
  
 <span data-ttu-id="50213-130">**Gleichgeordnetes Element erstellen**</span><span class="sxs-lookup"><span data-stu-id="50213-130">**Create sibling**</span></span>  
 <span data-ttu-id="50213-131">Erstellt ein neues Element auf derselben Ebene wie das ausgewählte Element.</span><span class="sxs-lookup"><span data-stu-id="50213-131">Creates a new member at the same level as the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50213-132">Diese Option ist nur verfügbar, wenn ein Element auf einer anderen Ebene als der Ebene (Alle) ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="50213-132">This option is enabled only if a member at a level other than the (All) level is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50213-133">Diese Option wird nur angezeigt, wenn der Rückschreibemodus aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="50213-133">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="50213-134">**Untergeordnetes Element erstellen**</span><span class="sxs-lookup"><span data-stu-id="50213-134">**Create child**</span></span>  
 <span data-ttu-id="50213-135">Erstellt ein neues Element auf der nächstniedrigeren Ebene, als untergeordnetes Element des ausgewählten Elements.</span><span class="sxs-lookup"><span data-stu-id="50213-135">Creates a new member at the next lower level as the selected member, as a child of the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50213-136">Diese Option ist nur verfügbar, wenn ein Element auf einer anderen Ebene als der untersten ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="50213-136">This option is enabled only if a member at a level other than the lowest level is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50213-137">Diese Option wird nur angezeigt, wenn der Rückschreibemodus aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="50213-137">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="50213-138">**Ausschneiden**</span><span class="sxs-lookup"><span data-stu-id="50213-138">**Cut**</span></span>  
 <span data-ttu-id="50213-139">Kopiert die ausgewählten Elemente in die Zwischenablage und entfernt sie aus der Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="50213-139">Copies the selected members to the clipboard and removes them from the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50213-140">Diese Option ist nur verfügbar, wenn ein anderes als das Element Alle ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="50213-140">This option is enabled only if a member other than the All member is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50213-141">Diese Option wird nur angezeigt, wenn der Rückschreibemodus aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="50213-141">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="50213-142">**Einfügen**</span><span class="sxs-lookup"><span data-stu-id="50213-142">**Paste**</span></span>  
 <span data-ttu-id="50213-143">Fügt die zuvor mithilfe der Option **Ausschneiden** entfernten Elemente direkt hinter dem ausgewählten Element ein.</span><span class="sxs-lookup"><span data-stu-id="50213-143">Pastes members previously removed using **Cut** immediately after the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50213-144">Diese Option wird nur angezeigt, wenn der Rückschreibemodus aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="50213-144">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="50213-145">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="50213-145">**Delete**</span></span>  
 <span data-ttu-id="50213-146">Entfernt die ausgewählten Elemente aus der Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="50213-146">Removes the selected members from the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50213-147">Diese Option ist nur verfügbar, wenn ein anderes als das Element Alle ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="50213-147">This option is enabled only if a member other than the All member is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50213-148">Diese Option wird nur angezeigt, wenn der Rückschreibemodus aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="50213-148">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="50213-149">**Umbenennen**</span><span class="sxs-lookup"><span data-stu-id="50213-149">**Rename**</span></span>  
 <span data-ttu-id="50213-150">Wählen Sie diese Option aus, um den Namen des ausgewählten Elements zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="50213-150">Select to edit the name of the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50213-151">Diese Option ist nur verfügbar, wenn ein anderes als das Element Alle ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="50213-151">This option is enabled only if a member other than the All member is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50213-152">Diese Option wird nur angezeigt, wenn der Rückschreibemodus aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="50213-152">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="50213-153">**Elemente filtern**</span><span class="sxs-lookup"><span data-stu-id="50213-153">**Filter Members**</span></span>  
 <span data-ttu-id="50213-154">Zeigt das Dialogfeld **Elemente filtern** an, mit dessen Hilfe Elemente gefiltert werden können, die unter **Ebene und Elemente** für die ausgewählte Hierarchie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="50213-154">Displays the **Filter Members** dialog box to filter members displayed in **Level and Members** for the selected hierarchy.</span></span> <span data-ttu-id="50213-155">Weitere Informationen zum Dialogfeld **Elemente filtern** finden Sie unter [Dialogfeld „Elemente filtern“ &#40;Analysis Services – Mehrdimensionale Daten&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="50213-155">For more information about the **Filter Members** dialog box, see [Filter Members Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="50213-156">**Alle aufklappen**</span><span class="sxs-lookup"><span data-stu-id="50213-156">**Expand All**</span></span>  
 <span data-ttu-id="50213-157">Erweitert alle Elemente unter **Struktur**.</span><span class="sxs-lookup"><span data-stu-id="50213-157">Expands all members in **Tree**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50213-158">Diese Option ist nur verfügbar, wenn ein Element auf einer anderen Ebene als der untersten ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="50213-158">This option is enabled only if a member at a level other than the lowest level is selected.</span></span>  
  
 <span data-ttu-id="50213-159">**Alle reduzieren**</span><span class="sxs-lookup"><span data-stu-id="50213-159">**Collapse All**</span></span>  
 <span data-ttu-id="50213-160">Reduziert alle Elemente unter **Struktur**.</span><span class="sxs-lookup"><span data-stu-id="50213-160">Collapse all members in **Tree**.</span></span>  
  
 <span data-ttu-id="50213-161">**Element erweitern**</span><span class="sxs-lookup"><span data-stu-id="50213-161">**Expand Member**</span></span>  
 <span data-ttu-id="50213-162">Erweitert das ausgewählte Element unter **Struktur**.</span><span class="sxs-lookup"><span data-stu-id="50213-162">Expand the selected member in **Tree**.</span></span>  
  
 <span data-ttu-id="50213-163">**Element reduzieren**</span><span class="sxs-lookup"><span data-stu-id="50213-163">**Collapse Member**</span></span>  
 <span data-ttu-id="50213-164">Reduziert das ausgewählte Element unter **Struktur**.</span><span class="sxs-lookup"><span data-stu-id="50213-164">Collapse the selected member in **Tree**.</span></span>  
  
 <span data-ttu-id="50213-165">**Rückschreiben**</span><span class="sxs-lookup"><span data-stu-id="50213-165">**Writeback**</span></span>  
 <span data-ttu-id="50213-166">Wählen Sie diese Option aus, um den Rückschreibemodus zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="50213-166">Select to enable writeback mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50213-167">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50213-167">See Also</span></span>  
 <span data-ttu-id="50213-168">[Symbolleiste &#40;Registerkarte "Browser", Dimensions-Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="50213-168">[Toolbar &#40;Browser Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="50213-169">Browser &#40;Dimensions-Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="50213-169">Browser &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browser-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
