---
title: Einschränken der Abfrage mit Abfrage-und Slicerachsen (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Multidimensional Expressions [Analysis Services], axes
- queries [MDX], axes
- axes [MDX]
- MDX [Analysis Services], axes
ms.assetid: a64b8172-cd73-42f9-8847-52e967b9697a
author: minewiskan
ms.author: owend
ms.openlocfilehash: ed4d50aa40d2915c60f887e64cdc3ef8a6d52c5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718766"
---
# <a name="restricting-the-query-with-query-and-slicer-axes-mdx"></a><span data-ttu-id="f3f3c-102">Einschränken der Abfrage mit Abfrage- und Slicerachsen (MDX)</span><span class="sxs-lookup"><span data-stu-id="f3f3c-102">Restricting the Query with Query and Slicer Axes (MDX)</span></span>
  <span data-ttu-id="f3f3c-103">Wenn Sie eine MDX-SELECT-Anweisung (Multidimensional Expressions) formulieren, durchsucht eine Anwendung i. d. R. einen Cube und unterteilt die Menge der Hierarchien in zwei Teilmengen:</span><span class="sxs-lookup"><span data-stu-id="f3f3c-103">When formulating a Multidimensional Expressions (MDX) SELECT statement, an application typically examines a cube and divides the set of hierarchies into two subsets:</span></span>  
  
-   <span data-ttu-id="f3f3c-104">**Abfrage Achsen**: der Satz von Hierarchien, aus denen Daten für mehrere Elemente abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f3f3c-104">**Query axes**-the set of hierarchies from which data is retrieved for multiple members.</span></span> <span data-ttu-id="f3f3c-105">Weitere Informationen zu den Abfrageachsen finden Sie unter [Angeben des Inhalts einer Abfrageachse &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span><span class="sxs-lookup"><span data-stu-id="f3f3c-105">For more information about query axes, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span></span>  
  
-   <span data-ttu-id="f3f3c-106">**Slicerachse**: der Satz von Hierarchien, aus denen Daten für einen einzelnen Member abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f3f3c-106">**Slicer axis**-the set of hierarchies from which data is retrieved for a single member.</span></span> <span data-ttu-id="f3f3c-107">Weitere Informationen zu den Slicerachsen finden Sie unter [Angeben des Inhalts einer Slicerachse &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span><span class="sxs-lookup"><span data-stu-id="f3f3c-107">For more information about the slicer axis, see [Specifying the Contents of a Slicer Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span></span>  
  
 <span data-ttu-id="f3f3c-108">Da Abfrage- und Slicerachsen aus mehreren Hierarchien des abzufragenden Cubes erstellt werden können, wird mit diesen Begriffen unterschieden zwischen den Hierarchien, die im abzufragenden Cube verwendet werden, und den Hierarchien, die im von einer MDX-Abfrage zurückgegebenen Cube erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f3f3c-108">Because query and slicer axes can be constructed from multiple hierarchies of the cube to be queried, these terms are used to differentiate the hierarchies used by the cube that is to be queried from the hierarchies created in the cube returned by an MDX query.</span></span>  
  
 <span data-ttu-id="f3f3c-109">Ein einfaches Beispiel mit Verwendung von Abfrage- und Slicerachsen finden Sie unter [Verwenden von Abfrage- und Slicerachsen in einem einfachen Beispiel &#40;MDX&#41;](mdx-query-and-slicer-axes-using-axes-in-a-simple-example.md).</span><span class="sxs-lookup"><span data-stu-id="f3f3c-109">To see a simple example using query and slicer axes, see [Using Query and Slicer Axes in a Simple Example &#40;MDX&#41;](mdx-query-and-slicer-axes-using-axes-in-a-simple-example.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3f3c-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3f3c-110">See Also</span></span>  
 <span data-ttu-id="f3f3c-111">[Arbeiten mit Membern, Tupeln und Mengen &#40;MDX-&#41;](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="f3f3c-111">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 [<span data-ttu-id="f3f3c-112">Grundlegendes zu MDX-Abfragen &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f3f3c-112">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
