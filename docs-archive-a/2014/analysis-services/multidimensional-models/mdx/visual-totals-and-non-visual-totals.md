---
title: Visuelle Gesamtsummen und nicht visuelle Gesamtwerte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ea9d02f2-a668-4547-ade5-e3d077a2e1bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: ddff047be6a819d05276848cbeb430fb8e4c9c2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721885"
---
# <a name="visual-totals-and-non-visual-totals"></a><span data-ttu-id="a83d0-102">Sichtbare Gesamtwerte und nicht sichtbare Gesamtwerte</span><span class="sxs-lookup"><span data-stu-id="a83d0-102">Visual Totals and Non Visual Totals</span></span>
  <span data-ttu-id="a83d0-103">Als sichtbare Gesamtwerte werden Gesamtbeträge am Ende einer Spalte oder Zeile bezeichnet, in denen alle in der Spalte bzw. Zeile sichtbaren Elemente zusammengezählt wurden.</span><span class="sxs-lookup"><span data-stu-id="a83d0-103">Visual Totals are totals at the end of a column or row that add up all of the items visible in the column or row.</span></span> <span data-ttu-id="a83d0-104">Dies ist bei der Anzeige der meisten Tabellen das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="a83d0-104">This is the default behavior for most tables when displayed.</span></span> <span data-ttu-id="a83d0-105">In bestimmten Fällen sollen jedoch möglicherweise nur bestimmte Spalten in einer Tabelle, jedoch die Gesamtbeträge für die komplette Zeile angezeigt werden, einschließlich der nicht sichtbaren Spalten.</span><span class="sxs-lookup"><span data-stu-id="a83d0-105">However, there are times when the user wants to display only certain columns in a table but keep the totals for the entire row, including those that are not displayed.</span></span> <span data-ttu-id="a83d0-106">Diese werden als `Non Visual Totals` bezeichnet, da der Gesamtbetrag sowohl die sichtbaren als auch die nicht sichtbaren Werte beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="a83d0-106">These are called `Non Visual Totals`, because the total comes from both the visible and non-visible values.</span></span>  
  
 <span data-ttu-id="a83d0-107">Das folgende Szenario veranschaulicht das Verhalten von nicht sichtbaren Gesamtwerten.</span><span class="sxs-lookup"><span data-stu-id="a83d0-107">The following scenario demonstrates the behavior of Non Visual totals.</span></span> <span data-ttu-id="a83d0-108">Der erste Schritt zeigt das Standardverhalten von sichtbaren Gesamtwerten.</span><span class="sxs-lookup"><span data-stu-id="a83d0-108">The first step shows the default behavior of Visual Totals.</span></span>  
  
 <span data-ttu-id="a83d0-109">Das nachfolgende Beispiel zeigt eine [Adventure Works]-Abfrage, um Werte zu [Reseller Sales Amount] in einer Tabelle abzurufen, wobei die Produktkategorien die Spalten und die Geschäftstypen der Wiederverkäufer die Zeilen sind.</span><span class="sxs-lookup"><span data-stu-id="a83d0-109">The following example is a query of [Adventure Works] to obtain [Reseller Sales Amount] figures in a table where the product categories are the columns and the reseller business types are the rows.</span></span> <span data-ttu-id="a83d0-110">Beachten Sie, dass sowohl für Produkte als auch für Wiederverkäufer Gesamtbeträge angegeben werden, wenn die folgende SELECT-Anweisung ausgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="a83d0-110">Note that totals are given for both products and resellers when the following SELECT statement is issued:</span></span>  
  
 `select [Category].members on 0,`  
  
 `[Business Type].members on 1`  
  
 `from [Adventure Works]`  
  
 `where [Measures].[Reseller Sales Amount]`  
  
 <span data-ttu-id="a83d0-111">Hierdurch werden folgende Ergebnisse erzielt:</span><span class="sxs-lookup"><span data-stu-id="a83d0-111">Produces the following results:</span></span>  
  
