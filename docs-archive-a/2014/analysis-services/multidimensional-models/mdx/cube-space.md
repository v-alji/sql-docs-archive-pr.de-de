---
title: Cube-Bereich | Microsoft-Dokumentation
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c3a012b4-9ca0-4fb8-9c26-5ecc0e2e2b2b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0a6a6da73815f06aa5ab80f6ad5a9d06227ed842
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616742"
---
# <a name="cube-space"></a><span data-ttu-id="fef99-102">Cuberaum</span><span class="sxs-lookup"><span data-stu-id="fef99-102">Cube Space</span></span>
  <span data-ttu-id="fef99-103">Der Cuberaum ist das Produkt aus den Elementen der Attributhierarchien eines Cubes und den Measures des Cubes.</span><span class="sxs-lookup"><span data-stu-id="fef99-103">Cube space is the product of the members of a cube's attribute hierarchies with the cube's measures.</span></span> <span data-ttu-id="fef99-104">Daher wird der Cuberaum durch das Kombinationsprodukt aller Attributhierarchieelemente im Cube und den Measures des Cubes bestimmt und definiert die maximale Größe des Cubes.</span><span class="sxs-lookup"><span data-stu-id="fef99-104">Therefore, the cube space is determined by the combinatorial product of all attribute hierarchy members in the cube and the cube's measures and defines the maximum size of the cube.</span></span> <span data-ttu-id="fef99-105">Beachten Sie, dass dieser Raum alle potenziellen Kombinationen von Attributhierarchieelementen umfasst, einschließlich Kombinationen, die in der wirklichen Welt unmöglich sind, z. B. Kombinationen aus der Stadt Paris und den Ländern England, Spanien, Japan oder Indien.</span><span class="sxs-lookup"><span data-stu-id="fef99-105">It is important to note that this space includes all possible combinations of attribute hierarchy members; even combinations that might be deem as impossible in the real world i.e. combinations where the city is Paris and the countries are England or Spain or Japan or India or elsewhere.</span></span>  
  
## <a name="autoexists-and-cube-space"></a><span data-ttu-id="fef99-106">Autoexists und Cuberaum</span><span class="sxs-lookup"><span data-stu-id="fef99-106">Autoexists and cube space</span></span>  
 <span data-ttu-id="fef99-107">*Autoexists* schränkt den Cuberaum auf solche Zellen ein, die tatsächlich vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="fef99-107">The concept of *autoexists* limits this cube space to those cells that actually exist.</span></span> <span data-ttu-id="fef99-108">Elemente einer Attributhierarchie in einer Dimension sind möglicherweise nicht gemeinsam mit Elementen einer anderen Attributhierarchie in der gleichen Dimension vorhanden.</span><span class="sxs-lookup"><span data-stu-id="fef99-108">Members of an attribute hierarchy in a dimension may not exist with members of another attribute hierarchy in the same dimension.</span></span>  
  
 <span data-ttu-id="fef99-109">Bei einem Cube z. B., der eine City-Attributhierarchie, eine Country-Attributhierarchie und eine Internet Sales Amount-Measure aufweist, schließt der Cuberaum nur solche Elemente ein, die gemeinsam vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="fef99-109">For example, if you have a cube that has a City attribute hierarchy, a Country attribute hierarchy, and an Internet Sales Amount measure, the space of this cube only includes those members that exist with each other.</span></span> <span data-ttu-id="fef99-110">Wenn beispielsweise die City-Attributhierarchie die Städte New York, London, Paris, Tokyo und Melbourne und die Country-Attributhierarchie die Länder United States, United Kingdom, France, Japan, and Australia umfasst, schließt der Cuberaum nicht den Raum (die Zelle) am Schnittpunkt von Paris und United States ein.</span><span class="sxs-lookup"><span data-stu-id="fef99-110">For example, if the City attribute hierarchy includes the cities New York, London, Paris, Tokyo, and Melbourne; and the Country attribute hierarchy includes the countries United States, United Kingdom, France, Japan, and Australia; then the space of the cube does not include the space (cell) at the intersection of Paris and United States.</span></span>  
  
 <span data-ttu-id="fef99-111">Beim Abfragen von nicht vorhandenen Zellen wird NULL zurückgegeben, d. h., nicht vorhandene Zellen können keine Berechnungen enthalten, und Sie können auch keine Berechnungen definieren, die in sie schreiben.</span><span class="sxs-lookup"><span data-stu-id="fef99-111">When querying cells that do not exist, non-existing cells return nulls; that is, they cannot contain calculations and you cannot define a calculation that writes to this space.</span></span> <span data-ttu-id="fef99-112">Die folgende Anweisung beinhaltet beispielsweise Zellen, die nicht vorhanden sind:</span><span class="sxs-lookup"><span data-stu-id="fef99-112">For example, the following statement includes cells that do not exist.</span></span>  
  
