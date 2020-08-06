---
title: Hinzufügen eines Berichts (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 10ae54e7-0e8a-4dff-995d-05516c51d076
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 61a5444c437027d92a9f054e74cbcac6af5cc776
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726510"
---
# <a name="add-a-filter-report-builder-and-ssrs"></a><span data-ttu-id="a9195-102">Hinzufügen eines Filters (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="a9195-102">Add a Filter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a9195-103">Fügen Sie einem Dataset, einem Datenbereich oder einer Gruppe einen Filter hinzu, wenn Sie spezifische Werte in Berechnungen oder in die Anzeige einschließen bzw. davon ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="a9195-103">Add a filter to a dataset, data region, or group when you want to include or exclude specific values for calculations or display.</span></span> <span data-ttu-id="a9195-104">Filter werden zuerst auf das Dataset, dann auf den Datenbereich und anschließend auf die Gruppe angewendet (von oben nach unten bei Gruppenhierarchien).</span><span class="sxs-lookup"><span data-stu-id="a9195-104">Filters are applied at run time first on the dataset, and then on the data region, and then on the group, in top-down order for group hierarchies.</span></span> <span data-ttu-id="a9195-105">In einer Tabelle, Matrix oder Liste werden Filter für Zeilen- und Spaltengruppen sowie für angrenzende Gruppen unabhängig voneinander angewendet.</span><span class="sxs-lookup"><span data-stu-id="a9195-105">In a table, matrix, or list, filters for row groups, column groups, and adjacent groups are applied independently.</span></span> <span data-ttu-id="a9195-106">In Diagrammen werden Filter für Kategorie- und Reihengruppen unabhängig voneinander angewendet.</span><span class="sxs-lookup"><span data-stu-id="a9195-106">In a chart, filters for category groups and series groups are applied independently.</span></span>  
  
 <span data-ttu-id="a9195-107">Um einen Filter hinzuzufügen, müssen Sie eine oder mehrere Filtergleichungen angeben.</span><span class="sxs-lookup"><span data-stu-id="a9195-107">To add a filter, you must specify one or more filter equations.</span></span> <span data-ttu-id="a9195-108">Eine Filtergleichung besteht aus einem Ausdruck, der die zu filternden Daten definiert, einem Operator und dem Vergleichswert.</span><span class="sxs-lookup"><span data-stu-id="a9195-108">A filter equation consists of an expression that identifies the data that you want to filter, an operator, and the value to compare to.</span></span> <span data-ttu-id="a9195-109">Der Datentyp der gefilterten Daten und des Werts muss übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a9195-109">The data types of the filtered data and the value must match.</span></span> <span data-ttu-id="a9195-110">Bei Datasets und Datenbereichen wird das Filtern anhand aggregierter Werte nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a9195-110">Filtering on aggregate values for a dataset or data region is not supported.</span></span>  
  
 <span data-ttu-id="a9195-111">Um Datenpunkte in einem Diagramm zu filtern, können Sie einen Filter für eine Kategoriegruppe oder eine Reihengruppe festlegen.</span><span class="sxs-lookup"><span data-stu-id="a9195-111">To filter data points in a chart, you can set a filter on a category group or a series group.</span></span> <span data-ttu-id="a9195-112">Standardmäßig verwendet das Diagramm die integrierte Sum-Funktion, um Werte, die zur selben Gruppe gehören, in einem einzelnen Datenpunkt in der Reihe zu aggregieren.</span><span class="sxs-lookup"><span data-stu-id="a9195-112">By default, the chart uses the built-in function Sum to aggregate values that belong to the same group into an individual data point in the series.</span></span> <span data-ttu-id="a9195-113">Falls Sie die Aggregatfunktion einer Reihe ändern, müssen Sie auch die Aggregatfunktion im Filterausdruck ändern.</span><span class="sxs-lookup"><span data-stu-id="a9195-113">If you change the aggregate function of a series, you must change the aggregate function in the filter expression.</span></span>  
  
 <span data-ttu-id="a9195-114">Weitere Informationen zum Filtern von eingebetteten und freigegebenen Datasets finden Sie unter [Hinzufügen eines Filters zu einem Dataset (Berichts-Generator und SSRS)](../report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a9195-114">For more information about filtering embedded and shared datasets, see [Add a Filter to a Dataset &#40;Report Builder and SSRS&#41;](../report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-a-filter-on-a-data-region"></a><span data-ttu-id="a9195-115">So legen Sie einen Filter für einen Datenbereich fest</span><span class="sxs-lookup"><span data-stu-id="a9195-115">To set a filter on a data region</span></span>  
  
1.  <span data-ttu-id="a9195-116">Öffnen Sie einen Bericht in der **Entwurfssicht** .</span><span class="sxs-lookup"><span data-stu-id="a9195-116">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="a9195-117">Wählen Sie den Datenbereich auf der Entwurfs Oberfläche aus, und klicken Sie dann mit der rechten Maustaste auf _\<data region>_ **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a9195-117">Select the data region on the design surface, and then right-click _\<data region>_**Properties**.</span></span> <span data-ttu-id="a9195-118">Wählen Sie bei einem Messgerät **Messgerätbereichseigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="a9195-118">For a gauge, select **Gauge Panel Properties**.</span></span> <span data-ttu-id="a9195-119">Das _\<data region>_ Dialogfeld **Eigenschaften** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a9195-119">The _\<data region>_**Properties** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a9195-120">Klicken Sie im Tablix-Datenbereich mit der rechten Maustaste auf das Handle in der Eckzelle, einer Zeile oder Spalte, und klicken Sie anschließend auf **Tablix-Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a9195-120">On a Tablix data region, right-click the corner cell or a row or column handle, and then click **Tablix Properties**.</span></span>  
  
3.  <span data-ttu-id="a9195-121">Klicken Sie auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="a9195-121">Click **Filters**.</span></span> <span data-ttu-id="a9195-122">Die aktuelle Liste mit Filtergleichungen wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9195-122">This displays the current list of filter equations.</span></span> <span data-ttu-id="a9195-123">Standardmäßig ist die Liste leer.</span><span class="sxs-lookup"><span data-stu-id="a9195-123">By default, the list is empty.</span></span>  
  
4.  <span data-ttu-id="a9195-124">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a9195-124">Click **Add**.</span></span> <span data-ttu-id="a9195-125">Es wird eine neue leere Filtergleichung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9195-125">A new blank filter equation appears.</span></span>  
  
5.  <span data-ttu-id="a9195-126">Geben Sie unter **Ausdruck**einen Ausdruck für das zu filternde Feld ein, oder wählen Sie einen Ausdruck aus.</span><span class="sxs-lookup"><span data-stu-id="a9195-126">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="a9195-127">Wenn Sie den Ausdruck bearbeiten möchten, klicken Sie auf die Ausdrucksschaltfläche (*fx*).</span><span class="sxs-lookup"><span data-stu-id="a9195-127">To edit the expression, click the expression (*fx*) button.</span></span>  
  
6.  <span data-ttu-id="a9195-128">Wählen Sie im Dropdownfeld den Datentyp aus, der dem Typ der Daten in dem Ausdruck entspricht, den Sie in Schritt 5 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a9195-128">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
7.  <span data-ttu-id="a9195-129">Wählen Sie im Feld **Operator** den Operator aus, der vom Filter zum Vergleichen der Werte in den Feldern **Ausdruck** und **Wert** verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a9195-129">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="a9195-130">Der gewählte Operator bestimmt, wie viele Werte ab dem nächsten Schritt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9195-130">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
8.  <span data-ttu-id="a9195-131">Geben Sie im Feld **Wert** den Ausdruck oder Wert ein, den der Filter mit dem Wert im Feld **Ausdruck**vergleichen soll.</span><span class="sxs-lookup"><span data-stu-id="a9195-131">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="a9195-132">Beispiele für Filtergleichungen finden Sie unter [Beispiele für Filtergleichungen (Berichts-Generator und SSRS)](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a9195-132">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-set-a-filter-on-a-tablix-row-or-column-group"></a><span data-ttu-id="a9195-133">So legen Sie einen Filter für eine Tablix-Zeilen- oder Spaltengruppe fest</span><span class="sxs-lookup"><span data-stu-id="a9195-133">To set a filter on a Tablix row or column group</span></span>  
  
1.  <span data-ttu-id="a9195-134">Öffnen Sie einen Bericht in der **Entwurfssicht** .</span><span class="sxs-lookup"><span data-stu-id="a9195-134">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="a9195-135">Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf den Tabellen-, Matrix- oder Listendatenbereich, um ihn auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="a9195-135">Right-click the table, matrix, or list data region on the design surface to select it.</span></span> <span data-ttu-id="a9195-136">Im Gruppierungsbereich werden die Gruppen für das ausgewählte Element angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9195-136">The Grouping pane displays the groups for the selected item.</span></span>  
  
3.  <span data-ttu-id="a9195-137">Klicken Sie im Gruppierungsbereich mit der rechten Maustaste auf die Gruppe, und klicken Sie anschließend auf **Gruppe bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="a9195-137">In the Grouping pane, right-click the group, and then click **Edit Group**.</span></span> <span data-ttu-id="a9195-138">Das Dialogfeld **Tablix-Gruppe** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a9195-138">The **Tablix Group** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="a9195-139">Klicken Sie auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="a9195-139">Click **Filters**.</span></span> <span data-ttu-id="a9195-140">Die aktuelle Liste mit Filtergleichungen wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9195-140">This displays the current list of filter equations.</span></span> <span data-ttu-id="a9195-141">Standardmäßig ist die Liste leer.</span><span class="sxs-lookup"><span data-stu-id="a9195-141">By default, the list is empty.</span></span>  
  
5.  <span data-ttu-id="a9195-142">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a9195-142">Click **Add**.</span></span> <span data-ttu-id="a9195-143">Es wird eine neue leere Filtergleichung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9195-143">A new blank filter equation appears.</span></span>  
  
6.  <span data-ttu-id="a9195-144">Geben Sie unter **Ausdruck**einen Ausdruck für das zu filternde Feld ein, oder wählen Sie einen Ausdruck aus.</span><span class="sxs-lookup"><span data-stu-id="a9195-144">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="a9195-145">Wenn Sie den Ausdruck bearbeiten möchten, klicken Sie auf die Ausdrucksschaltfläche (*fx*).</span><span class="sxs-lookup"><span data-stu-id="a9195-145">To edit the expression, click the expression (*fx*) button.</span></span>  
  
7.  <span data-ttu-id="a9195-146">Wählen Sie im Dropdownfeld den Datentyp aus, der dem Typ der Daten in dem Ausdruck entspricht, den Sie in Schritt 5 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a9195-146">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
8.  <span data-ttu-id="a9195-147">Wählen Sie im Feld **Operator** den Operator aus, der vom Filter zum Vergleichen der Werte in den Feldern **Ausdruck** und **Wert** verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a9195-147">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="a9195-148">Der gewählte Operator bestimmt, wie viele Werte ab dem nächsten Schritt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9195-148">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
9. <span data-ttu-id="a9195-149">Geben Sie im Feld **Wert** den Ausdruck oder Wert ein, den der Filter mit dem Wert im Feld **Ausdruck**vergleichen soll.</span><span class="sxs-lookup"><span data-stu-id="a9195-149">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="a9195-150">Beispiele für Filtergleichungen finden Sie unter [Beispiele für Filtergleichungen (Berichts-Generator und SSRS)](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a9195-150">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-set-a-filter-on-a-chart-category-group"></a><span data-ttu-id="a9195-151">So legen Sie einen Filter für eine Diagrammkategoriegruppe fest</span><span class="sxs-lookup"><span data-stu-id="a9195-151">To set a filter on a Chart category group</span></span>  
  
1.  <span data-ttu-id="a9195-152">Öffnen Sie einen Bericht in der **Entwurfssicht** .</span><span class="sxs-lookup"><span data-stu-id="a9195-152">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="a9195-153">Klicken Sie auf der Entwurfsoberfläche zwei Mal auf das Diagramm, um die Daten-, Reihen- und Kategoriefeldablagezonen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a9195-153">On the design surface, click the chart twice to bring up data, series and category field drop zones.</span></span>  
  
3.  <span data-ttu-id="a9195-154">Klicken Sie mit der rechten Maustaste auf ein Feld in der Kategoriefeldablagezone, und wählen Sie **Kategoriegruppeneigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="a9195-154">Right-click on a field contained in the category field drop zone and select **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="a9195-155">Klicken Sie auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="a9195-155">Click **Filters**.</span></span> <span data-ttu-id="a9195-156">Die aktuelle Liste mit Filtergleichungen wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9195-156">This displays the current list of filter equations.</span></span> <span data-ttu-id="a9195-157">Standardmäßig ist die Liste leer.</span><span class="sxs-lookup"><span data-stu-id="a9195-157">By default, the list is empty.</span></span>  
  
5.  <span data-ttu-id="a9195-158">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a9195-158">Click **Add**.</span></span> <span data-ttu-id="a9195-159">Es wird eine neue leere Filtergleichung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9195-159">A new blank filter equation appears.</span></span>  
  
6.  <span data-ttu-id="a9195-160">Geben Sie unter **Ausdruck**einen Ausdruck für das zu filternde Feld ein, oder wählen Sie einen Ausdruck aus.</span><span class="sxs-lookup"><span data-stu-id="a9195-160">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="a9195-161">Wenn Sie den Ausdruck bearbeiten möchten, klicken Sie auf die Ausdrucksschaltfläche (*fx*).</span><span class="sxs-lookup"><span data-stu-id="a9195-161">To edit the expression, click the expression (*fx*) button.</span></span>  
  
7.  <span data-ttu-id="a9195-162">Wählen Sie im Dropdownfeld den Datentyp aus, der dem Typ der Daten in dem Ausdruck entspricht, den Sie in Schritt 5 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a9195-162">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
8.  <span data-ttu-id="a9195-163">Wählen Sie im Feld **Operator** den Operator aus, der vom Filter zum Vergleichen der Werte in den Feldern **Ausdruck** und **Wert** verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a9195-163">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="a9195-164">Der gewählte Operator bestimmt, wie viele Werte ab dem nächsten Schritt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9195-164">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
9. <span data-ttu-id="a9195-165">Geben Sie im Feld **Wert** den Ausdruck oder Wert ein, den der Filter mit dem Wert im Feld **Ausdruck**vergleichen soll.</span><span class="sxs-lookup"><span data-stu-id="a9195-165">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="a9195-166">Beispiele für Filtergleichungen finden Sie unter [Beispiele für Filtergleichungen (Berichts-Generator und SSRS)](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a9195-166">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-set-a-filter-on-a-chart-series-group"></a><span data-ttu-id="a9195-167">So legen Sie einen Filter für eine Diagrammreihengruppe fest</span><span class="sxs-lookup"><span data-stu-id="a9195-167">To set a filter on a Chart series group</span></span>  
  
1.  <span data-ttu-id="a9195-168">Öffnen Sie einen Bericht in der **Entwurfssicht** .</span><span class="sxs-lookup"><span data-stu-id="a9195-168">Open a report in **Design** view.</span></span>  
  
2.  <span data-ttu-id="a9195-169">Klicken Sie auf der Entwurfsoberfläche zwei Mal auf das Diagramm, um die Daten-, Reihen- und Kategoriefeldablagezonen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a9195-169">On the design surface, click the chart twice to bring up data, series and category field drop zones.</span></span>  
  
3.  <span data-ttu-id="a9195-170">Klicken Sie mit der rechten Maustaste auf ein Feld in der Reihenfeldablagezone, und wählen Sie **Reihengruppeneigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="a9195-170">Right-click on a field contained in the series field drop zone and select **Series Group Properties**.</span></span>  
  
4.  <span data-ttu-id="a9195-171">Klicken Sie auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="a9195-171">Click **Filters**.</span></span> <span data-ttu-id="a9195-172">Die aktuelle Liste mit Filtergleichungen wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9195-172">This displays the current list of filter equations.</span></span> <span data-ttu-id="a9195-173">Standardmäßig ist die Liste leer.</span><span class="sxs-lookup"><span data-stu-id="a9195-173">By default, the list is empty.</span></span>  
  
5.  <span data-ttu-id="a9195-174">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a9195-174">Click **Add**.</span></span> <span data-ttu-id="a9195-175">Es wird eine neue leere Filtergleichung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9195-175">A new blank filter equation appears.</span></span>  
  
6.  <span data-ttu-id="a9195-176">Geben Sie unter **Ausdruck**einen Ausdruck für das zu filternde Feld ein, oder wählen Sie einen Ausdruck aus.</span><span class="sxs-lookup"><span data-stu-id="a9195-176">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="a9195-177">Wenn Sie den Ausdruck bearbeiten möchten, klicken Sie auf die Ausdrucksschaltfläche (*fx*).</span><span class="sxs-lookup"><span data-stu-id="a9195-177">To edit the expression, click the expression (*fx*) button.</span></span>  
  
7.  <span data-ttu-id="a9195-178">Wählen Sie im Dropdownfeld den Datentyp aus, der dem Typ der Daten in dem Ausdruck entspricht, den Sie in Schritt 5 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a9195-178">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
8.  <span data-ttu-id="a9195-179">Wählen Sie im Feld **Operator** den Operator aus, der vom Filter zum Vergleichen der Werte in den Feldern **Ausdruck** und **Wert** verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a9195-179">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="a9195-180">Der gewählte Operator bestimmt, wie viele Werte ab dem nächsten Schritt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9195-180">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
9. <span data-ttu-id="a9195-181">Geben Sie im Feld **Wert** den Ausdruck oder Wert ein, den der Filter mit dem Wert im Feld **Ausdruck**vergleichen soll.</span><span class="sxs-lookup"><span data-stu-id="a9195-181">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="a9195-182">Beispiele für Filtergleichungen finden Sie unter [Beispiele für Filtergleichungen (Berichts-Generator und SSRS)](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a9195-182">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a9195-183">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a9195-183">See Also</span></span>  
 <span data-ttu-id="a9195-184">[Hinzufügen von Datasetfiltern, Datenbereichsfiltern und Gruppenfiltern &#40;Berichts-Generator und SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="a9195-184">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="a9195-185">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a9195-185">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a9195-186">[Messgeräte &#40;Berichts-Generator und SSRS&#41;](gauges-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a9195-186">[Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a9195-187">[Listet &#40;Berichts-Generator und SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a9195-187">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a9195-188">Diagramme &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a9195-188">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
