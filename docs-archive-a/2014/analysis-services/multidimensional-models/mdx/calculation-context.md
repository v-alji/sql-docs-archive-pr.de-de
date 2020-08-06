---
title: Berechnungs Kontext | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: aec8aa98-b77d-4f8f-9684-2618b1d8e970
author: minewiskan
ms.author: owend
ms.openlocfilehash: e6d14df51c6ec37fb96520af7acf207227ae4ea5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702008"
---
# <a name="calculation-context"></a><span data-ttu-id="5f7ec-102">Berechnungskontext</span><span class="sxs-lookup"><span data-stu-id="5f7ec-102">Calculation Context</span></span>
  <span data-ttu-id="5f7ec-103">Als Berechnungskontext wird der bekannte Teilbereich des Cubes bezeichnet, in dem ein Ausdruck ausgewertet wird und in dem alle Koordinaten entweder explizit bekannt sind oder vom Ausdruck abgeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="5f7ec-103">The calculation context is the known subspace of the cube where an expression is evaluated and all coordinates are either explicitly known or can be derived from the expression.</span></span>  
  
## <a name="determining-the-calculation-context"></a><span data-ttu-id="5f7ec-104">Bestimmen des Berechnungskontexts</span><span class="sxs-lookup"><span data-stu-id="5f7ec-104">Determining the calculation context</span></span>  
 <span data-ttu-id="5f7ec-105">Alle Mengen, Elemente, Tupel und numerischen Funktionen werden im Kontext des gesamten MDX-Ausdrucks bzw. der gesamten MDX-Anweisung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5f7ec-105">Every set, member, tuple, or numeric function executes in the context of the entire MDX expression or statement.</span></span> <span data-ttu-id="5f7ec-106">Beim Übergeben eines Arguments, z. B. eines Tupels, an eine Funktion werden nur einige Koordinaten im Cuberaum explizit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5f7ec-106">When an argument, such as a tuple, is passed to a function, only some of the coordinates in the cube space are explicitly provided.</span></span> <span data-ttu-id="5f7ec-107">Die anderen Koordinaten werden basierend auf dem aktuellen Berechnungskontext ermittelt.</span><span class="sxs-lookup"><span data-stu-id="5f7ec-107">The other coordinates are obtained based on the current calculation context.</span></span>  
  
 <span data-ttu-id="5f7ec-108">Der Berechnungskontext für nicht angegebene Zellenkoordinaten und Attributelemente wird in der folgenden Reihenfolge bestimmt:</span><span class="sxs-lookup"><span data-stu-id="5f7ec-108">The calculation context for unspecified cell coordinates and attribute members is determined in the following order:</span></span>  
  
1.  <span data-ttu-id="5f7ec-109">Die FROM-Klausel (ggf.) – Diese Klausel kann entweder einen gesamten Cube oder einen Teilcube in Form einer SELECT-Anweisung angeben.</span><span class="sxs-lookup"><span data-stu-id="5f7ec-109">The FROM clause (if applicable) - this clause can either specify an entire cube or can specify a subcube in the form of a SELECT statement.</span></span>  
  
2.  <span data-ttu-id="5f7ec-110">Die WHERE-Klausel (ggf.) – Über diese Klausel, die auch *Slicerachse*genannt wird, werden Mengen, Tupel oder Elemente angegeben, die die von der Abfrage zurückgegebenen Elemente auf der Spalten- und Zeilenachse einschränken.</span><span class="sxs-lookup"><span data-stu-id="5f7ec-110">The WHERE clause (if applicable) - this clause, which is also known as the *slicer axis*, on which you specify a set, tuple, or member that restricts the members returned on the column and row axis by a query.</span></span> <span data-ttu-id="5f7ec-111">Prinzipiell sind die Standardelemente aller Attributhierarchien, die nicht explizit auf der Spalten- oder Zeilenachse angegeben werden, Teil der Slicerachse.</span><span class="sxs-lookup"><span data-stu-id="5f7ec-111">Conceptually, the default member of every attribute hierarchy that is not explicitly specified on column or row axis is part of the slicer axis.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5f7ec-112">Wenn Zellenkoordinaten für ein bestimmtes Attribut sowohl auf der Slicerachse als auch auf einer weiteren Achse angegeben sind, werden die in der Funktion angegebenen Koordinaten möglicherweise vorrangig zur Bestimmung der Elemente der Menge auf der Achse verwendet.</span><span class="sxs-lookup"><span data-stu-id="5f7ec-112">When cell coordinates for a particular attribute are specified on both the slicer axis and on another axis, the coordinates specified in the function may take precedence in determining the members of the set on the axis.</span></span> <span data-ttu-id="5f7ec-113">Die Funktionen [Filter (MDX)](/sql/mdx/filter-mdx) und [Order (MDX)](/sql/mdx/order-mdx) sind Beispiele für solche Funktionen – Sie können ein Ergebnis nach Attributelementen filtern oder sortieren, die von der WHERE-Klausel oder der SELECT-Anweisung in der FROM-Klausel aus dem Berechnungskontext ausgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="5f7ec-113">The [Filter (MDX)](/sql/mdx/filter-mdx) and [Order (MDX)](/sql/mdx/order-mdx) functions are examples of such functions - you can filter or order a result by attribute members that are excluded from the calculation context by the WHERE clause, or by a SELECT statement in the FROM clause.</span></span>  
  
3.  <span data-ttu-id="5f7ec-114">Die in der Abfrage oder im Ausdruck definierten benannten Mengen und berechneten Elemente</span><span class="sxs-lookup"><span data-stu-id="5f7ec-114">The named sets and calculated members defined in the query or expression.</span></span>  
  
