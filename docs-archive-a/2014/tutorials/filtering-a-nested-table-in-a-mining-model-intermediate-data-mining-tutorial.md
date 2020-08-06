---
title: Filtern einer geclusterte Tabelle in einem Mining Modell (Data Mining-Lernprogramm für Fortgeschrittene) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0a3ae0e5-897b-4898-a60d-5455eec3d305
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a1e6ce2936a3c6763ea41999b2724c0fe8c79301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723238"
---
# <a name="filtering-a-nested-table-in-a-mining-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="ce4e9-102">Filtern einer geschachtelten Tabelle in einem Miningmodell (Data Mining-Lernprogramm für Fortgeschrittene)</span><span class="sxs-lookup"><span data-stu-id="ce4e9-102">Filtering a Nested Table in a Mining Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="ce4e9-103">Nachdem Sie das Modell erstellt und sich damit vertraut gemacht haben, möchten Sie sich mit einer Teilmenge der Kundendaten näher beschäftigen.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-103">After you have created and explored the model, you decide that you want to focus on a subset of the customer data.</span></span> <span data-ttu-id="ce4e9-104">Dazu können Sie beispielsweise nur die Einkaufskörbe betrachten, die ein bestimmtes Element enthalten, oder die demografischen Daten von Kunden analysieren, die über einen bestimmten Zeitraum keine Einkäufe getätigt haben.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-104">For example, you might want to analyze only the baskets that contain a specific item, or to analyze the demographics of customers who have not purchased anything in a certain period.</span></span>  
  
 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="ce4e9-105">bietet die Möglichkeit, die in einem Miningmodell verwendeten Daten zu filtern.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-105">provides the ability to filter the data that is used in a mining model.</span></span> <span data-ttu-id="ce4e9-106">Diese Funktion ist nützlich, da Sie keine neue Datenquellen Sicht einrichten müssen, um unterschiedliche Daten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-106">This feature is useful because you do not need to set up a new data source view to use different data.</span></span> <span data-ttu-id="ce4e9-107">Im Lernprogramm zu Data Mining-Grundlagen haben Sie gelernt, Daten in einer flachen Tabelle anhand von Bedingungen für die Falltabelle zu filtern.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-107">In the Basic Data Mining Tutorial, you learned how to filter data from a flat table by applying conditions to the case table.</span></span> <span data-ttu-id="ce4e9-108">In dieser Aufgabe erstellen Sie einen Filter für eine geschachtelte Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-108">In this task, you create a filter that applies to a nested table.</span></span>  
  
## <a name="filters-on-nested-vs-case-tables"></a><span data-ttu-id="ce4e9-109">Filter für geschachtelte Tabellen und Filter für Falltabellen</span><span class="sxs-lookup"><span data-stu-id="ce4e9-109">Filters on Nested vs. Case Tables</span></span>  
 <span data-ttu-id="ce4e9-110">Wenn die Datenquellenansicht wie im Modell Association eine Falltabelle und eine geschachtelte Tabelle enthält, können Sie einen Filter für Werte in der Falltabelle, einen Filter für vorhandene oder nicht vorhandene Werte in der geschachtelten Tabelle oder eine Kombination aus beiden verwenden.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-110">If your data source view contains a case table and a nested table, like the data source view used in the Association model, you can filter on values from the case table, the presence or absence of a value in the nested table, or some combination of both.</span></span>  
  
 <span data-ttu-id="ce4e9-111">In dieser Aufgabe erstellen Sie zunächst eine Kopie des Modells Association und fügen die Attribute IncomeGroup und Region hinzu, um diese später als Filterkriterien für die Falltabelle verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-111">In this task, you will first make a copy of the Association model and then add the IncomeGroup and Region attributes to the new related model, so that you can filter on those attributes in the case table.</span></span>  
  
#### <a name="to-create-and-modify-a-copy-of-the-association-model"></a><span data-ttu-id="ce4e9-112">So erstellen und ändern Sie eine Kopie des Modells Association</span><span class="sxs-lookup"><span data-stu-id="ce4e9-112">To create and modify a copy of the Association model</span></span>  
  
1.  <span data-ttu-id="ce4e9-113">Klicken Sie in der Registerkarte **Mining Modelle** mit [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] der rechten Maustaste auf das `Association` Modell, und wählen Sie **Neues Mining Modell**aus.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-113">In the **Mining Models** tab of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], right-click the `Association` model, and select **New Mining Model**.</span></span>  
  
