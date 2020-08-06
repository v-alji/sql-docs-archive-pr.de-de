---
title: Tupel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 35b629ae-b1ef-44b1-b556-96956aeb56e7
author: minewiskan
ms.author: owend
ms.openlocfilehash: c39d03d60cb66f3b2e26b2e660bd85f4e5e9d4ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721893"
---
# <a name="tuples"></a><span data-ttu-id="841e1-102">Tupel</span><span class="sxs-lookup"><span data-stu-id="841e1-102">Tuples</span></span>
  <span data-ttu-id="841e1-103">Ein Tupel dient zur eindeutigen Identifizierung eines Slices von Daten aus einem Cube.</span><span class="sxs-lookup"><span data-stu-id="841e1-103">A tuple uniquely identifies a slice of data from a cube.</span></span> <span data-ttu-id="841e1-104">Das Tupel wird durch eine Kombination aus Dimensionselementen gebildet, sofern nicht zwei oder mehr Elemente zur gleichen Hierarchie gehören.</span><span class="sxs-lookup"><span data-stu-id="841e1-104">The tuple is formed by a combination of dimension members, as long as there are no two or more members that belong to the same hierarchy.</span></span>  
  
## <a name="implicit-or-default-attribute-members-in-a-tuple"></a><span data-ttu-id="841e1-105">Implizite oder Standardattributelemente in einem Tupel</span><span class="sxs-lookup"><span data-stu-id="841e1-105">Implicit or default attribute members in a tuple</span></span>  
 <span data-ttu-id="841e1-106">Zum Definieren eines Tupels in einer MDX-Abfrage oder in einem MDX-Ausdruck ist es nicht erforderlich, die Attributelemente aus allen Attributhierarchien explizit einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="841e1-106">When defining a tuple in an MDX query or expression, you do not need to explicitly include the attribute member from every attribute hierarchy.</span></span> <span data-ttu-id="841e1-107">Wenn ein Element aus einer Attributhierarchie nicht explizit in eine Abfrage oder einen Ausdruck eingeschlossen ist, wird das Standardelement der betreffenden Attributhierarchie implizit in das Tupel eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="841e1-107">If a member from an attribute hierarchy is not explicitly included in a query or an expression, the default member for that attribute hierarchy is the attribute member implicitly included in the tuple.</span></span> <span data-ttu-id="841e1-108">Sofern nicht anderweitig explizit in einem Cube definiert, ist das Standardelement jeder Attributhierarchie das (Alle)-Element, falls ein solches vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="841e1-108">Unless otherwise explicitly defined in a cube, the default member for every attribute hierarchy is the (All) member, if an (All) member exists.</span></span> <span data-ttu-id="841e1-109">Wenn kein (Alle)-Element innerhalb einer Attributhierarchie vorhanden ist, wird als Standardelement ein Element der obersten Ebene der Attributhierarchie verwendet.</span><span class="sxs-lookup"><span data-stu-id="841e1-109">If an (All) member does not exist within an attribute hierarchy, the default member is a member of the attribute hierarchy's top level.</span></span> <span data-ttu-id="841e1-110">Sofern kein anderes Standardmeasure explizit definiert wurde, wird als Standardmeasure das erste im Cube angegebene Measure verwendet.</span><span class="sxs-lookup"><span data-stu-id="841e1-110">The default measure is the first measure specified in the cube, unless a default measure is explicitly defined.</span></span> <span data-ttu-id="841e1-111">Weitere Informationen finden Sie unter [Definieren eines Standardelements](../attribute-properties-define-a-default-member.md) und [DefaultMember &#40;MDX&#41;](/sql/mdx/defaultmember-mdx).</span><span class="sxs-lookup"><span data-stu-id="841e1-111">For more information, see [Define a Default Member](../attribute-properties-define-a-default-member.md) and [DefaultMember &#40;MDX&#41;](/sql/mdx/defaultmember-mdx).</span></span>  
  
 <span data-ttu-id="841e1-112">Beispielsweise identifiziert das folgende Tupel eine einzelne Zelle in der Adventure Works-Datenbank, wobei nur ein einziges Element der Measuredimension explizit definiert ist.</span><span class="sxs-lookup"><span data-stu-id="841e1-112">For example, the following tuple identifies a single cell in the Adventure Works database by explicitly defining only a single member of the Measures dimension.</span></span>  
  
