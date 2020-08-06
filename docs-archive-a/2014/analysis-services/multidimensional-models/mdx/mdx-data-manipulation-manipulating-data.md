---
title: Bearbeiten von Daten (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/19/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], data manipulation
- data manipulation [MDX]
- Multidimensional Expressions [Analysis Services], data manipulation
ms.assetid: 4865192e-f46b-4ce5-b51c-9e08dbad5b85
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1a1de8b9a3431d79573cd916fa7273b6d8fa7f0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618360"
---
# <a name="manipulating-data-mdx"></a><span data-ttu-id="0b220-102">Bearbeiten von Daten (MDX)</span><span class="sxs-lookup"><span data-stu-id="0b220-102">Manipulating Data (MDX)</span></span>

<span data-ttu-id="0b220-103">Mit MDX (Multidimensional Expressions) können Daten auf viele Arten bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="0b220-103">Multidimensional Expressions (MDX) can be used to manipulate the data in a variety of ways.</span></span> <span data-ttu-id="0b220-104">Der in diesem Artikel aufgeführte Artikel behandelt einige der erweiterten Konzepte der Datenbearbeitung in der MDX-Sprache.</span><span class="sxs-lookup"><span data-stu-id="0b220-104">The article listed in this article cover some of the more advanced concepts of data manipulation in the MDX language.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="0b220-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0b220-105">In This Section</span></span>

|<span data-ttu-id="0b220-106">Thema</span><span class="sxs-lookup"><span data-stu-id="0b220-106">Topic</span></span>|<span data-ttu-id="0b220-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0b220-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="0b220-108">Verwenden von DRILLTHROUGH zum Abrufen von Quelldaten &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="0b220-108">Using DRILLTHROUGH to Retrieve Source Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-retrieve-source-data-using-drillthrough.md)|<span data-ttu-id="0b220-109">Erläutert die Verwendung der MDX- [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough) -Anweisung zum Abrufen der Rowsets von Quelldaten, die auf eine Zelle in einer mehrdimensionalen Datenquelle anwendbar ist.</span><span class="sxs-lookup"><span data-stu-id="0b220-109">Discusses the use of the MDX [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough) statement to retrieve the rowsets of source data applicable to a cell in a multidimensional data source</span></span>|  
|[<span data-ttu-id="0b220-110">Arbeiten mit der RollupChildren-Funktion &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="0b220-110">Working with the RollupChildren Function &#40;MDX&#41;</span></span>](mdx-data-manipulation-rollupchildren-function.md)|<span data-ttu-id="0b220-111">Erläutert die Auswirkung der MDX- [RollupChildren](/sql/mdx/rollupchildren-mdx)</span><span class="sxs-lookup"><span data-stu-id="0b220-111">Discusses the impact of the MDX [RollupChildren](/sql/mdx/rollupchildren-mdx)</span></span>
|[<span data-ttu-id="0b220-112">Grundlegendes zu Durchlauf- und Lösungsreihenfolge &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="0b220-112">Understanding Pass Order and Solve Order &#40;MDX&#41;</span></span>](mdx-data-manipulation-understanding-pass-order-and-solve-order.md)|<span data-ttu-id="0b220-113">Erläutert die Konzepte der Lösungsreihenfolge und erläutert, wie sich diese Funktion auf MDX-Ausdrücke, -Anweisungen und -Skripts auswirkt.</span><span class="sxs-lookup"><span data-stu-id="0b220-113">Details the concepts of solve order, and how this feature affects MDX expressions, statements, and scripts.</span></span>|  

<!-- ??

|[Script for Search and Replace] function on the analysis of multidimensional data.|

GeneMi is removing this commented row because it is unclear what article its link meant to link to.
Also, I had to add its leading '|' character, for consistency to aid bulk automated updated to our markdown source code.

GeneMi , 2019/01/19
-->

## <a name="see-also"></a><span data-ttu-id="0b220-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b220-114">See Also</span></span>

[<span data-ttu-id="0b220-115">Grundlegendes zu MDX-Abfragen (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="0b220-115">MDX Query Fundamentals (Analysis Services)</span></span>](mdx-query-fundamentals-analysis-services.md)
