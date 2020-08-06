---
title: Drillthrough-Aktions Formular-Editor (Registerkarte Aktionen, Cube-Designer) (Analysis Services-Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.actionexpression.drillthroughaction.f1
ms.assetid: 225fd818-b5ea-494f-b67b-66e09798274a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 546448bd05f3af45b7093acb2dbb9d1e1a8f1bd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621245"
---
# <a name="drillthrough-action-form-editor-actions-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="42a44-102">Drillthroughaktionsformular-Editor (Registerkarte 'Aktionen', Cube-Designer) (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="42a44-102">Drillthrough Action Form Editor (Actions Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="42a44-103">Im Bereich des **Drillthroughaktionsformular-Editors** auf der Registerkarte **Aktionen** des Cube-Designers können Sie die im Bereich **Aktionsplaner** ausgewählte Drillthroughaktion ändern.</span><span class="sxs-lookup"><span data-stu-id="42a44-103">Use the **Drillthrough Action Form Editor** pane on the **Actions** tab in Cube Designer to modify the drillthrough action selected in the **Action Organizer** pane.</span></span> <span data-ttu-id="42a44-104">Weitere Informationen zu Drillthroughaktionen finden Sie unter [Aktionen &#40;Analysis Services – mehrdimensionale Daten&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="42a44-104">For more information about drillthrough actions, see [Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42a44-105">Durch die Drillthroughaktionen wird kein Drilldown zum zugrunde liegenden Datenspeicher mehr ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="42a44-105">Drillthrough actions no longer drill down to the underlying data store.</span></span> <span data-ttu-id="42a44-106">Die Informationen, auf die die Drillthroughaktionen zugreifen, müssen im Cube mithilfe von Dimensions- oder Hierarchieelementen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="42a44-106">The information that drillthrough actions access must be modeled within the cube by using dimension or hierarchy members.</span></span>  
  
## <a name="options"></a><span data-ttu-id="42a44-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="42a44-107">Options</span></span>  
 <span data-ttu-id="42a44-108">**name**</span><span class="sxs-lookup"><span data-stu-id="42a44-108">**name**</span></span>  
 <span data-ttu-id="42a44-109">Geben Sie den Namen der Aktion ein.</span><span class="sxs-lookup"><span data-stu-id="42a44-109">Type the name of the action.</span></span>  
  
 <span data-ttu-id="42a44-110">**Aktionsziel**</span><span class="sxs-lookup"><span data-stu-id="42a44-110">**Action Target**</span></span>  
 <span data-ttu-id="42a44-111">Erweitern Sie dieses Element, um die Option **Measuregruppenelemente** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="42a44-111">Expand to view the **Measure group members** option.</span></span>  
  
 <span data-ttu-id="42a44-112">**Measuregruppenelemente**</span><span class="sxs-lookup"><span data-stu-id="42a44-112">**Measure group members**</span></span>  
 <span data-ttu-id="42a44-113">Wählen Sie die Measuregruppe aus, der die Drillthroughaktion zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="42a44-113">Select the measure group to which the drillthrough action is to be associated.</span></span>  
  
 <span data-ttu-id="42a44-114">**Bedingung (Optional)**</span><span class="sxs-lookup"><span data-stu-id="42a44-114">**Condition (Optional)**</span></span>  
 <span data-ttu-id="42a44-115">Geben Sie einen MDX-Ausdruck (Multidimensional Expressions) ein, der eine optionale Bedingung beschreibt, die in Verbindung mit **Measuregruppenelemente**verwendet werden soll, um die Verfügbarkeit der Aktion weiter einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="42a44-115">Enter the Multidimensional Expressions (MDX) expression that describes an optional condition, used in conjunction with **Measure group members**, which further restricts when the action is available.</span></span> <span data-ttu-id="42a44-116">Der Ausdruck muss einen booleschen Wert zurückgeben, der mit "True" anzeigt, dass die Aktion verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="42a44-116">The expression must return a Boolean value that, if true, indicates the action is available.</span></span>  
  
 <span data-ttu-id="42a44-117">Ziehen Sie ausgewählte Elemente aus dem Bereich **Berechnungstools** auf diese Option, um die MDX-Syntax für das ausgewählte Element einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="42a44-117">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="42a44-118">**Drillthroughspalten**</span><span class="sxs-lookup"><span data-stu-id="42a44-118">**Drillthrough Columns**</span></span>  
 <span data-ttu-id="42a44-119">Erweitern Sie dieses Element, um ein Raster zur Kennzeichnung der Attribute anzuzeigen, die zurückgegeben werden, wenn der Benutzer diese Aktion ausführt.</span><span class="sxs-lookup"><span data-stu-id="42a44-119">Expand to display a grid in which to indicate the attributes that are returned when the user runs this action.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42a44-120">Sie können zwar mehrere Dimensionen auswählen, jede Dimension kann jedoch nur einmal in einer Drillthroughaktion verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="42a44-120">You can select more than one dimension, but no dimension can be used more than once in a drillthrough action.</span></span>  
  
 <span data-ttu-id="42a44-121">Das Raster enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="42a44-121">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="42a44-122">Spalte</span><span class="sxs-lookup"><span data-stu-id="42a44-122">Column</span></span>|<span data-ttu-id="42a44-123">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="42a44-123">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="42a44-124">**Dimensionen**</span><span class="sxs-lookup"><span data-stu-id="42a44-124">**Dimensions**</span></span>|<span data-ttu-id="42a44-125">Wählen Sie die Dimension aus, aus der das zurückgegebene Attribut stammt.</span><span class="sxs-lookup"><span data-stu-id="42a44-125">Select the dimension from which the returned attribute is derived.</span></span> <span data-ttu-id="42a44-126">Um das Drillthrough für Measures auszuführen, wählen Sie MEASURES aus.</span><span class="sxs-lookup"><span data-stu-id="42a44-126">Select MEASURES to drillthrough on measures.</span></span>|  
|<span data-ttu-id="42a44-127">**Rückgabespalten**</span><span class="sxs-lookup"><span data-stu-id="42a44-127">**Return Columns**</span></span>|<span data-ttu-id="42a44-128">Wählen Sie das Attribut oder Measure aus der ausgewählten Dimension aus, das bei Ausführung der Aktion zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="42a44-128">Select the attribute or measure from the selected dimension to be returned when the action is run.</span></span>|  
  
 <span data-ttu-id="42a44-129">**Zusätzliche Eigenschaften**</span><span class="sxs-lookup"><span data-stu-id="42a44-129">**Additional Properties**</span></span>  
 <span data-ttu-id="42a44-130">Erweitern Sie dieses Element, um die Optionen **Standard**, **Maximale Zeilenanzahl**, **Aufruf**, **Anwendung**, **Beschreibung**, **Beschriftung**und **Beschriftung ist MDX** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="42a44-130">Expand to view the **Default**, **Maximum rows**, **Invocation**, **Application**, **Description**, **Caption**, and **Caption Is MDX** options.</span></span>  
  
 <span data-ttu-id="42a44-131">**Standard**</span><span class="sxs-lookup"><span data-stu-id="42a44-131">**Default**</span></span>  
 <span data-ttu-id="42a44-132">Wählen Sie **True** aus, um diese Drillthroughaktion als Standarddrillthroughaktion einzuschließen. Andernfalls wählen Sie **False**aus.</span><span class="sxs-lookup"><span data-stu-id="42a44-132">Select **True** to include this drillthrough action as a default drillthrough action, otherwise, select **False**.</span></span>  
  
 <span data-ttu-id="42a44-133">Wenn die- `RETURN` Klausel in einer MDX `DRILLTHROUGH` -Anweisung ausgelassen wird, die von einer Client Anwendung ausgeführt wird, wertet die [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Instanz alle standardmäßigen Drillthrough-Aktionen aus und führt die erste standardmäßige Drillthrough-Aktion aus, die eine nicht leere Gruppe zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="42a44-133">If the `RETURN` clause is omitted from an MDX `DRILLTHROUGH` statement executed by a client application, the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance evaluates all default drillthrough actions and runs the first default drillthrough action that returns a non-empty set.</span></span> <span data-ttu-id="42a44-134">Weitere Informationen zur MDX- `DRILLTHROUGH` Anweisung finden Sie unter [DRILLTHROUGH-Anweisung &#40;MDX-&#41;](/sql/mdx/mdx-data-manipulation-drillthrough).</span><span class="sxs-lookup"><span data-stu-id="42a44-134">For more information about the MDX `DRILLTHROUGH` statement, see [DRILLTHROUGH Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-drillthrough).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42a44-135">Diese Option wird im Interesse der Abwärtskompatibilität verwendet.</span><span class="sxs-lookup"><span data-stu-id="42a44-135">This option is used for backwards compatibility purposes.</span></span>  
  
 <span data-ttu-id="42a44-136">**Maximale Zeilenanzahl**</span><span class="sxs-lookup"><span data-stu-id="42a44-136">**Maximum rows**</span></span>  
 <span data-ttu-id="42a44-137">Geben Sie die maximale Anzahl der Zeilen ein, die durch die Drillthroughaktion zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="42a44-137">Type the maximum number of rows to be returned by the drillthrough action.</span></span> <span data-ttu-id="42a44-138">Wenn für diese Option null oder ein leerer Wert festgelegt wird, werden durch die Drillthroughaktion alle Zeilen zurückgegeben, die durch die Aktion für die Clientanwendung abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="42a44-138">Setting this option to zero or an empty value indicates that the drillthrough action returns all rows retrieved by the action to the client application.</span></span>  
  
 <span data-ttu-id="42a44-139">**Aufruf**</span><span class="sxs-lookup"><span data-stu-id="42a44-139">**Invocation**</span></span>  
 <span data-ttu-id="42a44-140">Wählen Sie die Einstellung aus, durch die angegeben wird, wann die Aktion ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="42a44-140">Select the setting that indicates when the action should be carried out.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42a44-141">Diese Option stellt einer Clientanwendung nur eine Empfehlung für den Ausführungszeitpunkt einer Aktion zur Verfügung. Sie steuert nicht direkt den Aufruf der Aktion.</span><span class="sxs-lookup"><span data-stu-id="42a44-141">This option only provides a recommendation to a client application as to when to execute an action, and does not directly control the invocation of the action.</span></span>  
  
 <span data-ttu-id="42a44-142">Die folgende Tabelle beschreibt die verfügbaren Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="42a44-142">The following table describes the available settings.</span></span>  
  
|<span data-ttu-id="42a44-143">Wert</span><span class="sxs-lookup"><span data-stu-id="42a44-143">Value</span></span>|<span data-ttu-id="42a44-144">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="42a44-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="42a44-145">Batch</span><span class="sxs-lookup"><span data-stu-id="42a44-145">Batch</span></span>|<span data-ttu-id="42a44-146">Die Aktion sollte als Teil eines Batchvorgangs oder eines [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Tasks ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="42a44-146">The action should run as part of a batch operation or an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] task.</span></span>|  
|<span data-ttu-id="42a44-147">Interactive</span><span class="sxs-lookup"><span data-stu-id="42a44-147">Interactive</span></span>|<span data-ttu-id="42a44-148">Die Aktion wird ausgeführt, wenn der Benutzer die Aktion aufruft.</span><span class="sxs-lookup"><span data-stu-id="42a44-148">The action runs when the user invokes the action.</span></span>|  
|<span data-ttu-id="42a44-149">Beim Öffnen</span><span class="sxs-lookup"><span data-stu-id="42a44-149">On Open</span></span>|<span data-ttu-id="42a44-150">Die Aktion wird ausgeführt, wenn der Cube erstmalig geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="42a44-150">The action runs when the cube is first opened.</span></span>|  
  
 <span data-ttu-id="42a44-151">**Anwendung**</span><span class="sxs-lookup"><span data-stu-id="42a44-151">**Application**</span></span>  
 <span data-ttu-id="42a44-152">Geben Sie den Namen der Anwendung ein, durch die die Drillthroughaktion ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="42a44-152">Type the name of the application that can execute the drillthrough action.</span></span>  
  
 <span data-ttu-id="42a44-153">Sie können diese Option auch verwenden, um zu ermitteln, welche Clientanwendung diese Aktion am häufigsten verwendet, oder um entsprechende Symbole neben der Aktion in einem Popupmenü anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="42a44-153">You can also use this option to identify which client application most commonly uses this action, as well as to display appropriate icons next to the action in a pop-up menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42a44-154">Diese Option stellt nur eine Empfehlung für eine Clientanwendung bereit, die angibt, welche Clientanwendung eine Aktion ausführen soll. Sie steuert nicht direkt den Zugriff auf die Aktion.</span><span class="sxs-lookup"><span data-stu-id="42a44-154">This option only provides a recommendation to a client application as to what client application should execute an action, and does not directly control access to the action.</span></span> <span data-ttu-id="42a44-155">Clientanwendungen sollten alle Aktionen ausblenden, die anderen Clientanwendungen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="42a44-155">Client applications should hide any actions that are associated with other client applications.</span></span>  
  
 <span data-ttu-id="42a44-156">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="42a44-156">**Description**</span></span>  
 <span data-ttu-id="42a44-157">Geben Sie die optionale Beschreibung der Aktion ein.</span><span class="sxs-lookup"><span data-stu-id="42a44-157">Type the optional description of the action.</span></span>  
  
 <span data-ttu-id="42a44-158">**Caption**</span><span class="sxs-lookup"><span data-stu-id="42a44-158">**Caption**</span></span>  
 <span data-ttu-id="42a44-159">Geben Sie die Beschriftung ein, die für die Aktion in der Clientanwendung angezeigt wird, wenn **Beschriftung ist MDX** auf **FALSE**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="42a44-159">Type the caption to be displayed for the action in the client application if **Caption Is MDX** is set to **False**.</span></span>  
  
 <span data-ttu-id="42a44-160">Geben Sie den MDX-Ausdruck (Multidimensional Expressions) ein, der eine Zeichenfolge für die Beschriftung zurückgibt, wenn **Beschriftung ist MDX** auf **TRUE**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="42a44-160">Type the Multidimensional Expressions (MDX) expression that returns a string for the caption if **Caption Is MDX** is set to **True**.</span></span>  
  
 <span data-ttu-id="42a44-161">**Beschriftung ist MDX**</span><span class="sxs-lookup"><span data-stu-id="42a44-161">**Caption Is MDX**</span></span>  
 <span data-ttu-id="42a44-162">Wählen Sie **FALSE** aus, um anzuzeigen, dass **Beschriftung** eine Literalzeichenfolge enthält, die eine Beschriftung darstellt, welche für die Aktion in der Clientanwendung angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="42a44-162">Select **False** to indicate that **Caption** contains a literal string representing a caption to be displayed for the action in the client application.</span></span>  
  
 <span data-ttu-id="42a44-163">Wählen Sie **True** aus, um anzuzeigen, dass **Beschriftung** einen MDX-Ausdruck enthält, der eine Zeichenfolge mit einer Beschriftung zurückgibt, die für die Aktion in der Clientanwendung angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="42a44-163">Select **True** to indicate that **Caption** contains an MDX expression that returns a string representing a caption to be displayed for the action in the client application.</span></span> <span data-ttu-id="42a44-164">Der MDX-Ausdruck muss aufgelöst werden, bevor die Aktion an die Clientanwendung zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="42a44-164">The MDX expression must be resolved before the action is returned to the client application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42a44-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="42a44-165">See Also</span></span>  
 <span data-ttu-id="42a44-166">[Mehrdimensionale Ausdrücke &#40;MDX-&#41; Referenz](/sql/mdx/multidimensional-expressions-mdx-reference) </span><span class="sxs-lookup"><span data-stu-id="42a44-166">[Multidimensional Expressions &#40;MDX&#41; Reference](/sql/mdx/multidimensional-expressions-mdx-reference) </span></span>  
 <span data-ttu-id="42a44-167">[Aktionen &#40;Cube-Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;](actions-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="42a44-167">[Actions &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](actions-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="42a44-168">[Symbolleiste &#40;Registerkarte "Aktionen", Cube-Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;](toolbar-actions-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="42a44-168">[Toolbar &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-actions-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="42a44-169">[Aktions Planer &#40;Registerkarte Aktionen, Cube-Designer&#41; &#40;Analysis Services-Mehrdimensionale Daten&#41;](action-organizer-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="42a44-169">[Action Organizer &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](action-organizer-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="42a44-170">[Berechnungs Tools &#40;Registerkarte "Aktionen", Cube-Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;](calculation-tools-actions-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="42a44-170">[Calculation Tools &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculation-tools-actions-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="42a44-171">[Aktions Formular-Editor &#40;Registerkarte Aktionen, Cube-Designer&#41; &#40;Analysis Services-Mehrdimensionale Daten&#41;](action-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="42a44-171">[Action Form Editor &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](action-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="42a44-172">Berichts Aktions Formular-Editor &#40;Registerkarte Aktionen, Cube-Designer&#41; &#40;Analysis Services-Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="42a44-172">Report Action Form Editor &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](report-action-form-editor-cube-designer-analysis-services-multidimensional-data.md)  
  
  
