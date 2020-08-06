---
title: Anwenden eines Filters auf ein Mining Modell | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- model filter [data mining]
- filters [data mining]
- filtering input rows [Analysis Services]
- filtering data [Analysis Services]
ms.assetid: 4d0abeb5-e939-46d3-9097-6e0358244300
author: minewiskan
ms.author: owend
ms.openlocfilehash: d9f3147c36e69d9c2249d5bf6d1ba201799c6e27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620060"
---
# <a name="apply-a-filter-to-a-mining-model"></a><span data-ttu-id="89d21-102">Anwenden eines Filters auf ein Miningmodell</span><span class="sxs-lookup"><span data-stu-id="89d21-102">Apply a Filter to a Mining Model</span></span>
  <span data-ttu-id="89d21-103">Wenn Ihre Miningstruktur eine geschachtelte Tabelle enthält, können Sie einen Filter auf die Falltabelle und/oder die geschachtelte Tabelle anwenden.</span><span class="sxs-lookup"><span data-stu-id="89d21-103">If your mining structure contains a nested table, you can apply a filter to the case table, the nested table, or both.</span></span>  
  
 <span data-ttu-id="89d21-104">Die folgende Vorgehensweise veranschaulicht das Erstellen beider Filterarten: Fallfilter und Filter in den Zeilen der geschachtelten Tabelle.</span><span class="sxs-lookup"><span data-stu-id="89d21-104">The following procedure demonstrates how to create both kinds of filters: case filters, and filters on the nested table rows.</span></span>  
  
 <span data-ttu-id="89d21-105">Die Bedingung in der Falltabelle schränkt Kunden auf Kunden mit einem Einkommen zwischen 30000 und 40000 ein.</span><span class="sxs-lookup"><span data-stu-id="89d21-105">The condition on the case table restricts customers to those with income between 30000 and 40000.</span></span> <span data-ttu-id="89d21-106">Die Bedingung in der geschachtelten Tabelle schränkt die Kunden auf Kunden ein, die einen bestimmten Artikel nicht gekauft haben.</span><span class="sxs-lookup"><span data-stu-id="89d21-106">The condition on the nested table restricts the customers to those who did not purchase a particular item.</span></span>  
  
 <span data-ttu-id="89d21-107">Die vollständige in diesem Beispiel erstellte Filterbedingung lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="89d21-107">The complete filter condition created in this example is as follows:</span></span>  
  
```  
[Income] > '30000'   
AND  [Income] < '40000'   
AND EXISTS (SELECT * FROM [<nested table name>]   
WHERE [Model] <> 'Water Bottle' )   
```  
  
### <a name="to-create-a-case-filter-on-a-mining-model"></a><span data-ttu-id="89d21-108">So erstellen Sie einen Fallfilter für ein Miningmodell</span><span class="sxs-lookup"><span data-stu-id="89d21-108">To create a case filter on a mining model</span></span>  
  
1.  <span data-ttu-id="89d21-109">Klicken Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]im Projektmappen-Explorer auf die Miningstruktur, die das Miningmodell enthält, auf das Sie einen Filter anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="89d21-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in Solution Explorer, click the mining structure that contains the mining model you want to filter.</span></span>  
  
2.  <span data-ttu-id="89d21-110">Klicken Sie auf die Registerkarte **Miningmodelle** .</span><span class="sxs-lookup"><span data-stu-id="89d21-110">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="89d21-111">Wählen Sie das Modell aus, und klicken Sie mit der rechten Maustaste, um das Kontextmenü zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="89d21-111">Select the model, and right-click to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="89d21-112">Oder</span><span class="sxs-lookup"><span data-stu-id="89d21-112">-or-</span></span>  
  
     <span data-ttu-id="89d21-113">Wählen Sie das Modell aus.</span><span class="sxs-lookup"><span data-stu-id="89d21-113">Select the model.</span></span> <span data-ttu-id="89d21-114">Wählen Sie dann im Menü **Miningmodell** die Funktion **Modellfilter festlegen**aus.</span><span class="sxs-lookup"><span data-stu-id="89d21-114">Then, on the **Mining Model** menu, select **Set Model Filter**.</span></span>  
  
4.  <span data-ttu-id="89d21-115">Klicken Sie im Dialogfeld **Modellfilter** im Textfeld **Miningstrukturspalte** auf die oberste Zeile im Raster.</span><span class="sxs-lookup"><span data-stu-id="89d21-115">In the **Model Filter** dialog box, click the top row in the grid, in the **Mining Structure Column** text box.</span></span>  
  