|||||||  
|-|-|-|-|-|-|  
||<span data-ttu-id="a83d0-112">**Alle Produkte**</span><span class="sxs-lookup"><span data-stu-id="a83d0-112">**All Products**</span></span>|<span data-ttu-id="a83d0-113">**Accessories**</span><span class="sxs-lookup"><span data-stu-id="a83d0-113">**Accessories**</span></span>|<span data-ttu-id="a83d0-114">**Fahrräder**</span><span class="sxs-lookup"><span data-stu-id="a83d0-114">**Bikes**</span></span>|<span data-ttu-id="a83d0-115">**Kleidung**</span><span class="sxs-lookup"><span data-stu-id="a83d0-115">**Clothing**</span></span>|<span data-ttu-id="a83d0-116">**Komponenten**</span><span class="sxs-lookup"><span data-stu-id="a83d0-116">**Components**</span></span>|  
|<span data-ttu-id="a83d0-117">**All Resellers**</span><span class="sxs-lookup"><span data-stu-id="a83d0-117">**All Resellers**</span></span>|<span data-ttu-id="a83d0-118">**$80,450,596.98**</span><span class="sxs-lookup"><span data-stu-id="a83d0-118">**$80,450,596.98**</span></span>|<span data-ttu-id="a83d0-119">**$571,297.93**</span><span class="sxs-lookup"><span data-stu-id="a83d0-119">**$571,297.93**</span></span>|<span data-ttu-id="a83d0-120">**$66,302,381.56**</span><span class="sxs-lookup"><span data-stu-id="a83d0-120">**$66,302,381.56**</span></span>|<span data-ttu-id="a83d0-121">**$1,777,840.84**</span><span class="sxs-lookup"><span data-stu-id="a83d0-121">**$1,777,840.84**</span></span>|<span data-ttu-id="a83d0-122">**$11,799,076.66**</span><span class="sxs-lookup"><span data-stu-id="a83d0-122">**$11,799,076.66**</span></span>|  
|<span data-ttu-id="a83d0-123">**Specialty Bike Shop**</span><span class="sxs-lookup"><span data-stu-id="a83d0-123">**Specialty Bike Shop**</span></span>|<span data-ttu-id="a83d0-124">**$6,756,166.18**</span><span class="sxs-lookup"><span data-stu-id="a83d0-124">**$6,756,166.18**</span></span>|<span data-ttu-id="a83d0-125">**$65,125.48**</span><span class="sxs-lookup"><span data-stu-id="a83d0-125">**$65,125.48**</span></span>|<span data-ttu-id="a83d0-126">**$6,080,117.73**</span><span class="sxs-lookup"><span data-stu-id="a83d0-126">**$6,080,117.73**</span></span>|<span data-ttu-id="a83d0-127">**$252,933.91**</span><span class="sxs-lookup"><span data-stu-id="a83d0-127">**$252,933.91**</span></span>|<span data-ttu-id="a83d0-128">**$357,989.07**</span><span class="sxs-lookup"><span data-stu-id="a83d0-128">**$357,989.07**</span></span>|  
|<span data-ttu-id="a83d0-129">**Value Added Reseller**</span><span class="sxs-lookup"><span data-stu-id="a83d0-129">**Value Added Reseller**</span></span>|<span data-ttu-id="a83d0-130">**$34,967,517.33**</span><span class="sxs-lookup"><span data-stu-id="a83d0-130">**$34,967,517.33**</span></span>|<span data-ttu-id="a83d0-131">**$175,002.81**</span><span class="sxs-lookup"><span data-stu-id="a83d0-131">**$175,002.81**</span></span>|<span data-ttu-id="a83d0-132">**$30,892,354.33**</span><span class="sxs-lookup"><span data-stu-id="a83d0-132">**$30,892,354.33**</span></span>|<span data-ttu-id="a83d0-133">**$592,385.71**</span><span class="sxs-lookup"><span data-stu-id="a83d0-133">**$592,385.71**</span></span>|<span data-ttu-id="a83d0-134">**$3,307,774.48**</span><span class="sxs-lookup"><span data-stu-id="a83d0-134">**$3,307,774.48**</span></span>|  
|<span data-ttu-id="a83d0-135">**Warehouse**</span><span class="sxs-lookup"><span data-stu-id="a83d0-135">**Warehouse**</span></span>|<span data-ttu-id="a83d0-136">**$38,726,913.48**</span><span class="sxs-lookup"><span data-stu-id="a83d0-136">**$38,726,913.48**</span></span>|<span data-ttu-id="a83d0-137">**$331,169.64**</span><span class="sxs-lookup"><span data-stu-id="a83d0-137">**$331,169.64**</span></span>|<span data-ttu-id="a83d0-138">**$29,329,909.50**</span><span class="sxs-lookup"><span data-stu-id="a83d0-138">**$29,329,909.50**</span></span>|<span data-ttu-id="a83d0-139">**$932,521.23**</span><span class="sxs-lookup"><span data-stu-id="a83d0-139">**$932,521.23**</span></span>|<span data-ttu-id="a83d0-140">**$8,133,313.11**</span><span class="sxs-lookup"><span data-stu-id="a83d0-140">**$8,133,313.11**</span></span>|  
  
