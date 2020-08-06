---
title: Grundlegendes zu Durchlauf-und Lösungs Reihenfolge (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- evaluation order [MDX]
- calculation order [MDX]
- SOLVE_ORDER property
- queries [MDX], solve orders
- solve orders [MDX]
- pass orders [MDX]
- expressions [MDX], solve orders
ms.assetid: 7ed7d4ee-4644-4c5d-99a4-c4b429d0203c
author: minewiskan
ms.author: owend
ms.openlocfilehash: d92ccd9d1eeb05272a95c6f429f8c756bcb0022e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616737"
---
# <a name="understanding-pass-order-and-solve-order-mdx"></a><span data-ttu-id="3ed06-102">Grundlegendes zu Durchlauf- und Lösungsreihenfolge (MDX)</span><span class="sxs-lookup"><span data-stu-id="3ed06-102">Understanding Pass Order and Solve Order (MDX)</span></span>
  <span data-ttu-id="3ed06-103">Wird ein Cube als Ergebnis eines MDX-Skripts berechnet, durchläuft er, abhängig von der Verwendung verschiedener Berechnungsfunktionen, möglicherweise viele Berechnungsphasen.</span><span class="sxs-lookup"><span data-stu-id="3ed06-103">When a cube is calculated as the result of an MDX script, it can go through many stages of computation depending on the use of various calculation-related features.</span></span> <span data-ttu-id="3ed06-104">Jede Phase bezeichnet man als Berechnungsdurchlauf.</span><span class="sxs-lookup"><span data-stu-id="3ed06-104">Each of these stages is referred to as a calculation pass.</span></span>  
  
 <span data-ttu-id="3ed06-105">Auf einen Berechnungsdurchlauf kann durch eine Ordnungsposition verwiesen werden, die Berechnungsdurchlaufnummer genannt wird.</span><span class="sxs-lookup"><span data-stu-id="3ed06-105">A calculation pass can be referred to by an ordinal position, called the calculation pass number.</span></span> <span data-ttu-id="3ed06-106">Die Anzahl an Berechnungsdurchläufen, die für eine vollständige Berechnung aller Zellen eines Cubes erforderlich sind, wird als Berechnungsdurchlauftiefe des Cubes bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3ed06-106">The count of calculation passes that are required to fully compute all the cells of a cube is referred to as the calculation pass depth of the cube.</span></span>  
  
 <span data-ttu-id="3ed06-107">Faktentabelle und Rückschreibedaten wirken sich nur auf Durchlauf 0 aus.</span><span class="sxs-lookup"><span data-stu-id="3ed06-107">Fact table and writeback data only impact pass 0.</span></span> <span data-ttu-id="3ed06-108">Skripts füllen Daten nach Durchlauf 0 auf. Durch jede Zuweisung und Berechnungsanweisung in einem Skript wird ein neuer Durchlauf erstellt.</span><span class="sxs-lookup"><span data-stu-id="3ed06-108">Scripts populate data after pass 0; each assignment and calculate statement in a script creates a new pass.</span></span> <span data-ttu-id="3ed06-109">Außerhalb des MDX-Skripts beziehen sich Verweise auf den absoluten Durchlauf 0 auf den letzten Durchlauf, der durch das Skript für den Cube erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="3ed06-109">Outside the MDX script, references to absolute pass 0 refer to the last pass created by the script for the cube.</span></span>  
  
 <span data-ttu-id="3ed06-110">Berechnete Elemente werden in allen Durchläufen erstellt, aber der Ausdruck wird auf den aktuellen Durchlauf angewendet.</span><span class="sxs-lookup"><span data-stu-id="3ed06-110">Calculated members are created at all passes, but the expression is applied at the current pass.</span></span> <span data-ttu-id="3ed06-111">Vorherige Durchläufe enthalten das berechnete Measure, allerdings mit einem NULL-Wert.</span><span class="sxs-lookup"><span data-stu-id="3ed06-111">Prior passes contain the calculated measure, but with a null value.</span></span>  
  
## <a name="solve-order"></a><span data-ttu-id="3ed06-112">Lösungsreihenfolge</span><span class="sxs-lookup"><span data-stu-id="3ed06-112">Solve Order</span></span>  
 <span data-ttu-id="3ed06-113">Die Lösungsreihenfolge bestimmt die Priorität der Berechnung bei konkurrierenden Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="3ed06-113">Solve order determines the priority of calculation in the event of competing expressions.</span></span> <span data-ttu-id="3ed06-114">Innerhalb eines einzelnen Durchlaufes bestimmt die Lösungsreihenfolge zwei Dinge:</span><span class="sxs-lookup"><span data-stu-id="3ed06-114">Within a single pass, solve order determines two things:</span></span>  
  
-   <span data-ttu-id="3ed06-115">Die Reihenfolge, in der [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] Dimensionen, Elemente, berechnete Elemente, benutzerdefinierte Rollups und berechnete Zellen auswertet.</span><span class="sxs-lookup"><span data-stu-id="3ed06-115">The order in which [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] evaluates dimensions, members, calculated members, custom rollups, and calculated cells.</span></span>  
  
-   <span data-ttu-id="3ed06-116">Die Reihenfolge, in der [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] benutzerdefinierte Elemente, berechnete Elemente, benutzerdefinierte Rollups und berechnete Zellen berechnet.</span><span class="sxs-lookup"><span data-stu-id="3ed06-116">The order in which [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calculates custom members, calculated members, custom rollup, and calculated cells.</span></span>  
  
 <span data-ttu-id="3ed06-117">Das Element mit der höchsten Lösungsreihenfolge hat Vorrang.</span><span class="sxs-lookup"><span data-stu-id="3ed06-117">The member with the highest solve order takes precedence.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3ed06-118">Dies gilt jedoch nicht für die Aggregatfunktion.</span><span class="sxs-lookup"><span data-stu-id="3ed06-118">The exception to this precedence is the Aggregate function.</span></span> <span data-ttu-id="3ed06-119">Mit der Aggregatfunktion berechnete Elemente haben eine niedrigere Lösungsreihenfolge als alle berechneten Measures, die eine Schnittmenge bilden.</span><span class="sxs-lookup"><span data-stu-id="3ed06-119">Calculated members with the Aggregate function have a lower solve order than any intersecting calculated measure.</span></span>  
  
## <a name="solve-order-values-and-precedence"></a><span data-ttu-id="3ed06-120">Werte der Lösungsreihenfolge und Rangfolge</span><span class="sxs-lookup"><span data-stu-id="3ed06-120">Solve Order Values and Precedence</span></span>  
 <span data-ttu-id="3ed06-121">Werte der Lösungsreihenfolge können im Bereich von -8.181 bis 65.535 liegen.</span><span class="sxs-lookup"><span data-stu-id="3ed06-121">Solve order values can range from -8181 to 65535.</span></span> <span data-ttu-id="3ed06-122">In diesem Bereich entsprechen einige Werte der Lösungsreihenfolge bestimmten Berechnungsarten, wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3ed06-122">In this range, some solve order values correspond to specific kinds of calculations, as shown in the following table.</span></span>  
  
|<span data-ttu-id="3ed06-123">Berechnung</span><span class="sxs-lookup"><span data-stu-id="3ed06-123">Calculation</span></span>|<span data-ttu-id="3ed06-124">Lösungsreihenfolge</span><span class="sxs-lookup"><span data-stu-id="3ed06-124">Solve Order</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="3ed06-125">Benutzerdefinierte Elementformeln</span><span class="sxs-lookup"><span data-stu-id="3ed06-125">Custom member formulas</span></span>|<span data-ttu-id="3ed06-126">-5119</span><span class="sxs-lookup"><span data-stu-id="3ed06-126">-5119</span></span>|  
|<span data-ttu-id="3ed06-127">Unäre Operatoren</span><span class="sxs-lookup"><span data-stu-id="3ed06-127">Unary operators</span></span>|<span data-ttu-id="3ed06-128">-5119</span><span class="sxs-lookup"><span data-stu-id="3ed06-128">-5119</span></span>|  
|<span data-ttu-id="3ed06-129">Berechnung sichtbarer Gesamtwerte</span><span class="sxs-lookup"><span data-stu-id="3ed06-129">Visual totals calculation</span></span>|<span data-ttu-id="3ed06-130">-4096</span><span class="sxs-lookup"><span data-stu-id="3ed06-130">-4096</span></span>|  
|<span data-ttu-id="3ed06-131">Alle anderen Berechnungen (wenn nicht anders angegeben)</span><span class="sxs-lookup"><span data-stu-id="3ed06-131">All other calculations (if not otherwise specified)</span></span>|<span data-ttu-id="3ed06-132">0</span><span class="sxs-lookup"><span data-stu-id="3ed06-132">0</span></span>|  
  
 <span data-ttu-id="3ed06-133">Beim Festlegen von Werten der Lösungsreihenfolge sollten Sie unbedingt nur positive ganze Zahlen verwenden.</span><span class="sxs-lookup"><span data-stu-id="3ed06-133">It is highly recommended that you use only positive integers when setting solve order values.</span></span> <span data-ttu-id="3ed06-134">Wenn Sie Werte zuweisen, die niedriger sind als die in der vorherigen Tabelle angezeigten Werte der Lösungsreihenfolge, kann der Berechnungsdurchlauf unvorhersehbar werden.</span><span class="sxs-lookup"><span data-stu-id="3ed06-134">If you assign values that are lower than the solve order values shown in the previous table, the calculation pass can become unpredictable.</span></span> <span data-ttu-id="3ed06-135">Angenommen, die Berechnung für ein berechnetes Element erhält einen Wert der Lösungsreihenfolge, der niedriger ist als der Standardformelwert für benutzerdefinierte Rollups von -5.119.</span><span class="sxs-lookup"><span data-stu-id="3ed06-135">For example, the calculation for a calculated member receives a solve order value that is lower than the default custom rollup formula value of -5119.</span></span> <span data-ttu-id="3ed06-136">Ein so niedriger Wert der Lösungsreihenfolge führt dazu, dass die berechneten Elemente vor den benutzerdefinierten Rollupformeln berechnet werden. Dies kann zu falschen Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="3ed06-136">Such a low solve order value causes the calculated members to be calculated before the custom rollup formulas, and can produce incorrect results.</span></span>  
  
### <a name="creating-and-changing-solve-order"></a><span data-ttu-id="3ed06-137">Erstellen und Ändern der Lösungsreihenfolge</span><span class="sxs-lookup"><span data-stu-id="3ed06-137">Creating and Changing Solve Order</span></span>  
 <span data-ttu-id="3ed06-138">Im Cube-Designer können Sie im Bereich **Berechnungen**die Lösungsreihenfolge für berechnete Elemente und berechnete Zellen ändern, indem Sie die Reihenfolge der Berechnungen ändern.</span><span class="sxs-lookup"><span data-stu-id="3ed06-138">In Cube Designer, on the **Calculations Pane**, you can change the solve order for calculated members and calculated cells by changing the order of the calculations.</span></span>  
  
 <span data-ttu-id="3ed06-139">In MDX können Sie mit dem `SOLVE_ORDER`-Schlüsselwort berechnete Elemente und berechnete Zellen erstellen bzw. ändern.</span><span class="sxs-lookup"><span data-stu-id="3ed06-139">In MDX, you can use the `SOLVE_ORDER` keyword to create or change calculated members and calculated cells.</span></span>  
  
## <a name="solve-order-examples"></a><span data-ttu-id="3ed06-140">Beispiele für die Lösungsreihenfolge</span><span class="sxs-lookup"><span data-stu-id="3ed06-140">Solve Order Examples</span></span>  
 <span data-ttu-id="3ed06-141">Um die mögliche Komplexität der Lösungsreihenfolge zu veranschaulichen, beginnt die folgende Reihe von MDX-Abfragen mit zwei Abfragen, die einzeln betrachtet keine Probleme mit der Lösungsreihenfolge aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3ed06-141">To illustrate the potential complexities of solve order, the following series of MDX queries starts with two queries that each individually have no solve order issues.</span></span> <span data-ttu-id="3ed06-142">Die beiden Abfragen werden dann in einer Abfrage kombiniert, für die eine Lösungsreihenfolge erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="3ed06-142">These two queries are then combined into a query that requires solve order.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3ed06-143">Sie können diese MDX-Abfragen unter Verwendung der mehrdimensionalen Adventure Works-Beispieldatenbank ausführen.</span><span class="sxs-lookup"><span data-stu-id="3ed06-143">You can run these MDX queries against the Adventure Works sample multidimensional database.</span></span> <span data-ttu-id="3ed06-144">Sie können das Beispiel zu [AdventureWorks Multidimensional Models SQL Server 2012](https://msftdbprodsamples.codeplex.com/releases/view/55330) von der Codeplex-Website herunterladen.</span><span class="sxs-lookup"><span data-stu-id="3ed06-144">You can download the [AdventureWorks Multidimensional Models SQL Server 2012](https://msftdbprodsamples.codeplex.com/releases/view/55330) sample from the codeplex site.</span></span>  
  
### <a name="query-1-differences-in-income-and-expenses"></a><span data-ttu-id="3ed06-145">Abfrage 1: Unterschiede bei Einkommen und Ausgaben</span><span class="sxs-lookup"><span data-stu-id="3ed06-145">Query 1-Differences in Income and Expenses</span></span>  
 <span data-ttu-id="3ed06-146">Mit der ersten MDX-Abfrage berechnen Sie die Differenz zwischen Umsätzen und Kosten für jedes Jahr, indem Sie eine einfache MDX-Abfrage wie im folgenden Beispiel erstellen:</span><span class="sxs-lookup"><span data-stu-id="3ed06-146">For the first MDX query, calculate the difference in sales and costs for each year by constructing a simple MDX query similar to the following example:</span></span>  
  
```  
WITH   
MEMBER  
[Date].[Calendar].[Year Difference] AS ([Date].[Calendar].[Calendar Year].&[2008] - [Date].[Calendar].[Calendar Year].&[2007] )  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008], [Date].[Year Difference] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="3ed06-147">Diese Abfrage enthält als einziges berechnetes Element `Year Difference`.</span><span class="sxs-lookup"><span data-stu-id="3ed06-147">In this query, there is only one calculated member, `Year Difference`.</span></span> <span data-ttu-id="3ed06-148">Da nur ein berechnetes Element vorhanden ist, stellt die Lösungsreihenfolge kein Problem dar, vorausgesetzt der Cube verwendet keine berechneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="3ed06-148">Because there is only one calculated member, solve order is not an issue, as long as the cube does not use any calculated members.</span></span>  
  
 <span data-ttu-id="3ed06-149">Mit dieser MDX-Abfrage wird ein der folgenden Tabelle ähnelndes Resultset erstellt.</span><span class="sxs-lookup"><span data-stu-id="3ed06-149">This MDX query produces a result set similar to the following table.</span></span>  
  
||<span data-ttu-id="3ed06-150">Internet Sales Amount</span><span class="sxs-lookup"><span data-stu-id="3ed06-150">Internet Sales Amount</span></span>|<span data-ttu-id="3ed06-151">Internet Total Product Cost</span><span class="sxs-lookup"><span data-stu-id="3ed06-151">Internet Total Product Cost</span></span>|  
|-|---------------------------|---------------------------------|  
|<span data-ttu-id="3ed06-152">**CY 2007**</span><span class="sxs-lookup"><span data-stu-id="3ed06-152">**CY 2007**</span></span>|<span data-ttu-id="3ed06-153">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="3ed06-153">$9,791,060.30</span></span>|<span data-ttu-id="3ed06-154">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="3ed06-154">$5,718,327.17</span></span>|  
|<span data-ttu-id="3ed06-155">**KJ 2008**</span><span class="sxs-lookup"><span data-stu-id="3ed06-155">**CY 2008**</span></span>|<span data-ttu-id="3ed06-156">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="3ed06-156">$9,770,899.74</span></span>|<span data-ttu-id="3ed06-157">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="3ed06-157">$5,721,205.24</span></span>|  
|<span data-ttu-id="3ed06-158">**Year Difference**</span><span class="sxs-lookup"><span data-stu-id="3ed06-158">**Year Difference**</span></span>|<span data-ttu-id="3ed06-159">($20,160.56)</span><span class="sxs-lookup"><span data-stu-id="3ed06-159">($20,160.56)</span></span>|<span data-ttu-id="3ed06-160">$2,878.06</span><span class="sxs-lookup"><span data-stu-id="3ed06-160">$2,878.06</span></span>|  
  
### <a name="query-2-percentage-of-income-after-expenses"></a><span data-ttu-id="3ed06-161">Abfrage 2: Prozentsatz des Einkommens nach Ausgaben</span><span class="sxs-lookup"><span data-stu-id="3ed06-161">Query 2-Percentage of Income after Expenses</span></span>  
 <span data-ttu-id="3ed06-162">Mit der zweiten Abfrage berechnen Sie den Prozentsatz des Einkommens nach Abzug der Ausgaben für jedes Jahr. Verwenden Sie dazu die folgende MDX-Abfrage:</span><span class="sxs-lookup"><span data-stu-id="3ed06-162">For the second query, calculate the percentage of income after expenses for each year using the following MDX query:</span></span>  
  
```  
WITH   
MEMBER  
[Measures].[Profit Margin] AS   
([Measures].[Internet Sales Amount] - [Measures].[Internet Total Product Cost] ) / [Measures].[Internet Sales Amount] ,  
FORMAT_STRING="Percent"  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost], [Measures].[Profit Margin] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="3ed06-163">Wie die vorherige MDX-Abfrage enthält auch diese nur ein berechnetes Element, `Profit Margin`, und muss daher keine Lösungsreihenfolge berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="3ed06-163">This MDX query, like the previous one, has only a single calculated member, `Profit Margin`, and therefore does not have any solve order complications.</span></span>  
  
 <span data-ttu-id="3ed06-164">Mit dieser MDX-Abfrage wird ein etwas anderes Resultset erstellt, ähnlich der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3ed06-164">This MDX query produces a slightly different result set, similar to the following table.</span></span>  
  
||<span data-ttu-id="3ed06-165">Internet Sales Amount</span><span class="sxs-lookup"><span data-stu-id="3ed06-165">Internet Sales Amount</span></span>|<span data-ttu-id="3ed06-166">Internet Total Product Cost</span><span class="sxs-lookup"><span data-stu-id="3ed06-166">Internet Total Product Cost</span></span>|<span data-ttu-id="3ed06-167">Profit Margin</span><span class="sxs-lookup"><span data-stu-id="3ed06-167">Profit Margin</span></span>|  
|-|---------------------------|---------------------------------|-------------------|  
|<span data-ttu-id="3ed06-168">**CY 2007**</span><span class="sxs-lookup"><span data-stu-id="3ed06-168">**CY 2007**</span></span>|<span data-ttu-id="3ed06-169">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="3ed06-169">$9,791,060.30</span></span>|<span data-ttu-id="3ed06-170">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="3ed06-170">$5,718,327.17</span></span>|<span data-ttu-id="3ed06-171">41.60%</span><span class="sxs-lookup"><span data-stu-id="3ed06-171">41.60%</span></span>|  
|<span data-ttu-id="3ed06-172">**KJ 2008**</span><span class="sxs-lookup"><span data-stu-id="3ed06-172">**CY 2008**</span></span>|<span data-ttu-id="3ed06-173">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="3ed06-173">$9,770,899.74</span></span>|<span data-ttu-id="3ed06-174">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="3ed06-174">$5,721,205.24</span></span>|<span data-ttu-id="3ed06-175">41.45%</span><span class="sxs-lookup"><span data-stu-id="3ed06-175">41.45%</span></span>|  
  
 <span data-ttu-id="3ed06-176">Der Grund für die unterschiedlichen Resultsets aus der ersten und der zweiten Abfrage ist eine andere Platzierung des berechneten Elements.</span><span class="sxs-lookup"><span data-stu-id="3ed06-176">The difference in result sets between the first query and the second query comes from the difference in placement of the calculated member.</span></span> <span data-ttu-id="3ed06-177">In der ersten Abfrage ist das berechnete Element Teil der ROWS-Achse und nicht der COLUMNS-Achse, wie in der zweiten Abfrage.</span><span class="sxs-lookup"><span data-stu-id="3ed06-177">In the first query, the calculated member is part of the ROWS axis, not the COLUMNS axis shown in the second query.</span></span> <span data-ttu-id="3ed06-178">Diese unterschiedliche Platzierung gewinnt in der nächsten Abfrage an Bedeutung, wenn die beiden berechneten Elemente in einer einzigen MDX-Abfrage kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="3ed06-178">This difference in placement becomes important in the next query, which combines the two calculated members in a single MDX query.</span></span>  
  
### <a name="query-3-combined-year-difference-and-net-income-calculations"></a><span data-ttu-id="3ed06-179">Abfrage 3: kombinierte Berechnung von Jahres Unterschied und Nettoeinkommen</span><span class="sxs-lookup"><span data-stu-id="3ed06-179">Query 3-Combined Year Difference and Net Income Calculations</span></span>  
 <span data-ttu-id="3ed06-180">In dieser letzten Abfrage, in der die beiden vorherigen Beispiele in einer MDX-Abfrage kombiniert werden, ist die Lösungsreihenfolge von Bedeutung, da Berechnungen sowohl für Spalten als auch für Zeilen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3ed06-180">In this final query combining both of the previous examples into a single MDX query, solve order becomes important because of the calculations on both columns and rows.</span></span> <span data-ttu-id="3ed06-181">Um sicherzustellen, dass die Berechnungen in der richtigen Reihenfolge vorgenommen werden, definieren Sie diese Reihenfolge mithilfe des `SOLVE_ORDER`-Schlüsselworts.</span><span class="sxs-lookup"><span data-stu-id="3ed06-181">To make sure that the calculations occur in the correct sequence, define the sequence in which the calculations occur by using the `SOLVE_ORDER` keyword.</span></span>  
  
 <span data-ttu-id="3ed06-182">Das `SOLVE_ORDER`-Schlüsselwort gibt die Lösungsreihenfolge der berechneten Elemente in einer MDX-Abfrage oder einem `CREATE MEMBER`-Befehl an.</span><span class="sxs-lookup"><span data-stu-id="3ed06-182">The `SOLVE_ORDER` keyword specifies the solve order of calculated members in an MDX query or a `CREATE MEMBER` command.</span></span> <span data-ttu-id="3ed06-183">Die mit dem `SOLVE_ORDER`-Schlüsselwort verwendeten ganzzahligen Werte sind relativ, müssen nicht mit 0 beginnen und nicht aufeinander folgen.</span><span class="sxs-lookup"><span data-stu-id="3ed06-183">The integer values used with the `SOLVE_ORDER` keyword are relative, do not need to start at zero, and do not need to be consecutive.</span></span> <span data-ttu-id="3ed06-184">Der Wert weist MDX lediglich an, ein Element auf der Grundlage von Werten zu berechnen, die aus der Berechnung von Elementen mit einem höheren Wert abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="3ed06-184">The value simply tells MDX to calculate a member based on values derived from calculating members with a higher value.</span></span> <span data-ttu-id="3ed06-185">Wird ein berechnetes Element ohne das `SOLVE_ORDER`-Schlüsselwort definiert, lautet sein Standardwert 0.</span><span class="sxs-lookup"><span data-stu-id="3ed06-185">If a calculated member is defined without the `SOLVE_ORDER` keyword, the default value of that calculated member is zero.</span></span>  
  
 <span data-ttu-id="3ed06-186">Wenn Sie beispielsweise die in den ersten beiden Beispielabfragen verwendeten Berechnungen kombinieren, überschneiden sich die beiden berechneten Elemente `Year Difference` und `Profit Margin`in einer einzelnen Zelle im Resultdataset der MDX-Beispielabfrage.</span><span class="sxs-lookup"><span data-stu-id="3ed06-186">For example, if you combine the calculations used in the first two example queries, the two calculated members, `Year Difference` and `Profit Margin`, intersect at a single cell in the result dataset of the MDX query example.</span></span> <span data-ttu-id="3ed06-187">Nur anhand der Lösungsreihenfolge lässt sich bestimmen, wie [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] diese Zelle auswertet.</span><span class="sxs-lookup"><span data-stu-id="3ed06-187">The only way to determine how [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] will evaluate this cell is by the solve order.</span></span> <span data-ttu-id="3ed06-188">Die Formeln, mit denen diese Zelle erstellt wird, erzeugen je nach Lösungsreihenfolge der beiden berechneten Elemente unterschiedliche Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="3ed06-188">The formulas that are used to construct this cell will produce different results depending upon the solve order of the two calculated members.</span></span>  
  
 <span data-ttu-id="3ed06-189">Versuchen Sie zunächst, die in den ersten beiden Abfragen verwendeten Berechnungen in der folgenden MDX-Abfrage zu kombinieren:</span><span class="sxs-lookup"><span data-stu-id="3ed06-189">First, try combining the calculations used in the first two queries in the following MDX query:</span></span>  
  
```  
WITH   
MEMBER  
[Date].[Calendar].[Year Difference] AS ([Date].[Calendar].[Calendar Year].&[2008] - [Date].[Calendar].[Calendar Year].&[2007] ) ,  
SOLVE_ORDER = 1  
MEMBER  
[Measures].[Profit Margin] AS   
( [Measures].[Internet Sales Amount] - [Measures].[Internet Total Product Cost] ) / [Measures].[Internet Sales Amount] ,  
FORMAT_STRING="Percent" ,  
SOLVE_ORDER = 2  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost], [Measures].[Profit Margin] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008], [Date].[Year Difference] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="3ed06-190">In diesem Beispiel für eine kombinierte MDX-Abfrage weist `Profit Margin` die höchste Lösungsreihenfolge auf und hat daher bei der Interaktion zweier Ausdrücke Vorrang.</span><span class="sxs-lookup"><span data-stu-id="3ed06-190">In this combined MDX query example, `Profit Margin` has the highest solve order, so it takes precedence when the two expressions interact.</span></span> [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="3ed06-191">wertet die betreffende Zelle mit der `Profit Margin` -Formel aus.</span><span class="sxs-lookup"><span data-stu-id="3ed06-191">evaluates the cell in question by using the `Profit Margin` formula.</span></span> <span data-ttu-id="3ed06-192">Das Ergebnis dieser geschachtelten Berechnung ist in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3ed06-192">The results of this nested calculation, as shown in the following table.</span></span>  
  
||<span data-ttu-id="3ed06-193">Internet Sales Amount</span><span class="sxs-lookup"><span data-stu-id="3ed06-193">Internet Sales Amount</span></span>|<span data-ttu-id="3ed06-194">Internet Total Product Cost</span><span class="sxs-lookup"><span data-stu-id="3ed06-194">Internet Total Product Cost</span></span>|<span data-ttu-id="3ed06-195">Profit Margin</span><span class="sxs-lookup"><span data-stu-id="3ed06-195">Profit Margin</span></span>|  
|-|---------------------------|---------------------------------|-------------------|  
|<span data-ttu-id="3ed06-196">**CY 2007**</span><span class="sxs-lookup"><span data-stu-id="3ed06-196">**CY 2007**</span></span>|<span data-ttu-id="3ed06-197">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="3ed06-197">$9,791,060.30</span></span>|<span data-ttu-id="3ed06-198">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="3ed06-198">$5,718,327.17</span></span>|<span data-ttu-id="3ed06-199">41.60%</span><span class="sxs-lookup"><span data-stu-id="3ed06-199">41.60%</span></span>|  
|<span data-ttu-id="3ed06-200">**KJ 2008**</span><span class="sxs-lookup"><span data-stu-id="3ed06-200">**CY 2008**</span></span>|<span data-ttu-id="3ed06-201">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="3ed06-201">$9,770,899.74</span></span>|<span data-ttu-id="3ed06-202">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="3ed06-202">$5,721,205.24</span></span>|<span data-ttu-id="3ed06-203">41.45%</span><span class="sxs-lookup"><span data-stu-id="3ed06-203">41.45%</span></span>|  
|<span data-ttu-id="3ed06-204">**Year Difference**</span><span class="sxs-lookup"><span data-stu-id="3ed06-204">**Year Difference**</span></span>|<span data-ttu-id="3ed06-205">($20,160.56)</span><span class="sxs-lookup"><span data-stu-id="3ed06-205">($20,160.56)</span></span>|<span data-ttu-id="3ed06-206">$2,878.06</span><span class="sxs-lookup"><span data-stu-id="3ed06-206">$2,878.06</span></span>|<span data-ttu-id="3ed06-207">114.28%</span><span class="sxs-lookup"><span data-stu-id="3ed06-207">114.28%</span></span>|  
  
 <span data-ttu-id="3ed06-208">Das Ergebnis in der freigegebenen Zelle basiert auf der Formel für `Profit Margin`.</span><span class="sxs-lookup"><span data-stu-id="3ed06-208">The result in the shared cell is based on the formula for `Profit Margin`.</span></span> <span data-ttu-id="3ed06-209">[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] berechnet also das Ergebnis in der freigegebenen Zelle mit den `Year Difference` -Daten, wodurch folgende Formel erzeugt wird (das Ergebnis wurde zur besseren Übersicht gerundet):</span><span class="sxs-lookup"><span data-stu-id="3ed06-209">That is, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calculates the result in the shared cell with the `Year Difference` data, producing the following formula (the result is rounded for clarity):</span></span>  
  
```  
((9,770,899.74 - 9,791,060.30) - (5,721,205.24 - 5,718,327.17)) / (9,770,899.74 - 9,791,060.30) = 1.14275744   
```  
  
 <span data-ttu-id="3ed06-210">oder</span><span class="sxs-lookup"><span data-stu-id="3ed06-210">or</span></span>  
  
```  
(23,038.63) / (20,160.56) = 114.28%  
```  
  
 <span data-ttu-id="3ed06-211">Dies ist eindeutig falsch.</span><span class="sxs-lookup"><span data-stu-id="3ed06-211">This is clearly incorrect.</span></span> <span data-ttu-id="3ed06-212">Wenn die Lösungsreihenfolge für die berechneten Elemente in der MDX-Abfrage vertauscht wird, berechnet [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] das Ergebnis in der freigegebenen Zelle jedoch anders.</span><span class="sxs-lookup"><span data-stu-id="3ed06-212">However, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calculates the result in the shared cell differently if you switch the solve orders for the calculated members in the MDX query.</span></span> <span data-ttu-id="3ed06-213">Mit der folgenden kombinierten MDX-Abfrage wird die Lösungsreihenfolge für berechnete Elemente umgekehrt:</span><span class="sxs-lookup"><span data-stu-id="3ed06-213">The following combined MDX query reverses the solve order for the calculated members:</span></span>  
  
```  
WITH   
MEMBER  
[Date].[Calendar].[Year Difference] AS ([Date].[Calendar].[Calendar Year].&[2008] - [Date].[Calendar].[Calendar Year].&[2007] ) ,  
SOLVE_ORDER = 2  
MEMBER  
[Measures].[Profit Margin] AS   
( [Measures].[Internet Sales Amount] - [Measures].[Internet Total Product Cost] ) / [Measures].[Internet Sales Amount] ,  
FORMAT_STRING="Percent" ,  
SOLVE_ORDER = 1  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost], [Measures].[Profit Margin] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008], [Date].[Year Difference] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="3ed06-214">Da die Reihenfolge der berechneten Elemente vertauscht wurde, verwendet [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] zum Auswerten der Zelle die `Year Difference` -Formel, wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3ed06-214">As the order of the calculated members has been switched, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] uses the `Year Difference` formula to evaluate the cell, as shown in the following table.</span></span>  
  
