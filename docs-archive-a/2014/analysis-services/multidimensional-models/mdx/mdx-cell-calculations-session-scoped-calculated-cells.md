---
title: Erstellen berechneter Zellen im Bereich einer Sitzung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- session-scoped calculated members [MDX]
ms.assetid: f2d14a89-6286-4e74-9afb-091076f93f21
author: minewiskan
ms.author: owend
ms.openlocfilehash: 199de07778a153cd1bc40b5033d364e5e0055bd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616739"
---
# <a name="creating-session-scoped-calculated-cells"></a><span data-ttu-id="e6980-102">Erstellen berechneter Zellen im Bereich einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="e6980-102">Creating Session-Scoped Calculated Cells</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="e6980-103">Diese Syntax wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="e6980-103">This syntax has been deprecated.</span></span> <span data-ttu-id="e6980-104">Sie sollten stattdessen MDX-Zuweisungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e6980-104">You should use MDX assignments should instead.</span></span> <span data-ttu-id="e6980-105">Weitere Informationen zu Zuweisungen finden Sie unter [Grundlegendes MDX-Skript &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="e6980-105">For more information on assignments, see [The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span></span>  
  
 <span data-ttu-id="e6980-106">Wenn Sie berechnete Zellen erstellen möchten, die für alle Abfragen in derselben Sitzung verfügbar sind, verwenden Sie entweder die [CREATE CELL CALCULATION](/sql/mdx/mdx-data-definition-create-cell-calculation) -Anweisung oder die [ALTER CUBE](/sql/mdx/mdx-data-definition-alter-cube) -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e6980-106">To create calculated cells that are available to all queries in the same session, you can use either the [CREATE CELL CALCULATION](/sql/mdx/mdx-data-definition-create-cell-calculation) statement or the [ALTER CUBE](/sql/mdx/mdx-data-definition-alter-cube) statement.</span></span> <span data-ttu-id="e6980-107">Beide Anweisungen führen zum selben Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="e6980-107">Both statements have the same result.</span></span>  
  
## <a name="create-cell-calculation-syntax"></a><span data-ttu-id="e6980-108">Syntax von CREATE CELL CALCULATION</span><span class="sxs-lookup"><span data-stu-id="e6980-108">CREATE CELL CALCULATION Syntax</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e6980-109">Diese Syntax wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="e6980-109">This syntax has been deprecated.</span></span> <span data-ttu-id="e6980-110">Sie sollten stattdessen MDX-Zuweisungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e6980-110">You should use MDX assignments should instead.</span></span> <span data-ttu-id="e6980-111">Weitere Informationen zu Zuweisungen finden Sie unter [Grundlegendes MDX-Skript &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="e6980-111">For more information on assignments, see [The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span></span>  
  
 <span data-ttu-id="e6980-112">Verwenden Sie folgende Syntax, wenn Sie mit der CREATE CELL CALCULATION-Anweisung eine berechnete Zelle im Bereich einer Sitzung definieren möchten:</span><span class="sxs-lookup"><span data-stu-id="e6980-112">Use the following syntax to use the CREATE CELL CALCULATION statement to define a session-scoped calculated cell:</span></span>  
  
```  
CREATE CELL CALCULATION Cube_Expression.<CREATE CELL CALCULATION body clause>  
  
<CREATE CELL CALCULATION body clause> ::=CellCalc_Identifier FOR String_Expression AS 'MDX_Expression'   
   [ <CREATE CELL CALCULATION property clause> [ , <CREATE CELL CALCULATION property clause> ... ] ]  
  
<CREATE CELL CALCULATION property clause> ::=  
   ( CONDITION = 'Logical_Expression' ) |   
   ( DISABLED = { TRUE | FALSE } ) |   
   ( DESCRIPTION =String_Expression ) |   
   ( CALCULATION_PASS_NUMBER = Integer_Expression ) |   
   ( CALCULATION_PASS_DEPTH = Integer_Expression ) |   
   ( SOLVE_ORDER = Integer_Expression ) |   
   ( FORMAT_STRING = String_Expression ) |   
   ( CellProperty_Identifier = Scalar_Expression )  
```  
  
## <a name="alter-cube-syntax"></a><span data-ttu-id="e6980-113">Syntax von ALTER CUBE</span><span class="sxs-lookup"><span data-stu-id="e6980-113">ALTER CUBE Syntax</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e6980-114">Diese Syntax wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="e6980-114">This syntax has been deprecated.</span></span> <span data-ttu-id="e6980-115">Sie sollten stattdessen MDX-Zuweisungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e6980-115">You should use MDX assignments should instead.</span></span> <span data-ttu-id="e6980-116">Weitere Informationen zu Zuweisungen finden Sie unter [Grundlegendes MDX-Skript &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="e6980-116">For more information on assignments, see [The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span></span>  
  
 <span data-ttu-id="e6980-117">Verwenden Sie folgende Syntax, wenn Sie mit der ALTER CUBE -Anweisung eine berechnete Zelle im Bereich einer Sitzung definieren möchten:</span><span class="sxs-lookup"><span data-stu-id="e6980-117">Use the following syntax to use the ALTER CUBE statement to define a session-scoped calculated cell:</span></span>  
  