## <a name="non-visual-on-rows-and-columns"></a><span data-ttu-id="a83d0-141">Nicht sichtbare Gesamtwerte für Zeilen und Spalten</span><span class="sxs-lookup"><span data-stu-id="a83d0-141">Non-Visual on rows and columns</span></span>  
 <span data-ttu-id="a83d0-142">Wenn Sie eine Tabelle erstellen möchten, die nur Accessories- und Clothing-Produkte sowie Wiederverkäufer vom Typ Value Added Reseller und Warehouse enthält, wobei die Gesamtbeträge jedoch beibehalten werden, können Sie die folgende Anweisung mit NON VISUAL ausgeben:</span><span class="sxs-lookup"><span data-stu-id="a83d0-142">To produce a table with data only for the Accessories and Clothing products, the Value Added Reseller and Warehouse resellers, yet keeping the overall totals could be written as follows using NON VISUAL:</span></span>  
  
 `select [Category].members on 0,`  
  
 `[Business Type].members on 1`  
  
 `from NON VISUAL (Select {[Category].Accessories, [Category].Clothing} on 0,`  
  
 `{[Business Type].[Value Added Reseller], [Business Type].[Warehouse]} on 1`  
  
 `from [Adventure Works])`  
  
 `where [Measures].[Reseller Sales Amount]`  
  
 <span data-ttu-id="a83d0-143">Hierdurch werden folgende Ergebnisse erzielt:</span><span class="sxs-lookup"><span data-stu-id="a83d0-143">Produces the following results:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="a83d0-144">**Alle Produkte**</span><span class="sxs-lookup"><span data-stu-id="a83d0-144">**All Products**</span></span>|<span data-ttu-id="a83d0-145">**Accessories**</span><span class="sxs-lookup"><span data-stu-id="a83d0-145">**Accessories**</span></span>|<span data-ttu-id="a83d0-146">**Kleidung**</span><span class="sxs-lookup"><span data-stu-id="a83d0-146">**Clothing**</span></span>|  
