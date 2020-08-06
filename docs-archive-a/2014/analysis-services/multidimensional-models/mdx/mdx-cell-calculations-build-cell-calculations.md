---
title: Aufbauen von Zellen Berechnungen in MDX (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- calculated cells [MDX]
- queries [MDX], cell calculations
- cells [MDX]
- MDX [Analysis Services], calculations
- calculation subcubes [MDX]
- calculated values [MDX]
- Multidimensional Expressions [Analysis Services], cell calculations
ms.assetid: 068aea63-d419-4791-a960-3d74e76f808e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9ab3219850c49c2ec16a12aab3ba7db67e9a8721
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718784"
---
# <a name="building-cell-calculations-in-mdx-mdx"></a><span data-ttu-id="8d8ce-102">Erstellen von Zellenberechnungen in MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="8d8ce-102">Building Cell Calculations in MDX (MDX)</span></span>
  <span data-ttu-id="8d8ce-103">MDX (Multidimensional Expressions) stellt eine Reihe von Tools zum Generieren berechneter Werte bereit, wie z. B. berechnete Elemente, benutzerdefinierte Rollups und benutzerdefinierte Elemente.</span><span class="sxs-lookup"><span data-stu-id="8d8ce-103">Multidimensional Expressions (MDX) provides you with a number of tools for generating calculated values, such as calculated members, custom rollups, and custom members.</span></span> <span data-ttu-id="8d8ce-104">Allerdings ist es schwierig, mithilfe dieser Funktionen eine bestimmte Menge von Zellen oder eine einzelne Zelle zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="8d8ce-104">However, using these features to affect a specific set of cells, or a single cell for that matter, would be difficult.</span></span>  
  
 <span data-ttu-id="8d8ce-105">Wenn Sie berechnete Werte für bestimmte Zellen generieren möchten, sollten Sie die Funktion für berechnete Zellen in MDX verwenden.</span><span class="sxs-lookup"><span data-stu-id="8d8ce-105">To generated calculated values for specifically for cells, you need to use the calculated cells feature in MDX.</span></span> <span data-ttu-id="8d8ce-106">Mit berechneten Zellen können Sie einen bestimmten Slice von Zellen definieren, der als *Berechnungsteilcube*bezeichnet wird, und eine Formel auf jede einzelne Zelle im Berechnungsteilcube anwenden, wobei eine optionale Bedingung zugrunde liegt, die auf jede Zelle angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="8d8ce-106">Calculated cells let you define a specific slice of cells, called a *calculation subcube*, and apply a formula to each and every cell within the calculation subcube, subject to an optional condition that can be applied to each cell.</span></span>  
  
 <span data-ttu-id="8d8ce-107">Berechnete Zellen stellen außerdem eine komplexe Funktionalität bereit, z. B. zielsuchende Formeln (wie sie in KPIs verwendet werden) oder Formeln für spekulative Analysen.</span><span class="sxs-lookup"><span data-stu-id="8d8ce-107">Calculated cells also offer complex functionality, such as goal-seeking formulas, as used in KPIs, or speculative analysis formulas.</span></span> <span data-ttu-id="8d8ce-108">Dieses Maß an Funktionalität ergibt sich aus der Funktion "Pass Order" in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , mit der rekursive Übergänge mit berechneten Zellen ausgeführt werden können, wobei Berechnungsformeln bei bestimmten Durchläufen in der Durchlauf Reihenfolge angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="8d8ce-108">This level of functionality comes from the pass order feature in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] that allows recursive passes to be made with calculated cells, with calculation formulas applied at specific passes in the pass order.</span></span> <span data-ttu-id="8d8ce-109">Weitere Informationen zur Durchlaufreihenfolge finden Sie unter [Grundlegendes zu Durchlauf- und Lösungsreihenfolge &#40;MDX&#41;](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span><span class="sxs-lookup"><span data-stu-id="8d8ce-109">For more information on pass order, see [Understanding Pass Order and Solve Order &#40;MDX&#41;](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span></span>  
  
 <span data-ttu-id="8d8ce-110">In Bezug auf den Gültigkeitsbereich sind berechnete Zellen sowohl mit benannten Mengen als auch mit berechneten Elementen vergleichbar, da berechnete Zellen temporär für die Dauer einer Sitzung oder einer einzelnen Abfrage erstellt oder global als Teil eines Cubes zur Verfügung gestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="8d8ce-110">In terms of creation scope, calculated cells are similar to both named sets and calculated members in that calculated cells can be temporarily created for the lifetime of either a session or a single query, or made globally available as part of a cube:</span></span>  
  
-   <span data-ttu-id="8d8ce-111">**Im Bereich einer Abfrage** Mit dem WITH-Schlüsselwort können Sie eine berechnete Zelle erstellen, die als Teil einer MDX-Abfrage definiert ist und deren Bereich somit auf die Abfrage beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="8d8ce-111">**Query-scoped** To create a calculated cell that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="8d8ce-112">Anschließend können Sie die berechnete Zelle in einer MDX-SELECT-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="8d8ce-112">You can then use the calculated cell within an MDX SELECT statement.</span></span> <span data-ttu-id="8d8ce-113">Bei dieser Vorgehensweise kann die mit dem `WITH`-Schlüsselwort erstellte berechnete Zelle geändert werden, ohne dass die SELECT-Anweisung davon beeinflusst wird.</span><span class="sxs-lookup"><span data-stu-id="8d8ce-113">Using this approach, the calculated cell created by using the `WITH` keyword can be changed without disturbing the SELECT statement.</span></span>  
  
     <span data-ttu-id="8d8ce-114">Weitere Informationen zum Erstellen berechneter Elemente mithilfe des WITH-Schlüsselworts finden Sie unter [Erstellen von Zellenberechnungen im Bereich einer Abfrage &#40;MDX&#41;](../../multidimensional-models-olap-logical-cube-objects/calculations.md).</span><span class="sxs-lookup"><span data-stu-id="8d8ce-114">For more information about how to use the WITH keyword to create calculated members, see [Creating Query-Scoped Cell Calculations &#40;MDX&#41;](../../multidimensional-models-olap-logical-cube-objects/calculations.md).</span></span>  
  
-   <span data-ttu-id="8d8ce-115">**Im Bereich einer Sitzung** Mit der CREATE CELL CALCULATION- oder der ALTER CUBE-Anweisung können Sie ein berechnetes Element erstellen, dessen Bereich mehr als den Kontext der Abfrage umfasst, dessen Bereich nämlich die Dauer der MDX-Sitzung ist.</span><span class="sxs-lookup"><span data-stu-id="8d8ce-115">**Session-scoped** To create a calculated member whose scope is wider than the context of the query, that is, whose scope is the lifetime of the MDX session, you use either the CREATE CELL CALCULATION or ALTER CUBE statement.</span></span>  
  
     <span data-ttu-id="8d8ce-116">Weitere Informationen zum Erstellen berechneter Elemente in einer Sitzung mithilfe der CREATE CELL CALCULATION- oder der ALTER CUBE-Anweisung finden Sie unter [Erstellen berechneter Zellen im Bereich einer Sitzung](mdx-cell-calculations-session-scoped-calculated-cells.md).</span><span class="sxs-lookup"><span data-stu-id="8d8ce-116">For more information about how to use either the CREATE CELL CALCULATION or ALTER CUBE statement to create calculated cells in a session, see [Creating Session-Scoped Calculated Cells](mdx-cell-calculations-session-scoped-calculated-cells.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d8ce-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8d8ce-117">See Also</span></span>  
 <span data-ttu-id="8d8ce-118">[ALTER CUBE-Anweisung &#40;MDX-&#41;](/sql/mdx/mdx-data-definition-alter-cube) </span><span class="sxs-lookup"><span data-stu-id="8d8ce-118">[ALTER CUBE Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-alter-cube) </span></span>  
 <span data-ttu-id="8d8ce-119">[Create Cell Berechnung-Anweisung &#40;MDX-&#41;](/sql/mdx/mdx-data-definition-create-cell-calculation) </span><span class="sxs-lookup"><span data-stu-id="8d8ce-119">[CREATE CELL CALCULATION Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-cell-calculation) </span></span>  
 <span data-ttu-id="8d8ce-120">[Erstellen von Zellen Berechnungen im Bereich einer Abfrage &#40;MDX-&#41;](../../multidimensional-models-olap-logical-cube-objects/calculations.md) </span><span class="sxs-lookup"><span data-stu-id="8d8ce-120">[Creating Query-Scoped Cell Calculations &#40;MDX&#41;](../../multidimensional-models-olap-logical-cube-objects/calculations.md) </span></span>  
 [<span data-ttu-id="8d8ce-121">Grundlegendes zu MDX-Abfragen &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8d8ce-121">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