```  
SELECT [Customer].[Gender].[Gender].Members ON COLUMNS,  
{[Customer].[Customer].[Aaron A. Allen]  
   ,[Customer].[Customer].[Abigail Clark]} ON ROWS   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="fef99-113">Diese Abfrage verwendet die [Members (Menge) (MDX)](/sql/mdx/members-set-mdx) -Funktion, um eine Menge von Elementen der Gender-Attributhierarchie auf der Spaltenachse zurückzugeben und diese Menge mit der angegebenen Menge von Elementen der Customer-Attributhierarchie auf der Zeilenachse zu kreuzen.</span><span class="sxs-lookup"><span data-stu-id="fef99-113">This query uses the [Members (Set) (MDX)](/sql/mdx/members-set-mdx) function to return the set of members of the Gender attribute hierarchy on the column axis, and crosses this set with the specified set of members from the Customer attribute hierarchy on the row axis.</span></span>  
  
 <span data-ttu-id="fef99-114">Beim Ausführen der vorherigen Abfrage zeigt die Zelle am Schnittpunkt zwischen Aaron A. Allen und Female eine Null an.</span><span class="sxs-lookup"><span data-stu-id="fef99-114">When you execute the previous query, the cell at the intersection of Aaron A. Allen and Female displays a null.</span></span> <span data-ttu-id="fef99-115">Entsprechend zeigt die Zelle am Schnittpunkt zwischen Abigail Clark und Male ebenfalls eine Null an.</span><span class="sxs-lookup"><span data-stu-id="fef99-115">Similarly, the cell at the intersection of Abigail Clark and Male displays a null.</span></span> <span data-ttu-id="fef99-116">Diese Zellen sind nicht vorhanden und können daher keine Werte enthalten, sie können jedoch im Ergebnis einer Abfrage angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="fef99-116">These cells do not exist and cannot contain a value, but cells that do not exist can appear in the result returned by a query.</span></span>  
  
 <span data-ttu-id="fef99-117">Wenn Sie die [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) -Funktion verwenden, um das Kreuzprodukt von Attributhierarchie-Elementen und Attributhierarchien in der gleichen Dimension zurückzugeben, beschränkt Auto-exist das zurückgegebene Ergebnis auf die Menge der Tupel, die tatsächlich vorhanden sind, und gibt nicht das vollständige kartesische Produkt zurück.</span><span class="sxs-lookup"><span data-stu-id="fef99-117">When you use the [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) function to return the cross-product of attribute hierarchy members from attribute hierarchies in the same dimension, auto-exists limits those tuples being returned to the set of tuples that actually exist, rather than returning a full Cartesian product.</span></span> <span data-ttu-id="fef99-118">Führen Sie z. B. die folgenden Abfrage aus, und überprüfen Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="fef99-118">For example, run and then examine the results from the execution of the following query.</span></span>  
  
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
>  <span data-ttu-id="fef99-119">Beachten Sie, dass 0 hier für die Spaltenachse steht (als Kurzform für axis(0)).</span><span class="sxs-lookup"><span data-stu-id="fef99-119">Notice that 0 is used to designate the column axis, which is shorthand for axis(0) - which is the column axis.</span></span>  
  
 <span data-ttu-id="fef99-120">Die vorherige Abfrage gibt nur Zellen für Elemente der Attributhierarchien in der Abfrage zurück, die gemeinsam vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="fef99-120">The previous query only returns cells for members from each attribute hierarchy in the query that exist with each other.</span></span> <span data-ttu-id="fef99-121">Die vorherige Abfrage kann auch mithilfe der neuen \*-Variante der [ \* (Crossjoin) (MDX)](/sql/mdx/crossjoin-mdx) -Funktion geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="fef99-121">The previous query can also be written using the new \* variant of the [\* (Crossjoin) (MDX)](/sql/mdx/crossjoin-mdx) function.</span></span>  
  
```  
SELECT   
   [Customer].[Country].[United States] *   
      [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
 <span data-ttu-id="fef99-122">Die vorherige Abfrage kann auch wie folgt formuliert werden:</span><span class="sxs-lookup"><span data-stu-id="fef99-122">The previous query could also be written in the following manner:</span></span>  
  
```  
SELECT [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE (Measures.[Internet Sales Amount],  
   [Customer].[Country].[United States])  
```  
  
 <span data-ttu-id="fef99-123">Die zurückgegebenen Zellenwerte sind identisch, die Metadaten im Resultset sind jedoch verschieden.</span><span class="sxs-lookup"><span data-stu-id="fef99-123">The cells values returned will be identical, although the metadata in the result set will be different.</span></span> <span data-ttu-id="fef99-124">Beispielsweise wurde in der vorherigen Abfrage die Country-Hierarchie auf die Slicerachse verschoben (in die WHERE-Klausel), sodass sie nicht explizit im Resultset angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fef99-124">For example, with the previous query, the Country hierarchy was moved to the slicer axis (in the WHERE clause) and therefore does not appear explicitly in the result set.</span></span>  
  
 <span data-ttu-id="fef99-125">Jede dieser drei vorherigen Abfragen veranschaulicht die Auswirkung des Auto-es-Verhaltens in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fef99-125">Each of these three previous queries demonstrates the effect of the auto-exists behavior in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="user-defined-hierarchies-and-cube-space"></a><span data-ttu-id="fef99-126">Benutzerdefinierte Hierarchien und Cuberaum</span><span class="sxs-lookup"><span data-stu-id="fef99-126">User-Defined Hierarchies and Cube Space</span></span>  
 <span data-ttu-id="fef99-127">In den vorherigen Beispielen in diesem Thema wurden Positionen im Cuberaum mithilfe von Attributhierarchien definiert.</span><span class="sxs-lookup"><span data-stu-id="fef99-127">The previous examples in this topic define positions in cube space by using attribute hierarchies.</span></span> <span data-ttu-id="fef99-128">Es ist jedoch auch möglich, Positionen um Cuberaum mithilfe von benutzerdefinierten Hierarchien zu definieren, die basierend auf Attributhierarchien in einer Dimension definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="fef99-128">However, you can also define a position in cube space by using user-defined hierarchies that have been defined based on attribute hierarchies in a dimension.</span></span> <span data-ttu-id="fef99-129">Eine benutzerdefinierte Hierarchie ist eine Hierarchie von Attributhierarchien, die es dem Benutzer ermöglicht, Cubedaten zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="fef99-129">A user-defined hierarchy is a hierarchy of attribute hierarchies designed to facilitate browsing of cube data by users.</span></span>  
  
 <span data-ttu-id="fef99-130">Beispielsweise ließe sich die `CROSSJOIN`-Abfrage im vorherigen Abschnitt auch wie folgt formulieren:</span><span class="sxs-lookup"><span data-stu-id="fef99-130">For example, the `CROSSJOIN` query in the previous section could also have been written as follows:</span></span>  
  
```  
SELECT CROSSJOIN  
   (  
      {[Customer].[Country].[United States]},  
         [Customer].[Customer Geography].[State-Province].Members  
   )   
ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
 <span data-ttu-id="fef99-131">In der vorherigen Abfrage wurde die benutzerdefinierte Customer Geography-Hierarchie innerhalb der Customer-Dimension zum Definieren der Position im Cuberaum verwendet, die zuvor über eine Attributhierarchie definiert worden war.</span><span class="sxs-lookup"><span data-stu-id="fef99-131">In the previous query, the Customer Geography user-defined hierarchy within the Customer dimension is used to define the position in cube space that was previously defined by using an attribute hierarchy.</span></span> <span data-ttu-id="fef99-132">Die gleiche Position im Cuberaum kann sowohl mithilfe von Attributhierarchien als auch mithilfe von benutzerdefinierten Hierarchien definiert werden.</span><span class="sxs-lookup"><span data-stu-id="fef99-132">The identical position in cube space can be defined by using either attribute hierarchies or user-defined hierarchies.</span></span>  
  
##  <a name="attribute-relationships-and-cube-space"></a><a name="AttribRelationships"></a> <span data-ttu-id="fef99-133">Attributbeziehungen und Cuberaum</span><span class="sxs-lookup"><span data-stu-id="fef99-133">Attribute Relationships and Cube Space</span></span>  
 <span data-ttu-id="fef99-134">Das Definieren von Attributbeziehungen zwischen verknüpften Attributen verbessert die Abfrageleistung (durch vereinfachte Erstellung von entsprechenden Aggregationen) und wirkt sich auf das Element einer verknüpften Attributhierarchie aus, das zusammen mit einem Attributhierarchie-Element auftritt.</span><span class="sxs-lookup"><span data-stu-id="fef99-134">Defining attribute relationships between related attributes improves query performance (by facilitating the creation of appropriate aggregations) and affects the member of a related attribute hierarchy that appears with an attribute hierarchy member.</span></span> <span data-ttu-id="fef99-135">Wenn Sie beispielsweise ein Tupel definieren, das ein Element der City-Attributhierarchie einschließt, und das Tupel nicht explizit die Country-Attributelemente definiert, wäre zu erwarten, dass das Element der Country-Attributhierarchie das verknüpfte Element der Country-Attributhierarchie darstellt.</span><span class="sxs-lookup"><span data-stu-id="fef99-135">For example, when you define a tuple that includes a member from the City attribute hierarchy and the tuple does not explicitly define the Country attribute hierarchy member, you might expect that the default Country attribute hierarchy member would be the related member of the Country attribute hierarchy.</span></span> <span data-ttu-id="fef99-136">Dies ist jedoch nicht der Fall, wenn eine Attributbeziehung zwischen der City-Attributhierarchie und der Country-Attributhierarchie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="fef99-136">However, this is only true if an attribute relationship is defined between the City attribute hierarchy and the Country attribute hierarchy.</span></span>  
  
 <span data-ttu-id="fef99-137">Im folgenden Beispiel wird das Element einer verknüpften Attributhierarchie zurückgegeben, die nicht explizit in der Abfrage eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="fef99-137">The following example returns the member of a related attribute hierarchy that is not included explicitly in the query.</span></span>  
  
```  
WITH MEMBER Measures.x AS   
   Customer.Country.CurrentMember.Name  
SELECT Measures.x ON 0,  
Customer.City.Members ON 1  
FROM [Adventure Works]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="fef99-138">Beachten Sie, dass das `WITH` -Schlüsselwort mit der [CurrentMember (MDX)](/sql/mdx/current-mdx) -Funktion und der [Name (MDX)](/sql/mdx/members-string-mdx) -Funktion verwendet wird, um ein berechnetes Element zur Verwendung in der Abfrage zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fef99-138">Notice that the `WITH` keyword is used with the [CurrentMember (MDX)](/sql/mdx/current-mdx) and [Name (MDX)](/sql/mdx/members-string-mdx) functions to create a calculated member for use in the query.</span></span> <span data-ttu-id="fef99-139">Weitere Informationen finden Sie unter [Die grundlegende MDX-Abfrage&#40;MDX&#41;](mdx-query-the-basic-query.md).</span><span class="sxs-lookup"><span data-stu-id="fef99-139">For more information, see [The Basic MDX Query &#40;MDX&#41;](mdx-query-the-basic-query.md).</span></span>  
  
 <span data-ttu-id="fef99-140">In der vorherigen Abfrage wurde der Name des Elements der Country-Attributhierarchie zurückgegeben, das mit jedem Element der State-Attributhierarchie verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="fef99-140">In the previous query, the name of the member of the Country attribute hierarchy that is associated with each member of the State attribute hierarchy is returned.</span></span> <span data-ttu-id="fef99-141">Das erwartete Country-Element wird angezeigt (weil eine Attributbeziehung zwischen City- und Country-Attributen definiert ist).</span><span class="sxs-lookup"><span data-stu-id="fef99-141">The expected Country member appears (because an attribute relationship is defined between the City and Country attributes).</span></span> <span data-ttu-id="fef99-142">Ohne Attributbeziehung zwischen Attributhierarchien der gleichen Dimension wäre das (Alle)-Element zurückgegeben worden, wie die folgende Abfrage veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="fef99-142">However, if no attribute relationship were defined between attribute hierarchies in the same dimension, the (All) member would be returned, as illustrated in the following query.</span></span>  
  
```  
WITH MEMBER Measures.x AS   
   Customer.Education.Currentmember.Name  
SELECT Measures.x  ON 0,   
Customer.City.Members ON 1  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="fef99-143">In der vorherigen Abfrage wird das (Alle)-Element ("All Customers") zurückgegeben, weil keine Beziehung zwischen Education und City besteht.</span><span class="sxs-lookup"><span data-stu-id="fef99-143">In the previous query, the (All) member ("All Customers") is returned, because there is no relationship between Education and City.</span></span> <span data-ttu-id="fef99-144">Daher ist das (Alle)-Element der Education-Attributhierarchie das Standardelement der Education-Attributhierarchie, das in jedem Tupel verwendet wird, in dem die City-Attributhierarchie vorkommt und in dem kein Education-Element explizit bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="fef99-144">Therefore, the (All) member of the Education attribute hierarchy would be the default member of the Education attribute hierarchy used in any tuple involving the City attribute hierarchy where an Education member is not explicitly provided.</span></span>  
  
## <a name="calculation-context"></a><span data-ttu-id="fef99-145">Berechnungskontext</span><span class="sxs-lookup"><span data-stu-id="fef99-145">Calculation Context</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fef99-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fef99-146">See Also</span></span>  
 <span data-ttu-id="fef99-147">[Wichtige Konzepte in MDX-&#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="fef99-147">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="fef99-148">[Tupel](tuples.md) </span><span class="sxs-lookup"><span data-stu-id="fef99-148">[Tuples](tuples.md) </span></span>  
 <span data-ttu-id="fef99-149">[Autoexists](autoexists.md) </span><span class="sxs-lookup"><span data-stu-id="fef99-149">[Autoexists](autoexists.md) </span></span>  
 <span data-ttu-id="fef99-150">[Arbeiten mit Membern, Tupeln und Mengen &#40;MDX-&#41;](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="fef99-150">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 <span data-ttu-id="fef99-151">[Visuelle Gesamtsummen und nicht visuelle Gesamtwerte](visual-totals-and-non-visual-totals.md) </span><span class="sxs-lookup"><span data-stu-id="fef99-151">[Visual Totals and Non Visual Totals](visual-totals-and-non-visual-totals.md) </span></span>  
 <span data-ttu-id="fef99-152">[MDX-Sprachreferenz &#40;MDX-&#41;](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="fef99-152">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 [<span data-ttu-id="fef99-153">Multidimensional Expressions &#40;MDX&#41; – Referenz</span><span class="sxs-lookup"><span data-stu-id="fef99-153">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