2.  <span data-ttu-id="ce4e9-114">Geben Sie unter **Modell Name den Namen**ein `Association Filtered` .</span><span class="sxs-lookup"><span data-stu-id="ce4e9-114">For **Model Name**, type `Association Filtered`.</span></span> <span data-ttu-id="ce4e9-115">Wählen Sie unter **Algorithmusname**die Option **Microsoft Association Rules**aus.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-115">For **Algorithm Name**, select **Microsoft Association Rules**.</span></span> <span data-ttu-id="ce4e9-116">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-116">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="ce4e9-117">Klicken Sie in der Spalte für das gefilterte Assoziations Modell auf die Zeile IncomeGroup, und ändern Sie den Wert von **ignorieren** in **Eingabe**.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-117">In the column for the Association Filtered model, click the IncomeGroup row and change the value from **Ignore** to **Input**.</span></span>  
  
 <span data-ttu-id="ce4e9-118">Anschließend erstellen Sie einen Filter für die Falltabelle im neuen Association-Modell.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-118">Next, you will create a filter on the case table in the new association model.</span></span> <span data-ttu-id="ce4e9-119">Durch den Filter werden nur Kunden in der Zielregion oder Kunden mit einem Einkommensniveau entsprechend den Kriterien im Modell verwendet.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-119">The filter will pass to the model only the customers in the target region or with the target income level.</span></span> <span data-ttu-id="ce4e9-120">Nun fügen Sie eine weitere Reihe von Filterbedingungen hinzu, um anzugeben, dass nur Kunden im Modell berücksichtigt werden sollen, in deren Einkaufskorb sich mindestens ein Element befindet.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-120">Then, you will add a second set of filter conditions to specify that the model uses only customers whose shopping baskets contained at least one item.</span></span>  
  
#### <a name="to-add-a-filter-to-a-mining-model"></a><span data-ttu-id="ce4e9-121">So fügen Sie einem Miningmodell einen Filter hinzu</span><span class="sxs-lookup"><span data-stu-id="ce4e9-121">To add a filter to a mining model</span></span>  
  
1.  <span data-ttu-id="ce4e9-122">Klicken Sie auf der Registerkarte **Mining Modelle** mit der rechten Maustaste auf die gefilterte Modell Zuordnung, und wählen Sie **Modell Filter festlegen**aus.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-122">In the **Mining Models** tab, right-click the model Association Filtered, and select **Set Model Filter**.</span></span>  
  
2.  <span data-ttu-id="ce4e9-123">Klicken Sie im Dialogfeld **Modellfilter** im Textfeld **Miningstrukturspalte** auf die oberste Zeile im Raster.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-123">In the **Model Filter** dialog box, click the top row in the grid, in the **Mining Structure Column** text box.</span></span>  
  
3.  <span data-ttu-id="ce4e9-124">Wählen Sie im Textfeld **Mining Struktur Spalte** die Option IncomeGroup aus.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-124">In the **Mining Structure Column** text box, select IncomeGroup.</span></span>  
  
     <span data-ttu-id="ce4e9-125">Das Symbol auf der linken Seite des Textfelds ändert sich und gibt dadurch an, dass es sich beim ausgewählten Element um eine Spalte handelt.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-125">The icon at the left side of the text box changes to indicate that the selected item is a column.</span></span>  
  
4.  <span data-ttu-id="ce4e9-126">Klicken Sie auf das Textfeld **Operator** , und wählen Sie den **=** Operator aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-126">Click the **Operator** text box and select the **=** operator from the list.</span></span>  
  
5.  <span data-ttu-id="ce4e9-127">Klicken Sie auf das Textfeld **Wert** , und geben Sie `High` in das Feld ein.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-127">Click the **Value** text box, and type `High` in the box.</span></span>  
  
6.  <span data-ttu-id="ce4e9-128">Klicken Sie auf die nächste Zeile im Raster.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-128">Click the next row in the grid.</span></span>  
  
7.  <span data-ttu-id="ce4e9-129">Klicken Sie in der nächsten Zeile des Rasters auf das Textfeld **und/oder** , und wählen Sie **oder**aus.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-129">Click the **AND/OR** text box in the next row of the grid and select **OR**.</span></span>  
  