5.  <span data-ttu-id="89d21-116">Wenn die Datenquelle eine einzelne flache Tabelle enthält, zeigt die Dropdown-Liste nur die Namen der Spalten in dieser Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="89d21-116">If the data source contains a single flat table, the drop-down list displays only the names of the columns in that table.</span></span>  
  
     <span data-ttu-id="89d21-117">Wenn die Miningstruktur mehrere Tabellen enthält, zeigt die Liste die Namen der Quelltabellen an.</span><span class="sxs-lookup"><span data-stu-id="89d21-117">If the mining structure contains multiple tables, the list shows the names of the source tables.</span></span> <span data-ttu-id="89d21-118">Die Spaltennamen werden nur angezeigt, wenn eine Tabelle ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="89d21-118">The column names do not display until a table has been selected.</span></span>  
  
     <span data-ttu-id="89d21-119">Wenn die Miningstruktur eine Falltabelle und eine geschachtelte Tabelle enthält, werden in der Dropdown-Liste Spalten aus der Falltabelle sowie der Name der geschachtelten Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="89d21-119">If the mining structure contains a case table and a nested table, the drop-down list shows columns from the case table, and the name of the nested table.</span></span>  
  
6.  <span data-ttu-id="89d21-120">Wählen Sie eine Spalte aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="89d21-120">Select a column from the drop-down list.</span></span>  
  
     <span data-ttu-id="89d21-121">Das Symbol auf der linken Seite des Textfelds ändert sich und gibt dadurch an, dass es sich beim ausgewählten Element um eine Tabelle oder eine Spalte handelt.</span><span class="sxs-lookup"><span data-stu-id="89d21-121">The icon at the left side of the text box changes to indicate that the selected item is a table or a column.</span></span>  
  
7.  <span data-ttu-id="89d21-122">Klicken Sie auf das Textfeld **Operator** , und wählen Sie einen Operator aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="89d21-122">Click the **Operator** text box and select an operator from the list.</span></span> <span data-ttu-id="89d21-123">Die gültigen Operatoren hängen vom Datentyp der Spalte ab, die Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="89d21-123">The valid operators change depending on the data type of the column you selected.</span></span>  
  
8.  <span data-ttu-id="89d21-124">Klicken Sie auf das Textfeld **Wert** , und geben Sie einen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="89d21-124">Click the **Value** text box, and type a value in the box.</span></span>  
  
     <span data-ttu-id="89d21-125">Wählen Sie z. b. `Income` als Spalte aus, wählen Sie den Operator "größer als" (>) aus, und geben Sie dann ein `30000` .</span><span class="sxs-lookup"><span data-stu-id="89d21-125">For example, select `Income` as the column, select the greater than operator (>), and then type `30000`.</span></span>  
  
9. <span data-ttu-id="89d21-126">Klicken Sie auf die nächste Zeile im Raster.</span><span class="sxs-lookup"><span data-stu-id="89d21-126">Click the next row in the grid.</span></span>  
  
     <span data-ttu-id="89d21-127">Die erstellte Filterbedingung wird automatisch zum Textfeld Ausdruck hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="89d21-127">The filter condition that you created is automatically added to the Expression text box.</span></span> <span data-ttu-id="89d21-128">Zum Beispiel, `[Income] > '30000'`</span><span class="sxs-lookup"><span data-stu-id="89d21-128">For example, `[Income] > '30000'`</span></span>  
  
10. <span data-ttu-id="89d21-129">Klicken Sie in der nächsten Zeile des Rasters auf das Textfeld **AND/OR** , um eine Bedingung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="89d21-129">Click the **AND/OR** text box in the next row of the grid to add a condition.</span></span>  
  
     <span data-ttu-id="89d21-130">Um z. b. eine between-Bedingung zu erstellen, wählen Sie `AND` aus der Dropdown Liste der logischen Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="89d21-130">For example, to create a BETWEEN condition, select `AND` from the drop-down list of logical operands.</span></span>  
  
11. <span data-ttu-id="89d21-131">Wählen Sie einen Operator aus, und geben Sie einen Wert ein, wie in Schritt 7 und 8 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="89d21-131">Select an operator and type a value as described in Steps 7 and 8.</span></span>  
  
     <span data-ttu-id="89d21-132">Wählen Sie z `Income` . b. erneut als Spalte aus, wählen Sie den Operator kleiner als (<) aus, und geben Sie dann ein `40000` .</span><span class="sxs-lookup"><span data-stu-id="89d21-132">For example, select `Income` as the column again, select the less than operator (<), and then type `40000`.</span></span>  
  
12. <span data-ttu-id="89d21-133">Klicken Sie auf die nächste Zeile im Raster.</span><span class="sxs-lookup"><span data-stu-id="89d21-133">Click the next row in the grid.</span></span>  
  
