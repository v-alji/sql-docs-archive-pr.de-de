---
title: Sortieren von Daten in einem Datenbereich (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2fcb9be2-1daa-4c92-ad00-5f63cdf39f70
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bc1fb458066bb942a490b08c0faad876dd3d5438
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723378"
---
# <a name="sort-data-in-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="bcbaf-102">Sortieren von Daten in einem Datenbereich (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="bcbaf-102">Sort Data in a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="bcbaf-103">Wenn Sie bei der erstmaligen Ausführung eines Berichts die Sortierreihenfolge für Daten in einem Datenbereich ändern möchten, müssen Sie den Sortierungsausdruck für den Datenbereich oder die Datengruppe festlegen.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-103">To change the sort order of data in a data region when a report first runs, you must set the sort expression on the data region or group.</span></span> <span data-ttu-id="bcbaf-104">Die Sortierungsausdruck für eine Gruppe wird automatisch auf den gleichen Wert wie der Gruppierungsausdruck festgelegt.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-104">By default, the sort expression for a group is automatically set to the same value as the group expression.</span></span>  
  
-   <span data-ttu-id="bcbaf-105">Legen Sie in einem Tablix-Datenbereich den Sortierungsausdruck für den Datenbereich oder für die einzelnen Gruppen, einschließlich der Detailgruppe, fest.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-105">In a tablix data region, set the sort expression for the data region or for each group, including the details group.</span></span> <span data-ttu-id="bcbaf-106">Enthält ein Tablix-Datenbereich nur eine Detailgruppe, können Sie mit gleichem Ergebnis einen Sortierungsausdruck in der Abfrage, für den Datenbereich oder aber für die Detailgruppe definieren.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-106">If you have only one details group in a tablix data region, you can define a sort expression in the query, on the data region, or on the details group and they all have the same effect.</span></span>  
  
-   <span data-ttu-id="bcbaf-107">Legen Sie in einem Diagrammdatenbereich den Sortierungsausdruck für die Kategorie- und Reihengruppen fest, um die Sortierreihenfolgen für die einzelnen Gruppen zu steuern.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-107">In a chart data region, set the sort expression for the Category and Series groups to control the sort order for each group.</span></span> <span data-ttu-id="bcbaf-108">Die Reihenfolge der Farben in einer Diagrammlegende wird durch den Sortierungsausdruck für die Datenpunkte in der Kategoriegruppe bestimmt.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-108">The order for colors in a chart legend is determined by the sort expression for the data points in the Category group.</span></span>  
  
-   <span data-ttu-id="bcbaf-109">Daten in einen Messgerätdatenbereich müssen meist nicht sortiert werden, da auf dem Messgerät ein einzelner Wert in Bezug auf einen Bereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-109">In a gauge data region, you do not typically need to sort data because the gauge displays a single value relative to a range.</span></span> <span data-ttu-id="bcbaf-110">Wenn Sie die Daten eines Messgeräts dennoch sortieren müssen, definieren Sie zunächst eine Gruppe, und legen Sie dann den Sortierungsausdruck für die Gruppe fest.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-110">If you do need sort data in a gauge, you must first define a group, and then set the sort expression for the group.</span></span>  
  
 <span data-ttu-id="bcbaf-111">Weitere Informationen finden Sie unter [Filtern, Gruppieren und Sortieren von Daten &#40;Berichts-Generator und SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bcbaf-111">For more information, see [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="bcbaf-112">Bei einem Tablix-Datenbereich können Sie auch am oberen Rand eines Spaltenheaders eine interaktive Sortierschaltfläche hinzufügen, um Benutzern die Möglichkeit zu geben, die Sortierreihenfolge von Gruppen oder Detailzeilen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-112">For a tablix data region, you can also add an interactive sort button to the top of a column header to provide the user with the ability to change the sort order of groups or detail rows.</span></span> <span data-ttu-id="bcbaf-113">Weitere Informationen finden Sie unter [Interaktive Sortierung &#40;Berichts-Generator und SSRS&#41;](interactive-sort-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bcbaf-113">For more information, see [Interactive Sort &#40;Report Builder and SSRS&#41;](interactive-sort-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-sort-data-in-a-tablix-data-region"></a><span data-ttu-id="bcbaf-114">So sortieren Sie Daten in einem Tablix-Datenbereich</span><span class="sxs-lookup"><span data-stu-id="bcbaf-114">To sort data in a Tablix data region</span></span>  
  
1.  <span data-ttu-id="bcbaf-115">Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf ein Zeilenhandle, und klicken Sie anschließend auf **Tablix-Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-115">On the design surface, right-click a row handle, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="bcbaf-116">Klicken Sie auf **Sortierung**.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-116">Click **Sorting**.</span></span>  
  
3.  <span data-ttu-id="bcbaf-117">Führen Sie für jeden Sortierungsausdruck die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="bcbaf-117">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="bcbaf-118">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-118">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="bcbaf-119">Geben Sie einen Ausdruck ein, nach dem die Daten sortiert werden sollen, oder wählen Sie diesen aus.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-119">Type or select an expression by which to sort the data.</span></span>  
  
    3.  <span data-ttu-id="bcbaf-120">Wählen Sie in der Dropdownliste der Spalte **Reihenfolge** die Sortierreihenfolge für die einzelnen Ausdrücke aus.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-120">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="bcbaf-121">Bei Auswahl von**A-Z** sortiert der Ausdruck in aufsteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-121">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="bcbaf-122">Bei Auswahl von**Z-A** sortiert der Ausdruck in absteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-122">**Z-A** sorts the expression in descending order.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-values-in-a-group-including-the-details-group-for-a-tablix"></a><span data-ttu-id="bcbaf-123">So sortieren Sie Werte in einer Gruppe (einschließlich der Detailgruppe) für eine Tablix</span><span class="sxs-lookup"><span data-stu-id="bcbaf-123">To sort values in a group, including the details group, for a Tablix</span></span>  
  
1.  <span data-ttu-id="bcbaf-124">Klicken Sie auf der Entwurfsoberfläche auf den Tablix-Datenbereich, um ihn auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-124">On the design surface, click in the tablix data region to select it.</span></span> <span data-ttu-id="bcbaf-125">Im Bereich "Gruppierung" werden die Zeilengruppen und Spaltengruppen für den Tablix-Datenbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-125">The Grouping pane displays the row groups and column groups for the Tablix data region.</span></span>  
  
2.  <span data-ttu-id="bcbaf-126">Klicken Sie im Bereich „Zeilengruppen“ mit der rechten Maustaste auf den Gruppennamen, und klicken Sie anschließend auf **Gruppe bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-126">In the Row Groups pane, right-click the group name, and then click **Edit Group**.</span></span>  
  
3.  <span data-ttu-id="bcbaf-127">Klicken Sie im Dialogfeld **Tablix-Gruppe** auf **Sortieren**.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-127">In the **Tablix Group** dialog box, click **Sort**.</span></span>  
  
4.  <span data-ttu-id="bcbaf-128">Führen Sie für jeden Sortierungsausdruck die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="bcbaf-128">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="bcbaf-129">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-129">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="bcbaf-130">Geben Sie einen Ausdruck ein, nach dem die Daten sortiert werden sollen, oder wählen Sie diesen aus.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-130">Type or select an expression by which to sort the data.</span></span>  
  
    3.  <span data-ttu-id="bcbaf-131">Wählen Sie in der Dropdownliste der Spalte **Reihenfolge** die Sortierreihenfolge für die einzelnen Ausdrücke aus.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-131">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="bcbaf-132">Bei Auswahl von**A-Z** sortiert der Ausdruck in aufsteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-132">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="bcbaf-133">Bei Auswahl von**Z-A** sortiert der Ausdruck in absteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-133">**Z-A** sorts the expression in descending order.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-x-axis-labels-in-alphabetical-order-on-a-chart"></a><span data-ttu-id="bcbaf-134">So sortieren Sie x-Achsenbezeichnungen in alphabetischer Reihenfolge in einem Diagramm</span><span class="sxs-lookup"><span data-stu-id="bcbaf-134">To sort x-axis labels in alphabetical order on a chart</span></span>  
  
1.  <span data-ttu-id="bcbaf-135">Klicken Sie mit der rechten Maustaste auf ein Feld in der Kategoriefeldablagezone, und klicken Sie auf **Kategoriegruppeneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-135">Right-click a field in the Category Field drop-zone and click **Category GroupProperties**.</span></span>  
  
2.  <span data-ttu-id="bcbaf-136">Klicken Sie im Dialogfeld **Kategoriegruppeneigenschaften** auf **Sortierung**.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-136">In the **Category Group Properties** dialog box, click **Sorting**.</span></span>  
  
3.  <span data-ttu-id="bcbaf-137">Führen Sie für jeden Sortierungsausdruck die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="bcbaf-137">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="bcbaf-138">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-138">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="bcbaf-139">Wählen Sie den Ausdruck aus, der mit dem Gruppierungsfeld übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-139">Select the expression that matches your grouping field.</span></span> <span data-ttu-id="bcbaf-140">Sie können den Ausdruck für das Gruppierungsfeld überprüfen, indem Sie auf **Gruppierung**klicken.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-140">You can verify the expression for the grouping field by clicking **Grouping**.</span></span>  
  
    3.  <span data-ttu-id="bcbaf-141">Wählen Sie in der Dropdownliste der Spalte **Reihenfolge** die Sortierreihenfolge für die einzelnen Ausdrücke aus.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-141">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="bcbaf-142">Bei Auswahl von**A-Z** sortiert der Ausdruck in aufsteigender alphabetischer Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-142">**A-Z** sorts the expression in ascending alphabetical order.</span></span> <span data-ttu-id="bcbaf-143">Bei Auswahl von**Z-A** sortiert der Ausdruck in absteigender alphabetischer Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-143">**Z-A** sorts the expression in descending alphabetical order.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-the-data-points-in-ascending-or-descending-order-on-a-chart"></a><span data-ttu-id="bcbaf-144">So sortieren Sie die Datenpunkte in aufsteigender oder absteigender Reihenfolge in einem Diagramm</span><span class="sxs-lookup"><span data-stu-id="bcbaf-144">To sort the data points in ascending or descending order on a chart</span></span>  
  
1.  <span data-ttu-id="bcbaf-145">Klicken Sie mit der rechten Maustaste auf ein Feld in der Kategoriefeldablagezone, und klicken Sie auf **Kategoriegruppeneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-145">Right-click a field in the Category Field drop zone and click **Category GroupProperties**.</span></span>  
  
2.  <span data-ttu-id="bcbaf-146">Klicken Sie im Dialogfeld **Kategoriegruppeneigenschaften** auf **Sortierung**.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-146">In the **Category Group Properties** dialog box, click **Sorting**.</span></span>  
  
3.  <span data-ttu-id="bcbaf-147">Führen Sie für jeden Sortierungsausdruck die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="bcbaf-147">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="bcbaf-148">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-148">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="bcbaf-149">Wählen Sie den Ausdruck aus, der mit dem Datenfeld übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-149">Select the expression that matches your data field.</span></span> <span data-ttu-id="bcbaf-150">In den meisten Fällen ist dies ein aggregierter Wert, z. B. `=Sum(Fields!Quantity.Value)`.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-150">In most cases, this is an aggregated value, such as `=Sum(Fields!Quantity.Value)`.</span></span>  
  
    3.  <span data-ttu-id="bcbaf-151">Wählen Sie in der Dropdownliste der Spalte **Reihenfolge** die Sortierreihenfolge für die einzelnen Ausdrücke aus.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-151">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="bcbaf-152">Bei Auswahl von**A-Z** sortiert der Ausdruck in aufsteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-152">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="bcbaf-153">Bei Auswahl von**Z-A** sortiert der Ausdruck in absteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-153">**Z-A** sorts the expression in descending order.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-sort-data-in-ascending-or-descending-order-for-display-on-a-gauge"></a><span data-ttu-id="bcbaf-154">So sortieren Sie die Daten in aufsteigender oder absteigender Reihenfolge zur Anzeige auf einem Messgerät</span><span class="sxs-lookup"><span data-stu-id="bcbaf-154">To sort data in ascending or descending order for display on a gauge</span></span>  
  
1.  <span data-ttu-id="bcbaf-155">Klicken Sie mit der rechten Maustaste auf das Messgerät, und klicken Sie auf **Datengruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-155">Right-click the gauge and click **Add Data Group**.</span></span>  
  
2.  <span data-ttu-id="bcbaf-156">Klicken Sie im Dialogfeld **Messgerätbereichsgruppen-Eigenschaften** bei Bedarf auf **Allgemein** .</span><span class="sxs-lookup"><span data-stu-id="bcbaf-156">In the **Gauge Panel GroupProperties** dialog box, click **General** if necessary.</span></span>  
  
3.  <span data-ttu-id="bcbaf-157">Klicken Sie unter **Gruppierungsausdrücke**auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-157">In **Group expressions**, click **Add**.</span></span>  
  
4.  <span data-ttu-id="bcbaf-158">Geben Sie unter **Gruppieren nach**einen Ausdruck ein, nach dem die Daten gruppiert werden sollen, oder wählen Sie diesen aus.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-158">In **Group on**, type or select an expression by which to group the data.</span></span>  
  
5.  <span data-ttu-id="bcbaf-159">Wiederholen Sie die Schritte 3 und 4, bis Sie alle zu verwendenden Gruppierungsausdrücke hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-159">Repeat steps 3 and 4 until you have added all the group expressions you want to use.</span></span>  
  
6.  <span data-ttu-id="bcbaf-160">Klicken Sie auf **Sortierung**.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-160">Click **Sorting**.</span></span>  
  
7.  <span data-ttu-id="bcbaf-161">Führen Sie für jeden Sortierungsausdruck die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="bcbaf-161">For each sort expression, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="bcbaf-162">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-162">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="bcbaf-163">Wählen Sie den Ausdruck aus, der mit dem Gruppierungsfeld übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-163">Select the expression that matches your grouping field.</span></span> <span data-ttu-id="bcbaf-164">Sie können den Ausdruck für das Gruppierungsfeld überprüfen, indem Sie auf **Gruppierung**klicken.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-164">You can verify the expression for the grouping field by clicking **Grouping**.</span></span>  
  
    3.  <span data-ttu-id="bcbaf-165">Wählen Sie in der Dropdownliste der Spalte **Reihenfolge** die Sortierreihenfolge für die einzelnen Ausdrücke aus.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-165">From the **Order** column drop-down list, choose the sort direction for each expression.</span></span> <span data-ttu-id="bcbaf-166">Bei Auswahl von**A-Z** sortiert der Ausdruck in aufsteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-166">**A-Z** sorts the expression in ascending order.</span></span> <span data-ttu-id="bcbaf-167">Bei Auswahl von**Z-A** sortiert der Ausdruck in absteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="bcbaf-167">**Z-A** sorts the expression in descending order.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="bcbaf-168">Weitere Informationen zur Gruppierung von Daten auf einem Messgerät finden Sie unter [Messgeräte (Berichts-Generator und SSRS)](gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bcbaf-168">For more information about how data is grouped in a gauge, see [Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcbaf-169">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bcbaf-169">See Also</span></span>  
 <span data-ttu-id="bcbaf-170">[Berichts-Generator Hilfe zu Dialog Feldern, Bereichen und Assistenten](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="bcbaf-170">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="bcbaf-171">[Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bcbaf-171">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bcbaf-172">[Formatieren von Achsen Bezeichnungen in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bcbaf-172">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bcbaf-173">Angeben von Farben, die für mehrere Formdiagramme konsistent sind &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bcbaf-173">Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;</span></span>](shape-charts-report-builder-and-ssrs.md)  
  
  