```  
ALTER CUBE Cube_Identifier CREATE CELL CALCULATION  
FOR String_Expression AS 'MDX_Expression'   
   [ <CREATE CELL CALCULATION property clause> [ , <CREATE CELL CALCULATION property clause> ... ] ]  
  
<CREATE CELL CALCULATION property clause> ::=  
   ( CONDITION = 'Logical_Expression' ) |   
   ( DISABLED = { TRUE | FALSE } ) |   
   ( DESCRIPTION =String_Expression ) |   
   ( CALCULATION_PASS_NUMBER = Integer_Expression ) |   
   ( CALCULATION_PASS_DEPTH = Integer_Expression ) |   
   ( SOLVE_ORDER = Integer_Expression ) |   
   ( FORMAT_STRING = String_Expression ) |   
   ( CellProperty_Identifier = Scalar_Expression )  
```  
  
 <span data-ttu-id="e6980-118">Der `String_Expression` -Wert enthält eine Liste der orthogonalen, eindimensionalen MDX-Mengenausdrücke, von denen jeder aufgelöst zu einer der Mengenkategorien gehören muss, die in der folgenden Tabelle aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="e6980-118">The `String_Expression` value contains a list of orthogonal, single-dimensional MDX set expressions, each of which must resolve to one of the categories of sets that are listed in the following table.</span></span>  
  
|<span data-ttu-id="e6980-119">Category</span><span class="sxs-lookup"><span data-stu-id="e6980-119">Category</span></span>|<span data-ttu-id="e6980-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e6980-120">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="e6980-121">Leere Menge</span><span class="sxs-lookup"><span data-stu-id="e6980-121">Empty set</span></span>|<span data-ttu-id="e6980-122">Ein MDX-Mengenausdruck, der zu einer leeren Menge aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e6980-122">An MDX set expression that resolves into an empty set.</span></span> <span data-ttu-id="e6980-123">In diesem Fall ist der Gültigkeitsbereich der berechneten Zelle gleich dem gesamten Cube.</span><span class="sxs-lookup"><span data-stu-id="e6980-123">In this case, the scope of the calculated cell is the whole cube.</span></span>|  
|<span data-ttu-id="e6980-124">Menge mit einem einzelnen Element</span><span class="sxs-lookup"><span data-stu-id="e6980-124">Single member set</span></span>|<span data-ttu-id="e6980-125">Ein MDX-Mengenausdruck, der zu einem einzelnen Element aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e6980-125">An MDX set expression that resolves into a single member.</span></span>|  
|<span data-ttu-id="e6980-126">Menge von Ebenenelementen</span><span class="sxs-lookup"><span data-stu-id="e6980-126">Set of level members</span></span>|<span data-ttu-id="e6980-127">Ein MDX-Mengenausdruck, der zu den Elementen einer einzelnen Ebene aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e6980-127">An MDX set expression that resolves into the members of a single level.</span></span> <span data-ttu-id="e6980-128">Ein Beispiel hierfür ist die *Level_Expression*.`Members`</span><span class="sxs-lookup"><span data-stu-id="e6980-128">An example of this is the *Level_Expression*.`Members`</span></span> <span data-ttu-id="e6980-129">MDX-Funktion.</span><span class="sxs-lookup"><span data-stu-id="e6980-129">MDX function.</span></span> <span data-ttu-id="e6980-130">Um berechnete Elemente einzuschließen, verwenden Sie die *Level_Expression*.`AllMembers`</span><span class="sxs-lookup"><span data-stu-id="e6980-130">To include calculated members, use the *Level_Expression*.`AllMembers`</span></span> <span data-ttu-id="e6980-131">MDX-Funktion.</span><span class="sxs-lookup"><span data-stu-id="e6980-131">MDX function.</span></span><br /><br /> <span data-ttu-id="e6980-132">Weitere Informationen finden Sie unter [AllMembers &#40;MDX&#41;](/sql/mdx/allmembers-mdx).</span><span class="sxs-lookup"><span data-stu-id="e6980-132">For more information, see [AllMembers &#40;MDX&#41;](/sql/mdx/allmembers-mdx).</span></span>|  
|<span data-ttu-id="e6980-133">Menge nachfolgender Werte</span><span class="sxs-lookup"><span data-stu-id="e6980-133">Set of descendants</span></span>|<span data-ttu-id="e6980-134">Ein MDX-Mengenausdruck, der zu den nachfolgenden Werten eines angegebenen Elements aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e6980-134">An MDX set expression that resolves into the descendants of a specified member.</span></span> <span data-ttu-id="e6980-135">Ein Beispiel hierfür ist die `Descendants` MDX-Funktion (*Member_Expression*, *Level_Expression* *Desc_Flag*).</span><span class="sxs-lookup"><span data-stu-id="e6980-135">An example of this is the `Descendants`(*Member_Expression*, *Level_Expression*, *Desc_Flag*) MDX function.</span></span><br /><br /> <span data-ttu-id="e6980-136">Weitere Informationen finden Sie unter [Descendants &#40;MDX&#41;](/sql/mdx/descendants-mdx).</span><span class="sxs-lookup"><span data-stu-id="e6980-136">For more information, see [Descendants &#40;MDX&#41;](/sql/mdx/descendants-mdx).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e6980-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e6980-137">See Also</span></span>  
 [<span data-ttu-id="e6980-138">Erstellen von Zellenberechnungen in MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="e6980-138">Building Cell Calculations in MDX &#40;MDX&#41;</span></span>](../../multidimensional-models-olap-logical-cube-objects/calculations.md)  
  
  
