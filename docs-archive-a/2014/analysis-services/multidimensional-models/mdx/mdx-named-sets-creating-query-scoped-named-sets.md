---
title: Erstellen benannter Mengen im Bereich einer Abfrage (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- query-scoped named sets [MDX]
- WITH keyword
ms.assetid: 78bc1e9a-1bc4-4a5a-ab0b-cf430c8fbfe1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6eccb4e20fca03079a04a0219b07f6411b80a433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698625"
---
# <a name="creating-query-scoped-named-sets-mdx"></a><span data-ttu-id="02fcf-102">Erstellen benannter Mengen im Bereich einer Abfrage (MDX)</span><span class="sxs-lookup"><span data-stu-id="02fcf-102">Creating Query-Scoped Named Sets (MDX)</span></span>
  <span data-ttu-id="02fcf-103">Wenn eine benannte Menge nur für eine einzelne MDX-Abfrage (Multidimensional Expressions) benötigt wird, können Sie die benannte Menge mit dem WITH-Schlüsselwort definieren.</span><span class="sxs-lookup"><span data-stu-id="02fcf-103">If a named set is only required for a single Multidimensional Expressions (MDX) query, you can define that named set by using the WITH keyword.</span></span> <span data-ttu-id="02fcf-104">Eine benannte Menge, die mit dem WITH-Schlüsselwort erstellt wird, ist nach der Ausführung der Abfrage nicht länger vorhanden.</span><span class="sxs-lookup"><span data-stu-id="02fcf-104">A named set that is created by using the WITH keyword no longer exists after the query has finished running.</span></span>  
  
 <span data-ttu-id="02fcf-105">Wie in diesem Thema erläutert wird, ist die Syntax des WITH-Schlüsselworts sehr flexibel und ermöglicht sogar die Verwendung von Funktionen, um die benannte Menge zu definieren.</span><span class="sxs-lookup"><span data-stu-id="02fcf-105">As discussed in this topic, the syntax of the WITH keyword is quite flexible, even accommodating the use of functions to define the named set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="02fcf-106">Weitere Informationen zu benannten Mengen finden Sie unter [Erstellen von benannten Mengen in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="02fcf-106">For more information about named sets, see [Building Named Sets in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span></span>  
  
## <a name="with-keyword-syntax"></a><span data-ttu-id="02fcf-107">WITH-Schlüsselwort (Syntax)</span><span class="sxs-lookup"><span data-stu-id="02fcf-107">WITH Keyword Syntax</span></span>  
 <span data-ttu-id="02fcf-108">Verwenden Sie die folgende Syntax, um einer SELECT-Anweisung von MDX das WITH-Schlüsselwort hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="02fcf-108">Use the following syntax to add the WITH keyword to a MDX SELECT statement:</span></span>  
  
```  
[ WITH <SELECT WITH clause> [ , <SELECT WITH clause> ... ] ]   
SELECT [ * | ( <SELECT query axis clause> [ , <SELECT query axis clause> ... ] ) ]  
FROM <SELECT subcube clause>   
[ <SELECT slicer axis clause> ]  
[ <SELECT cell property list clause> ]  
  
<SELECT WITH clause> ::=  
   ( SET Set_Identifier AS 'Set_Expression')  
  
```  
  
 <span data-ttu-id="02fcf-109">In der Syntax des WITH-Schlüsselworts enthält der `Set_Identifier` -Parameter den Alias für die benannte Menge.</span><span class="sxs-lookup"><span data-stu-id="02fcf-109">In the syntax for the WITH keyword, the `Set_Identifier` parameter contains the alias for the named set.</span></span> <span data-ttu-id="02fcf-110">Der `Set_Expression` -Parameter enthält den Mengenausdruck, auf den der Alias der benannten Menge verweist.</span><span class="sxs-lookup"><span data-stu-id="02fcf-110">The `Set_Expression` parameter contains the set expression to which the named set alias refers.</span></span>  
  
## <a name="with-keyword-example"></a><span data-ttu-id="02fcf-111">Beispiel für das WITH-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="02fcf-111">WITH Keyword Example</span></span>  
 <span data-ttu-id="02fcf-112">Mit der folgenden MDX-Abfrage werden die umgesetzten Stückzahlen (Unit Sales) der verschiedenen Chardonnay- und Chablis-Weine in `FoodMart 2000` (der Beispieldatenbank für Microsoft SQL Server 2000 Analysis Services) untersucht.</span><span class="sxs-lookup"><span data-stu-id="02fcf-112">The following MDX query examines the unit sales of the various Chardonnay and Chablis wines in `FoodMart 2000`, the sample database for Microsoft SQL Server 2000 Analysis Services.</span></span> <span data-ttu-id="02fcf-113">Diese Abfrage ist zwar relativ einfach bezüglich des Resultsets, für Wartungszwecke ist sie jedoch zu lang und schwer zu handhaben.</span><span class="sxs-lookup"><span data-stu-id="02fcf-113">This query, although fairly simple in terms of the result set, is lengthy and unwieldy when you have to maintenance such a query.</span></span>  
  
```  
SELECT  
   {[Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chardonnay],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chablis Wine],   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chablis Wine]} ON COLUMNS,  
   {Measures.[Unit Sales]} ON ROWS  
FROM Sales  
```  
  
 <span data-ttu-id="02fcf-114">Sie können die Wartung der obigen MDX-Abfrage vereinfachen, indem Sie mit dem WITH-Schlüsselwort eine benannte Menge für die Abfrage erstellen.</span><span class="sxs-lookup"><span data-stu-id="02fcf-114">To make the previous MDX query easier to maintain, you can create a named set for the query by using the WITH keyword.</span></span> <span data-ttu-id="02fcf-115">Der folgende Code zeigt, wie mit dem WITH-Schlüsselwort eine benannte Menge, `[ChardonnayChablis]`, erstellt wird und wie durch diese Menge die SELECT-Anweisung verkürzt und ihre Wartung vereinfacht wird.</span><span class="sxs-lookup"><span data-stu-id="02fcf-115">The following code shows how to use the WITH keyword to create a named set, `[ChardonnayChablis]`, and how the named set makes the SELECT statement shorter and easier to maintain.</span></span>  
  
```  
WITH SET [ChardonnayChablis] AS  
   {[Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chardonnay],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Good].[Good Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Pearl].[Pearl Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Portsmouth].[Portsmouth Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Top Measure].[Top Measure Chablis Wine],  
   [Product].[All Products].[Drink].[Alcoholic Beverages].[Beer and Wine].[Wine].[Walrus].[Walrus Chablis Wine]}  
  
SELECT  
   [ChardonnayChablis] ON COLUMNS,  
   {Measures.[Unit Sales]} ON ROWS  
FROM Sales  
```  
  
### <a name="using-functions-together-with-the-with-keyword"></a><span data-ttu-id="02fcf-116">Verwenden von Funktionen zusammen mit dem WITH-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="02fcf-116">Using Functions Together with the WITH Keyword</span></span>  
 <span data-ttu-id="02fcf-117">Sie können zwar jedes Element einer benannten Menge explizit definieren, dies kann jedoch zu einer sehr langen Anweisung führen.</span><span class="sxs-lookup"><span data-stu-id="02fcf-117">Although you can explicitly define each member of a named set, this approach can produce a lengthy statement.</span></span> <span data-ttu-id="02fcf-118">Um die Erstellung und Wartung einer benannten Menge zu vereinfachen, können Sie die Elemente mithilfe von MDX-Funktionen definieren.</span><span class="sxs-lookup"><span data-stu-id="02fcf-118">To make the creation and maintenance of a named set easier, you can use MDX functions to define the members.</span></span>  
  
 <span data-ttu-id="02fcf-119">Beispielsweise verwendet die folgende MDX-Abfrage die Funktionen [Filter](/sql/mdx/filter-mdx), [CurrentMember](/sql/mdx/current-mdx)und [Name](/sql/mdx/members-string-mdx) sowie die VBA-Funktion InStr, um die benannte Menge `[ChardonnayChablis]` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="02fcf-119">For example, the following MDX query example uses the [Filter](/sql/mdx/filter-mdx), [CurrentMember](/sql/mdx/current-mdx), and [Name](/sql/mdx/members-string-mdx) MDX functions and the InStr VBA function to create the `[ChardonnayChablis]` named set.</span></span> <span data-ttu-id="02fcf-120">Diese Version der benannten Menge `[ChardonnayChablis]` ist identisch mit der explizit definierten Version weiter oben in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="02fcf-120">This version of the `[ChardonnayChablis]` named set is the same as the explicitly defined version shown previously in this topic.</span></span>  
  
```  
WITH SET [ChardonnayChablis] AS  
   'Filter([Product].Members, (InStr(1, [Product].CurrentMember.Name, "chardonnay") <> 0) OR (InStr(1, [Product].CurrentMember.Name, "chablis") <> 0))'  
  
SELECT  
   [ChardonnayChablis] ON COLUMNS,  
   {Measures.[Unit Sales]} ON ROWS  
FROM Sales  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="02fcf-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02fcf-121">See Also</span></span>  
 <span data-ttu-id="02fcf-122">[SELECT-Anweisung &#40;MDX-&#41;](/sql/mdx/mdx-data-manipulation-select) </span><span class="sxs-lookup"><span data-stu-id="02fcf-122">[SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span></span>  
 [<span data-ttu-id="02fcf-123">Erstellen benannter Mengen im Bereich einer Sitzung &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="02fcf-123">Creating Session-Scoped Named Sets &#40;MDX&#41;</span></span>](mdx-named-sets-creating-session-scoped-named-sets.md)  
  
  