```  
(Measures.[Reseller Sales Amount])  
```  
  
 <span data-ttu-id="841e1-113">Im vorherigen Beispiel wurde die Zelle eindeutig identifiziert, die das Reseller Sales Amount-Element der Measure-Dimension und das Standardelement jeder Attributhierarchie im Cube enthält.</span><span class="sxs-lookup"><span data-stu-id="841e1-113">The previous example uniquely identifies the cell consisting of the Reseller Sales Amount member from the Measures dimension and the default member from every attribute hierarchy in the cube.</span></span> <span data-ttu-id="841e1-114">Das Standardelement jeder Attributhierarchie ist dabei das jeweilige (Alle)-Element. Eine Ausnahme stellt die Destination Currency-Attributhierarchie dar.</span><span class="sxs-lookup"><span data-stu-id="841e1-114">The default member is the (All) member for every attribute hierarchy other than the Destination Currency attribute hierarchy.</span></span> <span data-ttu-id="841e1-115">Das Standardelement der Destination Currency-Hierarchie ist das US Dollar-Element (dieses Standardelement ist im MDX-Skript des Adventure Works-Cube definiert).</span><span class="sxs-lookup"><span data-stu-id="841e1-115">The default member for the Destination Currency hierarchy is the US Dollar member (this default member is defined in the MDX script for the Adventure Works cube).</span></span>  
  
 <span data-ttu-id="841e1-116">Die folgende Abfrage gibt den Wert der Zelle zurück, auf die sich das im vorherigen Beispiel angegebene Tupel bezog ($80,450.596.98).</span><span class="sxs-lookup"><span data-stu-id="841e1-116">The following query returns the value for the cell referenced by the tuple specified in the previous example, ($80,450.596.98).</span></span>  
  
