---
title: Ändern der Sicht der Ablauf Verfolgungs Ergebnisse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 860a80dc-bac0-4ef0-bf7f-7a9b430d7aa3
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 050c8f179742cf3cef6473b03f062390caf195f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609390"
---
# <a name="modify-the-trace-results-view"></a><span data-ttu-id="394f0-102">Ändern der Sicht der Ablaufverfolgungsergebnisse</span><span class="sxs-lookup"><span data-stu-id="394f0-102">Modify the Trace Results View</span></span>
  <span data-ttu-id="394f0-103">In diesem Thema wird beschrieben, wie die Ablaufverfolgungsergebnisse-Sicht einer Sitzung für erweiterte Ereignisse in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] durch die Ausführung der folgenden Aufgaben geändert wird.</span><span class="sxs-lookup"><span data-stu-id="394f0-103">This topic describes how to modify the trace results view of an Extended Events session in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] by performing the following tasks.</span></span>  
  
1.  [<span data-ttu-id="394f0-104">Hinzufügen oder Entfernen von Spalten</span><span class="sxs-lookup"><span data-stu-id="394f0-104">Add or Remove Columns</span></span>](#AddRemoveColumns)  
  
2.  [<span data-ttu-id="394f0-105">Erstellen, Bearbeiten oder Löschen zusammengeführter Spalten</span><span class="sxs-lookup"><span data-stu-id="394f0-105">Create, Edit, or Delete Merged Columns</span></span>](#ChangeColumns)  
  
3.  [<span data-ttu-id="394f0-106">Sortieren der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="394f0-106">Sort the Results</span></span>](#SortResults)  
  
4.  [<span data-ttu-id="394f0-107">Gruppieren der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="394f0-107">Group the Results</span></span>](#GroupResults)  
  
5.  [<span data-ttu-id="394f0-108">Aggregieren der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="394f0-108">Aggregate the Results</span></span>](#AggregateResults)  
  
6.  [<span data-ttu-id="394f0-109">Filtern der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="394f0-109">Filter the Results</span></span>](#Filter)  
  
7.  [<span data-ttu-id="394f0-110">Textsuche in Spalten</span><span class="sxs-lookup"><span data-stu-id="394f0-110">Search for Text in Columns</span></span>](#Search)  
  
8.  [<span data-ttu-id="394f0-111">Ändern der Anzeigeeinstellungen</span><span class="sxs-lookup"><span data-stu-id="394f0-111">Change the Display Settings</span></span>](#ChangeDisplay)  
  
##  <a name="add-or-remove-columns"></a><a name="AddRemoveColumns"></a><span data-ttu-id="394f0-112">Hinzufügen oder Entfernen von Spalten</span><span class="sxs-lookup"><span data-stu-id="394f0-112">Add or Remove Columns</span></span>  
  
1.  <span data-ttu-id="394f0-113">Öffnen Sie eine XEL-Datei, um die Ablaufverfolgungsergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="394f0-113">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="394f0-114"> Sie können auch mit der rechten Maustaste auf den Sitzungsnamen klicken, und dann **Livedaten ansehen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="394f0-114">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="394f0-115">Klicken Sie im Fenster für die Ablaufverfolgungsergebnisse mit der rechten Maustaste auf den Spaltenheader, und wählen Sie dann **Spalten auswählen**aus.</span><span class="sxs-lookup"><span data-stu-id="394f0-115">In the trace results window, right-click the column header, and then select **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="394f0-116">Wählen Sie im Dialogfeld **Spalten auswählen** im Abschnitt **Verfügbare Spalten** die Spaltennamen aus, die Sie hinzufügen möchten, und klicken Sie dann auf den Pfeil nach rechts.</span><span class="sxs-lookup"><span data-stu-id="394f0-116">In the **Choose Columns** dialog box, in the **Available columns** section, select the column names you want to add, and then click the right arrow.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="394f0-117">Standardmäßig werden die Spalten nach Namen sortiert.</span><span class="sxs-lookup"><span data-stu-id="394f0-117">By default, the columns are arranged by name.</span></span> <span data-ttu-id="394f0-118">Um die Spalten nach Ereignis anzuzeigen, klicken Sie auf **Nach Ereignis anordnen**.</span><span class="sxs-lookup"><span data-stu-id="394f0-118">To display the columns by event, click **Arrange by event**.</span></span>  
  
     <span data-ttu-id="394f0-119">Um Spalten im Abschnitt **Ausgewählte Spalten** zu entfernen, wählen Sie die Spalten aus, die Sie entfernen möchten, und klicken Sie auf die den Pfeil nach links.</span><span class="sxs-lookup"><span data-stu-id="394f0-119">To remove columns, in the **Selected columns** section, select the columns you want to remove, and click the left arrow.</span></span>  
  
4.  <span data-ttu-id="394f0-120">Um im Abschnitt **Ausgewählte Spalten** die Spaltenreihenfolge zu ändern, klicken Sie auf **Nach oben** bzw. **Nach unten** .</span><span class="sxs-lookup"><span data-stu-id="394f0-120">In the **Selected columns** section, to change the column order display, click **Move Up** or **Move Down** respectively.</span></span> <span data-ttu-id="394f0-121">Sie können nicht mehrere Zeilen gleichzeitig verschieben.</span><span class="sxs-lookup"><span data-stu-id="394f0-121">You cannot move multiple rows.</span></span>  
  
5.  <span data-ttu-id="394f0-122">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="394f0-122">Click **OK**.</span></span>  
  
##  <a name="create-edit-or-delete-merged-columns"></a><a name="ChangeColumns"></a><span data-ttu-id="394f0-123">Erstellen, bearbeiten oder löschen zusammen geführter Spalten</span><span class="sxs-lookup"><span data-stu-id="394f0-123">Create, Edit, or Delete Merged Columns</span></span>  
  
#### <a name="to-create-merged-columns"></a><span data-ttu-id="394f0-124">So erstellen Sie zusammengeführte Spalten</span><span class="sxs-lookup"><span data-stu-id="394f0-124">To create merged columns</span></span>  
  
1.  <span data-ttu-id="394f0-125">Öffnen Sie eine XEL-Datei, um die Ablaufverfolgungsergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="394f0-125">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="394f0-126"> Sie können auch mit der rechten Maustaste auf den Sitzungsnamen klicken, und dann **Livedaten ansehen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="394f0-126">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="394f0-127">Klicken Sie im Fenster für die Ablaufverfolgungsergebnisse mit der rechten Maustaste auf den Spaltenheader, und klicken Sie dann auf **Spalten auswählen**.</span><span class="sxs-lookup"><span data-stu-id="394f0-127">In the trace results window, right-click the column header, and then click **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="394f0-128">Klicken Sie im Dialogfeld **Spalten auswählen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="394f0-128">In the **Choose Columns** dialog box, click **New**.</span></span>  
  
4.  <span data-ttu-id="394f0-129">Geben Sie im Dialogfeld **Neue zusammengeführte Spalte** im Feld **Name der zusammengeführten Spalte** einen Namen für die zusammengeführte Spalte ein.</span><span class="sxs-lookup"><span data-stu-id="394f0-129">In the **New Merged Column** dialog box, in the **Merged column name** box, enter a name for the merged columns.</span></span>  
  
5.  <span data-ttu-id="394f0-130">Wählen Sie im Feld **Zusammenzuführende Originalspalten** in der Dropdownliste zwei oder mehr Spalten aus, die zusammengeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="394f0-130">In the **Original columns to merge** box, select two or more columns to merge from the drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="394f0-131">Erweiterte Ereignisse unterstützen nur das Zusammenführen von bis zu fünf Spalten.</span><span class="sxs-lookup"><span data-stu-id="394f0-131">Extended Events only supports merging up to five columns.</span></span>  
  
6.  <span data-ttu-id="394f0-132">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="394f0-132">Click **OK**.</span></span>  
  
#### <a name="to-edit-merged-columns"></a><span data-ttu-id="394f0-133">So bearbeiten Sie zusammengeführte Spalten</span><span class="sxs-lookup"><span data-stu-id="394f0-133">To edit merged columns</span></span>  
  
1.  <span data-ttu-id="394f0-134">Öffnen Sie eine XEL-Datei, um die Ablaufverfolgungsergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="394f0-134">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="394f0-135"> Sie können auch mit der rechten Maustaste auf den Sitzungsnamen klicken, und dann **Livedaten ansehen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="394f0-135">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="394f0-136">Klicken Sie im Fenster für die Ablaufverfolgungsergebnisse mit der rechten Maustaste auf den Spaltenheader, und klicken Sie dann auf **Spalten auswählen**.</span><span class="sxs-lookup"><span data-stu-id="394f0-136">In the trace results window, right-click the column header, and then click **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="394f0-137">Klicken Sie im Dialogfeld **Spalten auswählen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="394f0-137">In the **Choose Columns** dialog box, click **Edit**.</span></span>  
  
4.  <span data-ttu-id="394f0-138">Zum Ändern des Namens für die zusammengeführte Spalte geben Sie im Dialogfeld **Neue zusammengeführte Spalte** im Feld **Name der zusammengeführten Spalte** einen neuen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="394f0-138">To change the name of the merged column, in the **New Merged Column** dialog box, in the **Merged column name** box, enter the new name.</span></span>  
  
     <span data-ttu-id="394f0-139">Um die Spalten zu ändern, die Sie zusammenzuführen möchten, wählen Sie im Feld **Zusammenzuführende Originalspalten** in der Dropdownliste die zusammenzuführenden Spalten aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="394f0-139">To change the columns you want to merge, in the **Original columns to merge** box, select the columns you want to merge from the drop-down list, and then click **OK**.</span></span>  
  
#### <a name="to-delete-merged-columns"></a><span data-ttu-id="394f0-140">So löschen Sie zusammenzuführende Spalten</span><span class="sxs-lookup"><span data-stu-id="394f0-140">To delete merged columns</span></span>  
  
1.  <span data-ttu-id="394f0-141">Öffnen Sie eine XEL-Datei, um die Ablaufverfolgungsergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="394f0-141">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="394f0-142"> Sie können auch mit der rechten Maustaste auf den Sitzungsnamen klicken, und dann **Livedaten ansehen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="394f0-142">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="394f0-143">Klicken Sie im Fenster für die Ablaufverfolgungsergebnisse mit der rechten Maustaste auf den Spaltenheader, und klicken Sie dann auf **Spalten auswählen**.</span><span class="sxs-lookup"><span data-stu-id="394f0-143">In the trace results window, right-click the column header, and then click **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="394f0-144">Wählen Sie im Dialogfeld **Spalten auswählen** den Namen der zusammengeführten Spalte aus, die Sie löschen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="394f0-144">In the **Choose Columns** dialog box, select the name of the merged column you want to delete, and then click **Delete**.</span></span>  
  
##  <a name="sort-the-results"></a><a name="SortResults"></a><span data-ttu-id="394f0-145">Sortieren der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="394f0-145">Sort the Results</span></span>  
  
#### <a name="to-sort-the-results-in-ascending-or-descending-order"></a><span data-ttu-id="394f0-146">So sortieren Sie die Ergebnisse in aufsteigender oder absteigender Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="394f0-146">To sort the results in ascending or descending order</span></span>  
  
-   <span data-ttu-id="394f0-147">Öffnen Sie eine XEL-Datei, um die Ablaufverfolgungsergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="394f0-147">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="394f0-148"> Sie können auch mit der rechten Maustaste auf den Sitzungsnamen klicken, **Livedaten ansehen**auswählen und dann auf der Symbolleiste auf die Schaltfläche **Datenfeed beenden** klicken.</span><span class="sxs-lookup"><span data-stu-id="394f0-148">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.</span></span>  
  
-   <span data-ttu-id="394f0-149">Klicken Sie im Fenster für die Ablaufverfolgungsergebnisse mit der rechten Maustaste auf die Spaltenüberschrift, nach der die Sortierung erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="394f0-149">In the trace results window, right-click the column heading you want to sort.</span></span> <span data-ttu-id="394f0-150">Klicken Sie auf **Aufsteigend sortieren** oder **Absteigend sortieren** , um die Spalte in aufsteigender bzw. absteigender Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="394f0-150">Click **Sort Ascending** or **Sort Descending** to sort the column in ascending or descending order respectively.</span></span>  
  
     <span data-ttu-id="394f0-151">Bei gruppierten Spalten werden bei Sortierung der Spalte nur die Daten innerhalb der Gruppe sortiert.</span><span class="sxs-lookup"><span data-stu-id="394f0-151">If you have grouped columns, sorting the column will only sort data within the group.</span></span>  
  
##  <a name="group-results"></a><a name="GroupResults"></a><span data-ttu-id="394f0-152">Gruppieren von Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="394f0-152">Group Results</span></span>  
  
#### <a name="to-group-the-results-by-a-single-column"></a><span data-ttu-id="394f0-153">So gruppieren Sie die Ergebnisse nach einer einzelnen Spalte</span><span class="sxs-lookup"><span data-stu-id="394f0-153">To group the results by a single column</span></span>  
  
1.  <span data-ttu-id="394f0-154">Öffnen Sie eine XEL-Datei, um die Ablaufverfolgungsergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="394f0-154">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="394f0-155"> Sie können auch mit der rechten Maustaste auf den Sitzungsnamen klicken, **Livedaten ansehen**auswählen und dann auf der Symbolleiste für erweiterte Ereignisse auf die Schaltfläche **Datenfeed beenden** klicken.</span><span class="sxs-lookup"><span data-stu-id="394f0-155">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the Extended Events toolbar.</span></span>  
  
2.  <span data-ttu-id="394f0-156">Klicken Sie im Fenster für die Ablaufverfolgungsergebnisse mit der rechten Maustaste auf den Spaltenheader, den Sie gruppieren möchten, und klicken Sie dann auf **Nach dieser Spalte gruppieren**.</span><span class="sxs-lookup"><span data-stu-id="394f0-156">In the trace results window, right-click the column header you want to group, and then click **Group By This Column**.</span></span>  
  
#### <a name="to-group-the-results-by-multiple-columns"></a><span data-ttu-id="394f0-157">So gruppieren Sie die Ergebnisse nach mehreren Spalten</span><span class="sxs-lookup"><span data-stu-id="394f0-157">To group the results by multiple columns</span></span>  
  
1.  <span data-ttu-id="394f0-158">Öffnen Sie eine XEL-Datei, um die Ablaufverfolgungsergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="394f0-158">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="394f0-159"> Sie können auch mit der rechten Maustaste auf den Sitzungsnamen klicken, **Livedaten ansehen**auswählen und dann auf der Symbolleiste auf die Schaltfläche **Datenfeed beenden** klicken.</span><span class="sxs-lookup"><span data-stu-id="394f0-159">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.</span></span>  
  
2.  <span data-ttu-id="394f0-160">Klicken Sie auf der Symbolleiste für erweiterte Ereignisse auf die Schaltfläche **Gruppierung** .</span><span class="sxs-lookup"><span data-stu-id="394f0-160">Click the **Grouping** button on the Extended Events toolbar.</span></span>  
  
3.  <span data-ttu-id="394f0-161">Wählen Sie im Dialogfeld **Gruppierung** im Feld **Verfügbare Spalten** die Spalten aus, die Sie gruppieren möchten, und klicken Sie dann auf den Pfeil nach rechts.</span><span class="sxs-lookup"><span data-stu-id="394f0-161">In the **Grouping** dialog box, in the **Available columns** box, select the columns you want to group, and then click the right arrow.</span></span>  
  
     <span data-ttu-id="394f0-162">Um die Gruppierungsreihenfolge zu ändern, klicken Sie im Abschnitt **Spalten gruppiert nach** auf den Pfeil nach links bzw. rechts.</span><span class="sxs-lookup"><span data-stu-id="394f0-162">To change the grouping order, in the **Columns grouped on** section, click the up or down arrows.</span></span>  
  
     <span data-ttu-id="394f0-163">Um Spalten aus der Gruppierung zu entfernen, wählen Sie in der Liste **Spalten gruppiert nach** die zu entfernenden Spalten aus, und klicken Sie anschließend auf den Pfeil nach links.</span><span class="sxs-lookup"><span data-stu-id="394f0-163">To remove columns from the grouping, in the **Columns grouped on** box, select the columns you want to remove and then click the left arrow.</span></span>  
  
4.  <span data-ttu-id="394f0-164">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="394f0-164">Click **OK**.</span></span>  
  
##  <a name="aggregate-results"></a><a name="AggregateResults"></a><span data-ttu-id="394f0-165">Aggregat Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="394f0-165">Aggregate Results</span></span>  
 <span data-ttu-id="394f0-166">Erweiterte Ereignisse unterstützen fünf Aggregationsfunktionen:</span><span class="sxs-lookup"><span data-stu-id="394f0-166">Extended Events supports five aggregation functions:</span></span>  
  
-   <span data-ttu-id="394f0-167">SUM</span><span class="sxs-lookup"><span data-stu-id="394f0-167">Sum</span></span>  
  
-   <span data-ttu-id="394f0-168">Min</span><span class="sxs-lookup"><span data-stu-id="394f0-168">Min</span></span>  
  
-   <span data-ttu-id="394f0-169">Max</span><span class="sxs-lookup"><span data-stu-id="394f0-169">Max</span></span>  
  
-   <span data-ttu-id="394f0-170">Average</span><span class="sxs-lookup"><span data-stu-id="394f0-170">Average</span></span>  
  
-   <span data-ttu-id="394f0-171">Anzahl</span><span class="sxs-lookup"><span data-stu-id="394f0-171">Count</span></span>  
  
 <span data-ttu-id="394f0-172">Sum, Min, Max und Average können nur mit verfügbaren numerischen Spalten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="394f0-172">Sum, Min,  Max, and Average can only be used with available numeric columns.</span></span> <span data-ttu-id="394f0-173">Count ist die Anzahl von Werten ungleich NULL, die für die ausgewählte Spalte in der Gruppe vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="394f0-173">Count is the number of non-null values that exist for the selected column in the group.</span></span>  
  
#### <a name="to-aggregate-results"></a><span data-ttu-id="394f0-174">So aggregieren Sie Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="394f0-174">To aggregate results</span></span>  
  
1.  <span data-ttu-id="394f0-175">Öffnen Sie eine XEL-Datei, um die Ablaufverfolgungsergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="394f0-175">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="394f0-176"> Sie können auch mit der rechten Maustaste auf den Sitzungsnamen klicken, **Livedaten ansehen**auswählen und dann auf der Symbolleiste auf die Schaltfläche **Datenfeed beenden** klicken.</span><span class="sxs-lookup"><span data-stu-id="394f0-176">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="394f0-177">Die Aggregation wird für eine Gruppe ausgeführt, deshalb müssen Sie die Ergebnisse gruppieren, bevor Sie die Aggregation ausführen können.</span><span class="sxs-lookup"><span data-stu-id="394f0-177">Aggregation is run against a group, so you must group the results before you can perform the aggregation.</span></span>  
  
2.  <span data-ttu-id="394f0-178">Klicken Sie auf der Symbolleiste für erweiterte Ereignisse auf die Schaltfläche **Aggregat** .</span><span class="sxs-lookup"><span data-stu-id="394f0-178">On the Extended Events toolbar, click the **Aggregate** button.</span></span>  
  
     <span data-ttu-id="394f0-179">Das Dialogfeld **Aggregation** wird mit den für die Aggregation verfügbaren Spalten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="394f0-179">The **Aggregation** dialog box appears displaying the columns available for aggregation.</span></span>  
  
3.  <span data-ttu-id="394f0-180">Wählen Sie unter **Aggregationstyp**in der Dropdownliste aus, wie Sie die entsprechende Spalte aggregieren möchten.</span><span class="sxs-lookup"><span data-stu-id="394f0-180">Under **Aggregation Type**, select how you want to aggregate the corresponding column from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="394f0-181">Wählen Sie im Feld **Aggregation sortieren nach** in der Dropdownliste die Spalte aus, nach der die Sortierung erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="394f0-181">In the **Sort aggregation by** box, select the column you want to sort by from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="394f0-182">Aktivieren Sie die Option **In aufsteigender Reihenfolge** , um das Aggregationsergebnis in aufsteigender Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="394f0-182">Select the **In ascending order** option to sort the aggregation result in ascending order.</span></span>  
  
6.  <span data-ttu-id="394f0-183">Aktivieren Sie die Option **In absteigender Reihenfolge** , um das Aggregationsergebnis in absteigender Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="394f0-183">Select the **In descending order** option to sort the aggregation result in descending order.</span></span>  
  
7.  <span data-ttu-id="394f0-184">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="394f0-184">Click **OK**.</span></span>  
  
##  <a name="filter-results"></a><a name="Filter"></a><span data-ttu-id="394f0-185">Filter Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="394f0-185">Filter Results</span></span>  
 <span data-ttu-id="394f0-186">Sie können Filter auf Ablaufverfolgungsergebnisse anwenden, um die Ablaufverfolgungsergebnisse einzugrenzen, die im Ablaufverfolgungsfenster angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="394f0-186">You can apply filters to narrow down the trace results that are displayed in the trace window.</span></span> <span data-ttu-id="394f0-187">Der Anzeigefilter umfasst einen Zeitfilter und einen erweiterten Filter.</span><span class="sxs-lookup"><span data-stu-id="394f0-187">The display filter includes a time filter and an advanced filter.</span></span> <span data-ttu-id="394f0-188">Sie filtern mithilfe des Zeitfilters die Ablaufverfolgungsergebnisse nach Ereigniszeitstempel und erstellen mithilfe des erweiterten Filters Filterbedingungen mit Ereignisfeldern und -aktionen.</span><span class="sxs-lookup"><span data-stu-id="394f0-188">You use the time filter to filter the trace results by event timestamp, and you use the advanced filter to construct filter conditions using the event fields and actions.</span></span> <span data-ttu-id="394f0-189">Zwischen Zeit- und erweitertem Filter besteht eine logische UND-Beziehung.</span><span class="sxs-lookup"><span data-stu-id="394f0-189">There is an logical AND relationship between the Time and Advanced Filters.</span></span>  
  
#### <a name="to-create-a-filter"></a><span data-ttu-id="394f0-190">So erstellen Sie einen Filter</span><span class="sxs-lookup"><span data-stu-id="394f0-190">To create a filter</span></span>  
  
1.  <span data-ttu-id="394f0-191">Öffnen Sie eine XEL-Datei, um die Ablaufverfolgungsergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="394f0-191">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="394f0-192"> Sie können auch mit der rechten Maustaste auf den Sitzungsnamen klicken, und dann **Livedaten ansehen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="394f0-192">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="394f0-193">Wählen Sie im Fenster mit den Ablaufverfolgungsergebnissen die Ergebnisse aus, die Sie filtern möchten, und klicken Sie dann auf der Symbolleiste Erweiterte Ereignisse auf die Schaltfläche **Filter** .</span><span class="sxs-lookup"><span data-stu-id="394f0-193">In the trace results window, select the results you want to filter, and then on the Extended Events toolbar, click the **Filters** button.</span></span>  
  
3.  <span data-ttu-id="394f0-194">Wählen Sie zum Festlegen des Zeitfilters im Dialogfeld **Filter** die Option **Zeitfilter festlegen** aus, und ziehen Sie die Schieberegler, um die Zeitachse festzulegen.</span><span class="sxs-lookup"><span data-stu-id="394f0-194">In the **Filters** dialog box, select **Set time filter** to set the time filter by dragging the slider bars to set the timeline.</span></span> <span data-ttu-id="394f0-195">Beachten Sie, dass beim Bewegen des Schiebereglers der Zeitwert im Zeitfeld dementsprechend angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="394f0-195">Note that when you move the slider bars, the time box displays the time value accordingly.</span></span> <span data-ttu-id="394f0-196">Sie können die Zeit auch in den Zeitfeldern eingeben oder in der Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="394f0-196">You can also enter the time in the time boxes, or you select it from the drop-down list.</span></span> <span data-ttu-id="394f0-197">Wenn Sie die Zeit eingeben, bewegt sich der linke Zeitschieberegler entsprechend.</span><span class="sxs-lookup"><span data-stu-id="394f0-197">Note that when you enter the time, the left time slider will move accordingly.</span></span>  
  
4.  <span data-ttu-id="394f0-198">Wenden Sie im Abschnitt **zusätzliche Filter** die Filterkriterien an, und klicken Sie dann auf **anwenden**.</span><span class="sxs-lookup"><span data-stu-id="394f0-198">In the **Additional Filters** section, apply your filter criteria, and then click **Apply**.</span></span> <span data-ttu-id="394f0-199">Wenn Sie mit dem Erstellen des Filters fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="394f0-199">When your finished created the filter, click **OK**.</span></span>  
  
 <span data-ttu-id="394f0-200">Wenn ein Ereignisfeld über den gleichen Namen wie eine Aktion verfügt, liegt ein Sonderfall vor.</span><span class="sxs-lookup"><span data-stu-id="394f0-200">A special situation is when an event field has the same name as an action.</span></span> <span data-ttu-id="394f0-201">Ein Beispiel dafür ist session_id.</span><span class="sxs-lookup"><span data-stu-id="394f0-201">An example of this would be session_id.</span></span> <span data-ttu-id="394f0-202">Es gibt mehrere Ereignisse, die ein Feld session_id enthalten, und Sie könnten auch die Aktion session_id hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="394f0-202">There are several events that include a session_id field and you could also add the session_id action.</span></span> <span data-ttu-id="394f0-203">Beide Informationen werden gesammelt, im Anzeigeraster des Profilers für erweiterte Ereignisse wird jedoch folgende Logik angewendet.</span><span class="sxs-lookup"><span data-stu-id="394f0-203">Both pieces of information are collected, but the Extended Events profiler display grid uses the following logic.</span></span>  
  
-   <span data-ttu-id="394f0-204">Nur eine Kopie der Spalte (in diesem Fall session_id) wird in der Rasteranzeige dargestellt.</span><span class="sxs-lookup"><span data-stu-id="394f0-204">Only one copy of the column (session_id in this case) is shown in the grid display.</span></span>  
  
-   <span data-ttu-id="394f0-205">Wenn sowohl Felder als auch eine Aktion in den Daten enthalten sind, wird der Feldwert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="394f0-205">If both fields and action exist in the data, the field value is shown.</span></span>  
  
-   <span data-ttu-id="394f0-206">Wenn nur ein Feld oder eine Aktion in den Daten enthalten ist, wird das Feld oder die Aktion angezeigt.</span><span class="sxs-lookup"><span data-stu-id="394f0-206">If only field or action is exists in the data, the field or action is displayed.</span></span>  
  
-   <span data-ttu-id="394f0-207">Wenn weder eine Aktion noch ein Feld vorhanden ist, wird NULL angezeigt.</span><span class="sxs-lookup"><span data-stu-id="394f0-207">If neither action nor field exists, display NULL.</span></span>  
  
##  <a name="search-for-text-in-columns"></a><a name="Search"></a><span data-ttu-id="394f0-208">In Spalten nach Text suchen</span><span class="sxs-lookup"><span data-stu-id="394f0-208">Search for Text in Columns</span></span>  
  
1.  <span data-ttu-id="394f0-209">Öffnen Sie eine XEL-Datei, um die Ablaufverfolgungsergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="394f0-209">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="394f0-210"> Sie können auch mit der rechten Maustaste auf den Sitzungsnamen klicken, und dann **Livedaten ansehen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="394f0-210">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="394f0-211">Klicken Sie auf der Symbolleiste für erweiterte Ereignisse auf die Schaltfläche **Suchen** .</span><span class="sxs-lookup"><span data-stu-id="394f0-211">On the Extended Events toolbar, click the **Find** button.</span></span>  
  
3.  <span data-ttu-id="394f0-212">Geben Sie im Dialogfeld **In erweiterten Ereignissen suchen** im Feld **Suchen nach** den Text ein, nach dem Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="394f0-212">In the **Find in Extended Events** dialog box, in the **Find what** box, enter the text you want to search for.</span></span>  
  
     <span data-ttu-id="394f0-213">In der Dropdownliste können Sie eine der letzten 20 Suchzeichenfolgen auswählen.</span><span class="sxs-lookup"><span data-stu-id="394f0-213">You can select one of your last 20 search strings from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="394f0-214">Wählen Sie im Feld **Suchen in** in der Dropdownliste den Speicherort aus, an dem Sie nach dem angegebenen Text suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="394f0-214">In the **Look in** box, select the location in which to search for the specified text from the drop-down list.</span></span> <span data-ttu-id="394f0-215">Verwenden Sie zum Suchen die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="394f0-215">Use the following options for searching:</span></span>  
  
    -   <span data-ttu-id="394f0-216">**Tabellen Spalten**.</span><span class="sxs-lookup"><span data-stu-id="394f0-216">**Table Columns**.</span></span> <span data-ttu-id="394f0-217">Verwenden Sie diese Option, um alle sichtbaren Spalten im Ablaufverfolgungsfenster zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="394f0-217">Use this option to search all visible columns in the trace window.</span></span>  
  
    -   <span data-ttu-id="394f0-218">**Details**.</span><span class="sxs-lookup"><span data-stu-id="394f0-218">**Details**.</span></span> <span data-ttu-id="394f0-219">Verwenden Sie diese Option, um alle (höher gestuften und nicht höher gestuften) Spalten im Ablauf Verfolgungs Fenster zu durchsuchen, die vor dem Öffnen des Dialog Felds **in erweiterten Ereignissen suchen** ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="394f0-219">Use this option to search all columns (promoted and non-promoted) in the trace window that were selected before opening the **Find in Extended Events** dialog box.</span></span>  
  
    -   <span data-ttu-id="394f0-220">**\<Event column name>**.</span><span class="sxs-lookup"><span data-stu-id="394f0-220">**\<Event column name>**.</span></span> <span data-ttu-id="394f0-221">Verwenden Sie diese Option, um in einer bestimmten Ereignisspalte aus der Dropdownliste zu suchen.</span><span class="sxs-lookup"><span data-stu-id="394f0-221">Use this option to search in a specific event column from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="394f0-222">Verwenden Sie die folgenden Optionen, um anzugeben, wie Sie die Suche definieren möchten:</span><span class="sxs-lookup"><span data-stu-id="394f0-222">Use the following options to specify how you want to define the search:</span></span>  
  
    1.  <span data-ttu-id="394f0-223">**Groß-/Kleinschreibung**</span><span class="sxs-lookup"><span data-stu-id="394f0-223">**Match case**.</span></span> <span data-ttu-id="394f0-224">Verwenden Sie diese Option, um die Suchergebnisse für den Text anzuzeigen, den Sie im Feld **Suchen** nach eingegeben haben, das sowohl nach Inhalt als auch nach Groß-/Kleinschreibung übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="394f0-224">Use this option to display the search results for the text you entered in the **Find what** box that are matched both by content and by case.</span></span>  
  
    2.  <span data-ttu-id="394f0-225">Entsprechung für **ganzes Wort**suchen.</span><span class="sxs-lookup"><span data-stu-id="394f0-225">**Match whole word**.</span></span> <span data-ttu-id="394f0-226">Verwenden Sie diese Option, um nur die Suchergebnisse für den Text anzuzeigen, die mit vollständigen Wörtern übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="394f0-226">Use this option to display only the search results for the text you entered that match complete words.</span></span>  
  
    3.  <span data-ttu-id="394f0-227">**Suchen Sie nach oben**.</span><span class="sxs-lookup"><span data-stu-id="394f0-227">**Search up**.</span></span> <span data-ttu-id="394f0-228">Verwenden Sie diese Option, um ab der Cursorposition zum Anfang der Ergebnisse zu suchen.</span><span class="sxs-lookup"><span data-stu-id="394f0-228">Use this option to search from your cursor location to the beginning of the results.</span></span>  
  
    4.  <span data-ttu-id="394f0-229">**Verwenden**Sie.</span><span class="sxs-lookup"><span data-stu-id="394f0-229">**Use**.</span></span> <span data-ttu-id="394f0-230">Verwenden Sie diese Option, um die Sonderzeichen und die regulären Ausdrücke zu interpretieren, die Sie im Feld **Suchen nach** eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="394f0-230">Use this option to interpret the special characters and the regular expressions you entered in the **Find what** box.</span></span> <span data-ttu-id="394f0-231">Sonderzeichen zählen die Platzhalterzeichen (\*) und (?), mit denen Sie ein oder mehrere Zeichen darstellen.</span><span class="sxs-lookup"><span data-stu-id="394f0-231">Special characters include the wildcard characters (\*) and (?) to represent one or more characters.</span></span> <span data-ttu-id="394f0-232">Reguläre Ausdrücke sind besondere Schreibweisen, die verwendet wurden, um Muster im Suchtext zu definieren.</span><span class="sxs-lookup"><span data-stu-id="394f0-232">Regular expressions are special notations used to define patterns of search text.</span></span>  
  
6.  <span data-ttu-id="394f0-233">Klicken Sie auf **Weitersuchen** , um nach dem nächsten Vorkommen des Texts zu suchen, den Sie im Feld **Suchen nach** eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="394f0-233">Click **Find Next** to search for the next text that you entered in the **Find what** box.</span></span>  
  
##  <a name="change-the-display-settings"></a><a name="ChangeDisplay"></a><span data-ttu-id="394f0-234">Ändern der Anzeigeeinstellungen</span><span class="sxs-lookup"><span data-stu-id="394f0-234">Change the Display Settings</span></span>  
 <span data-ttu-id="394f0-235">Sie können Spalteninformationen (Spaltenreihenfolge, Mergespalte und Spaltenbreite) und Filterinformationen eines Ablaufverfolgungsergebnisses in einer Anzeigeeinstellungsdatei (VIEWSETTING-Datei) für erweiterte Ereignisse speichern.</span><span class="sxs-lookup"><span data-stu-id="394f0-235">You can save column information (column order, merge column, and column width) and filter information of a trace result into an Extended Events display setting file (.viewsetting file).</span></span> <span data-ttu-id="394f0-236">Nach dem Speichern der Datei können Sie sie auf die Ablaufverfolgungsergebnisse anwenden, um die Ansicht zu ändern.</span><span class="sxs-lookup"><span data-stu-id="394f0-236">After saving the file, you can apply it to your trace results to change the view.</span></span>  
  
#### <a name="to-change-the-display-settings"></a><span data-ttu-id="394f0-237">So ändern Sie die Anzeigeeinstellungen</span><span class="sxs-lookup"><span data-stu-id="394f0-237">To change the display settings</span></span>  
  
1.  <span data-ttu-id="394f0-238">Öffnen Sie eine XEL-Datei, um die Ablaufverfolgungsergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="394f0-238">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="394f0-239"> Sie können auch mit der rechten Maustaste auf den Sitzungsnamen klicken, und dann **Livedaten ansehen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="394f0-239">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="394f0-240">Wählen Sie im Fenster mit den Ablaufverfolgungsergebnissen auf der Symbolleiste für erweiterte Ereignisse oder im Menü **Anzeigeeinstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="394f0-240">In the trace results window, on the Extended Events toolbar or menu, select **Display Settings**.</span></span>  
  
3.  <span data-ttu-id="394f0-241">Wählen Sie eine der folgenden Optionen aus der Dropdownliste aus:</span><span class="sxs-lookup"><span data-stu-id="394f0-241">From the drop-down list, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="394f0-242">**Speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="394f0-242">**Save as**.</span></span> <span data-ttu-id="394f0-243">Speichern Sie die Spalten- und Filterinformationen eines Ablaufverfolgungsergebnisses in einer VIEWSETTING-Datei.</span><span class="sxs-lookup"><span data-stu-id="394f0-243">Save the columns and filter information of a trace result to a .viewsetting file.</span></span>  
  
    -   <span data-ttu-id="394f0-244">**Öffnen**Sie.</span><span class="sxs-lookup"><span data-stu-id="394f0-244">**Open**.</span></span> <span data-ttu-id="394f0-245">Öffnen Sie eine vorhandene VIEWSETTING-Datei.</span><span class="sxs-lookup"><span data-stu-id="394f0-245">Open an existing .viewsetting file.</span></span>  
  
    -   <span data-ttu-id="394f0-246">**Zuletzt verwendete öffnen**.</span><span class="sxs-lookup"><span data-stu-id="394f0-246">**Open recent**.</span></span> <span data-ttu-id="394f0-247">Öffnen Sie eine vor kurzem gespeicherte VIEWSETTING-Datei.</span><span class="sxs-lookup"><span data-stu-id="394f0-247">Open a recently saved .viewsetting file.</span></span>  
  
  