||<span data-ttu-id="3ed06-215">Internet Sales Amount</span><span class="sxs-lookup"><span data-stu-id="3ed06-215">Internet Sales Amount</span></span>|<span data-ttu-id="3ed06-216">Internet Total Product Cost</span><span class="sxs-lookup"><span data-stu-id="3ed06-216">Internet Total Product Cost</span></span>|<span data-ttu-id="3ed06-217">Profit Margin</span><span class="sxs-lookup"><span data-stu-id="3ed06-217">Profit Margin</span></span>|  
|-|---------------------------|---------------------------------|-------------------|  
|<span data-ttu-id="3ed06-218">**CY 2007**</span><span class="sxs-lookup"><span data-stu-id="3ed06-218">**CY 2007**</span></span>|<span data-ttu-id="3ed06-219">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="3ed06-219">$9,791,060.30</span></span>|<span data-ttu-id="3ed06-220">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="3ed06-220">$5,718,327.17</span></span>|<span data-ttu-id="3ed06-221">41.60%</span><span class="sxs-lookup"><span data-stu-id="3ed06-221">41.60%</span></span>|  
|<span data-ttu-id="3ed06-222">**KJ 2008**</span><span class="sxs-lookup"><span data-stu-id="3ed06-222">**CY 2008**</span></span>|<span data-ttu-id="3ed06-223">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="3ed06-223">$9,770,899.74</span></span>|<span data-ttu-id="3ed06-224">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="3ed06-224">$5,721,205.24</span></span>|<span data-ttu-id="3ed06-225">41.45%</span><span class="sxs-lookup"><span data-stu-id="3ed06-225">41.45%</span></span>|  
|<span data-ttu-id="3ed06-226">**Year Difference**</span><span class="sxs-lookup"><span data-stu-id="3ed06-226">**Year Difference**</span></span>|<span data-ttu-id="3ed06-227">($20,160.56)</span><span class="sxs-lookup"><span data-stu-id="3ed06-227">($20,160.56)</span></span>|<span data-ttu-id="3ed06-228">$2,878.06</span><span class="sxs-lookup"><span data-stu-id="3ed06-228">$2,878.06</span></span>|<span data-ttu-id="3ed06-229">(0.15%)</span><span class="sxs-lookup"><span data-stu-id="3ed06-229">(0.15%)</span></span>|  
  
 <span data-ttu-id="3ed06-230">Da in dieser Abfrage die `Year Difference` -Formel mit den Daten für `Profit Margin` verwendet wird, gleicht die Formel für die freigegebene Zelle der folgenden Berechnung:</span><span class="sxs-lookup"><span data-stu-id="3ed06-230">Because this query uses the `Year Difference` formula with the `Profit Margin` data, the formula for the shared cell resembles the following calculation:</span></span>  
  
