---
title: Gruppierungsbereich | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10033"
- sql12.rtp.rptdesigner.group.f1
helpviewer_keywords:
- Grouping Pane dialog box
ms.assetid: 8b4bd0b3-ec97-48f8-8bfb-82a53a2f35a1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8fc46055cb66a42b0662fbfcb3296373a7d10edb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700713"
---
# <a name="grouping-pane"></a><span data-ttu-id="92bf1-102">Gruppierungsbereich</span><span class="sxs-lookup"><span data-stu-id="92bf1-102">Grouping Pane</span></span>
  <span data-ttu-id="92bf1-103">Im Gruppierungsbereich werden die Zeilengruppen und Spaltengruppen für den derzeit ausgewählten Tablix-Datenbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="92bf1-103">The Grouping pane displays the row groups and column groups for the currently selected Tablix data region.</span></span> <span data-ttu-id="92bf1-104">Der Gruppierungsbereich ist für die Diagramm- und Messgerätdatenbereiche nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="92bf1-104">The Grouping pane is not available for the Chart or Gauge data regions.</span></span> <span data-ttu-id="92bf1-105">Der Gruppierungsbereich besteht aus dem Bereich Zeilengruppen und dem Bereich Spaltengruppen.</span><span class="sxs-lookup"><span data-stu-id="92bf1-105">The Grouping pane consists of a Row Groups pane and a Column Groups pane.</span></span> <span data-ttu-id="92bf1-106">Der Gruppierungsbereich weist zwei Modi auf, den Standard- und den erweiterten Modus.</span><span class="sxs-lookup"><span data-stu-id="92bf1-106">The Grouping pane has two modes: default and Advanced.</span></span> <span data-ttu-id="92bf1-107">Im Standardmodus wird eine hierarchische Sicht der dynamischen Elemente für Zeilen- und Spaltengruppen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="92bf1-107">Default mode displays a hierarchical view of the dynamic members for row and column groups.</span></span> <span data-ttu-id="92bf1-108">Im erweiterten Modus werden dynamische und statische Elemente für Zeilen- und Spaltengruppen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="92bf1-108">Advanced mode displays both dynamic and static members for row and column groups.</span></span> <span data-ttu-id="92bf1-109">Eine Gruppe ist ein benannter Satz von Daten aus einem Berichtsdataset, der in einem Datenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="92bf1-109">A group is a named set of data from a report dataset that is displayed on a data region.</span></span> <span data-ttu-id="92bf1-110">Gruppen werden in Hierarchien organisiert, die statische und dynamische Elemente einschließen.</span><span class="sxs-lookup"><span data-stu-id="92bf1-110">Groups are organized into hierarchies that include static and dynamic members.</span></span> <span data-ttu-id="92bf1-111">Weitere Informationen finden Sie unter [Grundlegendes zu Gruppen &#40;Berichts-Generator und SSRS&#41;](../report-design/understanding-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="92bf1-111">For more information, see [Understanding Groups &#40;Report Builder and SSRS&#41;](../report-design/understanding-groups-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="92bf1-112"> Wenn der Gruppierungsbereich nicht angezeigt wird, klicken Sie im Menü **Bericht** auf **Gruppierung**.</span><span class="sxs-lookup"><span data-stu-id="92bf1-112">If you do not see the Grouping pane, on the **Report** menu, click **Grouping**.</span></span>  
  
 <span data-ttu-id="92bf1-113">Zellen in den Zeilen- und Spaltengruppenbereiche können statische oder dynamische Elemente einer Gruppe sein.</span><span class="sxs-lookup"><span data-stu-id="92bf1-113">Cells in the row and column group areas can be static or dynamic members of a group.</span></span> <span data-ttu-id="92bf1-114">Statische Elemente wiederholen sich einmal pro Gruppe und enthalten meist Bezeichnungen oder Gesamtbeträge.</span><span class="sxs-lookup"><span data-stu-id="92bf1-114">Static members repeat once per group and typically contain labels or totals.</span></span> <span data-ttu-id="92bf1-115">Dynamische Elemente wiederholen sich einmal pro Gruppeninstanz und enthalten meist die eindeutigen Werte des Gruppierungsausdrucks.</span><span class="sxs-lookup"><span data-stu-id="92bf1-115">Dynamic members repeat once per group instance and typically contain the unique values of the group expression.</span></span> <span data-ttu-id="92bf1-116">Wenn Sie Tablix-Zellen im Zeilengruppenbereich oder Spaltengruppenbereich auswählen, wird das entsprechende Gruppenelement im Bereich Zeilengruppen oder Spaltengruppen ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="92bf1-116">As you select Tablix cells in the row group area or column group area, the corresponding group member is selected in the Row Groups or Column Groups pane.</span></span> <span data-ttu-id="92bf1-117">Wenn Sie umgekehrt Gruppen im Gruppierungsbereich auswählen, wird die entsprechende, dem Gruppenelement zugeordnete Zelle auf der Entwurfsoberfläche ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="92bf1-117">Conversely, if you select groups in the Grouping pane, the corresponding cell associated with the group member is selected on the design surface.</span></span> <span data-ttu-id="92bf1-118">Weitere Informationen zu Zeilen und Spalten von Tablix-Gruppierungsbereichen finden Sie unter [Zonen des Tablix-Datenbereichs (Berichts-Generator und SSRS)](../report-design/tablix-data-region-areas-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="92bf1-118">For more information about Tablix row and column group areas, see [Tablix Data Region Areas &#40;Report Builder and SSRS&#41;](../report-design/tablix-data-region-areas-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="92bf1-119">Der Gruppierungsbereich unterstützt die folgenden Modi:</span><span class="sxs-lookup"><span data-stu-id="92bf1-119">The Grouping pane supports the following modes:</span></span>  
  
-   <span data-ttu-id="92bf1-120">**Standard.**</span><span class="sxs-lookup"><span data-stu-id="92bf1-120">**Default.**</span></span> <span data-ttu-id="92bf1-121">Verwenden Sie den Standardmodus, um Gruppen hinzuzufügen, zu bearbeiten oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="92bf1-121">Use the default mode to add, edit, or delete groups.</span></span> <span data-ttu-id="92bf1-122">Sie können übergeordnete, untergeordnete und Detailgruppen hinzufügen, indem Sie Felder aus dem Berichtsdatenbereich ziehen und diese in der Gruppenhierarchie einfügen.</span><span class="sxs-lookup"><span data-stu-id="92bf1-122">You can add parent, child, and detail groups by dragging fields from the Report Data pane and inserting them in the group hierarchy.</span></span> <span data-ttu-id="92bf1-123">Um eine angrenzende Gruppe hinzuzufügen, müssen Sie die Verknüpfung **Gruppe hinzufügen** verwenden.</span><span class="sxs-lookup"><span data-stu-id="92bf1-123">To add an adjacent group, you must use the **Add Group** shortcut.</span></span> <span data-ttu-id="92bf1-124">Weitere Informationen finden Sie unter [Hinzufügen oder Löschen einer Gruppe in einem Datenbereich &#40;Berichts-Generator und SSRS&#41;](../report-design/add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="92bf1-124">For more information, see [Add or Delete a Group in a Data Region &#40;Report Builder and SSRS&#41;](../report-design/add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
-   <span data-ttu-id="92bf1-125">**Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="92bf1-125">**Advanced**.</span></span> <span data-ttu-id="92bf1-126">Verwenden Sie den **erweiterten Modus** , um alle Elemente der Zeilen- und Spaltengruppen anzuzeigen und die Eigenschaften auf statische Elemente festzulegen.</span><span class="sxs-lookup"><span data-stu-id="92bf1-126">Use the **Advanced mode** to view all members of row and column groups, and to set properties on static members.</span></span> <span data-ttu-id="92bf1-127">Wenn Sie Gruppen erstellen oder Gesamtwerte hinzufügen, werden die Eigenschaften automatisch festgelegt, mit denen gesteuert wird, wie der Tablix-Datenbereich Zeilen und Spalten für die einzelnen Berichtsseiten rendert.</span><span class="sxs-lookup"><span data-stu-id="92bf1-127">When you create groups or add totals, the properties that control how the Tablix data region renders rows and columns on each report page are set automatically.</span></span> <span data-ttu-id="92bf1-128">Um diese Eigenschaften manuell anzupassen, müssen Sie diese für das Tablix-Element festlegen.</span><span class="sxs-lookup"><span data-stu-id="92bf1-128">To manually adjust these properties, you must set them on the Tablix member.</span></span> <span data-ttu-id="92bf1-129">Weitere Informationen finden Sie unter [Steuern der Tablix-Datenbereichsanzeige auf einer Berichtsseite &#40;Berichts-Generator und SSRS&#41;](../report-design/controlling-the-tablix-data-region-display-on-a-report-page.md).</span><span class="sxs-lookup"><span data-stu-id="92bf1-129">For more information, see [Controlling the Tablix Data Region Display on a Report Page &#40;Report Builder and SSRS&#41;](../report-design/controlling-the-tablix-data-region-display-on-a-report-page.md).</span></span>  
  
## <a name="default-mode"></a><span data-ttu-id="92bf1-130">Standardmodus</span><span class="sxs-lookup"><span data-stu-id="92bf1-130">Default Mode</span></span>  
 <span data-ttu-id="92bf1-131">Im Standardmodus wird im Bereich Zeilengruppen und im Bereich Spaltengruppen eine hierarchische Sicht für alle übergeordneten Gruppen, untergeordneten Gruppen und angrenzenden Gruppen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="92bf1-131">In default mode, the Row Groups pane and the Column Groups pane display a hierarchical view for all parent groups, child groups, and adjacent groups.</span></span> <span data-ttu-id="92bf1-132">Untergeordnete Gruppen werden eingezogen unter der jeweils übergeordneten Gruppe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="92bf1-132">A child group appears indented under its parent group.</span></span> <span data-ttu-id="92bf1-133">Angrenzende Gruppen werden auf der gleichen Einzugsebene wie gleichgeordnete Gruppen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="92bf1-133">An adjacent group appears at the same indent level as its sibling groups.</span></span> <span data-ttu-id="92bf1-134">Die folgende Abbildung zeigt einen Tablix-Datenbereich mit geschachtelten Zeilengruppen und geschachtelten und angrenzenden Spaltengruppen.</span><span class="sxs-lookup"><span data-stu-id="92bf1-134">The following figure shows a Tablix data region with nested row groups and nested and adjacent column groups.</span></span>  
  
 <span data-ttu-id="92bf1-135">![Tablix, geschachtelte und angrenzende Zeilen- und Spaltengruppen](../media/rs-basictablixdesigngroupingpane.gif "Tablix, geschachtelte und angrenzende Zeilen- und Spaltengruppen")</span><span class="sxs-lookup"><span data-stu-id="92bf1-135">![Tablix, nested and adjacent row and column groups](../media/rs-basictablixdesigngroupingpane.gif "Tablix, nested and adjacent row and column groups")</span></span>  
  
 <span data-ttu-id="92bf1-136">Der Bereich Gruppierung zeigt die entsprechenden Zeilen- und Spaltengruppen an.</span><span class="sxs-lookup"><span data-stu-id="92bf1-136">The Grouping pane displays the corresponding row and column groups.</span></span> <span data-ttu-id="92bf1-137">In der folgenden Abbildung wurde die auf der Unterkategorie basierende Gruppe im Bereich Zeilengruppen ausgewählt, und die Gruppierungszelle [Subcat] ist im Tablix-Datenbereich ausgewählt:</span><span class="sxs-lookup"><span data-stu-id="92bf1-137">In the following figure, the group based on subcategory has been selected in the Row Groups pane, and the [Subcat] grouping cell is selected in the Tablix data region:</span></span>  
  
 <span data-ttu-id="92bf1-138">![Gruppierungsbereich für geschachtelte Zeilen- und Spaltengruppen](../media/rs-basictablixdesigngroupingpanedefaultview.gif "Gruppierungsbereich für geschachtelte Zeilen- und Spaltengruppen")</span><span class="sxs-lookup"><span data-stu-id="92bf1-138">![Grouping pane for nested row and column groups](../media/rs-basictablixdesigngroupingpanedefaultview.gif "Grouping pane for nested row and column groups")</span></span>  
  
 <span data-ttu-id="92bf1-139">Im Bereich Zeilengruppen ist die auf der Unterkategorie basierende Gruppe ein untergeordnetes Element der auf der Kategorie basierenden Gruppe.</span><span class="sxs-lookup"><span data-stu-id="92bf1-139">In the Row Groups pane, the group based on subcategory is a child of the group based on category.</span></span> <span data-ttu-id="92bf1-140">Im Bereich Spaltengruppen ist die Gruppe für Land und Region ein untergeordnetes Element der Gruppe für Geographie.</span><span class="sxs-lookup"><span data-stu-id="92bf1-140">In the Column Groups pane, the country/region group is a child of the geography group.</span></span> <span data-ttu-id="92bf1-141">Die Gruppe für das Jahr und die Gruppen für Land und Region sind angrenzende Gruppen.</span><span class="sxs-lookup"><span data-stu-id="92bf1-141">The year group and the country/region groups are adjacent groups.</span></span>  
  
 <span data-ttu-id="92bf1-142">Weitere Informationen finden Sie unter [Zellen, Zeilen und Spalten des Tablix-Datenbereichs (Berichts-Generator und SSRS)](../report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="92bf1-142">For more information, see [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](../report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span></span>  
  
## <a name="advanced-mode"></a><span data-ttu-id="92bf1-143">erweiterten Modus</span><span class="sxs-lookup"><span data-stu-id="92bf1-143">Advanced Mode</span></span>  
 <span data-ttu-id="92bf1-144">Im erweiterten Modus können Sie alle statischen und dynamischen Elemente einer Gruppe anzeigen.</span><span class="sxs-lookup"><span data-stu-id="92bf1-144">In Advanced mode, you can view all static and dynamic members of a group.</span></span> <span data-ttu-id="92bf1-145">Wenn Sie ein Element auswählen, zeigt das Eigenschaftenfenster Eigenschaften für das derzeit ausgewählte **Tablix-Element**an.</span><span class="sxs-lookup"><span data-stu-id="92bf1-145">When you select a member, the Properties window displays properties for the currently selected **Tablix member**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="92bf1-146">Wenn Sie den **erweiterten Modus**umschalten möchten, klicken Sie am Rand des Bereichs Spaltengruppen mit der rechten Maustaste auf den Pfeil nach unten, und klicken Sie anschließend auf **Erweiterter Modus**.</span><span class="sxs-lookup"><span data-stu-id="92bf1-146">To toggle **Advanced mode**, right-click the down arrow at the side of the Column Groups pane, and then click **Advanced Mode**.</span></span>  
  
 <span data-ttu-id="92bf1-147">In den meisten Fällen werden Eigenschaften, die die Anzeige statischer und dynamischer Gruppenzeilen und Gruppenspalten steuern, automatisch beim Erstellen einer Gruppe oder Hinzufügen von Gesamtwerten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="92bf1-147">In most cases, properties that control the display of static and dynamic group rows and group columns are set automatically when you create a group or add totals.</span></span> <span data-ttu-id="92bf1-148">Zum Bearbeiten der Standardwerte müssen Sie das Gruppenelement im Bereich Zeilengruppen oder Spaltengruppen auswählen und die Eigenschaftenwerte im Eigenschaftenfenster ändern.</span><span class="sxs-lookup"><span data-stu-id="92bf1-148">To edit the default values, you must select the group member in the Row or Column Groups pane, and change the property values in the Properties window.</span></span> <span data-ttu-id="92bf1-149">Die folgenden Eigenschaften sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="92bf1-149">The following properties are available:</span></span>  
  
-   <span data-ttu-id="92bf1-150">**FixedData**.</span><span class="sxs-lookup"><span data-stu-id="92bf1-150">**FixedData**.</span></span> <span data-ttu-id="92bf1-151">Boolesch.</span><span class="sxs-lookup"><span data-stu-id="92bf1-151">Boolean.</span></span> <span data-ttu-id="92bf1-152">Für äußere und Zeilen- und Spaltenheader.</span><span class="sxs-lookup"><span data-stu-id="92bf1-152">For outer row and column headers.</span></span> <span data-ttu-id="92bf1-153">Frieren Sie den Zeilengruppenbereich für vertikale Bildläufe oder den Spaltengruppenbereich für horizontale Bildläufe in einem Renderer ein, z. B. HTML.</span><span class="sxs-lookup"><span data-stu-id="92bf1-153">Freeze the row group area when scrolling vertically or the column group area when scrolling horizontally in a renderer such as HTML.</span></span>  
  
-   <span data-ttu-id="92bf1-154">**HideIfNoRows**.</span><span class="sxs-lookup"><span data-stu-id="92bf1-154">**HideIfNoRows**.</span></span> <span data-ttu-id="92bf1-155">Boolesch.</span><span class="sxs-lookup"><span data-stu-id="92bf1-155">Boolean.</span></span> <span data-ttu-id="92bf1-156">Nur für statische Elemente.</span><span class="sxs-lookup"><span data-stu-id="92bf1-156">For static members only.</span></span> <span data-ttu-id="92bf1-157">Bei erfolgter Festlegung werden Hidden und ToggleItem ignoriert.</span><span class="sxs-lookup"><span data-stu-id="92bf1-157">If set, Hidden and ToggleItem are ignored.</span></span> <span data-ttu-id="92bf1-158">Blenden Sie dieses Element aus, wenn der Tablix-Datenbereich keine Datenzeilen enthält.</span><span class="sxs-lookup"><span data-stu-id="92bf1-158">Hide this member if the Tablix data region contains no rows of data.</span></span>  
  
-   <span data-ttu-id="92bf1-159">**KeepTogether**.</span><span class="sxs-lookup"><span data-stu-id="92bf1-159">**KeepTogether**.</span></span>  
  
-   <span data-ttu-id="92bf1-160">`KeepWithGroup`.</span><span class="sxs-lookup"><span data-stu-id="92bf1-160">`KeepWithGroup`.</span></span> <span data-ttu-id="92bf1-161">Boolesch.</span><span class="sxs-lookup"><span data-stu-id="92bf1-161">Boolean.</span></span> <span data-ttu-id="92bf1-162">Nur für statische Zeilenelemente.</span><span class="sxs-lookup"><span data-stu-id="92bf1-162">For static row members only.</span></span> <span data-ttu-id="92bf1-163">Trennen Sie diese Zeile nach Möglichkeit nicht vom vorherigen oder folgenden gleichgeordneten dynamischen Element, sofern dieses nicht ausgeblendet ist.</span><span class="sxs-lookup"><span data-stu-id="92bf1-163">Where possible, keep this row with the previous or following sibling dynamic member, if it is not hidden.</span></span>  
  
-   <span data-ttu-id="92bf1-164">**RepeatOnNewPage**.</span><span class="sxs-lookup"><span data-stu-id="92bf1-164">**RepeatOnNewPage**.</span></span> <span data-ttu-id="92bf1-165">Boolesch.</span><span class="sxs-lookup"><span data-stu-id="92bf1-165">Boolean.</span></span> <span data-ttu-id="92bf1-166">Nur für statische Zeilenelemente und wenn KeepWithGroup nicht „None“ ist.</span><span class="sxs-lookup"><span data-stu-id="92bf1-166">For static row members only and where KeepWithGroup is not None.</span></span> <span data-ttu-id="92bf1-167">Wiederholen Sie diese statische Zeile nach Möglichkeit auf jeder Seite, die mindestens eine Instanz des von KeepWithGroup angegebenen dynamischen Elements aufweist.</span><span class="sxs-lookup"><span data-stu-id="92bf1-167">Where possible, repeat this static row on every page that has at least one instance of the dynamic member specified by KeepWithGroup.</span></span>  
  
-   <span data-ttu-id="92bf1-168">`Hidden`.</span><span class="sxs-lookup"><span data-stu-id="92bf1-168">`Hidden`.</span></span> <span data-ttu-id="92bf1-169">Boolesch.</span><span class="sxs-lookup"><span data-stu-id="92bf1-169">Boolean.</span></span> <span data-ttu-id="92bf1-170">Gibt an, ob die Zeile oder die Spalte anfänglich ausgeblendet sein soll.</span><span class="sxs-lookup"><span data-stu-id="92bf1-170">Indicates whether the row or column should be initially hidden.</span></span>  
  
-   <span data-ttu-id="92bf1-171">**ToggleItem.**</span><span class="sxs-lookup"><span data-stu-id="92bf1-171">**ToggleItem.**</span></span> <span data-ttu-id="92bf1-172">Eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="92bf1-172">String.</span></span> <span data-ttu-id="92bf1-173">Der Name des Textfelds, dem das Umschaltbild hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="92bf1-173">The name of the text box to which to add the toggle image.</span></span> <span data-ttu-id="92bf1-174">Das Textfeld muss demselben Gruppenbereich oder einem enthaltenden Bereich angehören.</span><span class="sxs-lookup"><span data-stu-id="92bf1-174">The text box must be in the same group scope or a containing scope.</span></span>  
  
 <span data-ttu-id="92bf1-175">Weitere Informationen dazu, wie dieses Verhalten in einem Tablix-Datenbereich gesteuert werden kann, finden Sie unter [Steuern der Tablix-Datenbereichsanzeige auf einer Berichtsseite (Berichts-Generator und SSRS)](../report-design/controlling-the-tablix-data-region-display-on-a-report-page.md).</span><span class="sxs-lookup"><span data-stu-id="92bf1-175">For more information about how this behavior can be controlled on a Tablix data region, see [Controlling the Tablix Data Region Display on a Report Page &#40;Report Builder and SSRS&#41;](../report-design/controlling-the-tablix-data-region-display-on-a-report-page.md).</span></span>  
  
 <span data-ttu-id="92bf1-176">Nicht jedes statische Element verfügt über einen Header, der einer Zelle auf der Entwurfsoberfläche entspricht.</span><span class="sxs-lookup"><span data-stu-id="92bf1-176">Not every static member has a header that corresponds to a cell on the design surface.</span></span> <span data-ttu-id="92bf1-177">Im Gruppierungsbereich wird mit der folgenden Konvention angegeben, ob ein statisches Element keinen Header besitzt:</span><span class="sxs-lookup"><span data-stu-id="92bf1-177">In the Grouping pane, the following convention indicates whether a static member has no header:</span></span>  
  
-   <span data-ttu-id="92bf1-178">**Statisch** Gibt ein statisches Element mit einer Headerzelle an.</span><span class="sxs-lookup"><span data-stu-id="92bf1-178">**Static** Indicates a static member with a header cell.</span></span>  
  
-   <span data-ttu-id="92bf1-179">**(Statisch)** Gibt ein statisches Element ohne Headerzelle an, wird als ausgeblendet statisch bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="92bf1-179">**(Static)** Indicates a static member with no header cell, known as a hidden static.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92bf1-180">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="92bf1-180">See Also</span></span>  
 <span data-ttu-id="92bf1-181">[Tabellen, Matrizen und Listen &#40;Berichts-Generator und SSRS&#41;](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="92bf1-181">[Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="92bf1-182">[Ausdrücke &#40;Berichts-Generator und SSRS&#41;](../report-design/expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="92bf1-182">[Expressions &#40;Report Builder and SSRS&#41;](../report-design/expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="92bf1-183">Filtern, Gruppieren und Sortieren von Daten &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="92bf1-183">Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;</span></span>](../report-design/filter-group-and-sort-data-report-builder-and-ssrs.md)  
  
  