8.  <span data-ttu-id="ce4e9-130">Wählen Sie im Textfeld **Mining Struktur Spalte** die Option IncomeGroup aus.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-130">In the **Mining Structure Column** text box, select IncomeGroup.</span></span> <span data-ttu-id="ce4e9-131">Geben Sie im Textfeld **Wert den Wert** ein `Moderate` .</span><span class="sxs-lookup"><span data-stu-id="ce4e9-131">In the **Value** text box, type `Moderate`.</span></span>  
  
     <span data-ttu-id="ce4e9-132">Die von Ihnen erstellte Filterbedingung wird automatisch zum Textfeld **Ausdruck** hinzugefügt und sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="ce4e9-132">The filter condition that you created is automatically added to the **Expression** text box, and should appears as follows:</span></span>  
  
     `[IncomeGroup] = 'High' OR [IncomeGroup] = 'Moderate'`  
  
9. <span data-ttu-id="ce4e9-133">Klicken Sie auf die nächste Zeile im Raster, und belassen Sie den Operator als Standard **und**.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-133">Click the next row in the grid, leaving the operator as the default, **AND**.</span></span>  
  
10. <span data-ttu-id="ce4e9-134">Überlassen Sie für **Operator**den Standardwert **enthält**.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-134">For **Operator**, leave the default value, **Contains**.</span></span> <span data-ttu-id="ce4e9-135">Klicken Sie auf das Textfeld **Wert** .</span><span class="sxs-lookup"><span data-stu-id="ce4e9-135">Click the **Value** text box.</span></span>  
  
11. <span data-ttu-id="ce4e9-136">Wählen Sie im Dialogfeld **Filter** in der ersten Zeile unter **Mining Struktur Spalte**die Option aus `Model` .</span><span class="sxs-lookup"><span data-stu-id="ce4e9-136">In the **Filter** dialog box, in the first row under **Mining Structure Column**, select `Model`.</span></span>  
  
12. <span data-ttu-id="ce4e9-137">Wählen Sie für **Operator**den Wert **ist nicht NULL**aus.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-137">For **Operator**, select **IS NOT NULL**.</span></span> <span data-ttu-id="ce4e9-138">Lassen Sie das Textfeld **Wert** leer.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-138">Leave the **Value** text box blank.</span></span> <span data-ttu-id="ce4e9-139">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-139">Click **OK**.</span></span>  
  
     <span data-ttu-id="ce4e9-140">Die Filterbedingung im Textfeld **Ausdruck** des Dialog Felds **Modell Filter** wird automatisch aktualisiert, um die neue Bedingung in die geclusterte Tabelle einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-140">The filter condition in the **Expression** text box of the **Model Filter** dialog box is automatically updated to include the new condition on the nested table.</span></span> <span data-ttu-id="ce4e9-141">Der vollständige Ausdruck lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ce4e9-141">The completed expression is as follows:</span></span>  
  
     `[IncomeGroup] = 'High' OR [IncomeGroup] = 'Moderate' AND EXISTS SELECT * FROM [vAssocSeqLineItems] WHERE [Model] <> NULL).`  
  
13. [!INCLUDE[clickOK](../includes/clickok-md.md)] ``  
  
#### <a name="to-enable-drillthrough-and-to-process-the-filtered-model"></a><span data-ttu-id="ce4e9-142">So aktivieren Sie Drillthrough und verarbeiten das gefilterte Modell</span><span class="sxs-lookup"><span data-stu-id="ce4e9-142">To enable drillthrough and to process the filtered model</span></span>  
  
1.  <span data-ttu-id="ce4e9-143">Klicken Sie auf der Registerkarte **Mining Modelle** mit der rechten Maustaste auf das `Association Filtered` Modell, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-143">In the **Mining Models** tab, right-click the `Association Filtered` model, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="ce4e9-144">Ändern Sie die **AllowDrillThrough** -Eigenschaft in **true**.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-144">Change the **AllowDrillThrough** property to **True**.</span></span>  
  
3.  <span data-ttu-id="ce4e9-145">Klicken Sie mit der rechten Maustaste auf das `Association Filtered` Mining Modell, und wählen Sie **Modell verarbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-145">Right-click the `Association Filtered` mining model, and select **Process Model**.</span></span>  
  