```  
(($9,770,899.74 - 5,721,205.24) / $9,770,899.74) - ((9,791,060.30 - 5,718,327.17) / 9,791,060.30) = -0.15   
```  
  
 <span data-ttu-id="3ed06-231">oder</span><span class="sxs-lookup"><span data-stu-id="3ed06-231">Or</span></span>  
  
```  
0.4145 - 0.4160= -0.15  
```  
  
## <a name="additional-considerations"></a><span data-ttu-id="3ed06-232">Weitere Überlegungen</span><span class="sxs-lookup"><span data-stu-id="3ed06-232">Additional Considerations</span></span>  
 <span data-ttu-id="3ed06-233">Die Lösungsreihenfolge kann ein sehr komplexes Problem darstellen, besonders in Cubes mit einer hohen Anzahl von Dimensionen, die berechnete Elemente, benutzerdefinierte Rollupformeln oder berechnete Zellen beinhalten.</span><span class="sxs-lookup"><span data-stu-id="3ed06-233">Solve order can be a very complex issue to deal with, especially in cubes with a high number of dimensions involving calculated member, custom rollup formulas, or calculated cells.</span></span> <span data-ttu-id="3ed06-234">Wenn [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] eine MDX-Abfrage auswertet, berücksichtigt [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] die Werte der Lösungsreihenfolge für alle Teile in einem bestimmten Durchlauf, einschließlich der Dimensionen des in der MDX-Abfrage angegebenen Cubes.</span><span class="sxs-lookup"><span data-stu-id="3ed06-234">When [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] evaluates an MDX query, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] takes into account the solve order values for everything involved within a given pass, including the dimensions of the cube specified in the MDX query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ed06-235">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3ed06-235">See Also</span></span>  
 <span data-ttu-id="3ed06-236">[CalculationCurrentPass-&#40;MDX-&#41;](/sql/mdx/calculationcurrentpass-mdx) </span><span class="sxs-lookup"><span data-stu-id="3ed06-236">[CalculationCurrentPass &#40;MDX&#41;](/sql/mdx/calculationcurrentpass-mdx) </span></span>  
 <span data-ttu-id="3ed06-237">[CalculationPassValue-&#40;MDX-&#41;](/sql/mdx/calculationpassvalue-mdx) </span><span class="sxs-lookup"><span data-stu-id="3ed06-237">[CalculationPassValue &#40;MDX&#41;](/sql/mdx/calculationpassvalue-mdx) </span></span>  
 <span data-ttu-id="3ed06-238">[Create Member-Anweisung &#40;MDX-&#41;](/sql/mdx/mdx-data-definition-create-member) </span><span class="sxs-lookup"><span data-stu-id="3ed06-238">[CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span></span>  
 [<span data-ttu-id="3ed06-239">Bearbeiten von Daten &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="3ed06-239">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)  
  
