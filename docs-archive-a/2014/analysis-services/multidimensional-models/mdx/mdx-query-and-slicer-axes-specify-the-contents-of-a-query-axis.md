---
title: Angeben des Inhalts einer Abfrage Achse (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cellsets [MDX]
- query axis [MDX]
ms.assetid: c745ade0-738e-4a98-a3f0-3eabfd3eeba2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 28fd867b8f8caaf74e4dd704753c354368da2e89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718772"
---
# <a name="specifying-the-contents-of-a-query-axis-mdx"></a><span data-ttu-id="69a58-102">Angeben des Inhalts einer Abfrageachse (MDX)</span><span class="sxs-lookup"><span data-stu-id="69a58-102">Specifying the Contents of a Query Axis (MDX)</span></span>
  <span data-ttu-id="69a58-103">Abfrageachsen geben die Kanten eines Cellsets an, die von einer SELECT-Anweisung von MDX (Multidimensional Expressions) zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="69a58-103">Query axes specify the edges of a cellset returned by a Multidimensional Expressions (MDX) SELECT statement.</span></span> <span data-ttu-id="69a58-104">Durch Angeben der Kanten eines Cellsets können Sie die zurückgegebenen Daten einschränken, die für den Client sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="69a58-104">Specifying the edges of a cellset lets you restrict the returned data that is visible to the client.</span></span>  
  
 <span data-ttu-id="69a58-105">Sie geben Abfrageachsen an, indem Sie einer Menge mithilfe eines `<SELECT query axis clause>` -Wertes eine bestimmte Abfrageachse zuweisen.</span><span class="sxs-lookup"><span data-stu-id="69a58-105">To specify query axes, you use the `<SELECT query axis clause>` to assign a set to a particular query axis.</span></span> <span data-ttu-id="69a58-106">Jeder `<SELECT query axis clause>` -Wert definiert eine Abfrageachse.</span><span class="sxs-lookup"><span data-stu-id="69a58-106">Each `<SELECT query axis clause>` value defines one query axis.</span></span> <span data-ttu-id="69a58-107">Die Anzahl der Achsen im Dataset entspricht der Anzahl von `<SELECT query axis clause>` -Werten in der SELECT-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="69a58-107">The number of axes in the dataset is equal to the number of `<SELECT query axis clause>` values in the SELECT statement.</span></span>  
  
## <a name="query-axis-syntax"></a><span data-ttu-id="69a58-108">Abfrageachse (Syntax)</span><span class="sxs-lookup"><span data-stu-id="69a58-108">Query Axis Syntax</span></span>  
 <span data-ttu-id="69a58-109">Nachstehend ist die Syntax von `<SELECT query axis clause>`definiert:</span><span class="sxs-lookup"><span data-stu-id="69a58-109">The following syntax shows the syntax for the `<SELECT query axis clause>`:</span></span>  
  
```  
  
<SELECT query axis clause> ::=  
   [ NON EMPTY ] Set_Expression [ <SELECT dimension property list clause> ] [<HAVING clause>]  
   ON {  
      Integer_Expression |   
      AXIS( Integer_Expression ) |   
      {COLUMNS | ROWS | PAGES | SECTIONS | CHAPTERS}     
      }  
  
```  
  
 <span data-ttu-id="69a58-110">Jede Abfrageachse hat eine Nummer: 0 für die x-Achse, 1 für die y-Achse, 2 für die z-Achse usw.</span><span class="sxs-lookup"><span data-stu-id="69a58-110">Each query axis has a number: zero (0) for the x-axis, 1 for the y-axis, 2 for the z-axis, and so on.</span></span> <span data-ttu-id="69a58-111">In der Syntax für `<SELECT query axis clause>`gibt der `Integer_Expression` -Wert die Achsennummer an.</span><span class="sxs-lookup"><span data-stu-id="69a58-111">In the syntax for the `<SELECT query axis clause>`, the `Integer_Expression` value specifies the axis number.</span></span> <span data-ttu-id="69a58-112">Eine MDX-Abfrage unterstützt maximal 128 angegebene Achsen, jedoch werden nur selten mehr als 5 Achsen verwendet.</span><span class="sxs-lookup"><span data-stu-id="69a58-112">An MDX query can support up to 128 specified axes, but very few MDX queries will use more than 5 axes.</span></span> <span data-ttu-id="69a58-113">Anstelle der ersten 5 Achsen können die Aliase COLUMNS, ROWS, PAGES, SECTIONS und CHAPTERS verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="69a58-113">For the first 5 axes, the aliases COLUMNS, ROWS, PAGES, SECTIONS, and CHAPTERS can instead be used.</span></span>  
  
 <span data-ttu-id="69a58-114">In einer MDX-Abfrage können keine Abfrageachsen ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="69a58-114">An MDX query cannot skip query axes.</span></span> <span data-ttu-id="69a58-115">In einer Abfrage, die mindestens eine Abfrageachse enthält, dürfen also keine Achsen mit niedrigeren Nummern oder dazwischen liegenden Achsen fehlen.</span><span class="sxs-lookup"><span data-stu-id="69a58-115">That is, a query that includes one or more query axes must not exclude lower-numbered or intermediate axes.</span></span> <span data-ttu-id="69a58-116">Beispielsweise kann eine Abfrage keine ROWS-Achse ohne eine COLUMNS-Achse enthalten, und sie kann nicht die Achsen COLUMNS und PAGES ohne eine ROWS-Achse enthalten.</span><span class="sxs-lookup"><span data-stu-id="69a58-116">For example, a query cannot have a ROWS axis without a COLUMNS axis, or have COLUMNS and PAGES axes without a ROWS axis.</span></span>  
  
 <span data-ttu-id="69a58-117">Sie können jedoch eine SELECT-Klausel ohne Achsen (d. h. eine leere SELECT-Klausel) angeben.</span><span class="sxs-lookup"><span data-stu-id="69a58-117">However, you can specify a SELECT clause without any axes (that is, an empty SELECT clause).</span></span> <span data-ttu-id="69a58-118">In diesem Fall sind alle Dimensionen Slicerdimensionen, und die MDX-Abfrage wählt eine Zelle aus.</span><span class="sxs-lookup"><span data-stu-id="69a58-118">In this case, all dimensions are slicer dimensions, and the MDX query selects one cell.</span></span>  
  
 <span data-ttu-id="69a58-119">In der obigen Syntax für Abfrageachsen gibt jeder `Set_Expression` -Wert die Menge an, die den Inhalt der Abfrageachse definiert.</span><span class="sxs-lookup"><span data-stu-id="69a58-119">In the query axis syntax previously shown, each `Set_Expression` value specifies the set that defines the contents of the query axis.</span></span> <span data-ttu-id="69a58-120">Weitere Informationen zu Mengen finden Sie unter [Arbeiten mit Elementen, Tupeln und Mengen &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="69a58-120">For more information about sets, see [Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="69a58-121">Beispiele</span><span class="sxs-lookup"><span data-stu-id="69a58-121">Examples</span></span>  
 <span data-ttu-id="69a58-122">Die folgende einfache SELECT-Anweisung gibt das Measure Internet Sales Amount auf der COLUMNS-Achse zurück und verwendet die MDX MEMBERS-Funktion, um alle Elemente aus der Calendar-Hierarchie der Date-Dimension auf der ROWS-Achse zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="69a58-122">The following simple SELECT statement returns the measure Internet Sales Amount on the Columns axis, and uses the MDX MEMBERS function to return all the members from the Calendar hierarchy on the Date dimension on the Rows axis:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
{[Date].[Calendar].MEMBERS} ON ROWS  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="69a58-123">Die beiden folgenden Abfragen geben genau die gleichen Ergebnisse zurück. Dabei veranschaulichen sie die Verwendung von Achsennummern anstelle von Aliasen:</span><span class="sxs-lookup"><span data-stu-id="69a58-123">The two following queries return exactly the same results but demonstrate the use of axis numbers rather than aliases:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON 0,  
{[Date].[Calendar].MEMBERS} ON 1  
FROM [Adventure Works]  
  
SELECT {[Measures].[Internet Sales Amount]} ON AXIS(0),  
{[Date].[Calendar].MEMBERS} ON AXIS(1)  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="69a58-124">Um alle leeren Tupel von einer Achse zu entfernen, können Sie das NON EMPTY-Schlüsselwort vor der Mengendefinition verwenden.</span><span class="sxs-lookup"><span data-stu-id="69a58-124">The NON EMPTY keyword, used before the set definition, is an easy way to remove all empty tuples from an axis.</span></span> <span data-ttu-id="69a58-125">In den Beispielen, die bisher aufgetreten sind, gibt es beispielsweise keine Daten im Cube ab dem August 2004.</span><span class="sxs-lookup"><span data-stu-id="69a58-125">For example, in the examples we've seen so far there is no data in the cube from August 2004 onwards.</span></span> <span data-ttu-id="69a58-126">Um alle Zeilen, die in keiner Spalte Daten enthalten, aus dem Cellset zu entfernen, fügen Sie einfach NON EMPTY vor der Menge für die ROWS-Achsendefinition ein, wie nachfolgend gezeigt:</span><span class="sxs-lookup"><span data-stu-id="69a58-126">To remove all rows from the cellset that have no data in any column, simply add NON EMPTY before the set on the Rows axis definition as follows:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
NON EMPTY  
{[Date].[Calendar].MEMBERS} ON ROWS  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="69a58-127">NON EMPTY kann für alle Achsen in einer Abfrage verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="69a58-127">NON EMPTY can be used on all axes in a query.</span></span> <span data-ttu-id="69a58-128">Vergleichen Sie die Ergebnisse der folgenden beiden Abfragen. In der ersten wird NON EMPTY nicht verwendet, und in der zweiten wird NON EMPTY für beide Achsen verwendet:</span><span class="sxs-lookup"><span data-stu-id="69a58-128">Compare the results of the following two queries, the first of which does not use NON EMPTY and the second of which does on both axes:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]}   
* [Promotion].[Promotion].[Promotion].MEMBERS  
ON COLUMNS,  
{[Date].[Calendar].[Calendar Year].MEMBERS} ON ROWS  
FROM [Adventure Works]  
WHERE([Product].[Subcategory].&[19])  
  
SELECT NON EMPTY {[Measures].[Internet Sales Amount]}   
* [Promotion].[Promotion].[Promotion].MEMBERS  
ON COLUMNS,  
NON EMPTY  
{[Date].[Calendar].[Calendar Year].MEMBERS} ON ROWS  
FROM [Adventure Works]  
WHERE([Product].[Subcategory].&[19])  
  
```  
  
 <span data-ttu-id="69a58-129">Die HAVING-Klausel kann verwendet werden, um die Inhalte einer Achse anhand bestimmter Kriterien zu filtern. Sie ist weniger flexibel als andere Methoden, die die gleichen Ergebnisse erzielen, wie z. B. die FILTER-Funktion, sie ist jedoch einfacher zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="69a58-129">The HAVING clause can be used to filter the contents of an axis based on a specific criteria; it is less flexible than other methods that can achieve the same results, such as the FILTER function, but it is simpler to use.</span></span> <span data-ttu-id="69a58-130">Es folgt ein Beispiel, in dem nur die Daten zurückgegeben werden, bei denen Internet Sales Amount größer als 15.000 Dollar ist:</span><span class="sxs-lookup"><span data-stu-id="69a58-130">Here is an example that returns only those dates where Internet Sales Amount is greater than $15,000:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]}   
ON COLUMNS,  
NON EMPTY  
{[Date].[Calendar].[Date].MEMBERS}   
HAVING [Measures].[Internet Sales Amount]>15000  
ON ROWS  
FROM [Adventure Works]  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="69a58-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69a58-131">See Also</span></span>  
 [<span data-ttu-id="69a58-132">Angeben des Inhalts einer Slicerachse &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="69a58-132">Specifying the Contents of a Slicer Axis &#40;MDX&#41;</span></span>](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md)  
  
  
