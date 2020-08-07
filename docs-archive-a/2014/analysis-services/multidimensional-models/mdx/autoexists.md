---
title: Autoist vorhanden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 56283497-624c-45b5-8a0d-036b0e331d22
author: minewiskan
ms.author: owend
ms.openlocfilehash: dd35958a364456c12d58392afe3754f6adcf97b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619419"
---
# <a name="autoexists"></a><span data-ttu-id="c526a-102">Autoexists</span><span class="sxs-lookup"><span data-stu-id="c526a-102">Autoexists</span></span>
  <span data-ttu-id="c526a-103">Das *Autoexists* -Konzept beschränkt den Cuberaum auf Zellen, die tatsächlich im Cube enthalten sind, anstatt alle Zellen einzubeziehen, die durch die Erstellung aller potenziellen Kombinationen von Attributhierarchieelementen in der gleichen Hierarchie vorhanden sein könnten.</span><span class="sxs-lookup"><span data-stu-id="c526a-103">The concept of *autoexists* limits the cube space to those cells that actually exist in the cube in contraposition to those that might exist as a result of creating all possible combinations of attribute hierarchy members from the same hierarchy.</span></span> <span data-ttu-id="c526a-104">Dies liegt daran, dass Elemente einer Attributhierarchie nicht gemeinsam mit Elementen einer anderen Attributhierarchie in der gleichen Dimension vorhanden sein können.</span><span class="sxs-lookup"><span data-stu-id="c526a-104">This is because members of one attribute hierarchy cannot exist with members of another attribute hierarchy in the same dimension.</span></span> <span data-ttu-id="c526a-105">Wenn zwei oder mehr Attributhierarchien der gleichen Dimension in einer SELECT-Anweisung verwendet werden, wertet Analysis Services die Ausdrücke der Attribute aus, damit die Elemente dieser Attribute ordnungsgemäß beschränkt werden, so dass sie die Kriterien aller anderen Attribute erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c526a-105">When two or more attribute hierarchies of the same dimension are used in a SELECT statement, Analysis Services evaluates the attributes' expressions to make sure that the members of those attributes are properly confined to meet the criteria of all other attributes.</span></span>  
  
 <span data-ttu-id="c526a-106">Angenommen, Sie arbeiten mit Attributen der Geography-Dimension.</span><span class="sxs-lookup"><span data-stu-id="c526a-106">For example, suppose you are working with attributes from the Geography dimension.</span></span> <span data-ttu-id="c526a-107">Wenn ein Ausdruck alle Elemente des City-Attributs zurückgibt und ein anderer Ausdruck die Elemente des Country-Attributs auf alle Länder Europas beschränkt, sind als City-Elemente nur Orte in europäischen Ländern möglich.</span><span class="sxs-lookup"><span data-stu-id="c526a-107">If you have one expression that returns all members from the City attribute and another expression that confines members from the Country attribute to all countries in Europe, then this will result in the City members being confined to only those cities that belong to countries in Europe.</span></span> <span data-ttu-id="c526a-108">Dies ist auf das Autoexists-Merkmal von Analysis Services zurückzuführen.</span><span class="sxs-lookup"><span data-stu-id="c526a-108">This is because of the autoexists characteristic of Analysis Services.</span></span> <span data-ttu-id="c526a-109">Autoexists gilt nur für Attribute der gleichen Dimension, denn es versucht zu verhindern, dass die in einem Attributausdruck ausgeschlossenen Dimensionsdatensätze von den anderen Attributausdrücken eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="c526a-109">Autoexists only applies to attributes from the same dimension because it tries to prevent the dimension records excluded in one attribute expression from being included by the other attribute expressions.</span></span> <span data-ttu-id="c526a-110">Autoexists kann auch als resultierende Schnittmenge der unterschiedlichen Attributausdrücke in den Dimensionszeilen bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="c526a-110">Autoexists can also be understood as the resulting intersection of the different attributes expressions over the dimension rows.</span></span>  
  
## <a name="cell-existence"></a><span data-ttu-id="c526a-111">Vorhandensein von Zellen</span><span class="sxs-lookup"><span data-stu-id="c526a-111">Cell Existence</span></span>  
 <span data-ttu-id="c526a-112">Die folgenden Zellen sind immer vorhanden:</span><span class="sxs-lookup"><span data-stu-id="c526a-112">The following cells always exist:</span></span>  
  
-   <span data-ttu-id="c526a-113">Das (All)-Element jeder Hierarchie bei einer Schnittmenge mit Elementen anderer Hierarchien in der gleichen Dimension.</span><span class="sxs-lookup"><span data-stu-id="c526a-113">The (All) member, of every hierarchy, when crossed with members of other hierarchies in the same dimension.</span></span>  
  
-   <span data-ttu-id="c526a-114">Berechnete Elemente bei einer Schnittmenge mit nicht berechneten gleichgeordneten Elementen oder mit den übergeordneten Elementen oder Nachfolgern der nicht berechneten gleichgeordneten Elemente</span><span class="sxs-lookup"><span data-stu-id="c526a-114">Calculated members when crossed with their non-calculated siblings, or with the parents or descendants of their non-calculated siblings.</span></span>  
  
