---
title: Die grundlegende MDX-Abfrage (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [MDX], SELECT statement
- queries [MDX], about queries
- cellsets [MDX]
- SELECT statement [MDX]
- cubes [Analysis Services], SELECT statement
ms.assetid: 4fa5a95a-fec9-4584-875c-dbf030c53e82
author: minewiskan
ms.author: owend
ms.openlocfilehash: b6b1a70753abe8e477bd1e522a37f4513cc12a52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620613"
---
# <a name="the-basic-mdx-query-mdx"></a><span data-ttu-id="d49fc-102">Grundlegende MDX-Abfrage (MDX)</span><span class="sxs-lookup"><span data-stu-id="d49fc-102">The Basic MDX Query (MDX)</span></span>
  <span data-ttu-id="d49fc-103">Die grundlegende MDX-Abfrage (Multidimensional Expressions) ist die SELECT-Anweisung, die am häufigsten verwendete Abfrage in MDX.</span><span class="sxs-lookup"><span data-stu-id="d49fc-103">The basic Multidimensional Expressions (MDX) query is the SELECT statement-the most frequently used query in MDX.</span></span> <span data-ttu-id="d49fc-104">Wenn Sie wissen, wie in einer SELECT-Anweisung von MDX ein Resultset angegeben wird, wie die Syntax der SELECT-Anweisung lautet und wie eine einfache Abfrage mit der SELECT-Anweisung erstellt wird, verfügen Sie über das Basiswissen zum Abfragen mehrdimensionaler Daten mit MDX.</span><span class="sxs-lookup"><span data-stu-id="d49fc-104">By understanding how an MDX SELECT statement must specify a result set, what the syntax of the SELECT statement is, and how to create a simple query using the SELECT statement, you will have a solid understanding of how to use MDX to query multidimensional data.</span></span>  
  
## <a name="specifying-a-result-set"></a><span data-ttu-id="d49fc-105">Angeben eines Resultsets</span><span class="sxs-lookup"><span data-stu-id="d49fc-105">Specifying a Result Set</span></span>  
 <span data-ttu-id="d49fc-106">Die SELECT-Anweisung in MDX gibt ein Resultset an, das aus einer Teilmenge mehrdimensionaler Daten besteht, die aus einem Cube zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="d49fc-106">In MDX, the SELECT statement specifies a result set that contains a subset of multidimensional data that has been returned from a cube.</span></span> <span data-ttu-id="d49fc-107">Zum Angeben eines Resultsets muss die MDX-Abfrage die folgenden Informationen enthalten:</span><span class="sxs-lookup"><span data-stu-id="d49fc-107">To specify a result set, an MDX query must contain the following information:</span></span>  
  
-   <span data-ttu-id="d49fc-108">Die Anzahl der Achsen, die das Resultset enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="d49fc-108">The number of axes that you want the result set to contain.</span></span> <span data-ttu-id="d49fc-109">Sie können maximal 128 Achsen in einer MDX-Abfrage angeben.</span><span class="sxs-lookup"><span data-stu-id="d49fc-109">You can specify up to 128 axes in an MDX query.</span></span>  
  
-   <span data-ttu-id="d49fc-110">Die Menge von Elementen oder Tupeln, die auf jeder Achse der MDX-Abfrage enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="d49fc-110">The set of members or tuples to include on each axis of the MDX query.</span></span>  
  
-   <span data-ttu-id="d49fc-111">Der Name des Cubes, der den Kontext der MDX-Abfrage festlegt.</span><span class="sxs-lookup"><span data-stu-id="d49fc-111">The name of the cube that sets the context of the MDX query.</span></span>  
  
-   <span data-ttu-id="d49fc-112">Die Menge von Elementen oder Tupeln, die auf der Slicer-Achse enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="d49fc-112">The set of members or tuples to include on the slicer axis.</span></span> <span data-ttu-id="d49fc-113">Weitere Informationen zu Slicer- und Abfrageachsen finden Sie unter [Einschränken der Abfrage mit Abfrage- und Slicerachsen &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md).</span><span class="sxs-lookup"><span data-stu-id="d49fc-113">For more information about slicer and query axes, see[Restricting the Query with Query and Slicer Axes &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md).</span></span>  
  
 <span data-ttu-id="d49fc-114">Die SELECT-Anweisung von MDX verwendet die folgenden Klauseln zum Identifizieren der Abfrage-Achsen, des abgefragten Cubes und der Slicer-Achse:</span><span class="sxs-lookup"><span data-stu-id="d49fc-114">To identify the query axes, the cube that will be queried, and the slicer axis, the MDX SELECT statement uses the following clauses:</span></span>  
  
-   <span data-ttu-id="d49fc-115">Eine SELECT-Klausel, die die Abfrage-Achsen einer SELECT-Anweisung von MDX bestimmt.</span><span class="sxs-lookup"><span data-stu-id="d49fc-115">A SELECT clause that determines the query axes of an MDX SELECT statement.</span></span> <span data-ttu-id="d49fc-116">Weitere Informationen zur Erstellung von Abfrageachsen in einer SELECT-Klausel finden Sie unter [Angeben des Inhalts einer Abfrageachse &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span><span class="sxs-lookup"><span data-stu-id="d49fc-116">For more information about the construction of query axes in a SELECT clause, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span></span>  
  
-   <span data-ttu-id="d49fc-117">Eine FROM-Klausel, mit der festgelegt wird, welcher Cube abgefragt wird.</span><span class="sxs-lookup"><span data-stu-id="d49fc-117">A FROM clause that determines which cube will be queried.</span></span> <span data-ttu-id="d49fc-118">Weitere Informationen zur FROM-Klausel in der SELECT-Anweisung von MDX finden Sie unter [SELECT-Anweisung &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="d49fc-118">For more information about the FROM clause, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
-   <span data-ttu-id="d49fc-119">Eine optionale WHERE-Klausel, mit der festgelegt wird, welche Elemente oder Tupeln auf der Slicer-Achse verwendet werden sollen, um die zurückgegebenen Daten einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="d49fc-119">An optional WHERE clause that determines which members or tuples to use on the slicer axis to restrict the data returned.</span></span> <span data-ttu-id="d49fc-120">Weitere Informationen zur Erstellung einer Abfrageachse in einer WHERE-Klausel finden Sie unter [Angeben des Inhalts einer Slicerachse &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span><span class="sxs-lookup"><span data-stu-id="d49fc-120">For more information about the construction of a slicer axis in a WHERE clause, see [Specifying the Contents of a Slicer Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d49fc-121">Weitere Informationen zu den verschiedenen Klauseln der SELECT-Anweisung finden Sie unter [SELECT-Anweisung &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="d49fc-121">For more detailed information about the various clauses of the SELECT statement, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
## <a name="select-statement-syntax"></a><span data-ttu-id="d49fc-122">Syntax der SELECT-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d49fc-122">SELECT Statement Syntax</span></span>  
 <span data-ttu-id="d49fc-123">Die folgende Syntax zeigt eine grundlegende SELECT-Anweisung, in der SELECT-, FROM- und WHERE-Klauseln verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="d49fc-123">The following syntax shows a basic SELECT statement that includes the use of the SELECT, FROM, and WHERE clauses:</span></span>  
  
```  
[ WITH <SELECT WITH clause> [ , <SELECT WITH clause> ... ] ]   
SELECT [ * | ( <SELECT query axis clause>   
    [ , <SELECT query axis clause> ... ] ) ]  
FROM <SELECT subcube clause>   
[ <SELECT slicer axis clause> ]  
[ <SELECT cell property list clause> ]  
```  
  
 <span data-ttu-id="d49fc-124">Die SELECT-Anweisung von MDX unterstützt optionale Syntax, wie z. B. das WITH-Schlüsselwort und die Erstellung von berechneten Elementen mithilfe von MDX-Funktionen, um die Elemente in eine Achse oder Slicer-Achse einzuschließen. Außerdem bietet sie die Möglichkeit, die Werte bestimmter Zelleneigenschaften im Rahmen der Abfrage zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="d49fc-124">The MDX SELECT statement supports optional syntax, such as the WITH keyword, the use of MDX functions to create calculated members for inclusion in an axis or slicer axis, and the ability to return the values of specific cell properties as part of the query.</span></span> <span data-ttu-id="d49fc-125">Weitere Informationen zur SELECT-Anweisung von MDX finden Sie unter [SELECT-Anweisung &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="d49fc-125">For more information about the MDX SELECT statement, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
### <a name="comparing-the-syntax-of-the-mdx-select-statement-to-sql"></a><span data-ttu-id="d49fc-126">Vergleich der Syntax der SELECT-Anweisung von MDX mit SQL</span><span class="sxs-lookup"><span data-stu-id="d49fc-126">Comparing the Syntax of the MDX SELECT Statement to SQL</span></span>  
 <span data-ttu-id="d49fc-127">Das Syntaxformat der SELECT-Anweisung von MDX gleicht dem Format der SQL-Syntax.</span><span class="sxs-lookup"><span data-stu-id="d49fc-127">The syntax format for the MDX SELECT statement is similar to that of SQL syntax.</span></span> <span data-ttu-id="d49fc-128">Es gibt jedoch einige deutliche Unterschiede:</span><span class="sxs-lookup"><span data-stu-id="d49fc-128">However, there are several fundamental differences:</span></span>  
  
-   <span data-ttu-id="d49fc-129">Die MDX-Syntax unterscheidet Sätze, indem Tupel oder Elemente mit geschweiften Klammern (die Zeichen {und}) umgeben werden. Weitere Informationen zur Syntax von Membern, Tupeln und Mengen finden Sie unter [Arbeiten mit Elementen, Tupeln und festlegen &#40;MDX-&#41;](working-with-members-tuples-and-sets-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="d49fc-129">MDX syntax distinguishes sets by surrounding tuples or members with braces (the { and } characters.) For more information about member, tuple, and set syntax, see [Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md).</span></span>  
  
-   <span data-ttu-id="d49fc-130">MDX-Abfragen können 0, 1, 2 oder bis zu 128 Abfrage-Achsen in der SELECT-Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="d49fc-130">MDX queries can have 0, 1, 2 or up to 128 query axes in the SELECT statement.</span></span> <span data-ttu-id="d49fc-131">Jede Achse verhält sich auf exakt die gleiche Weise, im Gegensatz zu SQL, wo es deutliche Unterschiede zwischen den Verhaltensweisen der Zeilen und Spalten einer Abfrage gibt.</span><span class="sxs-lookup"><span data-stu-id="d49fc-131">Each axis behaves in exactly the same way, unlike SQL where there are significant differences between how the rows and the columns of a query behave.</span></span>  
  
-   <span data-ttu-id="d49fc-132">Wie in einer SQL-Abfrage benennt die FROM-Klausel die Quelle der Daten für die MDX-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="d49fc-132">As with an SQL query, the FROM clause names the source of the data for the MDX query.</span></span> <span data-ttu-id="d49fc-133">Die MDX-FROM-Klausel ist jedoch auf einen einzelnen Cube beschränkt.</span><span class="sxs-lookup"><span data-stu-id="d49fc-133">However, the MDX FROM clause is restricted to a single cube.</span></span> <span data-ttu-id="d49fc-134">Informationen aus anderen Cubes können Wert für Wert mithilfe der LookupCube-Funktion abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d49fc-134">Information from other cubes can be retrieved on a value-by-value basis by using the LookupCube function.</span></span>  
  
-   <span data-ttu-id="d49fc-135">Die WHERE-Klausel beschreibt die Slicer-Achse in einer MDX-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="d49fc-135">The WHERE clause describes the slicer axis in an MDX query.</span></span> <span data-ttu-id="d49fc-136">Sie verhält sich in etwa wie eine unsichtbare weitere Achse in der Abfrage, die die Werte, die in den Zellen im Resultset angezeigt werden, in Slices aufteilt. Im Gegensatz zur SQL-Klausel WHERE nimmt sie keinen direkten Einfluss darauf, was auf der ROWS-Achse der Abfrage angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d49fc-136">It acts as something like an invisible, extra axis in the query, slicing the values that appear in the cells in the result set; unlike the SQL WHERE clause it does not directly affect what appears on the rows axis of the query.</span></span> <span data-ttu-id="d49fc-137">Die Funktionalität der SQL-Klausel WHERE steht durch andere MDX-Funktionen zur Verfügung, wie z. B. die FILTER-Funktion.</span><span class="sxs-lookup"><span data-stu-id="d49fc-137">The functionality of the SQL WHERE clause is available through other MDX functions such as the FILTER function.</span></span>  
  
## <a name="select-statement-example"></a><span data-ttu-id="d49fc-138">Beispiel für die SELECT-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d49fc-138">SELECT Statement Example</span></span>  
 <span data-ttu-id="d49fc-139">Das folgende Beispiel zeigt eine grundlegende MDX-Abfrage mit der SELECT-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d49fc-139">The following example shows a basic MDX query that uses the SELECT statement.</span></span> <span data-ttu-id="d49fc-140">Die Abfrage gibt ein Resultset zurück, das die Umsatz- und Steuerbeträge für 2002 und 2003 in den südwestlichen Vertriebsregionen enthält.</span><span class="sxs-lookup"><span data-stu-id="d49fc-140">This query returns a result set that contains the 2002 and 2003 sales and tax amounts for the Southwest sales territories.</span></span>  
  
```  
SELECT  
    { [Measures].[Sales Amount],   
        [Measures].[Tax Amount] } ON COLUMNS,  
    { [Date].[Fiscal].[Fiscal Year].&[2002],   
        [Date].[Fiscal].[Fiscal Year].&[2003] } ON ROWS  
FROM [Adventure Works]  
WHERE ( [Sales Territory].[Southwest] )  
```  
  
 <span data-ttu-id="d49fc-141">In diesem Beispiel werden durch die Abfrage die folgenden Resultset-Informationen definiert:</span><span class="sxs-lookup"><span data-stu-id="d49fc-141">In this example, the query defines the following result set information:</span></span>  
  
-   <span data-ttu-id="d49fc-142">Die SELECT-Klausel legt die Abfrage-Achsen auf die Elemente Sales Amount (Umsatz) und Tax Amount (Steuern) der Measures-Dimension sowie auf die Elemente 2002 und 2003 der Date-Dimension fest.</span><span class="sxs-lookup"><span data-stu-id="d49fc-142">The SELECT clause sets the query axes as the Sales Amount and Tax Amount members of the Measures dimension, and the 2002 and 2003 members of the Date dimension.</span></span>  
  
-   <span data-ttu-id="d49fc-143">Die FROM-Klausel zeigt an, dass die Datenquelle im Adventure Works-Cube besteht.</span><span class="sxs-lookup"><span data-stu-id="d49fc-143">The FROM clause indicates that the data source is the Adventure Works cube.</span></span>  
  
-   <span data-ttu-id="d49fc-144">Die WHERE-Klausel definiert das Southwest-Element der Sales Territory-Dimension zur Slicer-Achse.</span><span class="sxs-lookup"><span data-stu-id="d49fc-144">The WHERE clause defines the slicer axis as the Southwest member of the Sales Territory dimension.</span></span>  
  
 <span data-ttu-id="d49fc-145">Beachten Sie, dass das Abfragebeispiel auch die Achsenaliase COLUMNS und ROWS verwendet.</span><span class="sxs-lookup"><span data-stu-id="d49fc-145">Notice that the query example also uses the COLUMNS and ROWS axis aliases.</span></span> <span data-ttu-id="d49fc-146">Ebenso können die Ordnungspositionen für diese Achsen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d49fc-146">The ordinal positions for these axes could also have been used.</span></span> <span data-ttu-id="d49fc-147">Das folgende Beispiel zeigt, wie die MDX-Abfrage mithilfe der Ordnungsposition jeder Achse geschrieben werden könnte:</span><span class="sxs-lookup"><span data-stu-id="d49fc-147">The following example shows how the MDX query could have been written to use the ordinal position of each axis:</span></span>  
  
```  
SELECT  
    { [Measures].[Sales Amount],   
        [Measures].[Tax Amount] } ON 0,  
    { [Date].[Fiscal].[Fiscal Year].&[2002],   
        [Date].[Fiscal].[Fiscal Year].&[2003] } ON 1  
FROM [Adventure Works]  
WHERE ( [Sales Territory].[Southwest] )  
```  
  
 <span data-ttu-id="d49fc-148">Ausführlichere Beispiele finden Sie unter [Angeben des Inhalts einer Abfrageachse &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md)und [Angeben des Inhalts einer Slicerachse &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span><span class="sxs-lookup"><span data-stu-id="d49fc-148">For more detailed examples, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md)and [Specifying the Contents of a Slicer Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d49fc-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d49fc-149">See Also</span></span>  
 <span data-ttu-id="d49fc-150">[Wichtige Konzepte in MDX-&#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="d49fc-150">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 [<span data-ttu-id="d49fc-151">SELECT-Anweisung &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="d49fc-151">SELECT Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-manipulation-select)  
  
  
