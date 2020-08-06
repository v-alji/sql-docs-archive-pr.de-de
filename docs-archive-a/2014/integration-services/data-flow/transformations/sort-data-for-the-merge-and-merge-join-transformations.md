---
title: Sortieren von Daten für die Transformationen für Zusammenführen und Zusammenführungsjoin | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- sort attributes [Integration Services]
- output columns [Integration Services]
ms.assetid: 22ce3f5d-8a88-4423-92c2-60a8f82cd4fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7bb4e91ad84c6baa52e1d7fb4b0104d835b7e4cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695858"
---
# <a name="sort-data-for-the-merge-and-merge-join-transformations"></a><span data-ttu-id="fd0a3-102">Sortieren von Daten für die Transformationen für Zusammenführen und Zusammenführungsjoin</span><span class="sxs-lookup"><span data-stu-id="fd0a3-102">Sort Data for the Merge and Merge Join Transformations</span></span>
  <span data-ttu-id="fd0a3-103">In [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]erfordern die Transformationen für Zusammenführen und Zusammenführungsjoin sortierte Daten für ihre Eingaben.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-103">In [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], the Merge and Merge Join transformations require sorted data for their inputs.</span></span> <span data-ttu-id="fd0a3-104">Die Eingabedaten müssen physisch sortiert werden, und die Sortierungsoptionen müssen für die Ausgaben und die Ausgabespalten in der Quelle oder Upstreamtransformation festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-104">The input data must be sorted physically, and sort options must be set on the outputs and the output columns in the source or in the upstream transformation.</span></span> <span data-ttu-id="fd0a3-105">Wenn die Sortierungsoptionen anzeigen, dass die Daten sortiert sind, dies jedoch in Wirklichkeit nicht der Fall ist, sind die Ergebnisse des Vorgangs der Zusammenführung oder des Zusammenführungsjoins nicht vorhersagbar.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-105">If the sort options indicate that the data is sorted, but the data is not actually sorted, the results of the merge or merge join operation are unpredictable.</span></span>  
  
## <a name="sorting-the-data"></a><span data-ttu-id="fd0a3-106">Sortieren der Daten</span><span class="sxs-lookup"><span data-stu-id="fd0a3-106">Sorting the Data</span></span>  
 <span data-ttu-id="fd0a3-107">Sie können diese Daten auch mithilfe einer der folgenden Methoden sortieren:</span><span class="sxs-lookup"><span data-stu-id="fd0a3-107">You can sort this data by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="fd0a3-108">Verwenden Sie in der Quelle eine ORDER BY-Klausel in der Anweisung, die zum Laden der Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-108">In the source, use an ORDER BY clause in the statement that is used to load the data.</span></span>  
  
-   <span data-ttu-id="fd0a3-109">Fügen Sie im Datenfluss vor der Transformation für Zusammenführung oder dem Zusammenführungsjoin eine Transformation zum Sortieren ein.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-109">In the data flow, insert a Sort transformation before the Merge or Merge Join transformation.</span></span>  
  
 <span data-ttu-id="fd0a3-110">Wenn es sich bei den Daten um Zeichenfolgendaten handelt, erwartet sowohl die Transformation für Zusammenführung als auch die für den Zusammenführungsjoin, dass die Zeichenfolgenwerte mithilfe der Windows-Sortierung sortiert wurden.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-110">If the data is string data, both the Merge and Merge Join transformations expect the string values to have been sorted by using Windows collation.</span></span> <span data-ttu-id="fd0a3-111">Führen Sie die folgenden Vorgänge aus, um Zeichenfolgenwerte für die Transformationen für Zusammenführung und für den Zusammenführungsjoin bereitzustellen, die mithilfe der Windows-Sortierung sortiert wurden.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-111">To provide string values to the Merge and Merge Join transformations that are sorted by using Windows collation, use the following procedure.</span></span>  
  
#### <a name="to-provide-string-values-that-are-sorted-by-using-windows-collation"></a><span data-ttu-id="fd0a3-112">So stellen Sie mithilfe der Windows-Sortierung sortierte Zeichenfolgenwerte bereit</span><span class="sxs-lookup"><span data-stu-id="fd0a3-112">To provide string values that are sorted by using Windows collation</span></span>  
  