|<span data-ttu-id="a83d0-147">**All Resellers**</span><span class="sxs-lookup"><span data-stu-id="a83d0-147">**All Resellers**</span></span>|<span data-ttu-id="a83d0-148">**$80,450,596.98**</span><span class="sxs-lookup"><span data-stu-id="a83d0-148">**$80,450,596.98**</span></span>|<span data-ttu-id="a83d0-149">**$571,297.93**</span><span class="sxs-lookup"><span data-stu-id="a83d0-149">**$571,297.93**</span></span>|<span data-ttu-id="a83d0-150">**$1,777,840.84**</span><span class="sxs-lookup"><span data-stu-id="a83d0-150">**$1,777,840.84**</span></span>|  
|<span data-ttu-id="a83d0-151">**Value Added Reseller**</span><span class="sxs-lookup"><span data-stu-id="a83d0-151">**Value Added Reseller**</span></span>|<span data-ttu-id="a83d0-152">**$34,967,517.33**</span><span class="sxs-lookup"><span data-stu-id="a83d0-152">**$34,967,517.33**</span></span>|<span data-ttu-id="a83d0-153">**$175,002.81**</span><span class="sxs-lookup"><span data-stu-id="a83d0-153">**$175,002.81**</span></span>|<span data-ttu-id="a83d0-154">**$592,385.71**</span><span class="sxs-lookup"><span data-stu-id="a83d0-154">**$592,385.71**</span></span>|  
|<span data-ttu-id="a83d0-155">**Warehouse**</span><span class="sxs-lookup"><span data-stu-id="a83d0-155">**Warehouse**</span></span>|<span data-ttu-id="a83d0-156">**$38,726,913.48**</span><span class="sxs-lookup"><span data-stu-id="a83d0-156">**$38,726,913.48**</span></span>|<span data-ttu-id="a83d0-157">**$331,169.64**</span><span class="sxs-lookup"><span data-stu-id="a83d0-157">**$331,169.64**</span></span>|<span data-ttu-id="a83d0-158">**$932,521.23**</span><span class="sxs-lookup"><span data-stu-id="a83d0-158">**$932,521.23**</span></span>|  
  
## <a name="non-visual-on-rows"></a><span data-ttu-id="a83d0-159">Nicht sichtbare Gesamtwerte für Zeilen</span><span class="sxs-lookup"><span data-stu-id="a83d0-159">Non-Visual on rows</span></span>  
 <span data-ttu-id="a83d0-160">Wenn Sie eine Tabelle erstellen möchten, in der sichtbare Gesamtwerte für die Spalten, für die Zeilensummen jedoch die tatsächliche Summe aller [Category]-Werten angezeigt werden, geben Sie die folgende Abfrage aus:</span><span class="sxs-lookup"><span data-stu-id="a83d0-160">To produce a table that visually totals the columns but for row totals brings the true total of all [Category], the following query should be issued:</span></span>  
  
 `select [Category].members on 0,`  
  
 `[Business Type].members on 1`  
  
 `from NON VISUAL (Select {[Category].Accessories, [Category].Clothing} on 0`  
  
 `from ( Select {[Business Type].[Value Added Reseller], [Business Type].[Warehouse]} on 0`  
  
 `from [Adventure Works])`  
  
 `)`  
  
 `where [Measures].[Reseller Sales Amount]`  
  
 <span data-ttu-id="a83d0-161">NON VISUAL wird nur auf [Category] angewendet.</span><span class="sxs-lookup"><span data-stu-id="a83d0-161">Note how NON VISUAL is only applied to [Category].</span></span>  
  
 <span data-ttu-id="a83d0-162">Die oben dargestellte Abfrage führt zu den folgenden Ergebnissen:</span><span class="sxs-lookup"><span data-stu-id="a83d0-162">The above query produces the following results:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="a83d0-163">All Products</span><span class="sxs-lookup"><span data-stu-id="a83d0-163">All Products</span></span>|<span data-ttu-id="a83d0-164">Accessories</span><span class="sxs-lookup"><span data-stu-id="a83d0-164">Accessories</span></span>|<span data-ttu-id="a83d0-165">Kleidung</span><span class="sxs-lookup"><span data-stu-id="a83d0-165">Clothing</span></span>|  