4.  <span data-ttu-id="ce4e9-146">Klicken Sie in der Fehlermeldung auf **Ja** , um das neue Modell in der Datenbank bereitzustellen [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce4e9-146">Click **Yes** in the error message to deploy the new model to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
5.  <span data-ttu-id="ce4e9-147">Klicken Sie im Dialogfeld **Mining Struktur verarbeiten** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-147">In the **Process Mining Structure** dialog box, click **Run**.</span></span>  
  
6.  <span data-ttu-id="ce4e9-148">Klicken Sie nach Abschluss der Verarbeitung auf schließen, **um das Dialogfeld Verarbeitungs Status** zu **Schließen** , und klicken Sie erneut auf schließen, um das Dialogfeld **Mining Struktur verarbeiten** zu **Schließen** .</span><span class="sxs-lookup"><span data-stu-id="ce4e9-148">When processing is complete click **Close** to exit the **Process Progress** dialog box, and click **Close** again to exit the **Process Mining Structure** dialog box.</span></span>  
  
 <span data-ttu-id="ce4e9-149">Im Microsoft Generic Content Tree Viewer können Sie anhand des Werts für NODE_SUPPORT feststellen, dass das gefilterte Modell weniger Fälle als das ursprüngliche Modell enthält.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-149">You can verify by using the Microsoft Generic Content Tree viewer and looking at the value for NODE_SUPPORT that the filtered model contains fewer cases than the original model.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce4e9-150">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ce4e9-150">Remarks</span></span>  
 <span data-ttu-id="ce4e9-151">Mit dem Filter für eine geschachtelte Tabelle, den Sie gerade erstellt haben, wird nur überprüft, ob mindestens eine Zeile in der geschachtelten Tabelle enthalten ist. Sie können jedoch Filterbedingungen erstellen, mit denen das Vorhandensein bestimmter Produkte überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-151">The nested table filter that you just created checks only for the presence of at least one row in the nested table; however, you can also create filter conditions that check for the presence of specific products.</span></span>  <span data-ttu-id="ce4e9-152">Beispielsweise können Sie folgenden Filter erstellen:</span><span class="sxs-lookup"><span data-stu-id="ce4e9-152">For example, you could create the following filter:</span></span>  
  
```  
[IncomeGroup] = 'High' AND  
 EXISTS (SELECT * FROM [<nested table name>] WHERE [Model] = 'Water Bottle' )   
```  
  
 <span data-ttu-id="ce4e9-153">Diese Anweisung bewirkt, dass die Kunden in der Falltabelle auf Kunden eingeschränkt werden, die eine Flasche Wasser gekauft haben.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-153">This statement means that you are restricting the customers from the case table to only those who have purchased a water bottle.</span></span> <span data-ttu-id="ce4e9-154">Da die Anzahl der Attribute für eine geschachtelte Tabelle jedoch praktisch unbegrenzt ist, stellt [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] keine Liste mit möglichen Werten zur Auswahl bereit.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-154">However, because the number of nested table attributes is potentially unlimited, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] does not supply a list of possible values from which to select.</span></span> <span data-ttu-id="ce4e9-155">Sie müssen stattdessen den genauen Wert eingeben.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-155">Instead, you must type the exact value.</span></span>  
  
 <span data-ttu-id="ce4e9-156">Sie können auf **Abfrage bearbeiten** klicken, um den Filter Ausdruck manuell zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-156">You can click **Edit Query** to manually change the filter expression.</span></span> <span data-ttu-id="ce4e9-157">Wenn Sie jedoch einen Teil eines Filterausdrucks manuell ändern, wird das Raster deaktiviert, und anschließend müssen Sie mit dem Filterausdruck im Textbearbeitungsmodus arbeiten.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-157">However, if you change any part of a filter expression manually, the grid will be disabled and thereafter you must work with the filter expression in text edit mode only.</span></span> <span data-ttu-id="ce4e9-158">Um den Rasterbearbeitungsmodus wiederherzustellen, müssen Sie den Filterausdruck löschen und von Neuem beginnen.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-158">To restore grid editing mode, you must clear the filter expression and start over.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="ce4e9-159">In einem Filter für geschachtelte Tabellen kann kein LIKE-Operator verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ce4e9-159">You cannot use the LIKE operator in a nested table filter.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ce4e9-160">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="ce4e9-160">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ce4e9-161">Vorhersagen von Zuordnungen &#40;Data&#41;Mining-Lernprogramms</span><span class="sxs-lookup"><span data-stu-id="ce4e9-161">Predicting Associations &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/predicting-associations-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="ce4e9-162">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ce4e9-162">See Also</span></span>  
 <span data-ttu-id="ce4e9-163">[Modell Filter Syntax und Beispiele &#40;Analysis Services Data Mining-&#41;](../../2014/analysis-services/data-mining/model-filter-syntax-and-examples-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="ce4e9-163">[Model Filter Syntax and Examples &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/model-filter-syntax-and-examples-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="ce4e9-164">Filter für Miningmodelle &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ce4e9-164">Filters for Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md)  
  
  