-   <span data-ttu-id="fd0a3-113">Sortieren Sie die Daten mit einer Transformation zum Sortieren.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-113">Use a Sort transformation to sort the data.</span></span>  
  
     <span data-ttu-id="fd0a3-114">Die Transformation zum Sortieren verwendet die Windows-Sortierung, um Zeichenfolgenwerte zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-114">The Sort transformation uses Windows collation to sort string values.</span></span>  
  
     <span data-ttu-id="fd0a3-115">Oder</span><span class="sxs-lookup"><span data-stu-id="fd0a3-115">-or-</span></span>  
  
-   <span data-ttu-id="fd0a3-116">Verwenden Sie den Transact-SQL-Umwandlungsoperator, um die `varchar`-Werte zuerst in `nvarchar`-Werte umzuwandeln, und sortieren Sie die Daten anschließend mit der ORDER BY-Klausel in Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-116">Use the Transact-SQL CAST operator to first cast `varchar` values to `nvarchar` values, and then use the Transact-SQL ORDER BY clause to sort the data.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="fd0a3-117">Die ORDER BY-Klausel allein reicht nicht aus, da sie eine [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Sortierung zum Sortieren der Zeichenfolgenwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-117">You cannot use the ORDER BY clause alone because the ORDER BY clause uses a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] collation to sort string values.</span></span> <span data-ttu-id="fd0a3-118">Mit der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Sortierung ergibt sich möglicherweise eine andere Sortierreihenfolge als mit der Windows-Sortierung. Dadurch könnte die Transformation für Zusammenführung und für Zusammenführungsjoin zu unerwarteten Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-118">The use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] collation might result in a different sort order than Windows collation, which can cause the Merge or Merge Join transformation to produce unexpected results.</span></span>  
  
## <a name="setting-sort-options-on-the-data"></a><span data-ttu-id="fd0a3-119">Festlegen von Sortieroptionen für die Daten</span><span class="sxs-lookup"><span data-stu-id="fd0a3-119">Setting Sort Options on the Data</span></span>  
 <span data-ttu-id="fd0a3-120">Es gibt zwei wichtige Sortiereigenschaften, die für die Quelle oder die Upstreamtransformation festgelegt werden müssen, die die Daten für Transformationen für Zusammenführen und für Zusammenführungsjoin bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-120">There are two important sort properties that must be set for the source or upstream transformation that supplies data to the Merge and Merge Join transformations:</span></span>  
  
-   <span data-ttu-id="fd0a3-121">Die `IsSorted`-Eigenschaft der Ausgabe, die angibt, ob die Daten sortiert wurden.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-121">The `IsSorted` property of the output that indicates whether the data has been sorted.</span></span> <span data-ttu-id="fd0a3-122">Diese Eigenschaft muss auf `True` festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-122">This property must be set to `True`.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="fd0a3-123">Durch die Festlegung des Werts für die Eigenschaft `IsSorted` auf `True` werden keine Daten sortiert.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-123">Setting the value of the `IsSorted` property to `True` does not sort the data.</span></span> <span data-ttu-id="fd0a3-124">Diese Eigenschaft ist lediglich ein Hinweis für die Downstreamkomponenten, dass die Daten vorher sortiert wurden.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-124">This property only provides a hint to downstream components that the data has been previously sorted.</span></span>  
  
-   <span data-ttu-id="fd0a3-125">Die `SortKeyPosition`-Eigenschaft der Ausgabespalten, die angibt, ob eine Spalte sortiert ist sowie die Sortierreihenfolge der Spalte und die Sequenz, in der mehrere Spalten sortiert wurden.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-125">The `SortKeyPosition` property of output columns that indicates whether a column is sorted, the column's sort order, and the sequence in which multiple columns are sorted.</span></span> <span data-ttu-id="fd0a3-126">Diese Eigenschaft muss für jede Spalte sortierter Daten festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-126">This property must be set for each column of sorted data.</span></span>  
  
 <span data-ttu-id="fd0a3-127">Wenn Sie zum Sortieren der Daten eine Transformation zum Sortieren verwenden, legt die Transformation zum Sortieren diese beiden von der Transformation für Zusammenführen und für Zusammenführungsjoin verlangten Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-127">If you use a Sort transformation to sort the data, the Sort transformation sets both of these properties as required by the Merge or Merge Join transformation.</span></span> <span data-ttu-id="fd0a3-128">Das heißt, die Transformation zum Sortieren legt die `IsSorted`-Eigenschaft ihrer Ausgabe auf `True` fest und legt die `SortKeyPosition`-Eigenschaften ihrer Ausgabespalten fest.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-128">That is, the Sort transformation sets the `IsSorted` property of its output to `True`, and sets the `SortKeyPosition` properties of its output columns.</span></span>  
  
 <span data-ttu-id="fd0a3-129">Wenn Sie zum Sortieren der Daten jedoch keine Transformation zum Sortieren verwenden, müssen Sie diese Sortiereigenschaften für die Quelle oder die Upstreamtransformation manuell festlegen.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-129">However, if you do not use a Sort transformation to sort the data, you must set these sort properties manually on the source or the upstream transformation.</span></span> <span data-ttu-id="fd0a3-130">Verwenden Sie folgendes Verfahren, um die Sortiereigenschaften für die Quelle oder Upstreamtransformation manuell festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-130">To manually set the sort properties on the source or upstream transformation, use the following procedure.</span></span>  
  