13. <span data-ttu-id="89d21-134">Die Filterbedingung im Textfeld Ausdruck wird automatisch aktualisiert, um die neue Bedingung einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="89d21-134">The filter condition in the Expression text box is automatically updated to include the new condition.</span></span> <span data-ttu-id="89d21-135">Der vollständige Ausdruck lautet wie folgt: `[Income] > '30000'AND [Income] < '40000'`</span><span class="sxs-lookup"><span data-stu-id="89d21-135">The completed expression is as follows: `[Income] > '30000'AND [Income] < '40000'`</span></span>  
  
### <a name="to-add-a-filter-on-the-nested-table-in-a-mining-model"></a><span data-ttu-id="89d21-136">So fügen Sie einen Filter in der geschachtelten Tabelle in einem Miningmodell hinzu</span><span class="sxs-lookup"><span data-stu-id="89d21-136">To add a filter on the nested table in a mining model</span></span>  
  
1.  <span data-ttu-id="89d21-137">Klicken Sie im Dialog Feld \*\* \<name> Modell Filter\*\* auf eine leere Zeile im Raster unter **Mining Struktur Spalte**.</span><span class="sxs-lookup"><span data-stu-id="89d21-137">In the **\<name>Model Filter** Dialog box, click an empty row in the grid under **Mining Structure Column**.</span></span>  
  
2.  <span data-ttu-id="89d21-138">Wählen Sie den Namen der geschachtelten Tabelle aus der Dropdown-Liste aus.</span><span class="sxs-lookup"><span data-stu-id="89d21-138">Select the name of the nested table from the drop-down list.</span></span>  
  
     <span data-ttu-id="89d21-139">Das Symbol auf der linken Seite des Textfelds ändert sich und gibt dadurch an, dass es sich beim ausgewählten Element um den Namen einer Tabelle handelt.</span><span class="sxs-lookup"><span data-stu-id="89d21-139">The icon at the left side of the text box changes to indicate that the selected item is the name of a table.</span></span>  
  
3.  <span data-ttu-id="89d21-140">Klicken Sie auf das Textfeld **Operator** , und wählen Sie **Enthält** oder **Enthält nicht**aus.</span><span class="sxs-lookup"><span data-stu-id="89d21-140">Click the **Operator** text box and select **Contains** or **Not Contain**.</span></span>  
  
     <span data-ttu-id="89d21-141">Dies sind die einzigen Bedingungen, die für die geschachtelte Tabelle im Dialogfeld **Modellfilter** verfügbar sind, da Sie die Falltabelle auf die Fälle einschränken, die einen bestimmten Wert in der verschachtelten Tabelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="89d21-141">These are the only conditions available for the nested table in the **Model Filter** dialog box, because you are restricting the case table to only those cases that contain a certain value in the nested table.</span></span> <span data-ttu-id="89d21-142">Den Wert für die Bedingung in der geschachtelten Tabelle legen Sie im nächsten Schritt fest.</span><span class="sxs-lookup"><span data-stu-id="89d21-142">You will set the value for the condition on the nested table in the next step.</span></span>  
  
4.  <span data-ttu-id="89d21-143">Klicken Sie auf das Feld **Wert** , und klicken Sie dann auf die Schaltfläche **(...)** , um einen Ausdruck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="89d21-143">Click the **Value** box, and then click the **(...)** button to build an expression.</span></span>  
  
     <span data-ttu-id="89d21-144">Das Dialogfeld \*\* \<name> Filter\*\* wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="89d21-144">The **\<name>Filter** dialog box opens.</span></span> <span data-ttu-id="89d21-145">Dieses Dialogfeld kann Bedingungen nur für die aktuelle Tabelle festlegen. In diesem Fall ist dies die geschachtelte Tabelle.</span><span class="sxs-lookup"><span data-stu-id="89d21-145">This dialog box can set conditions only on the current table, which in this case is the nested table.</span></span>  
  
5.  <span data-ttu-id="89d21-146">Klicken Sie auf das Feld **Miningstrukturspalte** , und wählen Sie einen Spaltennamen aus den Dropdown-Listen der Spalten der verschachtelten Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="89d21-146">Click the **Mining Structure Column** box and select a column name from the dropdown lists of nested table columns.</span></span>  
  
6.  <span data-ttu-id="89d21-147">Klicken Sie auf **Operator** , und wählen Sie einen Operator aus der Liste der gültigen Operatoren für die Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="89d21-147">Click **Operator** and select an operator from the list of valid operators for the column.</span></span>  
  