## <a name="providing-non-existing-cells"></a><span data-ttu-id="c526a-115">Bereitstellen von nicht vorhandenen Zellen</span><span class="sxs-lookup"><span data-stu-id="c526a-115">Providing Non-existing cells</span></span>  
 <span data-ttu-id="c526a-116">Eine nicht vorhandene Zelle ist eine Zelle, die vom System als Antwort auf eine Abfrage oder eine Berechnung bereitgestellt wird, in der eine im Cube nicht vorhandene Zelle angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="c526a-116">A non-existing cell is a cell provided by the system as a response to a query or calculation that requests a cell that does not exist in the cube.</span></span> <span data-ttu-id="c526a-117">Wenn beispielsweise ein Cube eine City-Attributhierarchie und eine Country-Attributhierarchie, die zur Geography-Dimension gehören, und eine Internet Sales Amount-Measure aufweist, schließt der Cuberaum nur solche Elemente ein, die gemeinsam vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c526a-117">For example, if you have a cube that has a City attribute hierarchy and a Country attribute hierarchy that belong to the Geography dimension, and an Internet Sales Amount measure, the space of this cube only includes those members that exist with each other.</span></span> <span data-ttu-id="c526a-118">Wenn beispielsweise die City-Attributhierarchie die Städte New York, London, Paris, Tokyo und Melbourne und die Country-Attributhierarchie die Länder United States, United Kingdom, France, Japan, and Australia umfasst, schließt der Cuberaum nicht den Raum (die Zelle) am Schnittpunkt von Paris und United States ein.</span><span class="sxs-lookup"><span data-stu-id="c526a-118">For example, if the City attribute hierarchy includes the cities New York, London, Paris, Tokyo, and Melbourne; and the Country attribute hierarchy includes the countries United States, United Kingdom, France, Japan, and Australia; then the space of the cube does not include the space (cell) at the intersection of Paris and United States.</span></span>  
  
 <span data-ttu-id="c526a-119">Beim Abfragen von nicht vorhandenen Zellen wird NULL zurückgegeben, d. h., nicht vorhandene Zellen können keine Berechnungen enthalten, und Sie können auch keine Berechnungen definieren, die in sie schreiben.</span><span class="sxs-lookup"><span data-stu-id="c526a-119">When querying cells that do not exist, non-existing cells return nulls; that is, they cannot contain calculations and you cannot define a calculation that writes to this space.</span></span> <span data-ttu-id="c526a-120">Die folgende Anweisung beinhaltet beispielsweise Zellen, die nicht vorhanden sind:</span><span class="sxs-lookup"><span data-stu-id="c526a-120">For example, the following statement includes cells that do not exist.</span></span>  
  
```  
SELECT [Customer].[Gender].[Gender].Members ON COLUMNS,  
{[Customer].[Customer].[Aaron A. Allen]  
   ,[Customer].[Customer].[Abigail Clark]} ON ROWS   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c526a-121">Diese Abfrage verwendet die [Members (Menge) (MDX)](/sql/mdx/members-set-mdx) -Funktion, um eine Menge von Elementen der Gender-Attributhierarchie auf der Spaltenachse zurückzugeben und diese Menge mit der angegebenen Menge von Elementen der Customer-Attributhierarchie auf der Zeilenachse zu kreuzen.</span><span class="sxs-lookup"><span data-stu-id="c526a-121">This query uses the [Members (Set) (MDX)](/sql/mdx/members-set-mdx) function to return the set of members of the Gender attribute hierarchy on the column axis, and crosses this set with the specified set of members from the Customer attribute hierarchy on the row axis.</span></span>  
  
 <span data-ttu-id="c526a-122">Beim Ausführen der vorherigen Abfrage zeigt die Zelle am Schnittpunkt zwischen Aaron A. Allen und Female eine Null an.</span><span class="sxs-lookup"><span data-stu-id="c526a-122">When you execute the previous query, the cell at the intersection of Aaron A. Allen and Female displays a null.</span></span> <span data-ttu-id="c526a-123">Entsprechend zeigt die Zelle am Schnittpunkt zwischen Abigail Clark und Male ebenfalls eine Null an.</span><span class="sxs-lookup"><span data-stu-id="c526a-123">Similarly, the cell at the intersection of Abigail Clark and Male displays a null.</span></span> <span data-ttu-id="c526a-124">Diese Zellen sind nicht vorhanden und können daher keine Werte enthalten, sie können jedoch im Ergebnis einer Abfrage angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c526a-124">These cells do not exist and cannot contain a value, but cells that do not exist can appear in the result returned by a query.</span></span>  
  
 <span data-ttu-id="c526a-125">Wenn Sie die [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) -Funktion verwenden, um das Kreuzprodukt von Attributhierarchie-Elementen und Attributhierarchien in der gleichen Dimension zurückzugeben, beschränkt Auto-exist das zurückgegebene Ergebnis auf die Menge der Tupel, die tatsächlich vorhanden sind, und gibt nicht das vollständige kartesische Produkt zurück.</span><span class="sxs-lookup"><span data-stu-id="c526a-125">When you use the [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) function to return the cross-product of attribute hierarchy members from attribute hierarchies in the same dimension, auto-exists limits those tuples being returned to the set of tuples that actually exist, rather than returning a full Cartesian product.</span></span> <span data-ttu-id="c526a-126">Führen Sie z. B. die folgenden Abfrage aus, und überprüfen Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="c526a-126">For example, run and then examine the results from the execution of the following query.</span></span>  
  
```  
SELECT CROSSJOIN  
   (  
      {[Customer].[Country].[United States]},  
         [Customer].[State-Province].Members  
  ) ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c526a-127">Beachten Sie, dass 0 hier für die Spaltenachse steht (als Kurzform für axis(0)).</span><span class="sxs-lookup"><span data-stu-id="c526a-127">Notice that 0 is used to designate the column axis, which is shorthand for axis(0) - which is the column axis.</span></span>  
  
 <span data-ttu-id="c526a-128">Die vorherige Abfrage gibt nur Zellen für Elemente der Attributhierarchien in der Abfrage zurück, die gemeinsam vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c526a-128">The previous query only returns cells for members from each attribute hierarchy in the query that exist with each other.</span></span> <span data-ttu-id="c526a-129">Die vorherige Abfrage kann auch mithilfe der neuen \*-Variante der [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) -Funktion geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="c526a-129">The previous query can also be written using the new \* variant of the [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) function.</span></span>  
  