#### <a name="to-manually-set-sort-attributes-on-a-source-or-transformation-component"></a><span data-ttu-id="fd0a3-131">So legen Sie Sortierattribute für eine Quelle oder Transformationskomponente manuell fest</span><span class="sxs-lookup"><span data-stu-id="fd0a3-131">To manually set sort attributes on a source or transformation component</span></span>  
  
1.  <span data-ttu-id="fd0a3-132">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-132">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="fd0a3-133">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-133">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="fd0a3-134">Suchen Sie auf der Registerkarte **Datenfluss** nach der entsprechenden Quelle oder Upstreamtransformation, oder ziehen Sie diese von der **Toolbox** auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-134">On the **Data Flow** tab, locate the appropriate source or upstream transformation, or drag it from the **Toolbox** to the design surface.</span></span>  
  
4.  <span data-ttu-id="fd0a3-135">Klicken Sie mit der rechten Maustaste auf die Komponente, und klicken Sie auf **Erweiterten Editor anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-135">Right-click the component and click **Show Advanced Editor**.</span></span>  
  
5.  <span data-ttu-id="fd0a3-136">Klicken Sie auf die Registerkarte **Eingabe- und Ausgabeeigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="fd0a3-136">Click the **Input and Output Properties** tab.</span></span>  
  
6.  <span data-ttu-id="fd0a3-137">Klicken Sie auf \*\* \<component name> Ausgabe\*\*, und legen Sie die- `IsSorted` Eigenschaft auf fest `True` .</span><span class="sxs-lookup"><span data-stu-id="fd0a3-137">Click **\<component name> Output**, and set the `IsSorted` property to `True`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fd0a3-138">Wenn Sie die `IsSorted`-Eigenschaft der Ausgabe manuell auf `True` festlegen und die Daten nicht sortiert sind, kann es beim Ausführen des Pakets in der Downstreamtransformation für Zusammenführung oder des Zusammenführungsjoins zu Vergleichsvorgängen mit fehlenden oder beschädigten Daten kommen.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-138">If you manually set the `IsSorted` property of the output to `True` and the data is not sorted, there might be missing data or bad data comparisons in the downstream Merge or Merge Join transformation when you run the package.</span></span>  
  
7.  <span data-ttu-id="fd0a3-139">Erweitern Sie **Ausgabespalten**.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-139">Expand **Output Columns**.</span></span>  
  
