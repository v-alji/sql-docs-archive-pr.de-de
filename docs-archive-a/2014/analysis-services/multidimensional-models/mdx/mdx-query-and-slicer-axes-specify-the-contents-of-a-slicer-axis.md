---
title: Angeben des Inhalts einer Slicerachse (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- slicer axis
- filtering data [MDX]
ms.assetid: c56b0a70-cdec-427f-990e-425290344e7d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8620c54970ea14a2ac01c85262a372d2b3db0d68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696238"
---
# <a name="specifying-the-contents-of-a-slicer-axis-mdx"></a><span data-ttu-id="477f3-102">Angeben des Inhalts einer Slicerachse (MDX)</span><span class="sxs-lookup"><span data-stu-id="477f3-102">Specifying the Contents of a Slicer Axis (MDX)</span></span>
  <span data-ttu-id="477f3-103">Die Slicerachse filtert die von der SELECT-Anweisung von MDX (Multidimensional Expressions) zurückgegebenen Daten, sodass nur die Daten zurückgegeben werden, die sich mit den angegebenen Elementen überschneiden.</span><span class="sxs-lookup"><span data-stu-id="477f3-103">The slicer axis filters the data returned by the Multidimensional Expressions (MDX) SELECT statement, restricting the returned data so that only data intersecting with the specified members will be returned.</span></span> <span data-ttu-id="477f3-104">Sie kann als zusätzliche unsichtbare Achse in einer Abfrage betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="477f3-104">It can be thought of as an invisible extra axis in a query.</span></span> <span data-ttu-id="477f3-105">Die Slicerachse wird in der WHERE-Klausel der SELECT-Anweisung von MDX definiert.</span><span class="sxs-lookup"><span data-stu-id="477f3-105">The slicer axis is defined in the WHERE clause of the SELECT statement in MDX.</span></span>  
  
## <a name="slicer-axis-syntax"></a><span data-ttu-id="477f3-106">Slicerachse (Syntax)</span><span class="sxs-lookup"><span data-stu-id="477f3-106">Slicer Axis Syntax</span></span>  
 <span data-ttu-id="477f3-107">Zum expliziten Angeben einer Slicerachse verwenden Sie in MDX die folgende `<SELECT slicer axis clause>` -Syntax:</span><span class="sxs-lookup"><span data-stu-id="477f3-107">To explicitly specify a slicer axis, you  using the `<SELECT slicer axis clause>` in MDX, as described in the following syntax:</span></span>  
  
```  
<SELECT slicer axis clause> ::=  WHERE Set_Expression  
```  
  
 <span data-ttu-id="477f3-108">In dieser Syntax der Slicerachse kann `Set_Expression` entweder einem Tupelausdruck entsprechen, der zum Auswerten der Klausel wie eine Menge behandelt wird, oder einem Mengenausdruck.</span><span class="sxs-lookup"><span data-stu-id="477f3-108">In the slicer axis syntax shown, `Set_Expression` can take either a tuple expression, which is treated as a set for the purposes of evaluating the clause, or a set expression.</span></span> <span data-ttu-id="477f3-109">Wird ein Mengenausdruck angegeben, versucht MDX, die Menge auszuwerten, indem die Ergebniszellen in jedem Tupel der Menge aggregiert werden.</span><span class="sxs-lookup"><span data-stu-id="477f3-109">If a set expression is specified, MDX will try to evaluate the set, aggregating the result cells in every tuple along the set.</span></span> <span data-ttu-id="477f3-110">Das heißt, MDX versucht, die [Aggregate](/sql/mdx/aggregate-mdx) -Funktion auf die Menge anzuwenden und aggregiert jedes Measure durch die ihm zugeordnete Aggregatfunktion.</span><span class="sxs-lookup"><span data-stu-id="477f3-110">In other words, MDX will try to use the [Aggregate](/sql/mdx/aggregate-mdx) function on the set, aggregating each measure by its associated aggregation function.</span></span> <span data-ttu-id="477f3-111">Wenn der Mengenausdruck nicht als Kreuzprodukt von Elementen der Attributhierarchie ausgedrückt werden kann, behandelt MDX Zellen außerhalb des Mengenausdrucks für die Slicerachse bei der Auswertung als NULL-Werte.</span><span class="sxs-lookup"><span data-stu-id="477f3-111">Also, if the set expression cannot be expressed as a crossjoin of attribute hierarchy members, MDX treats cells that fall outside of the set expression for the slicer as null for evaluation purposes.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="477f3-112">Im Gegensatz zur WHERE-Klausel in SQL filtert die WHERE-Klausel einer MDX SELECT-Anweisung nie direkt, was auf der ROWS-Achse einer Abfrage zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="477f3-112">Unlike the WHERE clause in SQL, the WHERE clause of an MDX SELECT statement never directly filters what is returned on the Rows axis of a query.</span></span> <span data-ttu-id="477f3-113">Um zu filtern, was auf der ROWS- oder COLUMNS-Achse einer Abfrage angezeigt wird, können Sie eine Vielzahl von MDX-Funktionen verwenden, z. B. FILTER, NONEMPTY und TOPCOUNT.</span><span class="sxs-lookup"><span data-stu-id="477f3-113">To filter what appears on the Rows or Columns axis of a query, you can use a variety of MDX functions, for example FILTER, NONEMPTY and TOPCOUNT.</span></span>  
  
### <a name="implicit-slicer-axis"></a><span data-ttu-id="477f3-114">Implizite Slicerachse</span><span class="sxs-lookup"><span data-stu-id="477f3-114">Implicit Slicer Axis</span></span>  
 <span data-ttu-id="477f3-115">Wenn ein Element aus einer Hierarchie im Cube nicht explizit in eine Abfrageachse eingeschlossen wird, wird das Standardelement aus dieser Hierarchie implizit in die Slicerachse eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="477f3-115">If a member from a hierarchy within the cube is not explicitly included in a query axis, the default member from that hierarchy is implicitly included in the slicer axis.</span></span> <span data-ttu-id="477f3-116">Weitere Informationen zu Standardelementen finden Sie unter [Definieren eines Standardelements](../attribute-properties-define-a-default-member.md).</span><span class="sxs-lookup"><span data-stu-id="477f3-116">For more information about default members, see [Define a Default Member](../attribute-properties-define-a-default-member.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="477f3-117">Beispiele</span><span class="sxs-lookup"><span data-stu-id="477f3-117">Examples</span></span>  
 <span data-ttu-id="477f3-118">Die folgende Abfrage enthält keine WHERE-Klausel und gibt den Wert des Internet Sales Amount-Measures für alle Kalenderjahre zurück:</span><span class="sxs-lookup"><span data-stu-id="477f3-118">The following query does not include a WHERE clause, and returns the value of the Internet Sales Amount measure for all Calendar Years:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="477f3-119">Durch Hinzufügen einer WHERE-Klausel wie folgt:</span><span class="sxs-lookup"><span data-stu-id="477f3-119">Adding a WHERE clause, as follows:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
WHERE([Customer].[Customer Geography].[Country].&[United States])  
  
```  
  
 <span data-ttu-id="477f3-120">wird nicht geändert, was in Zeilen oder Spalten in der Abfrage zurückgegeben wird. Dafür werden die zurückgegebenen Werte für die einzelnen Zellen geändert.</span><span class="sxs-lookup"><span data-stu-id="477f3-120">does not change what is returned on Rows or Columns in the query; it changes the values returned for each cell.</span></span> <span data-ttu-id="477f3-121">In diesem Beispiel ist die Abfrage in Slices aufgeteilt, sodass sie den Wert von Internet Sales Amount für alle Kalenderjahre zurückgibt, jedoch nur für Kunden, die in den USA wohnen. Der WHERE-Klausel können mehrere Elemente unterschiedlicher Hierarchien hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="477f3-121">In this example, the query is sliced so that it returns the value of Internet Sales Amount for all Calendar Years but only for Customers who live in the United States.Multiple members from different hierarchies can be added to the WHERE clause.</span></span> <span data-ttu-id="477f3-122">Die folgende Abfrage zeigt den Wert von Internet Sales Amount für alle Kalenderjahre für Kunden, die in den USA wohnen und die Produkte in der Kategorie Bikes gekauft haben.</span><span class="sxs-lookup"><span data-stu-id="477f3-122">The following query shows the value of Internet Sales Amount for all Calendar Years for Customers who live in the United States and who bought Products in the Category Bikes:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
WHERE([Customer].[Customer Geography].[Country].&[United States], [Product].[Category].&[1])  
```  
  
 <span data-ttu-id="477f3-123">Wenn Sie mehrere Elemente aus derselben Hierarchie verwenden möchten, muss der WHERE-Klausel eine Menge hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="477f3-123">If you want to use multiple members from the same hierarchy, you need to include a set in the WHERE clause.</span></span> <span data-ttu-id="477f3-124">Die folgende Abfrage zeigt beispielsweise den Wert von Internet Sales Amount für alle Kalenderjahre für Kunden, die Produkte in der Kategorie Bikes gekauft haben und die in den USA oder in Großbritannien wohnen:</span><span class="sxs-lookup"><span data-stu-id="477f3-124">For example, the following query shows the value of Internet Sales Amount for all Calendar Years for Customers who bought Products in the Category Bikes and live in either the United States or the United Kingdom:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
WHERE(  
{[Customer].[Customer Geography].[Country].&[United States]  
, [Customer].[Customer Geography].[Country].&[United Kingdom]}  
, [Product].[Category].&[1])  
  
```  
  
 <span data-ttu-id="477f3-125">Wie oben erwähnt, werden bei Verwendung einer Menge in der WHERE-Klausel implizit Werte für alle Elemente in der Menge aggregiert.</span><span class="sxs-lookup"><span data-stu-id="477f3-125">As mentioned above, using a set in the WHERE clause will implicitly aggregate values for all members in the set.</span></span> <span data-ttu-id="477f3-126">In diesem Fall zeigt die Abfrage aggregierte Werte für die USA und Großbritannien in jeder Zelle.</span><span class="sxs-lookup"><span data-stu-id="477f3-126">In this case, the query shows aggregated values for the United States and the United Kingdom in each cell.</span></span>  
  
  