```  
SELECT   
   [Customer].[Country].[United States] *   
      [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
 <span data-ttu-id="c526a-130">Die vorherige Abfrage kann auch wie folgt formuliert werden:</span><span class="sxs-lookup"><span data-stu-id="c526a-130">The previous query could also be written in the following manner:</span></span>  
  
```  
SELECT [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE (Measures.[Internet Sales Amount],  
   [Customer].[Country].[United States])  
```  
  
 <span data-ttu-id="c526a-131">Die zurückgegebenen Zellenwerte sind identisch, die Metadaten im Resultset sind jedoch verschieden.</span><span class="sxs-lookup"><span data-stu-id="c526a-131">The cells values returned will be identical, although the metadata in the result set will be different.</span></span> <span data-ttu-id="c526a-132">Beispielsweise wurde in der vorherigen Abfrage die Country-Hierarchie auf die Slicerachse verschoben (in die WHERE-Klausel), sodass sie nicht explizit im Resultset angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c526a-132">For example, with the previous query, the Country hierarchy was moved to the slicer axis (in the WHERE clause) and therefore does not appear explicitly in the result set.</span></span>  
  
 <span data-ttu-id="c526a-133">Jede dieser drei vorherigen Abfragen veranschaulicht die Auswirkung des Auto-es-Verhaltens in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c526a-133">Each of these three previous queries demonstrates the effect of the auto-exists behavior in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="deep-and-shallow-autoexists"></a><span data-ttu-id="c526a-134">Tiefe und flache Autoexists</span><span class="sxs-lookup"><span data-stu-id="c526a-134">Deep and Shallow Autoexists</span></span>  
 <span data-ttu-id="c526a-135">Autoexists können tief oder flach auf Ausdrücke angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="c526a-135">Autoexists can be applied to the expressions as Deep or Shallow.</span></span> <span data-ttu-id="c526a-136">`Deep Autoexists` bedeutet, dass alle Ausdrücke ausgewertet werden, um nach Anwendung der Slicerausdrücke, untergeordneten SELECT-Ausdrücke usw. einen möglichst tiefen Raum abzudecken.</span><span class="sxs-lookup"><span data-stu-id="c526a-136">`Deep Autoexists` means that all expressions will be evaluated to meet the deepest possible space after applying the slicer expressions, the sub select expressions in the axis, and so on.</span></span> <span data-ttu-id="c526a-137">`Shallow Autoexists` bedeutet, dass externe Ausdrücke vor dem aktuellen Ausdruck ausgewertet werden und dass diese Ergebnisse an den aktuellen Ausdruck übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="c526a-137">`Shallow Autoexists` means that external expressions are evaluated before the current expression and those results are passed to the current expression.</span></span> <span data-ttu-id="c526a-138">Die Standardeinstellung sind tiefe Autoexists.</span><span class="sxs-lookup"><span data-stu-id="c526a-138">The default setting is deep autoexists.</span></span>  
  
 <span data-ttu-id="c526a-139">Das folgende Szenario und die Beispiele veranschaulichen die verschiedenen Typen von Autoexists.</span><span class="sxs-lookup"><span data-stu-id="c526a-139">The following scenario and samples will help to illustrate the different types of Autoexistss.</span></span> <span data-ttu-id="c526a-140">In den folgenden Beispielen werden zwei Gruppen erstellt: eine als berechneteter Ausdruck und die andere als konstanter Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c526a-140">In the following examples two sets will be created: one as a calculated expression and the other as a constant expression.</span></span>  
  
 `//Obtain the Top 10 best reseller selling products by Name`  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `set Preferred10Products as '`  
  
 `{[Product].[Model Name].&[Mountain-200],`  
  
 `[Product].[Model Name].&[Road-250],`  
  
 `[Product].[Model Name].&[Mountain-100],`  
  
 `[Product].[Model Name].&[Road-650],`  
  
 `[Product].[Model Name].&[Touring-1000],`  
  
 `[Product].[Model Name].&[Road-550-W],`  
  
 `[Product].[Model Name].&[Road-350-W],`  
  
 `[Product].[Model Name].&[HL Mountain Frame],`  
  
 `[Product].[Model Name].&[Road-150],`  
  
 `[Product].[Model Name].&[Touring-3000]`  
  
 `}'`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Top10SellingProducts on 1`  
  
 `from [Adventure Works]`  
  
 <span data-ttu-id="c526a-141">Das Resultset lautet:</span><span class="sxs-lookup"><span data-stu-id="c526a-141">The obtained result set is:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="c526a-142">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="c526a-142">**Reseller Sales Amount**</span></span>|<span data-ttu-id="c526a-143">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="c526a-143">**Discount Amount**</span></span>|<span data-ttu-id="c526a-144">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="c526a-144">**PCT Discount**</span></span>|  
|<span data-ttu-id="c526a-145">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="c526a-145">**Mountain-200**</span></span>|<span data-ttu-id="c526a-146">**14.356.699,36 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-146">**$14,356,699.36**</span></span>|<span data-ttu-id="c526a-147">**19.012,71 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-147">**$19,012.71**</span></span>|<span data-ttu-id="c526a-148">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="c526a-148">**0.13%**</span></span>|  
|<span data-ttu-id="c526a-149">**Road-250**</span><span class="sxs-lookup"><span data-stu-id="c526a-149">**Road-250**</span></span>|<span data-ttu-id="c526a-150">**9.377.457,68 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-150">**$9,377,457.68**</span></span>|<span data-ttu-id="c526a-151">**4.032,47 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-151">**$4,032.47**</span></span>|<span data-ttu-id="c526a-152">**0,04%**</span><span class="sxs-lookup"><span data-stu-id="c526a-152">**0.04%**</span></span>|  
|<span data-ttu-id="c526a-153">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="c526a-153">**Mountain-100**</span></span>|<span data-ttu-id="c526a-154">**8.568.958,27 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-154">**$8,568,958.27**</span></span>|<span data-ttu-id="c526a-155">**139.393,27 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-155">**$139,393.27**</span></span>|<span data-ttu-id="c526a-156">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="c526a-156">**1.63%**</span></span>|  
|<span data-ttu-id="c526a-157">**Road-650**</span><span class="sxs-lookup"><span data-stu-id="c526a-157">**Road-650**</span></span>|<span data-ttu-id="c526a-158">**7.442.141,81 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-158">**$7,442,141.81**</span></span>|<span data-ttu-id="c526a-159">**39.698,30 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-159">**$39,698.30**</span></span>|<span data-ttu-id="c526a-160">**0,53 %**</span><span class="sxs-lookup"><span data-stu-id="c526a-160">**0.53%**</span></span>|  
|<span data-ttu-id="c526a-161">**Touring-1000**</span><span class="sxs-lookup"><span data-stu-id="c526a-161">**Touring-1000**</span></span>|<span data-ttu-id="c526a-162">**6.723.794,29 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-162">**$6,723,794.29**</span></span>|<span data-ttu-id="c526a-163">**166.144,17 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-163">**$166,144.17**</span></span>|<span data-ttu-id="c526a-164">**2,47%**</span><span class="sxs-lookup"><span data-stu-id="c526a-164">**2.47%**</span></span>|  
|<span data-ttu-id="c526a-165">**Road-550-W**</span><span class="sxs-lookup"><span data-stu-id="c526a-165">**Road-550-W**</span></span>|<span data-ttu-id="c526a-166">**3.668.383,88 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-166">**$3,668,383.88**</span></span>|<span data-ttu-id="c526a-167">**1.901,97 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-167">**$1,901.97**</span></span>|<span data-ttu-id="c526a-168">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="c526a-168">**0.05%**</span></span>|  
|<span data-ttu-id="c526a-169">**Road-350-W**</span><span class="sxs-lookup"><span data-stu-id="c526a-169">**Road-350-W**</span></span>|<span data-ttu-id="c526a-170">**3.665.932,31 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-170">**$3,665,932.31**</span></span>|<span data-ttu-id="c526a-171">**20.946,50 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-171">**$20,946.50**</span></span>|<span data-ttu-id="c526a-172">**0,57%**</span><span class="sxs-lookup"><span data-stu-id="c526a-172">**0.57%**</span></span>|  
|<span data-ttu-id="c526a-173">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="c526a-173">**HL Mountain Frame**</span></span>|<span data-ttu-id="c526a-174">**3.365.069,27 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-174">**$3,365,069.27**</span></span>|<span data-ttu-id="c526a-175">**174,11 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-175">**$174.11**</span></span>|<span data-ttu-id="c526a-176">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="c526a-176">**0.01%**</span></span>|  
|<span data-ttu-id="c526a-177">**Road-150**</span><span class="sxs-lookup"><span data-stu-id="c526a-177">**Road-150**</span></span>|<span data-ttu-id="c526a-178">**2.363.805,16 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-178">**$2,363,805.16**</span></span>|<span data-ttu-id="c526a-179">**$0,00**</span><span class="sxs-lookup"><span data-stu-id="c526a-179">**$0.00**</span></span>|<span data-ttu-id="c526a-180">**0,00%**</span><span class="sxs-lookup"><span data-stu-id="c526a-180">**0.00%**</span></span>|  
|<span data-ttu-id="c526a-181">**Touring-3000**</span><span class="sxs-lookup"><span data-stu-id="c526a-181">**Touring-3000**</span></span>|<span data-ttu-id="c526a-182">**2.046.508,26 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-182">**$2,046,508.26**</span></span>|<span data-ttu-id="c526a-183">**79.582,15 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-183">**$79,582.15**</span></span>|<span data-ttu-id="c526a-184">**3,89%**</span><span class="sxs-lookup"><span data-stu-id="c526a-184">**3.89%**</span></span>|  
  
 <span data-ttu-id="c526a-185">Die erhaltene Produktgruppe ist offenbar die gleiche wie Preferred10Products. Die Gruppe Preferred10Products wird deshalb überprüft:</span><span class="sxs-lookup"><span data-stu-id="c526a-185">The obtained set of products seems to be the same as Preferred10Products; so, verifying the Preferred10Products set:</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `set Preferred10Products as '`  
  
 `{[Product].[Model Name].&[Mountain-200],`  
  
 `[Product].[Model Name].&[Road-250],`  
  
 `[Product].[Model Name].&[Mountain-100],`  
  
 `[Product].[Model Name].&[Road-650],`  
  
 `[Product].[Model Name].&[Touring-1000],`  
  
 `[Product].[Model Name].&[Road-550-W],`  
  
 `[Product].[Model Name].&[Road-350-W],`  
  
 `[Product].[Model Name].&[HL Mountain Frame],`  
  
 `[Product].[Model Name].&[Road-150],`  
  
 `[Product].[Model Name].&[Touring-3000]`  
  
 `}'`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Preferred10Products on 1`  
  
 `from [Adventure Works]`  
  
 <span data-ttu-id="c526a-186">Laut den folgenden Ergebnissen sind beide Gruppen (Top10SellingProducts, Preferred10Products) identisch.</span><span class="sxs-lookup"><span data-stu-id="c526a-186">As per the following results, both sets (Top10SellingProducts, Preferred10Products) are the same</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="c526a-187">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="c526a-187">**Reseller Sales Amount**</span></span>|<span data-ttu-id="c526a-188">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="c526a-188">**Discount Amount**</span></span>|<span data-ttu-id="c526a-189">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="c526a-189">**PCT Discount**</span></span>|  
|<span data-ttu-id="c526a-190">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="c526a-190">**Mountain-200**</span></span>|<span data-ttu-id="c526a-191">**14.356.699,36 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-191">**$14,356,699.36**</span></span>|<span data-ttu-id="c526a-192">**19.012,71 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-192">**$19,012.71**</span></span>|<span data-ttu-id="c526a-193">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="c526a-193">**0.13%**</span></span>|  
|<span data-ttu-id="c526a-194">**Road-250**</span><span class="sxs-lookup"><span data-stu-id="c526a-194">**Road-250**</span></span>|<span data-ttu-id="c526a-195">**9.377.457,68 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-195">**$9,377,457.68**</span></span>|<span data-ttu-id="c526a-196">**4.032,47 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-196">**$4,032.47**</span></span>|<span data-ttu-id="c526a-197">**0,04%**</span><span class="sxs-lookup"><span data-stu-id="c526a-197">**0.04%**</span></span>|  
|<span data-ttu-id="c526a-198">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="c526a-198">**Mountain-100**</span></span>|<span data-ttu-id="c526a-199">**8.568.958,27 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-199">**$8,568,958.27**</span></span>|<span data-ttu-id="c526a-200">**139.393,27 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-200">**$139,393.27**</span></span>|<span data-ttu-id="c526a-201">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="c526a-201">**1.63%**</span></span>|  
|<span data-ttu-id="c526a-202">**Road-650**</span><span class="sxs-lookup"><span data-stu-id="c526a-202">**Road-650**</span></span>|<span data-ttu-id="c526a-203">**7.442.141,81 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-203">**$7,442,141.81**</span></span>|<span data-ttu-id="c526a-204">**39.698,30 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-204">**$39,698.30**</span></span>|<span data-ttu-id="c526a-205">**0,53 %**</span><span class="sxs-lookup"><span data-stu-id="c526a-205">**0.53%**</span></span>|  
|<span data-ttu-id="c526a-206">**Touring-1000**</span><span class="sxs-lookup"><span data-stu-id="c526a-206">**Touring-1000**</span></span>|<span data-ttu-id="c526a-207">**6.723.794,29 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-207">**$6,723,794.29**</span></span>|<span data-ttu-id="c526a-208">**166.144,17 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-208">**$166,144.17**</span></span>|<span data-ttu-id="c526a-209">**2,47%**</span><span class="sxs-lookup"><span data-stu-id="c526a-209">**2.47%**</span></span>|  
|<span data-ttu-id="c526a-210">**Road-550-W**</span><span class="sxs-lookup"><span data-stu-id="c526a-210">**Road-550-W**</span></span>|<span data-ttu-id="c526a-211">**3.668.383,88 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-211">**$3,668,383.88**</span></span>|<span data-ttu-id="c526a-212">**1.901,97 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-212">**$1,901.97**</span></span>|<span data-ttu-id="c526a-213">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="c526a-213">**0.05%**</span></span>|  
|<span data-ttu-id="c526a-214">**Road-350-W**</span><span class="sxs-lookup"><span data-stu-id="c526a-214">**Road-350-W**</span></span>|<span data-ttu-id="c526a-215">**3.665.932,31 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-215">**$3,665,932.31**</span></span>|<span data-ttu-id="c526a-216">**20.946,50 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-216">**$20,946.50**</span></span>|<span data-ttu-id="c526a-217">**0,57%**</span><span class="sxs-lookup"><span data-stu-id="c526a-217">**0.57%**</span></span>|  
|<span data-ttu-id="c526a-218">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="c526a-218">**HL Mountain Frame**</span></span>|<span data-ttu-id="c526a-219">**3.365.069,27 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-219">**$3,365,069.27**</span></span>|<span data-ttu-id="c526a-220">**174,11 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-220">**$174.11**</span></span>|<span data-ttu-id="c526a-221">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="c526a-221">**0.01%**</span></span>|  
|<span data-ttu-id="c526a-222">**Road-150**</span><span class="sxs-lookup"><span data-stu-id="c526a-222">**Road-150**</span></span>|<span data-ttu-id="c526a-223">**2.363.805,16 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-223">**$2,363,805.16**</span></span>|<span data-ttu-id="c526a-224">**$0,00**</span><span class="sxs-lookup"><span data-stu-id="c526a-224">**$0.00**</span></span>|<span data-ttu-id="c526a-225">**0,00%**</span><span class="sxs-lookup"><span data-stu-id="c526a-225">**0.00%**</span></span>|  
|<span data-ttu-id="c526a-226">**Touring-3000**</span><span class="sxs-lookup"><span data-stu-id="c526a-226">**Touring-3000**</span></span>|<span data-ttu-id="c526a-227">**2.046.508,26 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-227">**$2,046,508.26**</span></span>|<span data-ttu-id="c526a-228">**79.582,15 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-228">**$79,582.15**</span></span>|<span data-ttu-id="c526a-229">**3,89%**</span><span class="sxs-lookup"><span data-stu-id="c526a-229">**3.89%**</span></span>|  
  
 <span data-ttu-id="c526a-230">Im folgenden Beispiel wird der Begriff "tiefes Autoexists" veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c526a-230">The following example will illustrate the concept of deep Autoexists.</span></span> <span data-ttu-id="c526a-231">Im Beispiel filtern wir Top10SellingProducts mit dem [Product].[Product Line]-Attribut nach den in der [Mountain]-Gruppe enthaltenen Produkten.</span><span class="sxs-lookup"><span data-stu-id="c526a-231">In the example we are filtering Top10SellingProducts by [Product].[Product Line] attribute for those in [Mountain] group.</span></span> <span data-ttu-id="c526a-232">Beachten Sie, dass beide Attribute (Slicer und Achse) zur gleichen Dimension [Produkt] gehören.</span><span class="sxs-lookup"><span data-stu-id="c526a-232">Note that both attributes (slicer and axis) belong to the same dimension, [Product].</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `// Preferred10Products set removed for clarity`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Top10SellingProducts on 1`  
  
 `from [Adventure Works]`  
  
 `where [Product].[Product Line].[Mountain]`  
  
 <span data-ttu-id="c526a-233">Dadurch ergibt sich folgendes Resultset:</span><span class="sxs-lookup"><span data-stu-id="c526a-233">Produces the following result set:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="c526a-234">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="c526a-234">**Reseller Sales Amount**</span></span>|<span data-ttu-id="c526a-235">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="c526a-235">**Discount Amount**</span></span>|<span data-ttu-id="c526a-236">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="c526a-236">**PCT Discount**</span></span>|  
|<span data-ttu-id="c526a-237">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="c526a-237">**Mountain-200**</span></span>|<span data-ttu-id="c526a-238">**14.356.699,36 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-238">**$14,356,699.36**</span></span>|<span data-ttu-id="c526a-239">**19.012,71 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-239">**$19,012.71**</span></span>|<span data-ttu-id="c526a-240">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="c526a-240">**0.13%**</span></span>|  
|<span data-ttu-id="c526a-241">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="c526a-241">**Mountain-100**</span></span>|<span data-ttu-id="c526a-242">**8.568.958,27 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-242">**$8,568,958.27**</span></span>|<span data-ttu-id="c526a-243">**139.393,27 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-243">**$139,393.27**</span></span>|<span data-ttu-id="c526a-244">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="c526a-244">**1.63%**</span></span>|  
|<span data-ttu-id="c526a-245">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="c526a-245">**HL Mountain Frame**</span></span>|<span data-ttu-id="c526a-246">**3.365.069,27 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-246">**$3,365,069.27**</span></span>|<span data-ttu-id="c526a-247">**174,11 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-247">**$174.11**</span></span>|<span data-ttu-id="c526a-248">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="c526a-248">**0.01%**</span></span>|  
|<span data-ttu-id="c526a-249">**Mountain-300**</span><span class="sxs-lookup"><span data-stu-id="c526a-249">**Mountain-300**</span></span>|<span data-ttu-id="c526a-250">**1.907.249,38 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-250">**$1,907,249.38**</span></span>|<span data-ttu-id="c526a-251">**876,95 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-251">**$876.95**</span></span>|<span data-ttu-id="c526a-252">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="c526a-252">**0.05%**</span></span>|  
|<span data-ttu-id="c526a-253">**Mountain-500**</span><span class="sxs-lookup"><span data-stu-id="c526a-253">**Mountain-500**</span></span>|<span data-ttu-id="c526a-254">**1.067.327,31 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-254">**$1,067,327.31**</span></span>|<span data-ttu-id="c526a-255">**17.266,09 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-255">**$17,266.09**</span></span>|<span data-ttu-id="c526a-256">**1,62%**</span><span class="sxs-lookup"><span data-stu-id="c526a-256">**1.62%**</span></span>|  
|<span data-ttu-id="c526a-257">**Mountain-400-W**</span><span class="sxs-lookup"><span data-stu-id="c526a-257">**Mountain-400-W**</span></span>|<span data-ttu-id="c526a-258">**592.450,05 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-258">**$592,450.05**</span></span>|<span data-ttu-id="c526a-259">**303,49 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-259">**$303.49**</span></span>|<span data-ttu-id="c526a-260">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="c526a-260">**0.05%**</span></span>|  
|<span data-ttu-id="c526a-261">**LL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="c526a-261">**LL Mountain Frame**</span></span>|<span data-ttu-id="c526a-262">**521.864,42 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-262">**$521,864.42**</span></span>|<span data-ttu-id="c526a-263">**252,41 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-263">**$252.41**</span></span>|<span data-ttu-id="c526a-264">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="c526a-264">**0.05%**</span></span>|  
|<span data-ttu-id="c526a-265">**ML Mountain Frame-W**</span><span class="sxs-lookup"><span data-stu-id="c526a-265">**ML Mountain Frame-W**</span></span>|<span data-ttu-id="c526a-266">**482.953,16 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-266">**$482,953.16**</span></span>|<span data-ttu-id="c526a-267">**$206,95**</span><span class="sxs-lookup"><span data-stu-id="c526a-267">**$206.95**</span></span>|<span data-ttu-id="c526a-268">**0,04%**</span><span class="sxs-lookup"><span data-stu-id="c526a-268">**0.04%**</span></span>|  
|<span data-ttu-id="c526a-269">**ML Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="c526a-269">**ML Mountain Frame**</span></span>|<span data-ttu-id="c526a-270">**343.785,29 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-270">**$343,785.29**</span></span>|<span data-ttu-id="c526a-271">**161,82 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-271">**$161.82**</span></span>|<span data-ttu-id="c526a-272">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="c526a-272">**0.05%**</span></span>|  
|<span data-ttu-id="c526a-273">**Women's Mountain Shorts**</span><span class="sxs-lookup"><span data-stu-id="c526a-273">**Women's Mountain Shorts**</span></span>|<span data-ttu-id="c526a-274">**260.304,09 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-274">**$260,304.09**</span></span>|<span data-ttu-id="c526a-275">**6.675,56 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-275">**$6,675.56**</span></span>|<span data-ttu-id="c526a-276">**2,56%**</span><span class="sxs-lookup"><span data-stu-id="c526a-276">**2.56%**</span></span>|  
  
 <span data-ttu-id="c526a-277">Das obige Resultset enthält sieben Neueinträge für die Liste mit den Top10SellingProducts und Mountain-200, Mountain-100 sowie HL Mountain Frame wurden an den Anfang der Liste verschoben.</span><span class="sxs-lookup"><span data-stu-id="c526a-277">In the above result set we have seven newcomers to the list of Top10SellingProducts and Mountain-200, Mountain-100, and HL Mountain Frame have moved to the top of the list.</span></span> <span data-ttu-id="c526a-278">Im vorherigen Resultset befanden sich diese drei Werte an verschiedenen Stellen.</span><span class="sxs-lookup"><span data-stu-id="c526a-278">In the previous result set those three values were interspersed.</span></span>  
  
 <span data-ttu-id="c526a-279">Dies wird als tiefes Autoexists bezeichnet, da die Gruppe Top10SellingProducts so ausgewertet wird, dass die Slicingbedingungen der Abfrage erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="c526a-279">This is called Deep Autoexists, because the Top10SellingProducts set is evaluated to meet the slicing conditions of the query.</span></span> <span data-ttu-id="c526a-280">Tiefes Autoexists bedeutet, dass alle Ausdrücke so ausgewertet werden, dass nach Anwendung der Slicerausdrücke, der untergeordneten SELECT-Ausdrücke in der Achse usw. der tiefstmögliche Bereich erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="c526a-280">Deep Autoexists means that all expressions will be evaluated to meet the deepest possible space after applying the slicer expressions, the sub select expressions in the axis, and so on.</span></span>  
  
 <span data-ttu-id="c526a-281">Eventuell soll es jedoch auch möglich sein, die Analyse der Top10SellingProducts als Entsprechung zu Preferred10Products auszuführen wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c526a-281">However, one might want to be able to do the analysis over the Top10SellingProducts as equivalent to Preferred10Products, as in the following example:</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `set Preferred10Products as '`  
  
 `{[Product].[Model Name].&[Mountain-200],`  
  
 `[Product].[Model Name].&[Road-250],`  
  
 `[Product].[Model Name].&[Mountain-100],`  
  
 `[Product].[Model Name].&[Road-650],`  
  
 `[Product].[Model Name].&[Touring-1000],`  
  
 `[Product].[Model Name].&[Road-550-W],`  
  
 `[Product].[Model Name].&[Road-350-W],`  
  
 `[Product].[Model Name].&[HL Mountain Frame],`  
  
 `[Product].[Model Name].&[Road-150],`  
  
 `[Product].[Model Name].&[Touring-3000]`  
  
 `}'`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Preferred10Products on 1`  
  
 `from [Adventure Works]`  
  
 `where [Product].[Product Line].[Mountain]`  
  
 <span data-ttu-id="c526a-282">Dadurch ergibt sich folgendes Resultset:</span><span class="sxs-lookup"><span data-stu-id="c526a-282">Produces the following result set:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="c526a-283">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="c526a-283">**Reseller Sales Amount**</span></span>|<span data-ttu-id="c526a-284">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="c526a-284">**Discount Amount**</span></span>|<span data-ttu-id="c526a-285">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="c526a-285">**PCT Discount**</span></span>|  
|<span data-ttu-id="c526a-286">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="c526a-286">**Mountain-200**</span></span>|<span data-ttu-id="c526a-287">**14.356.699,36 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-287">**$14,356,699.36**</span></span>|<span data-ttu-id="c526a-288">**19.012,71 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-288">**$19,012.71**</span></span>|<span data-ttu-id="c526a-289">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="c526a-289">**0.13%**</span></span>|  
|<span data-ttu-id="c526a-290">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="c526a-290">**Mountain-100**</span></span>|<span data-ttu-id="c526a-291">**8.568.958,27 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-291">**$8,568,958.27**</span></span>|<span data-ttu-id="c526a-292">**139.393,27 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-292">**$139,393.27**</span></span>|<span data-ttu-id="c526a-293">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="c526a-293">**1.63%**</span></span>|  
|<span data-ttu-id="c526a-294">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="c526a-294">**HL Mountain Frame**</span></span>|<span data-ttu-id="c526a-295">**3.365.069,27 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-295">**$3,365,069.27**</span></span>|<span data-ttu-id="c526a-296">**174,11 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-296">**$174.11**</span></span>|<span data-ttu-id="c526a-297">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="c526a-297">**0.01%**</span></span>|  
  
 <span data-ttu-id="c526a-298">Nach den oben aufgeführten Ergebnissen führt das Slicing zu einem Ergebnis, das nur die Produkte von Preferred10Products enthält, die Teil der Gruppe [Mountain] in [Product].[Product Line] sind. Dies entspricht den Erwartungen, da Preferred10Products ein konstanter Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="c526a-298">In the above results, the slicing gives a result that contains only those products from Preferred10Products that are part of the [Mountain] group in [Product].[Product Line]; as expected, because Preferred10Products is a constant expression.</span></span>  
  
 <span data-ttu-id="c526a-299">Dieses Resultset wird auch als "flaches Autoexists" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c526a-299">This result set is also understood as Shallow Autoexists.</span></span> <span data-ttu-id="c526a-300">Das liegt daran, dass der Ausdruck vor der Slicingklausel ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="c526a-300">This is because the expression is evaluated before the slicing clause.</span></span> <span data-ttu-id="c526a-301">Im vorherigen Beispiel war der Ausdruck ein konstanter Ausdruck, damit das Konzept anschaulicher eingeführt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="c526a-301">In the previous example, the expression was a constant expression for illustration purposes in order to introduce the concept.</span></span>  
  
 <span data-ttu-id="c526a-302">Das Autoexists-Verhalten kann mit der `Autoexists`-Eigenschaft der Verbindungszeichenfolge auf Sitzungsebene geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c526a-302">Autoexists behavior can be modified at the session level using the `Autoexists` connection string property.</span></span> <span data-ttu-id="c526a-303">Im folgenden Beispiel wird zunächst eine neue Sitzung geöffnet und dann die *Autoexists=3* -Eigenschaft zur Verbindungszeichenfolge hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c526a-303">The following example begins by opening a new session and adding the *Autoexists=3* property to the connection string.</span></span> <span data-ttu-id="c526a-304">Sie müssen eine neue Verbindung öffnen, um das Beispiel ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="c526a-304">You must open a new connection in order to do the example.</span></span> <span data-ttu-id="c526a-305">Sobald die Verbindung mit der Autoexist-Einstellung hergestellt ist, bleibt diese Einstellung bis zum Ende der Verbindung wirksam.</span><span class="sxs-lookup"><span data-stu-id="c526a-305">Once the connection is established with the Autoexist setting it will remain in effect until that connection is finished.</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `//Preferred10Products set removed for clarity`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Top10SellingProducts on 1`  
  
 `from [Adventure Works]`  
  
 `where [Product].[Product Line].[Mountain]`  
  
 <span data-ttu-id="c526a-306">Das folgende Resultset zeigt jetzt das flache Verhalten von Autoexists.</span><span class="sxs-lookup"><span data-stu-id="c526a-306">The following result set now shows the shallow behavior of Autoexists.</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="c526a-307">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="c526a-307">**Reseller Sales Amount**</span></span>|<span data-ttu-id="c526a-308">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="c526a-308">**Discount Amount**</span></span>|<span data-ttu-id="c526a-309">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="c526a-309">**PCT Discount**</span></span>|  
|<span data-ttu-id="c526a-310">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="c526a-310">**Mountain-200**</span></span>|<span data-ttu-id="c526a-311">**14.356.699,36 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-311">**$14,356,699.36**</span></span>|<span data-ttu-id="c526a-312">**19.012,71 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-312">**$19,012.71**</span></span>|<span data-ttu-id="c526a-313">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="c526a-313">**0.13%**</span></span>|  
|<span data-ttu-id="c526a-314">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="c526a-314">**Mountain-100**</span></span>|<span data-ttu-id="c526a-315">**8.568.958,27 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-315">**$8,568,958.27**</span></span>|<span data-ttu-id="c526a-316">**139.393,27 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-316">**$139,393.27**</span></span>|<span data-ttu-id="c526a-317">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="c526a-317">**1.63%**</span></span>|  
|<span data-ttu-id="c526a-318">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="c526a-318">**HL Mountain Frame**</span></span>|<span data-ttu-id="c526a-319">**3.365.069,27 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-319">**$3,365,069.27**</span></span>|<span data-ttu-id="c526a-320">**174,11 €**</span><span class="sxs-lookup"><span data-stu-id="c526a-320">**$174.11**</span></span>|<span data-ttu-id="c526a-321">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="c526a-321">**0.01%**</span></span>|  
  
 <span data-ttu-id="c526a-322">Das autoes-Verhalten kann mithilfe des Parameters autoist = [1 | 2 | 3] in der Verbindungs Zeichenfolge geändert werden. Weitere Informationen finden Sie [unter Unterstützte XMLA-Eigenschaften &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/propertylist-element-supported-xmla-properties) und <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A> zur Parameter Verwendung.</span><span class="sxs-lookup"><span data-stu-id="c526a-322">Autoexists behavior can be modified by using the AUTOEXISTS=[1|2|3] parameter in the connection string; see [Supported XMLA Properties &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/propertylist-element-supported-xmla-properties) and <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A> for parameter usage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c526a-323">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c526a-323">See Also</span></span>  
 <span data-ttu-id="c526a-324">[Wichtige Konzepte in MDX-&#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="c526a-324">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="c526a-325">[Cube-Bereich](cube-space.md) </span><span class="sxs-lookup"><span data-stu-id="c526a-325">[Cube Space](cube-space.md) </span></span>  
 <span data-ttu-id="c526a-326">[Tupel](tuples.md) </span><span class="sxs-lookup"><span data-stu-id="c526a-326">[Tuples](tuples.md) </span></span>  
 <span data-ttu-id="c526a-327">[Arbeiten mit Membern, Tupeln und Mengen &#40;MDX-&#41;](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="c526a-327">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 <span data-ttu-id="c526a-328">[Visuelle Gesamtsummen und nicht visuelle Gesamtwerte](visual-totals-and-non-visual-totals.md) </span><span class="sxs-lookup"><span data-stu-id="c526a-328">[Visual Totals and Non Visual Totals](visual-totals-and-non-visual-totals.md) </span></span>  
 <span data-ttu-id="c526a-329">[MDX-Sprachreferenz &#40;MDX-&#41;](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="c526a-329">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 [<span data-ttu-id="c526a-330">Multidimensional Expressions &#40;MDX&#41; – Referenz</span><span class="sxs-lookup"><span data-stu-id="c526a-330">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
