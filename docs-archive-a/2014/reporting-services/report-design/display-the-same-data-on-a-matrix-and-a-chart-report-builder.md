---
title: Anzeigen derselben Daten in einer Matrix und einem Diagramm (Berichts-Generator) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1262f283-9fc2-4bc1-9c79-457f7642abc7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7746ce1f06d4dcc67c51ddc40714f19a3ff83d51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721163"
---
# <a name="display-the-same-data-on-a-matrix-and-a-chart-report-builder"></a><span data-ttu-id="beeec-102">Anzeigen derselben Daten in einer Matrix und einem Diagramm (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="beeec-102">Display the Same Data on a Matrix and a Chart (Report Builder)</span></span>
  <span data-ttu-id="beeec-103">Wenn sie dieselben Daten in einer Matrix und einem Diagramm anzeigen möchten, müssen Sie für beide Datenbereiche Eigenschaften festlegen, um dasselbe Dataset anzugeben, und außerdem identische Ausdrücke für Filter, Gruppen, Sortierungen und Daten.</span><span class="sxs-lookup"><span data-stu-id="beeec-103">When you want to show the same data in a matrix and a chart, you must set properties on both data regions to specify the same dataset, and also the same expressions for filters, groups, sorts, and data.</span></span>  
  
 <span data-ttu-id="beeec-104">Da beide Datenbereiche denselben Vorgänger für die Daten aufweisen (das Berichtsdataset), können Sie der Matrix eine interaktive Sortierschaltfläche hinzufügen, auf die Benutzer klicken können, um die Sortierreihenfolge in der Matrix und im Diagramm zu ändern.</span><span class="sxs-lookup"><span data-stu-id="beeec-104">Because both data regions will have the same ancestor for data (the report dataset), you can add an interactive sort button to the matrix that, when the user clicks it, changes the sort order for both the matrix and the chart.</span></span> <span data-ttu-id="beeec-105">Weitere Informationen finden Sie unter [Hinzufügen einer interaktiven Sortierung zu einer Tabelle oder Matrix &#40;Berichts-Generator und SSRS&#41;](add-interactive-sort-to-a-table-or-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="beeec-105">For more information, see [Add Interactive Sort to a Table or Matrix &#40;Report Builder and SSRS&#41;](add-interactive-sort-to-a-table-or-matrix-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="beeec-106">Wenn die Spaltengruppenwerte der Matrix als Legende für das Diagramm verwendet werden sollen, müssen Sie die Farben für die Reihendaten im Diagramm angeben und anschließend dieselben Farben als Füllfarben für den Hintergrund der Textfelder in der Matrixzelle verwenden, in der die Gruppenwerte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="beeec-106">To use the matrix column group values as a legend for the chart, you must specify the colors for the series data on the chart, and then use the same colors as the fill colors for the background of the text boxes in the matrix cell that displays the group values.</span></span> <span data-ttu-id="beeec-107">Weitere Informationen finden Sie unter [Angeben von Farben, die für mehrere Formdiagramme konsistent sind &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="beeec-107">For more information, see [Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="beeec-108">Wenn zu viele Gruppenwerte für die Gruppendefinitionen vorhanden sind, wird der Bericht zur Laufzeit möglicherweise überladen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="beeec-108">At run-time, your report may appear cluttered if there are too many group values for your group definitions.</span></span> <span data-ttu-id="beeec-109">Möglicherweise müssen Sie Werte filtern, Gruppen kombinieren oder den Schwellenwert für das Diagramm anpassen, sodass die Gruppen automatisch kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="beeec-109">You might need to filter values, combine groups, or adjust the threshold for the chart to combine groups for you.</span></span> <span data-ttu-id="beeec-110">Weitere Informationen finden Sie unter [Verknüpfen mehrerer Datenbereiche mit einem Dataset &#40;Berichts-Generator und SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="beeec-110">For more information, see [Linking Multiple Data Regions to the Same Dataset &#40;Report Builder and SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md)</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-matrix-and-chart-to-display-the-same-data"></a><span data-ttu-id="beeec-111">So fügen Sie eine Matrix und ein Diagramm zum Anzeigen derselben Daten hinzu</span><span class="sxs-lookup"><span data-stu-id="beeec-111">To add a matrix and chart to display the same data</span></span>  
  
1.  <span data-ttu-id="beeec-112">Öffnen Sie einen Bericht in der Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="beeec-112">Open a report in design view.</span></span>  
  
2.  <span data-ttu-id="beeec-113">Klicken Sie auf der Registerkarte **Einfügen** in der Gruppe **Datenbereiche** auf **Matrix**, und klicken Sie dann in den Bericht oder in ein Rechteck im Bericht.</span><span class="sxs-lookup"><span data-stu-id="beeec-113">From the **Insert** tab, in the **Data Regions** group, click **Matrix**, and then click the report body or in a rectangle in the report body.</span></span> <span data-ttu-id="beeec-114">Dem Bericht wird eine neue Matrix hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="beeec-114">A matrix is added to the report.</span></span>  
  
3.  <span data-ttu-id="beeec-115">Klicken Sie auf der Registerkarte **Einfügen** in der Gruppe **Datenbereiche** auf **Diagramm**, und wählen Sie dann den Diagrammtyp aus.</span><span class="sxs-lookup"><span data-stu-id="beeec-115">From the **Insert** tab, in the **Data Regions** group, click **Chart**, and then select the chart type.</span></span> <span data-ttu-id="beeec-116">Dem Bericht wird ein Diagramm hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="beeec-116">A chart is added to the report.</span></span>  
  
4.  <span data-ttu-id="beeec-117">(Optional) Klicken Sie auf der Registerkarte **Einfügen** in der Gruppe **Berichtselemente** auf **Rechteck**und anschließend auf den Bericht.</span><span class="sxs-lookup"><span data-stu-id="beeec-117">(Optional) From the **Insert** tab, in the **Report Items** group, click **Rectangle**, and then click the report.</span></span> <span data-ttu-id="beeec-118">Dem Bericht wird ein Rechteck hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="beeec-118">A rectangle is added to the report.</span></span> <span data-ttu-id="beeec-119">Ziehen Sie die Matrix und das Diagramm aus Schritt 2 und 3 in das Rechteck.</span><span class="sxs-lookup"><span data-stu-id="beeec-119">Drag the matrix and chart from steps 2 and 3 into the rectangle.</span></span>  
  
     <span data-ttu-id="beeec-120">Wenn Sie mehrere Datenbereiche in den Rechteckcontainer platzieren, können Sie steuern, wie die Matrix und das Diagramm beim Anzeigen des Berichts gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="beeec-120">By placing multiple data regions in the rectangle container, you help control how the matrix and chart render when you view the report.</span></span>  
  
     <span data-ttu-id="beeec-121">In den nächsten Schritten wählen Sie dasselbe Datasetfeld für die Anzeige in der Matrix und für die Anzeige im Diagramm aus.</span><span class="sxs-lookup"><span data-stu-id="beeec-121">In the next few steps, you will choose the same dataset field to display in the matrix and to display in the chart.</span></span>  
  
5.  <span data-ttu-id="beeec-122">Ziehen Sie ein numerisches Datasetfeld aus dem Berichtsdatenbereich in die Datenzelle in der Matrix.</span><span class="sxs-lookup"><span data-stu-id="beeec-122">From the Report Data pane, drag a numeric dataset field to the Data cell in the matrix.</span></span>  
  
     <span data-ttu-id="beeec-123">Standardmäßig wird die Aggregatfunktion „Sum“ zum Berechnen des Gruppenwerts verwendet.</span><span class="sxs-lookup"><span data-stu-id="beeec-123">By default, the aggregate function Sum is used for calculating the group value.</span></span> <span data-ttu-id="beeec-124">Wenn Sie die Aggregatfunktion in der Matrix ändern, müssen Sie diese auch im Diagramm ändern.</span><span class="sxs-lookup"><span data-stu-id="beeec-124">If you change the aggregate function in the matrix, you must change in the chart also.</span></span>  
  
6.  <span data-ttu-id="beeec-125">Klicken Sie in der Matrix mit der rechten Maustaste auf die Zelle mit den Daten, klicken Sie auf **Textfeldeigenschaften**, und klicken Sie anschließend auf **Zahl**.</span><span class="sxs-lookup"><span data-stu-id="beeec-125">In the matrix, right-click the cell with data, click **Text Box Properties**, and then click **Number**.</span></span> <span data-ttu-id="beeec-126">Wählen Sie ein für den Datasetfeldwert geeignetes Format aus.</span><span class="sxs-lookup"><span data-stu-id="beeec-126">Choose an appropriate format for the dataset field value.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="beeec-127">Ziehen Sie das in Schritt 3 ausgewählte Datasetfeld in den Bereich **Werte** des Diagramms.</span><span class="sxs-lookup"><span data-stu-id="beeec-127">Drag the same dataset field you chose in step 3 to the **Values** area on the chart.</span></span>  
  
9. <span data-ttu-id="beeec-128">Klicken Sie im Diagramm mit der rechten Maustaste auf die Y-Achse, klicken Sie auf **Achseneigenschaften**, und klicken Sie anschließend auf **Zahl**.</span><span class="sxs-lookup"><span data-stu-id="beeec-128">In the chart, right-click the Y axis, click **Axis Properties**, and then click **Number**.</span></span> <span data-ttu-id="beeec-129">Wählen Sie dasselbe Format für die Daten aus, die Sie in Schritt 4 ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="beeec-129">Choose the same format for the data that you chose in step 4.</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="beeec-130">In den nächsten Schritten legen Sie die Zeilengruppe der Matrix und die Reihengruppe des Diagramms auf denselben Ausdruck fest. Außerdem legen Sie die Sortierreihenfolge für die Reihengruppe des Diagramms fest.</span><span class="sxs-lookup"><span data-stu-id="beeec-130">In the next few steps, you will set the matrix row group and the chart series group to the same expression, and also set the sort order for the chart series group.</span></span>  
  
11. <span data-ttu-id="beeec-131">Ziehen Sie das Datasetfeld, nach dem die Sortierung für Matrixzeilen erfolgen soll, aus dem Berichtsdatenbereich in den Bereich Zeilengruppen.</span><span class="sxs-lookup"><span data-stu-id="beeec-131">From the Report Data pane, drag the dataset field that you want to group by for matrix rows to the Row Groups pane.</span></span>  
  
     <span data-ttu-id="beeec-132">Die Matrixzeilengruppe fügt standardmäßig einen Sortierungsausdruck hinzu, der mit dem Gruppierungsausdruck identisch ist.</span><span class="sxs-lookup"><span data-stu-id="beeec-132">By default, the matrix row group adds a sort expression that is the same as the group expression.</span></span>  
  
12. <span data-ttu-id="beeec-133">Ziehen Sie das in Schritt 9 verwendete Datasetfeld in den Bereich **Reihengruppen** des Diagramms.</span><span class="sxs-lookup"><span data-stu-id="beeec-133">Drag the same dataset field that you used in step 9 to the **Series Groups** area for the chart.</span></span>  
  
13. <span data-ttu-id="beeec-134">Klicken Sie mit der rechten Maustaste auf die Gruppe im Bereich **Reihengruppen** , und klicken Sie anschließend auf **Reihengruppeneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="beeec-134">Right-click the group in the **Series Groups** area, and then click **Series Group Properties**.</span></span>  
  
14. <span data-ttu-id="beeec-135">Klicken Sie auf **Sortierung**.</span><span class="sxs-lookup"><span data-stu-id="beeec-135">Click **Sorting**.</span></span>  
  
15. <span data-ttu-id="beeec-136">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="beeec-136">Click **Add**.</span></span> <span data-ttu-id="beeec-137">Im Sortierungsausdrucksraster wird eine neue Zeile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="beeec-137">A new row appears in the sort expressions grid.</span></span>  
  
16. <span data-ttu-id="beeec-138">Wählen Sie unter **Sortieren nach**in der Dropdownliste das Datasetfeld aus, das Sie in Schritt 9 als Sortierkriterium ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="beeec-138">In **Sort by**, from the drop-down list, choose the dataset field that you chose to group by in step 9.</span></span>  
  
17. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="beeec-139">In den nächsten Schritten legen Sie die Spaltengruppe der Matrix und die Kategoriegruppe des Diagramms auf denselben Ausdruck fest. Außerdem legen Sie die Sortierreihenfolge für die Kategoriegruppe des Diagramms fest.</span><span class="sxs-lookup"><span data-stu-id="beeec-139">In the next few steps, you will set the matrix column group and the chart category group to the same expression, and also set the sort order for the chart category group.</span></span>  
  
18. <span data-ttu-id="beeec-140">Ziehen Sie das Datasetfeld, nach dem die Sortierung für Matrixspalten erfolgen soll, aus dem Berichtsdatenbereich in den Bereich Spaltengruppen.</span><span class="sxs-lookup"><span data-stu-id="beeec-140">From the Report Data pane, drag the dataset field that you want to group by for matrix columns to the Column Groups pane.</span></span>  
  
     <span data-ttu-id="beeec-141">Die Matrixspaltengruppe fügt standardmäßig einen Sortierungsausdruck hinzu, der mit dem Gruppierungsausdruck identisch ist.</span><span class="sxs-lookup"><span data-stu-id="beeec-141">By default, the matrix column group adds a sort expression that is the same as the group expression.</span></span>  
  
19. <span data-ttu-id="beeec-142">Ziehen Sie das in Schritt 16 verwendete Datasetfeld in den Bereich **Kategoriegruppen** des Diagramms.</span><span class="sxs-lookup"><span data-stu-id="beeec-142">Drag the same dataset field that you used in step 16 to the **Category Groups** area for the chart.</span></span>  
  
20. <span data-ttu-id="beeec-143">Klicken Sie mit der rechten Maustaste auf die Gruppe im Bereich **Kategoriegruppen** , und klicken Sie anschließend auf **Kategoriegruppeneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="beeec-143">Right-click the group in the **CategoryGroups** area, and then click **Category Group Properties**.</span></span>  
  
21. <span data-ttu-id="beeec-144">Klicken Sie auf **Sortierung**.</span><span class="sxs-lookup"><span data-stu-id="beeec-144">Click **Sorting**.</span></span>  
  
22. <span data-ttu-id="beeec-145">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="beeec-145">Click **Add**.</span></span> <span data-ttu-id="beeec-146">Im Sortierungsausdrucksraster wird eine neue Zeile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="beeec-146">A new row appears in the sort expressions grid.</span></span>  
  
23. <span data-ttu-id="beeec-147">Wählen Sie unter **Sortieren nach**in der Dropdownliste das Datasetfeld aus, das Sie in Schritt 16 als Sortierkriterium ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="beeec-147">In **Sort by**, from the drop-down list, choose the dataset field that you chose to group by in step 16.</span></span>  
  
24. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
25. <span data-ttu-id="beeec-148">Zeigen Sie das Ergebnis als Vorschau an.</span><span class="sxs-lookup"><span data-stu-id="beeec-148">Preview the result.</span></span> <span data-ttu-id="beeec-149">In den Zeilen- und Spaltengruppen der Matrix werden dieselben Daten wie in den Reihen- und Kategoriegruppen des Diagramms angezeigt.</span><span class="sxs-lookup"><span data-stu-id="beeec-149">The matrix row and column groups display the same data as the chart series and category groups.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beeec-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="beeec-150">See Also</span></span>  
 <span data-ttu-id="beeec-151">[Verknüpfen mehrerer Datenbereiche mit einem Dataset &#40;Berichts-Generator und SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="beeec-151">[Linking Multiple Data Regions to the Same Dataset &#40;Report Builder and SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="beeec-152">[Hinzufügen von Datasetfiltern, Datenbereichsfiltern und Gruppenfiltern &#40;Berichts-Generator und SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="beeec-152">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="beeec-153">[Listet &#40;Berichts-Generator und SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="beeec-153">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="beeec-154">Diagramme &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="beeec-154">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