8.  <span data-ttu-id="fd0a3-140">Klicken Sie auf die Spalte, die Sie als sortiert kennzeichnen möchten, und legen Sie für die `SortKeyPosition`-Eigenschaft einen ganzzahligen Wert ungleich 0 fest. Beachten Sie dabei folgende Hinweise:</span><span class="sxs-lookup"><span data-stu-id="fd0a3-140">Click the column that you want to indicate is sorted and set its `SortKeyPosition` property to a nonzero integer value by following these guidelines:</span></span>  
  
    -   <span data-ttu-id="fd0a3-141">Der ganzzahlige Wert muss eine numerische Sequenz darstellen, die bei 1 beginnt und sich jeweils um 1 erhöht.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-141">The integer value must represent a numeric sequence, starting with 1 and incremented by 1.</span></span>  
  
    -   <span data-ttu-id="fd0a3-142">Ein positiver ganzzahliger Wert gibt eine aufsteigende Sortierreihenfolge an.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-142">A positive integer value indicates an ascending sort order.</span></span>  
  
    -   <span data-ttu-id="fd0a3-143">Ein negativer ganzzahliger Wert gibt eine absteigende Sortierreihenfolge an.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-143">A negative integer value indicates a descending sort order.</span></span> <span data-ttu-id="fd0a3-144">(Wenn eine negative Zahl angegeben wird, legt der absolute Wert der Zahl die Position der Spalte in der Sortierreihenfolge fest.)</span><span class="sxs-lookup"><span data-stu-id="fd0a3-144">(If set to a negative number, the absolute value of the number determines the column's position in the sort sequence.)</span></span>  
  
    -   <span data-ttu-id="fd0a3-145">Der Standardwert 0 gibt an, dass die Spalte nicht sortiert ist.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-145">The default value of 0 indicates that the column is not sorted.</span></span> <span data-ttu-id="fd0a3-146">Lassen Sie den Wert 0 für Ausgabespalten unverändert, die kein Bestandteil der Sortierung sind.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-146">Leave the value of 0 for output columns that do not participate in the sort.</span></span>  
  
     <span data-ttu-id="fd0a3-147">Beachten Sie als Beispiel für die Festlegung der `SortKeyPosition`-Eigenschaft folgende Transact-SQL-Anweisung, die Daten in eine Quelle lädt:</span><span class="sxs-lookup"><span data-stu-id="fd0a3-147">As an example of how to set the `SortKeyPosition` property, consider the following Transact-SQL statement that loads data in a source:</span></span>  
  
     `SELECT * FROM MyTable ORDER BY ColumnA, ColumnB DESC, ColumnC`  
  
     <span data-ttu-id="fd0a3-148">Für diese Anweisung würden Sie die `SortKeyPosition`-Eigenschaft für jede Spalte folgendermaßen festlegen:</span><span class="sxs-lookup"><span data-stu-id="fd0a3-148">For this statement, you would set the `SortKeyPosition` property for each column as follows:</span></span>  
  
    -   <span data-ttu-id="fd0a3-149">Legen Sie die `SortKeyPosition`-Eigenschaft von ColumnA auf 1 fest.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-149">Set the `SortKeyPosition` property of ColumnA to 1.</span></span> <span data-ttu-id="fd0a3-150">Dies gibt an, dass ColumnA die erste Spalte ist, die sortiert wird, und dass sie in aufsteigender Reihenfolge sortiert wird.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-150">This indicates that ColumnA is the first column to be sorted and is sorted in ascending order.</span></span>  
  
    -   <span data-ttu-id="fd0a3-151">Legen Sie die `SortKeyPosition`-Eigenschaft von ColumnB auf -2 fest.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-151">Set the `SortKeyPosition` property of ColumnB to -2.</span></span> <span data-ttu-id="fd0a3-152">Dies gibt an, dass ColumnB die zweite Spalte ist, die sortiert wird, und dass sie in absteigender Reihenfolge sortiert wird.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-152">This indicates that ColumnB is the second column to be sorted and is sorted in descending order</span></span>  
  
    -   <span data-ttu-id="fd0a3-153">Legen Sie die `SortKeyPosition`-Eigenschaft von ColumnC auf 3 fest.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-153">Set the `SortKeyPosition` property of ColumnC to 3.</span></span> <span data-ttu-id="fd0a3-154">Dies gibt an, dass ColumnC die dritte Spalte ist, die sortiert wird, und dass sie in aufsteigender Reihenfolge sortiert wird.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-154">This indicates that ColumnC is the third column to be sorted and is sorted in ascending order.</span></span>  
  
9. <span data-ttu-id="fd0a3-155">Wiederholen Sie Schritt 8 für jede sortierte Spalte.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-155">Repeat step 8 for each sorted column.</span></span>  
  
10. <span data-ttu-id="fd0a3-156">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-156">Click **OK**.</span></span>  
  
11. <span data-ttu-id="fd0a3-157">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="fd0a3-157">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd0a3-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fd0a3-158">See Also</span></span>  
 <span data-ttu-id="fd0a3-159">[Transformation für Zusammenführen](merge-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="fd0a3-159">[Merge Transformation](merge-transformation.md) </span></span>  
 <span data-ttu-id="fd0a3-160">[Transformation für Zusammenführungsjoin](merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="fd0a3-160">[Merge Join Transformation](merge-join-transformation.md) </span></span>  
 <span data-ttu-id="fd0a3-161">[SQL Server Integration Services-Transformationen](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="fd0a3-161">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="fd0a3-162">[SQL Server Integration Services-Pfade](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="fd0a3-162">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="fd0a3-163">Datenflusstask</span><span class="sxs-lookup"><span data-stu-id="fd0a3-163">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
