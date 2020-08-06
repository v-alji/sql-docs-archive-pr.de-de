---
title: Arbeiten mit Membern, Tupeln und Mengen (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], tuples
- member keys [MDX]
- MDX [Analysis Services], sets
- calculated members [MDX]
- members [MDX]
- Multidimensional Expressions [Analysis Services], members
- named sets [MDX]
- Multidimensional Expressions [Analysis Services], tuples
- member functions [MDX]
- sets [MDX]
- MDX [Analysis Services], members
- member names [MDX]
- Multidimensional Expressions [Analysis Services], sets
- tuple functions
- tuples
- set functions [MDX]
ms.assetid: b6ec2439-caef-46d3-9fd7-5f4526cee334
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5ce3bf2d5ad7df2b1cd74897b3b49c7cef97e8ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608884"
---
# <a name="working-with-members-tuples-and-sets-mdx"></a><span data-ttu-id="8a7cc-102">Verwenden von Elementen, Tupeln und Mengen (MDX)</span><span class="sxs-lookup"><span data-stu-id="8a7cc-102">Working with Members, Tuples, and Sets (MDX)</span></span>
  <span data-ttu-id="8a7cc-103">MDX stellt eine Reihe von Funktionen bereit, die ein oder mehrere Elemente, Tupel oder Mengen zurückgeben bzw. diese als Argumente nehmen.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-103">MDX provides numerous functions that return one or more members, tuples, or sets; or that act upon a member, tuple, or set.</span></span>  
  
## <a name="member-functions"></a><span data-ttu-id="8a7cc-104">Elementfunktionen</span><span class="sxs-lookup"><span data-stu-id="8a7cc-104">Member Functions</span></span>  
 <span data-ttu-id="8a7cc-105">MDX stellt viele Funktionen bereit, mit denen Elemente aus anderen MDX-Entitäten (z. B. Dimensionen, Ebenen, Mengen oder Tupeln) abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-105">MDX provides several functions for retrieving members from other MDX entities, such as from dimensions, levels, sets, or tuples.</span></span> <span data-ttu-id="8a7cc-106">Die [FirstChild](/sql/mdx/firstchild-mdx) -Funktion ist z. B. eine Funktion, die ein Element als Argument nimmt und ein Element zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-106">For example, the [FirstChild](/sql/mdx/firstchild-mdx) function is a function that acts upon a member and returns a member.</span></span>  
  
 <span data-ttu-id="8a7cc-107">Zum Abrufen des ersten untergeordneten Elements der Time-Dimension können Sie das Element explizit angeben (siehe folgendes Beispiel):</span><span class="sxs-lookup"><span data-stu-id="8a7cc-107">To obtain the first child member of the Time dimension, you can explicitly state the member, as in the following example.</span></span>  
  
