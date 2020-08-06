---
title: Aufbauen von benannten Mengen in MDX (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Multidimensional Expressions [Analysis Services], named sets
- named sets [MDX]
- sets [MDX]
- MDX [Analysis Services], named sets
- queries [MDX], named sets
- set expressions [MDX]
ms.assetid: 213b0035-e96d-4ba0-83f2-ded206905603
author: minewiskan
ms.author: owend
ms.openlocfilehash: 91296f8c5d47afb15c67f0b60435c7f961734573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698648"
---
# <a name="building-named-sets-in-mdx-mdx"></a><span data-ttu-id="b7971-102">Erstellen von benannten Mengen in MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="b7971-102">Building Named Sets in MDX (MDX)</span></span>
  <span data-ttu-id="b7971-103">Ein Mengenausdruck kann aus einer langen und komplexen und deshalb schwer verständlichen Deklaration bestehen.</span><span class="sxs-lookup"><span data-stu-id="b7971-103">A set expression can be a lengthy and complex declaration, and therefore be difficult to follow or understand.</span></span> <span data-ttu-id="b7971-104">Wenn ein Mengenausdruck häufig verwendet wird, kann das wiederholte Definieren der Menge lästig werden.</span><span class="sxs-lookup"><span data-stu-id="b7971-104">Or, a set expression may be used so frequently that repeatedly defining the set becomes burdensome.</span></span> <span data-ttu-id="b7971-105">Um das Verwenden längerer, komplexer oder häufig verwendeter Ausdrücke zu vereinfachen, ermöglicht MDX (Multidimensional Expressions) die Definition eines solchen Ausdrucks als *benannte Menge*.</span><span class="sxs-lookup"><span data-stu-id="b7971-105">To help make working with a lengthy, complex or commonly used expression easier, Multidimensional Expressions (MDX) lets you such an expression as a *named set*.</span></span>  
  
 <span data-ttu-id="b7971-106">Grundsätzlich handelt es sich bei einer benannten Menge um einen Mengenausdruck, dem ein Alias zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="b7971-106">Basically, a named set is a set expression to which an alias has been assigned.</span></span> <span data-ttu-id="b7971-107">Eine benannte Menge kann alle Elemente oder Funktionen enthalten, die normalerweise in eine Menge aufgenommen werden können.</span><span class="sxs-lookup"><span data-stu-id="b7971-107">A named set can incorporate any members or functions that can ordinarily be incorporated into a set.</span></span> <span data-ttu-id="b7971-108">Da der Alias der benannten Menge von MDX als Mengenausdruck behandelt wird, können Sie den Alias überall verwenden, wo ein Mengenausdruck zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="b7971-108">Because MDX treats the named set alias as a set expression, you can use that alias anywhere a set expression is accepted.</span></span>  
  
 <span data-ttu-id="b7971-109">Sie können eine benannte Menge in einem der folgenden Kontexte definieren:</span><span class="sxs-lookup"><span data-stu-id="b7971-109">You can define a named set to have one of the following contexts:</span></span>  
  
-   <span data-ttu-id="b7971-110">**Im Bereich einer Abfrage** Mit dem WITH-Schlüsselwort können Sie eine benannte Menge erstellen, die als Teil einer MDX-Abfrage definiert ist und deren Bereich daher auf die Abfrage beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="b7971-110">**Query-scoped** To create a named set that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="b7971-111">Anschließend können Sie die benannte Menge in einer SELECT-Anweisung von MDX verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7971-111">You can then use the named set within an MDX SELECT statement.</span></span> <span data-ttu-id="b7971-112">Bei dieser Vorgehensweise kann die mit dem WITH-Schlüsselwort erstellte benannte Menge geändert werden, ohne dass die SELECT-Anweisung davon beeinflusst wird.</span><span class="sxs-lookup"><span data-stu-id="b7971-112">Using this approach, the named set created by using the WITH keyword can be changed without disturbing the SELECT statement.</span></span>  
  
     <span data-ttu-id="b7971-113">Weitere Informationen zum Erstellen benannter Mengen mithilfe des WITH-Schlüsselworts finden Sie unter [Erstellen benannter Mengen im Bereich einer Abfrage &#40;MDX&#41;](mdx-named-sets-creating-query-scoped-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="b7971-113">For more information about how to use the WITH keyword to create named sets, see [Creating Query-Scoped Named Sets &#40;MDX&#41;](mdx-named-sets-creating-query-scoped-named-sets.md).</span></span>  
  
-   <span data-ttu-id="b7971-114">**Im Bereich einer Sitzung** Mit der CREATE SET-Anweisung können Sie eine benannte Menge erstellen, deren Bereich über den Kontext der Abfrage hinausgeht, d.h., deren Bereich die Dauer der MDX-Sitzung ist.</span><span class="sxs-lookup"><span data-stu-id="b7971-114">**Session-scoped** To create a named set whose scope is wider than the context of the query, that is, whose scope is the lifetime of the MDX session, you use the CREATE SET statement.</span></span> <span data-ttu-id="b7971-115">Eine mit der CREATE SET-Anweisung definierte benannte Menge ist für alle MDX-Abfragen in dieser Sitzung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b7971-115">A named set defined by using the CREATE SET statement is available to all MDX queries in that session.</span></span> <span data-ttu-id="b7971-116">Die CREATE SET-Anweisung ist z. B. in einer Clientanwendung sinnvoll, die die gleiche Menge in unterschiedlichen Abfragen wiederverwendet.</span><span class="sxs-lookup"><span data-stu-id="b7971-116">The CREATE SET statement makes sense, for example, in a client application that consistently reuses a set in a variety of queries.</span></span>  
  
     <span data-ttu-id="b7971-117">Weitere Informationen zum Erstellen benannter Mengen in einer Sitzung mithilfe der CREATE SET-Anweisung finden Sie unter [Erstellen benannter Mengen im Bereich einer Sitzung &#40;MDX&#41;](mdx-named-sets-creating-session-scoped-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="b7971-117">For more information about how to use the CREATE SET statement to create named sets in a session, see [Creating Session-Scoped Named Sets &#40;MDX&#41;](mdx-named-sets-creating-session-scoped-named-sets.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7971-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7971-118">See Also</span></span>  
 <span data-ttu-id="b7971-119">[SELECT-Anweisung &#40;MDX-&#41;](/sql/mdx/mdx-data-manipulation-select) </span><span class="sxs-lookup"><span data-stu-id="b7971-119">[SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span></span>  
 <span data-ttu-id="b7971-120">[CREATE SET-Anweisung &#40;MDX-&#41;](/sql/mdx/mdx-data-definition-create-set) </span><span class="sxs-lookup"><span data-stu-id="b7971-120">[CREATE SET Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-set) </span></span>  
 [<span data-ttu-id="b7971-121">Grundlegendes zu MDX-Abfragen &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b7971-121">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