4.  <span data-ttu-id="5f7ec-115">Die auf der Zeilen- und Spaltenachse angegebenen Tupel und Mengen, die die Standardelemente der Attribute verwenden, die nicht auf der Zeilen-, Spalten oder Slicerachse angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="5f7ec-115">The tuples and sets specified on the row and column axes, utilizing the default member for attributes that do not appear on the row, column, or slicer axis.</span></span>  
  
5.  <span data-ttu-id="5f7ec-116">Die Cube- oder die Teilcubezellen auf jeder Achse unter Entfernung leerer Tupel von der Achse und Anwendung der HAVING-Klausel</span><span class="sxs-lookup"><span data-stu-id="5f7ec-116">The cube or subcube cells on each axis, eliminating empty tuples on the axis and applying the HAVING clause.</span></span>  
  
6.  <span data-ttu-id="5f7ec-117">Weitere Informationen finden Sie unter [Festlegen des Cubekontexts in einer Abfrage &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="5f7ec-117">For more information, see [Establishing Cube Context in a Query &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md).</span></span>  
  
 <span data-ttu-id="5f7ec-118">In der folgenden Abfrage ist der Berechnungskontext für die Zeilenachse durch die in der WHERE-Klausel angegebenen Attributelemente Country und Calendar Year eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="5f7ec-118">In the following query, the calculation context for the row axis is restricted by the Country attribute member and the Calendar Year attribute member that are specified in the WHERE clause.</span></span>  
  
```  
SELECT Customer.City.City.Members ON 0  
FROM [Adventure Works]  
WHERE (Customer.Country.France, [Date].[Calendar].[Calendar Year].[CY 2004],  
   Measures.[Internet Sales Amount])  
```  
  
 <span data-ttu-id="5f7ec-119">Wenn Sie jedoch diese Abfrage ändern, indem Sie die `FILTER`-Funktion auf der Zeilenachse angeben und ein Element der Calendar Year-Attributhierarchie in der `FILTER`-Funktion verwenden, kann das Attributelement der Calendar Year-Attributhierarchie, das zum Bereitstellen des Berechnungskontexts für die Elemente der Menge auf der Spaltenachse verwendet wird, geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5f7ec-119">However, if you modify this query by specifying the `FILTER` function on the row axis, and utilize a Calendar Year attribute hierarchy member in the `FILTER` function, then the attribute member from the Calendar Year attribute hierarchy that is used to provide the calculation context for the members of the set on the column axis can be modified.</span></span>  
  
```  
SELECT FILTER  
   (  
      Customer.City.City.Members,   
         ([Date].[Calendar].[Calendar Year].[CY 2003],  
            Measures.[Internet Order Quantity]) > 75   
   ) ON 0  
FROM [Adventure Works]  
WHERE (Customer.Country.France,  
   [Date].[Calendar].[Calendar Year].[CY 2004],  
   Measures.[Internet Sales Amount])  
```  
  
 <span data-ttu-id="5f7ec-120">In der vorherigen Abfrage wird der Berechnungskontext für die Zellen in den Tupeln, die auf der Spaltenachse angezeigt werden, vom CY 2003-Element der Calendar Year-Attributhierarchie gefiltert, auch wenn CY 2004 der nominelle Berechnungskontext für die Calendar Year-Attributhierarchie ist.</span><span class="sxs-lookup"><span data-stu-id="5f7ec-120">In the previous query, the calculation context for the cells in the tuples that appear on the column axis is filtered by the CY 2003 member of the Calendar Year attribute hierarchy, even though the nominal calculation context for the Calendar Year attribute hierarchy is CY 2004.</span></span> <span data-ttu-id="5f7ec-121">Es wird weiterhin nach dem Measure Internetbestellmenge gefiltert.</span><span class="sxs-lookup"><span data-stu-id="5f7ec-121">Furthermore, it is filtered by the Internet Order Quantity measure.</span></span> <span data-ttu-id="5f7ec-122">Sobald jedoch die Elemente der Menge auf der Spaltenachse festgelegt sind, wird der Berechnungskontext für die Werte der Elemente, die auf der Achse angezeigt werden, wieder über die WHERE-Klausel bestimmt.</span><span class="sxs-lookup"><span data-stu-id="5f7ec-122">However, once the members of the set on the column axis is set, the calculation context for the values for the members that appear on the axis is again determined by the WHERE clause.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5f7ec-123">Zur Verbesserung der Abfrageleistung sollten Elemente und Tupel beim Auflösungsvorgang so früh wie möglich entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="5f7ec-123">To increase query performance, you should eliminate members and tuples as early in the resolution process as possible.</span></span> <span data-ttu-id="5f7ec-124">Auf diese Weise werden komplexe Abfragezeitberechnungen für die endgültige Menge der Elemente mit minimaler Zellenanzahl durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="5f7ec-124">In this manner, complex query time calculations on the final set of members operate on the fewest cells possible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f7ec-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5f7ec-125">See Also</span></span>  
 <span data-ttu-id="5f7ec-126">[Einrichten des Cubekontexts in einer Abfrage &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="5f7ec-126">[Establishing Cube Context in a Query &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span></span>  
 <span data-ttu-id="5f7ec-127">[Grundlagen der MDX-Abfrage &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="5f7ec-127">[MDX Query Fundamentals &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span></span>  
 [<span data-ttu-id="5f7ec-128">Schlüsselkonzepte in MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5f7ec-128">Key Concepts in MDX &#40;Analysis Services&#41;</span></span>](../key-concepts-in-mdx-analysis-services.md)  
  
  