|<span data-ttu-id="a83d0-166">All Resellers</span><span class="sxs-lookup"><span data-stu-id="a83d0-166">All Resellers</span></span>|<span data-ttu-id="a83d0-167">$73,694,430.80</span><span class="sxs-lookup"><span data-stu-id="a83d0-167">$73,694,430.80</span></span>|<span data-ttu-id="a83d0-168">$506,172.45</span><span class="sxs-lookup"><span data-stu-id="a83d0-168">$506,172.45</span></span>|<span data-ttu-id="a83d0-169">$1,524,906.93</span><span class="sxs-lookup"><span data-stu-id="a83d0-169">$1,524,906.93</span></span>|  
|<span data-ttu-id="a83d0-170">Value Added Reseller</span><span class="sxs-lookup"><span data-stu-id="a83d0-170">Value Added Reseller</span></span>|<span data-ttu-id="a83d0-171">$34,967,517.33</span><span class="sxs-lookup"><span data-stu-id="a83d0-171">$34,967,517.33</span></span>|<span data-ttu-id="a83d0-172">$175,002.81</span><span class="sxs-lookup"><span data-stu-id="a83d0-172">$175,002.81</span></span>|<span data-ttu-id="a83d0-173">$592,385.71</span><span class="sxs-lookup"><span data-stu-id="a83d0-173">$592,385.71</span></span>|  
|<span data-ttu-id="a83d0-174">Warehouse</span><span class="sxs-lookup"><span data-stu-id="a83d0-174">Warehouse</span></span>|<span data-ttu-id="a83d0-175">$38,726,913.48</span><span class="sxs-lookup"><span data-stu-id="a83d0-175">$38,726,913.48</span></span>|<span data-ttu-id="a83d0-176">$331,169.64</span><span class="sxs-lookup"><span data-stu-id="a83d0-176">$331,169.64</span></span>|<span data-ttu-id="a83d0-177">$932,521.23</span><span class="sxs-lookup"><span data-stu-id="a83d0-177">$932,521.23</span></span>|  
  
 <span data-ttu-id="a83d0-178">Im Vergleich zu den vorhergehenden Ergebnissen können Sie feststellen, dass die Zeile [All Resellers] jetzt die Summe der angezeigten Werte für [Value Added Reseller] und [Warehouse] enthält, die Spalte [All Products] hingegen den Gesamtwert aller Produkte anzeigt, einschließlich der nicht sichtbaren Produkte.</span><span class="sxs-lookup"><span data-stu-id="a83d0-178">When compared with the previous results, you can observe that the [All Resellers] row now adds up to the displayed values for [Value Added Reseller] and [Warehouse] but that the [All Products] column shows the total value for all products, including those not displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a83d0-179">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a83d0-179">See Also</span></span>  
 <span data-ttu-id="a83d0-180">[Wichtige Konzepte in MDX-&#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="a83d0-180">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="a83d0-181">[Autoexists](autoexists.md) </span><span class="sxs-lookup"><span data-stu-id="a83d0-181">[Autoexists](autoexists.md) </span></span>  
 <span data-ttu-id="a83d0-182">[Arbeiten mit Membern, Tupeln und Mengen &#40;MDX-&#41;](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="a83d0-182">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 <span data-ttu-id="a83d0-183">[Grundlagen der MDX-Abfrage &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="a83d0-183">[MDX Query Fundamentals &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span></span>  
 <span data-ttu-id="a83d0-184">[Die grundlegende MDX-Abfrage &#40;MDX-&#41;](mdx-query-the-basic-query.md) </span><span class="sxs-lookup"><span data-stu-id="a83d0-184">[The Basic MDX Query &#40;MDX&#41;](mdx-query-the-basic-query.md) </span></span>  
 <span data-ttu-id="a83d0-185">[Einschränken der Abfrage mit Abfrage-und Slicerachsen &#40;MDX-&#41;](mdx-query-and-slicer-axes-restricting-the-query.md) </span><span class="sxs-lookup"><span data-stu-id="a83d0-185">[Restricting the Query with Query and Slicer Axes &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md) </span></span>  
 [<span data-ttu-id="a83d0-186">Festlegen des Cubekontexts in einer Abfrage &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="a83d0-186">Establishing Cube Context in a Query &#40;MDX&#41;</span></span>](establishing-cube-context-in-a-query-mdx.md)  
  
  