```  
SELECT   
Measures.[Reseller Sales Amount] ON COLUMNS   
FROM [Adventure Works]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="841e1-117">Wenn Sie in einer Abfrage eine Achse für eine Menge angeben (in diesem Fall bestehend aus einem einzigen Tupel), müssen Sie zunächst eine Menge für die Spaltenachse und dann eine Menge für die Zeilenachse angeben.</span><span class="sxs-lookup"><span data-stu-id="841e1-117">When you specify an axis for a set (in this case composed of a single tuple) in a query, you must begin by specifying a set for the column axis before specifying a set for the row axis.</span></span> <span data-ttu-id="841e1-118">Die Spaltenachse wird auch als *axis(0)* oder einfach *0*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="841e1-118">The column axis can also be referred to as *axis(0)* or simply *0*.</span></span> <span data-ttu-id="841e1-119">Weitere Informationen zu MDX-Abfragen finden Sie unter [Die grundlegende MDX-Abfrage &#40;MDX&#41;](mdx-query-the-basic-query.md).</span><span class="sxs-lookup"><span data-stu-id="841e1-119">For more information about MDX queries, see [The Basic MDX Query &#40;MDX&#41;](mdx-query-the-basic-query.md).</span></span>  
  
### <a name="tuples-as-values-or-member-references"></a><span data-ttu-id="841e1-120">Tupel als Werte oder Elementverweise</span><span class="sxs-lookup"><span data-stu-id="841e1-120">Tuples as values or member references</span></span>  
 <span data-ttu-id="841e1-121">Wie das vorherige Beispiel zeigte, können Sie ein Tupel in einer Abfrage verwenden, um den Wert in der Zelle zurückzugeben, auf die das Tupel verweist.</span><span class="sxs-lookup"><span data-stu-id="841e1-121">You can use a tuple in a query to return the value in the cell that is referenced by the tuple, as in the previous example.</span></span> <span data-ttu-id="841e1-122">Sie können ein Tupel aber auch in einem Ausdruck verwenden, um explizit auf das im Tupel angegebene Element zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="841e1-122">Or you can use a tuple in an expression to explicitly refer to the members specified in the tuple.</span></span> <span data-ttu-id="841e1-123">Abfragen und Ausdrücke können mithilfe von Funktionen Tupel zurückgeben oder verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="841e1-123">The query or the expression can utilize functions that either return or consume tuples.</span></span> <span data-ttu-id="841e1-124">Mit einem Tupel kann entweder auf den Wert einer Zelle, die das Tupel angibt, verwiesen werden oder, bei Verwendung in einer Funktion, eine Kombination von Elementen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="841e1-124">A tuple can be used to either refer to the value of the cell that the tuple specifies, or to specify a combination of members when utilized in a function.</span></span>  
  
### <a name="tuple-dimensionality"></a><span data-ttu-id="841e1-125">Tupeldimensionalität</span><span class="sxs-lookup"><span data-stu-id="841e1-125">Tuple dimensionality</span></span>  
 <span data-ttu-id="841e1-126">Mit *Dimensionalität* eines Tupels ist die Sequenz oder Reihenfolge der Elemente im Tupel gemeint.</span><span class="sxs-lookup"><span data-stu-id="841e1-126">The *dimensionality* of a tuple refers to the sequence or order of the members in the tuple.</span></span> <span data-ttu-id="841e1-127">Da implizite Elemente immer in der gleichen Reihenfolge auftreten, bezieht sich der Begriff Dimensionalität meistens ausschließlich auf die explizit definierten Elemente eines Tupels.</span><span class="sxs-lookup"><span data-stu-id="841e1-127">Since the implicit members always occur in the same order, dimensionality is most often thought of in terms of the explicitly defined members of the tuple.</span></span> <span data-ttu-id="841e1-128">Die Reihenfolge der Elemente eines Tupels ist beim Definieren einer Menge von Tupeln von großer Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="841e1-128">The ordering of the members of the tuple is important when you define a set of tuples.</span></span> <span data-ttu-id="841e1-129">Im folgenden Beispiel werden zwei Elemente in ein Tupel auf der Spaltenachse eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="841e1-129">The following example includes two members in a tuple on the column axis.</span></span>  
  
```  
SELECT   
([Measures].[Reseller Sales Amount],[Date].[Calendar Year].[CY 2004]) ON COLUMNS   
FROM [Adventure Works]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="841e1-130">Wenn Sie in einem Tupel Elemente aus mehreren Dimensionen explizit angeben, müssen Sie das gesamte Tupel in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="841e1-130">When you explicitly specify a member in a tuple from more than one dimension, you must include the entire tuple in parentheses.</span></span> <span data-ttu-id="841e1-131">Wenn Sie nur ein einziges Element in einem Tupel angeben, sind die Klammern optional.</span><span class="sxs-lookup"><span data-stu-id="841e1-131">When only specifying a single member in a tuple, parentheses are optional.</span></span>  
  
 <span data-ttu-id="841e1-132">Das Tupel in der Abfrage aus dem vorherigen Beispiel gibt den Rückgabewert der Cubezelle an, die sich am Schnittpunkt des Reseller Sales Amount-Measures der Measure-Dimension mit dem CY 2004-Element der Calendar Year-Attributhierarchie in der Date-Dimension befindet.</span><span class="sxs-lookup"><span data-stu-id="841e1-132">The tuple in the query in the previous example specifies the return of the cube cell at the intersection of the Reseller Sales Amount Measure of the Measures dimension and the CY 2004 member of the Calendar Year attribute hierarchy in the Date dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="841e1-133">Auf ein Attributelement kann entweder mit seinem Elementnamen oder seinem Elementschlüssel verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="841e1-133">An attribute member can be referred by either its member name or its member key.</span></span> <span data-ttu-id="841e1-134">Der Verweis auf [CY 2004] im vorherigen Beispiel könnte durch &[2004] ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="841e1-134">In the previous example, you could replace the reference to [CY 2004] with &[2004].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="841e1-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="841e1-135">See Also</span></span>  
 <span data-ttu-id="841e1-136">[Wichtige Konzepte in MDX-&#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="841e1-136">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="841e1-137">[Cube-Bereich](cube-space.md) </span><span class="sxs-lookup"><span data-stu-id="841e1-137">[Cube Space](cube-space.md) </span></span>  
 <span data-ttu-id="841e1-138">[Autoexists](autoexists.md) </span><span class="sxs-lookup"><span data-stu-id="841e1-138">[Autoexists](autoexists.md) </span></span>  
 [<span data-ttu-id="841e1-139">Verwenden von Elementen, Tupeln und Mengen &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="841e1-139">Working with Members, Tuples, and Sets &#40;MDX&#41;</span></span>](working-with-members-tuples-and-sets-mdx.md)  
  
  