```  
SELECT [Date].[Calendar Year].[CY 2001] on 0  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="8a7cc-108">Sie können jedoch auch die `FirstChild`-Funktion verwenden, um dasselbe Element zurückzugeben (siehe nächstes Beispiel):</span><span class="sxs-lookup"><span data-stu-id="8a7cc-108">You can also use the `FirstChild` function to return the same member, as in the following example.</span></span>  
  
```  
SELECT [Date].[Calendar Year].FirstChild on 0  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="8a7cc-109">Weitere Informationen zu MDX-Elementfunktionen finden Sie unter [MDX-Funktionsreferenz &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="8a7cc-109">For more information about MDX member functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="tuple-functions"></a><span data-ttu-id="8a7cc-110">Tupelfunktionen</span><span class="sxs-lookup"><span data-stu-id="8a7cc-110">Tuple Functions</span></span>  
 <span data-ttu-id="8a7cc-111">Es gibt mehrere MDX-Funktionen, die Tupel zurückgeben. Diese Funktionen können überall dort verwendet werden, wo ein Tupel zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-111">MDX provides several functions that return tuples, and they can be used anywhere that a tuple is accepted.</span></span> <span data-ttu-id="8a7cc-112">Die [Item-Funktion &#40;Tupel, MDX&#41;](/sql/mdx/item-tuple-mdx) kann z.B. verwendet werden, um das erste Tupel aus einer Menge zu extrahieren. Diese Funktion kann sehr nützlich sein, wenn die Menge aus einem einzelnen Tupel besteht und Sie dieses Tupel an eine Funktion übergeben möchten, die ein Tupel als Argument erfordert.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-112">For example, the [Item &#40;Tuple&#41; &#40;MDX&#41;](/sql/mdx/item-tuple-mdx) function can be used to extract the first tuple from set, which is very useful when you know that a set is composed of a single tuple and you want to supply that tuple to a function that requires a tuple.</span></span>  
  
 <span data-ttu-id="8a7cc-113">Im folgenden Beispiel wird das erste Tupel aus einer Menge von Tupeln auf der Spaltenachse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-113">The following example returns the first tuple from within the set of tuples on the column axis.</span></span>  
  
```  
SELECT {  
   ([Measures].[Reseller Sales Amount]  
      ,[Date].[Calendar Year].[CY 2003]  
   )  
, ([Measures].[Reseller Sales Amount]  
      ,[Date].[Calendar Year].[CY 2004]  
   )  
}.Item(0)  
ON COLUMNS   
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="8a7cc-114">Weitere Informationen zu Tupelfunktionen finden Sie unter [MDX-Funktionsreferenz &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="8a7cc-114">For more information about tuple functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="set-functions"></a><span data-ttu-id="8a7cc-115">Mengenfunktionen</span><span class="sxs-lookup"><span data-stu-id="8a7cc-115">Set Functions</span></span>  
 <span data-ttu-id="8a7cc-116">Es gibt mehrere MDX-Funktionen, die Mengen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-116">MDX provides several functions that return sets.</span></span> <span data-ttu-id="8a7cc-117">Das explizite Eingeben von in geschweiften Klammern eingeschlossenen Tupeln ist nicht die einzige Möglichkeit, eine Menge abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-117">Explicitly typing tuples and enclosing them in braces is not the only way to retrieve a set.</span></span> <span data-ttu-id="8a7cc-118">Weitere Informationen über die Elementfunktionen, die Mengen zurückgeben, finden Sie unter [Schlüsselkonzepte in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="8a7cc-118">For more information about the members function to return a set, see [Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md).</span></span> <span data-ttu-id="8a7cc-119">Es stehen viele weitere Mengenfunktionen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-119">There are many additional set functions.</span></span>  
  
 <span data-ttu-id="8a7cc-120">Mithilfe des Doppelpunkt-Operators können Sie zum Erstellen einer Menge die natürliche Reihenfolge der Elemente verwenden.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-120">The colon operator lets you use the natural order of members to create a set.</span></span> <span data-ttu-id="8a7cc-121">Beispielsweise enthält die im folgenden Beispiel gezeigte Menge Tupel für das erste bis vierte Quartal des Kalenderjahres 2002:</span><span class="sxs-lookup"><span data-stu-id="8a7cc-121">For example, the set shown in the following example contains tuples for the 1st through the 4th quarter of calendar year 2002.</span></span>  
  
```  
SELECT   
   {[Calendar Quarter].[Q1 CY 2002]:[Calendar Quarter].[Q4 CY 2002]}   
ON 0  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="8a7cc-122">Dieselbe Menge von Elementen können Sie auch, anstatt den Doppelpunkt-Operator zu verwenden, wie im folgenden Beispiel durch Angeben der Tupel erstellen:</span><span class="sxs-lookup"><span data-stu-id="8a7cc-122">If you do not use the colon operator to create the set, you can create the same set of members by specifying the tuples in the following example.</span></span>  
  
```  
SELECT {  
   [Calendar Quarter].[Q1 CY 2002],   
   [Calendar Quarter].[Q2 CY 2002],   
   [Calendar Quarter].[Q3 CY 2002],   
   [Calendar Quarter].[Q4 CY 2002]  
   } ON 0  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="8a7cc-123">Der Doppelpunkt-Operator ist eine einschließende Funktion.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-123">The colon operator is an inclusive function.</span></span> <span data-ttu-id="8a7cc-124">Die Elemente auf beiden Seiten des Doppelpunkt-Operators werden in die Ergebnismenge eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-124">The members on both sides of the colon operator are included in the resulting set.</span></span>  
  
 <span data-ttu-id="8a7cc-125">Weitere Informationen zu Mengenfunktionen finden Sie unter [MDX-Funktionsreferenz &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="8a7cc-125">For more information about set functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="array-functions"></a><span data-ttu-id="8a7cc-126">Arrayfunktionen</span><span class="sxs-lookup"><span data-stu-id="8a7cc-126">Array Functions</span></span>  
 <span data-ttu-id="8a7cc-127">Eine Arrayfunktion nimmt eine Menge als Argument und gibt ein Array zurück.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-127">An array function acts upon a set and returns an array.</span></span> <span data-ttu-id="8a7cc-128">Weitere Informationen zu Arrayfunktionen finden Sie unter [MDX-Funktionsreferenz &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="8a7cc-128">For more information about array functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="hierarchy-functions"></a><span data-ttu-id="8a7cc-129">Hierarchiefunktionen</span><span class="sxs-lookup"><span data-stu-id="8a7cc-129">Hierarchy Functions</span></span>  
 <span data-ttu-id="8a7cc-130">Ein Hierarchiefunktion gibt eine Hierarchie zurück und nimmt ein Element, eine Ebene, eine Hierarchie oder eine Zeichenfolge als Argument.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-130">A hierarchy function returns a hierarchy by acting upon a member, level, hierarchy, or string.</span></span> <span data-ttu-id="8a7cc-131">Weitere Informationen zu Hierarchiefunktionen finden Sie unter [MDX-Funktionsreferenz &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="8a7cc-131">For more information about hierarchy functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="level-functions"></a><span data-ttu-id="8a7cc-132">Ebenenfunktionen</span><span class="sxs-lookup"><span data-stu-id="8a7cc-132">Level Functions</span></span>  
 <span data-ttu-id="8a7cc-133">Ein Ebenenfunktion gibt eine Ebene zurück und nimmt ein Element, eine Ebene oder eine Zeichenfolge als Argument.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-133">A level function returns a level by acting upon a member, level, or string.</span></span> <span data-ttu-id="8a7cc-134">Weitere Informationen zu Ebenenfunktionen finden Sie unter [MDX-Funktionsreferenz &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="8a7cc-134">For more information about level functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="logical-functions"></a><span data-ttu-id="8a7cc-135">Logische Funktionen</span><span class="sxs-lookup"><span data-stu-id="8a7cc-135">Logical Functions</span></span>  
 <span data-ttu-id="8a7cc-136">Eine logische Funktion nimmt einen MDX-Ausdruck als Argument und gibt Informationen zu Tupeln, Elementen oder Mengen in diesem Ausdruck zurück.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-136">A logical function acts upon a MDX expression to return information about the tuples, members, or sets in the expression.</span></span> <span data-ttu-id="8a7cc-137">Die [IsEmpty-Funktion &#40;MDX&#41;](/sql/mdx/isempty-mdx) wertet z.B. aus, ob ein Ausdruck einen leeren Zellenwert zurückgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-137">For example, the [IsEmpty &#40;MDX&#41;](/sql/mdx/isempty-mdx) function evaluates whether an expression has returned an empty cell value.</span></span> <span data-ttu-id="8a7cc-138">Weitere Informationen zu logischen Funktionen finden Sie unter [MDX-Funktionsreferenz &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="8a7cc-138">For more information about logical functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="numeric-functions"></a><span data-ttu-id="8a7cc-139">Numerische Funktionen</span><span class="sxs-lookup"><span data-stu-id="8a7cc-139">Numeric Functions</span></span>  
 <span data-ttu-id="8a7cc-140">Eine numerische Funktion nimmt einen MDX-Ausdruck als Argument und gibt einen Skalarwert zurück.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-140">A numeric function acts upon a MDX expression to return a scalar value.</span></span> <span data-ttu-id="8a7cc-141">Die [Aggregate-Funktion &#40;MDX&#41;](/sql/mdx/aggregate-mdx) gibt z.B. einen Skalarwert zurück, der durch Aggregieren von Measures über die Tupel in einer angegebenen Menge berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-141">For example, the [Aggregate &#40;MDX&#41;](/sql/mdx/aggregate-mdx) function returns a scalar value calculated by aggregating measures over the tuples in a specified set.</span></span> <span data-ttu-id="8a7cc-142">Weitere Informationen zu numerischen Funktionen finden Sie unter [MDX-Funktionsreferenz &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="8a7cc-142">For more information about numeric functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="string-functions"></a><span data-ttu-id="8a7cc-143">Zeichenfolgenfunktionen</span><span class="sxs-lookup"><span data-stu-id="8a7cc-143">String Functions</span></span>  
 <span data-ttu-id="8a7cc-144">Eine Zeichenfolgenfunktion nimmt einen MDX-Ausdruck als Argument und gibt eine Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-144">A string function acts upon a MDX expression to return a string.</span></span> <span data-ttu-id="8a7cc-145">Die [UniqueName-Funktion &#40;MDX&#41;](/sql/mdx/uniquename-mdx) z.B. gibt einen Zeichenfolgenwert zurück, der den eindeutigen Namen einer Dimension, Hierarchie, Ebene oder eines Elements enthält.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-145">For example, the [UniqueName &#40;MDX&#41;](/sql/mdx/uniquename-mdx) function returns a string value containing the unique name of a dimension, hierarchy, level, or member.</span></span> <span data-ttu-id="8a7cc-146">Weitere Informationen zu Zeichenfolgenfunktionen finden Sie unter [MDX-Funktionsreferenz &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="8a7cc-146">For more information about string functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a7cc-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8a7cc-147">See Also</span></span>  
 <span data-ttu-id="8a7cc-148">[Wichtige Konzepte in MDX-&#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="8a7cc-148">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="8a7cc-149">[Grundlagen der MDX-Abfrage &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="8a7cc-149">[MDX Query Fundamentals &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span></span>  
 [<span data-ttu-id="8a7cc-150">MDX-Funktionsreferenz &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="8a7cc-150">MDX Function Reference &#40;MDX&#41;</span></span>](/sql/mdx/mdx-function-reference-mdx)  
  
  