7.  <span data-ttu-id="89d21-148">Klicken Sie auf **Wert** , und geben Sie einen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="89d21-148">Click **Value** and type a value.</span></span>  
  
     <span data-ttu-id="89d21-149">Wählen Sie z. b. für **Mining Struktur Spalte** die Option aus `Model` .</span><span class="sxs-lookup"><span data-stu-id="89d21-149">For example, for **Mining Structure Column,** select `Model`.</span></span> <span data-ttu-id="89d21-150">Wählen Sie für **Operator**die Option aus `<>` , und geben Sie den Wert ein `Water Bottle` .</span><span class="sxs-lookup"><span data-stu-id="89d21-150">For **Operator**, select `<>`, and type the value `Water Bottle`.</span></span> <span data-ttu-id="89d21-151">Diese Bedingung erstellt den folgenden Filterausdruck:</span><span class="sxs-lookup"><span data-stu-id="89d21-151">This condition creates the following filter expression:</span></span>  
  
```  
EXISTS (SELECT * FROM [<nested table name>] WHERE [Model] <> 'Water Bottle' )   
```  
  
> [!NOTE]  
>  <span data-ttu-id="89d21-152">Da die Anzahl der Attribute für eine geschachtelte Tabelle praktisch unbegrenzt ist, stellt [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] keine Liste mit möglichen Werten zur Auswahl bereit.</span><span class="sxs-lookup"><span data-stu-id="89d21-152">Because the number of nested table attributes is potentially unlimited, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] does not supply a list of possible values from which to select.</span></span> <span data-ttu-id="89d21-153">Sie müssen den genauen Wert eingeben.</span><span class="sxs-lookup"><span data-stu-id="89d21-153">You must type the exact value.</span></span> <span data-ttu-id="89d21-154">Außerdem können Sie in einer geschachtelten Tabelle keinen LIKE-Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="89d21-154">Also, you cannot use a LIKE operator in a nested table.</span></span>  
  
1.  <span data-ttu-id="89d21-155">Fügen Sie nach Bedarf weitere Bedingungen hinzu, und kombinieren Sie die Bedingungen, indem Sie `AND` oder `OR` im Feld **und/oder** auf der linken Seite des Rasters **Bedingungen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="89d21-155">Add more conditions as necessary, combining the conditions by selecting `AND` or `OR` in the **AND/OR** box at the left side of the **Conditions** grid.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
2.  <span data-ttu-id="89d21-156">Prüfen Sie im Dialogfeld **Modellfilter** die von Ihnen erstellten Bedingungen mithilfe des Dialogfelds **Filter** .</span><span class="sxs-lookup"><span data-stu-id="89d21-156">In the **Model Filter** dialog box, review the conditions that you created by using the **Filter** dialog box.</span></span> <span data-ttu-id="89d21-157">Die Bedingungen für die geschachtelte Tabelle werden den Bedingungen für die Falltabelle hinzugefügt. Der gesamte Satz der Filterbedingungen wird im Textfeld **Ausdruck** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="89d21-157">The conditions for the nested table are appended to the conditions for the case table, and the complete set of filter conditions is displayed in the **Expression** text box.</span></span>  
  
3.  <span data-ttu-id="89d21-158">Sie können optional auf **Abfrage bearbeiten** klicken, um den Filterausdruck manuell zu ändern.</span><span class="sxs-lookup"><span data-stu-id="89d21-158">Optionally, click **Edit Query** to manually change the filter expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="89d21-159">Wenn Sie einen Teil eines Filterausdrucks manuell ändern, wird das Raster deaktiviert. Anschließend müssen Sie mit dem Filterausdruck im Textbearbeitungsmodus arbeiten.</span><span class="sxs-lookup"><span data-stu-id="89d21-159">If you change any part of a filter expression manually, the grid will be disabled and thereafter you must work with the filter expression in text edit mode only.</span></span> <span data-ttu-id="89d21-160">Um den Rasterbearbeitungsmodus wiederherzustellen, müssen Sie den Filterausdruck löschen und von Neuem beginnen.</span><span class="sxs-lookup"><span data-stu-id="89d21-160">To restore grid editing mode, you must clear the filter expression and start over.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="89d21-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89d21-161">See Also</span></span>  
 <span data-ttu-id="89d21-162">[Filter für Mining Modelle &#40;Analysis Services Data Mining-&#41;](mining-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="89d21-162">[Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](mining-models-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="89d21-163">[Mining Modell Tasks und Anleitungen](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="89d21-163">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="89d21-164">Löschen eines Filters aus einem Miningmodell</span><span class="sxs-lookup"><span data-stu-id="89d21-164">Delete a Filter from a Mining Model</span></span>](delete-a-filter-from-a-mining-model.md)  
  
  
