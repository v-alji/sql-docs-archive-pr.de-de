---
title: Hinzufügen oder Löschen einer Gruppe in einem Datenbereich (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4de53c3c-c6fc-49ce-b692-3609fc0b3ec5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c355ca87db578d47181935e1ca6bc48e75bf8b8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719606"
---
# <a name="add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="27378-102">Hinzufügen oder Löschen einer Gruppe in einem Datenbereich (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="27378-102">Add or Delete a Group in a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="27378-103">Fügen Sie einem Datenbereich eine Gruppe hinzu, wenn Sie Daten nach einem spezifischen Wert oder einer Reihe von Ausdrücken zu Anzeige- und Berechnungszwecken organisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="27378-103">Add a group to a data region when you want to organize data by a specific value or set of expressions, for display and calculations.</span></span> <span data-ttu-id="27378-104">Eine Gruppe verfügt über einen Namen und einen Ausdruck, der angibt, welche Daten aus einem Dataset zur Gruppe gehören.</span><span class="sxs-lookup"><span data-stu-id="27378-104">A group has a name and an expression that identifies which data from a dataset belongs to the group.</span></span> <span data-ttu-id="27378-105">Weitere Informationen zu Gruppen finden Sie unter [Grundlegendes zu Gruppen &#40;Berichts-Generator und SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="27378-105">For more information about groups, see [Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="27378-106">Klicken Sie in einem Tablix-Datenbereich in die Tabelle, Matrix oder Liste, um den Gruppierungsbereich anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="27378-106">In a tablix data region, click in the table, matrix, or list to display the Grouping pane.</span></span> <span data-ttu-id="27378-107">Ziehen Sie Datasetfelder in den Bereich Zeilengruppe und Spaltengruppe, um übergeordnete oder untergeordnete Gruppen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="27378-107">Drag dataset fields to the Row Group and Column Group pane to create parent or child groups.</span></span> <span data-ttu-id="27378-108">Klicken Sie mit der rechten Maustaste auf eine vorhandene Gruppe, um eine angrenzende Gruppe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="27378-108">Right-click an existing group to add an adjacent group.</span></span> <span data-ttu-id="27378-109">Definitionsgemäß ist die Detailgruppe die innerste Gruppe, die nur als untergeordnete Gruppe hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="27378-109">By definition, the details group is the innermost group and can only be added as a child group.</span></span> <span data-ttu-id="27378-110">Klicken Sie mit der rechten Maustaste auf eine vorhandene Gruppe, um diese zu löschen.</span><span class="sxs-lookup"><span data-stu-id="27378-110">Right-click an existing group to delete it.</span></span> <span data-ttu-id="27378-111">Zeilen und die Spalten, in denen Gruppenwerte angezeigt werden sollen, werden automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="27378-111">Rows and columns on which to display group values are automatically added for you.</span></span> <span data-ttu-id="27378-112">Weitere Informationen finden Sie unter [Tabellen, Matrizen und Listen &#40;Berichts-Generator und SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="27378-112">For more information, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="27378-113">Klicken Sie in einem Diagrammdatenbereich in das Diagramm, um die Ablagezonen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="27378-113">In a Chart data region, click in the chart to display the drop-zones.</span></span> <span data-ttu-id="27378-114">Erstellen Sie Gruppen, indem Sie Datasetfelder in die Ablagezonen für Kategorien und Reihen ziehen.</span><span class="sxs-lookup"><span data-stu-id="27378-114">Create groups by dragging dataset fields to the category and series drop zones.</span></span> <span data-ttu-id="27378-115">Wenn Sie geschachtelte Gruppen hinzufügen möchten, fügen Sie der Ablagezone mehrere Felder hinzu.</span><span class="sxs-lookup"><span data-stu-id="27378-115">To add nested groups, add multiple fields to the drop-zone.</span></span>  
  
 <span data-ttu-id="27378-116">In einem Messgerät sind standardmäßig keine Gruppen definiert.</span><span class="sxs-lookup"><span data-stu-id="27378-116">Groups are not defined in a gauge by default.</span></span> <span data-ttu-id="27378-117">Das Standardverhalten des Messgeräts besteht darin, dass alle Werte im angegebenen Feld zu einem Wert aggregiert werden, der auf dem Messgerät angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="27378-117">The default behavior for the gauge is to aggregate all values in the specified field into one value that is displayed on the gauge.</span></span> <span data-ttu-id="27378-118">Weitere Informationen finden Sie unter [Messgeräte &#40;Berichts-Generator und SSRS&#41;](gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="27378-118">For more information, see [Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-parent-or-child-row-or-column-group-to-a-tablix-data-region"></a><span data-ttu-id="27378-119">So fügen Sie einem Tablix-Datenbereich eine übergeordnete oder untergeordnete Zeilen- oder Spaltengruppe hinzu</span><span class="sxs-lookup"><span data-stu-id="27378-119">To add a parent or child row or column group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="27378-120">Ziehen Sie ein Feld aus dem **Berichtsdatenbereich** in den Bereich **Zeilengruppen** oder **Spaltengruppen** .</span><span class="sxs-lookup"><span data-stu-id="27378-120">Drag a field from the **Report Data** pane to the **Row Groups** pane or the **Column Groups** pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="27378-121">Wenn der Gruppierungsbereich nicht angezeigt wird, klicken Sie auf der Registerkarte „Ansicht“ auf **Gruppierung**.</span><span class="sxs-lookup"><span data-stu-id="27378-121">If you do not see the Grouping pane, on the View tab, click **Grouping**.</span></span>  
  
2.  <span data-ttu-id="27378-122">Legen Sie das Feld mithilfe des Führungsbalkens über oder unter der Gruppenhierarchie ab, um die Gruppe einer vorhandenen Gruppe als übergeordnete oder untergeordnete Gruppe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="27378-122">Drop the field above or below the group hierarchy using the guide bar to place the group as a parent group or a child group to an existing group.</span></span>  
  
     <span data-ttu-id="27378-123">Die Gruppe wird mit einem Standardnamen, einem Gruppierungsausdruck und einem Sortierungsausdruck hinzugefügt, die auf dem Feldnamen basieren.</span><span class="sxs-lookup"><span data-stu-id="27378-123">The group is added with a default name, group expression, and sort expression that is based on the field name.</span></span>  
  
### <a name="to-add-an-adjacent-row-or-column-group-to-a-tablix-data-region"></a><span data-ttu-id="27378-124">So fügen Sie einem Tablix-Datenbereich eine angrenzende Zeilen- oder Spaltengruppe hinzu</span><span class="sxs-lookup"><span data-stu-id="27378-124">To add an adjacent row or column group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="27378-125">Klicken Sie im Gruppierungsbereich mit der rechten Maustaste auf eine Gruppe, die einen Peer der hinzuzufügenden Gruppe darstellt.</span><span class="sxs-lookup"><span data-stu-id="27378-125">In the Grouping pane, right-click a group that is a peer to the group that you want to add.</span></span> <span data-ttu-id="27378-126">Klicken Sie auf **Gruppe hinzufügen**, und klicken Sie anschließend auf **Angrenzend vor** oder **Angrenzend nach** , um die Position anzugeben, an der die Gruppe hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="27378-126">Click **Add Group**, and then click **Adjacent Before** or **Adjacent After** to specify where to add the group.</span></span> <span data-ttu-id="27378-127">Das Dialogfeld **Tablix-Gruppe** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="27378-127">The **Tablix Group** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="27378-128">Geben Sie in **Name**einen Namen für die Gruppe ein.</span><span class="sxs-lookup"><span data-stu-id="27378-128">In **Name**, type a name for the group.</span></span>  
  
3.  <span data-ttu-id="27378-129">Geben Sie unter **Gruppierungsausdruck**einen Ausdruck ein, oder klicken Sie auf die Ausdrucksschaltfläche (**fx**), um einen Ausdruck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="27378-129">In **Group expression**, type an expression or click the expression button (**fx**) to create an expression.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="27378-130">Dem Gruppierungsbereich wird eine neue Gruppe hinzugefügt, und dem Tablix-Datenbereich auf der Entwurfsoberfläche wird eine Zeile oder Spalte hinzugefügt, in der Gruppenwerte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="27378-130">A new group is added to the Grouping pane and a row or column on which to display group values is added to the tablix data region on the design surface.</span></span>  
  
### <a name="to-add-a-details-group-to-a-tablix-data-region"></a><span data-ttu-id="27378-131">So fügen Sie einem Tablix-Datenbereich eine Detailgruppe hinzu</span><span class="sxs-lookup"><span data-stu-id="27378-131">To add a details group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="27378-132">Klicken Sie im Gruppierungsbereich mit der rechten Maustaste auf eine Gruppe, die der innersten untergeordneten Gruppe entspricht, jedoch nicht auf die Gruppe **Details** .</span><span class="sxs-lookup"><span data-stu-id="27378-132">In the Grouping pane, right-click a group that is the innermost child group, but not the **Details** group.</span></span> <span data-ttu-id="27378-133">Klicken Sie auf **Gruppe hinzufügen**und dann auf **Untergeordnete Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="27378-133">Click **Add Group**, and then click **Child Group**.</span></span> <span data-ttu-id="27378-134">Das Dialogfeld **Tablix-Gruppe** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="27378-134">The **Tablix Group** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="27378-135">Geben Sie in **Gruppierungsausdruck**keinen Ausdruck ein.</span><span class="sxs-lookup"><span data-stu-id="27378-135">In **Group expression**, leave the expression blank.</span></span> <span data-ttu-id="27378-136">Eine Detailgruppe verfügt über keinen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="27378-136">A details group has no expression.</span></span>  
  
3.  <span data-ttu-id="27378-137">Wählen Sie **Detaildaten anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="27378-137">Select **Show detail data**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="27378-138">Im Bereich Gruppierung wird eine neue Detailgruppe als untergeordnete Gruppe hinzugefügt, und vom Zeilenhandle für die in Schritt 1 ausgewählte Gruppe wird das Symbol für die Detailgruppe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="27378-138">A new details group is added as a child group in the Grouping pane, and the row handle for the group you selected in step 1 displays the details group icon.</span></span> <span data-ttu-id="27378-139">Weitere Informationen zu Handles finden Sie unter [Zellen, Zeilen und Spalten des Tablix-Datenbereichs (Berichts-Generator und SSRS)](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="27378-139">For more information about handles, see [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-edit-a-row-or-column-group-in-a-tablix-data-region"></a><span data-ttu-id="27378-140">So bearbeiten Sie eine Zeilen- oder Spaltengruppe in einem Tablix-Datenbereich</span><span class="sxs-lookup"><span data-stu-id="27378-140">To edit a row or column group in a tablix data region</span></span>  
  
1.  <span data-ttu-id="27378-141">Klicken Sie auf der Berichtsentwurfsoberfläche auf eine beliebige Stelle im Tablix-Datenbereich, um diesen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="27378-141">On the report design surface, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="27378-142">Im Gruppierungsbereich werden die Zeilen- und Spaltengruppen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="27378-142">The Grouping pane displays the row and column groups.</span></span>  
  
2.  <span data-ttu-id="27378-143">Klicken Sie mit der rechten Maustaste auf die Gruppe, und klicken Sie anschließend auf **Gruppeneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="27378-143">Right-click the group, and then click **Group Properties**.</span></span>  
  
3.  <span data-ttu-id="27378-144">Geben Sie unter **Name**den Namen der Gruppe ein.</span><span class="sxs-lookup"><span data-stu-id="27378-144">In **Name**, type the name of the group.</span></span>  
  
4.  <span data-ttu-id="27378-145">Geben Sie unter **Gruppierungsausdrücke**einen einfachen Ausdruck ein, bzw. wählen Sie diesen aus, oder klicken Sie auf die Ausdrucksschaltfläche (**fx**), um einen Gruppierungsausdruck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="27378-145">In **Group expressions**, type or select a simple expression, or click the Expression (**fx**) button to create a group expression.</span></span>  
  
5.  <span data-ttu-id="27378-146">Klicken Sie auf **Hinzufügen** , um zusätzliche Ausdrücke zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="27378-146">Click **Add** to create additional expressions.</span></span> <span data-ttu-id="27378-147">Alle angegebenen Ausdrücke werden mit einem logischen AND kombiniert, um Daten für diese Gruppe anzugeben.</span><span class="sxs-lookup"><span data-stu-id="27378-147">All expressions you specify are combined using a logical AND to specify data for this group.</span></span>  
  
6.  <span data-ttu-id="27378-148">(Optional) Klicken Sie auf **Seitenumbrüche** , um Seitenumbruchoptionen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="27378-148">(Optional) Click **Page Breaks** to set page break options.</span></span>  
  
7.  <span data-ttu-id="27378-149">(Optional) Klicken Sie auf **Sortierung** , um Ausdrücke auszuwählen bzw. einzugeben, mit denen die Sortierreihenfolge für Werte in der Gruppe angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="27378-149">(Optional) Click **Sorting** to select or type expressions that specify the sort order for values in the group.</span></span>  
  
8.  <span data-ttu-id="27378-150">(Optional) Klicken Sie auf **Sichtbarkeit** , um die Sichtbarkeitsoptionen für das Element auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="27378-150">(Optional) Click **Visibility** to select the visibility options for the item.</span></span>  
  
9. <span data-ttu-id="27378-151">(Optional) Klicken Sie auf **Filter** , um Filter für diese Gruppe festzulegen.</span><span class="sxs-lookup"><span data-stu-id="27378-151">(Optional) Click **Filters** to set filters for this group.</span></span>  
  
10. <span data-ttu-id="27378-152">(Optional) Klicken Sie auf **Variablen** , um Variablen zu definieren, deren Bereich auf diese Gruppe festgelegt ist und auf die aus untergeordneten Gruppen zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="27378-152">(Optional) Click **Variables** to define variables scoped to this group and accessible from any child groups.</span></span>  
  
11. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-group-from-a-tablix-data-region"></a><span data-ttu-id="27378-153">So löschen Sie eine Gruppe aus einem Tablix-Datenbereich</span><span class="sxs-lookup"><span data-stu-id="27378-153">To delete a group from a tablix data region</span></span>  
  
1.  <span data-ttu-id="27378-154">Klicken Sie im Bereich „Gruppierung“ mit der rechten Maustaste auf die Gruppe, und klicken Sie anschließend auf **Gruppe löschen**.</span><span class="sxs-lookup"><span data-stu-id="27378-154">In the Grouping pane, right-click the group, and then click **Delete Group**.</span></span>  
  
2.  <span data-ttu-id="27378-155">Wählen Sie im Dialogfeld **Gruppe löschen** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="27378-155">In the **Delete Group** dialog box, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="27378-156">**Gruppe und verwandte Zeilen und Spalten löschen** Wählen Sie diese Option aus, um die Gruppendefinition und alle zugehörigen Zeilen zu löschen, in denen Gruppendaten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="27378-156">**Delete group and related rows and columns** Choose this option to delete the group definition and all related rows that display group data.</span></span> <span data-ttu-id="27378-157">Für die Detailgruppe werden nur die Detaildatenzeilen gelöscht, wenn dieselbe Zeile sowohl zu den Zeilen- als auch zu den Gruppendaten gehört.</span><span class="sxs-lookup"><span data-stu-id="27378-157">For the details group, if the same row belongs to both detail and group data, only the detail data rows are deleted.</span></span>  
  
    -   <span data-ttu-id="27378-158">**Nur Gruppe löschen** Wählen Sie diese Option aus, wenn die Struktur des Tablix-Datenbereichs unverändert beibehalten und nur die Gruppendefinition gelöscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="27378-158">**Delete group only** Choose this option to keep the structure of the tablix data region the same and delete only the group definition.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-details-group-from-a-tablix-data-region"></a><span data-ttu-id="27378-159">So löschen Sie eine Detailgruppe aus einem Tablix-Datenbereich</span><span class="sxs-lookup"><span data-stu-id="27378-159">To delete a details group from a tablix data region</span></span>  
  
1.  <span data-ttu-id="27378-160">Klicken Sie im Bereich Gruppierung mit der rechten Maustaste auf die Detailgruppe, und klicken Sie anschließend auf **Gruppe löschen**.</span><span class="sxs-lookup"><span data-stu-id="27378-160">In the Grouping pane, right-click the details group, and then click **Delete Group**.</span></span>  
  
2.  <span data-ttu-id="27378-161">Wählen Sie im Dialogfeld **Gruppe löschen** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="27378-161">In the **Delete Group** dialog box, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="27378-162">**Gruppe und verwandte Zeilen und Spalten löschen** Wählen Sie diese Option aus, um die Gruppendefinition und alle zugehörigen Zeilen zu löschen, in denen Gruppendaten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="27378-162">**Delete group and related rows and columns** Choose this option to delete the group definition and all related rows that display group data.</span></span> <span data-ttu-id="27378-163">Für die Detailgruppe werden nur die Detaildatenzeilen gelöscht, wenn dieselbe Zeile sowohl zu den Zeilen- als auch zu den Gruppendaten gehört.</span><span class="sxs-lookup"><span data-stu-id="27378-163">For the details group, if the same row belongs to both detail and group data, only the detail data rows are deleted.</span></span>  
  
    -   <span data-ttu-id="27378-164">**Nur Gruppe löschen** Wählen Sie diese Option aus, wenn die Struktur des Tablix-Datenbereichs unverändert beibehalten und nur die Gruppendefinition gelöscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="27378-164">**Delete group only** Choose this option to keep the structure of the tablix data region the same and delete only the group definition.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="27378-165">Die Detailgruppe wird gelöscht.</span><span class="sxs-lookup"><span data-stu-id="27378-165">The details group is deleted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="27378-166">Vergewissern Sie sich nach dem Entfernen einer Detailzeile, dass mit dem Ausdruck in den jeweiligen Zellen ggf. ein Aggregatausdruck angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="27378-166">Verify that after you remove a details row, the expression in each cell specifies an aggregate expression where appropriate.</span></span> <span data-ttu-id="27378-167">Bearbeiten Sie ggf. den Ausdruck, sodass dieser die benötigten Aggregatfunktionen angibt.</span><span class="sxs-lookup"><span data-stu-id="27378-167">If necessary, edit the expression to specify aggregate functions as needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27378-168">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="27378-168">See Also</span></span>  
 <span data-ttu-id="27378-169">[Verweise auf Berichts- und Gruppenvariablensammlungen &#40;Berichts-Generator und SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="27378-169">[Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md) </span></span>  
 <span data-ttu-id="27378-170">[Beispiele für Gruppierungsausdrücke (Berichts-Generator und SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="27378-170">[Group Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="27378-171">[Filtern, Gruppieren und Sortieren von Daten &#40;Berichts-Generator und SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="27378-171">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="27378-172">[Tablix-Datenbereich &#40;Berichts-Generator und SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="27378-172">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="27378-173">[Tabellen (Berichts-Generator und SSRS)](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="27378-173">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="27378-174">[Matrizen (Berichts-Generator und SSRS)](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="27378-174">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="27378-175">[Listen (Berichts-Generator und SSRS)](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="27378-175">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="27378-176">Tabellen, Matrizen und Listen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="27378-176">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
