---
title: Ändern von Daten (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying data [MDX]
- Multidimensional Expressions [Analysis Services], data modifications
- MDX [Analysis Services], data modifications
- data modifications [MDX]
ms.assetid: 363b662c-b839-4971-bbd7-1842f73ce141
author: minewiskan
ms.author: owend
ms.openlocfilehash: 01df67471753922e3e7db39c56a9ed50aae900dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618924"
---
# <a name="modifying-data-mdx"></a><span data-ttu-id="813a4-102">Ändern von Daten (MDX)</span><span class="sxs-lookup"><span data-stu-id="813a4-102">Modifying Data (MDX)</span></span>
  <span data-ttu-id="813a4-103">MDX (Multidimensional Expressions) kann nicht nur zum Abrufen und Verwalten von Daten aus Dimensionen und Cubes, sondern auch zum Aktualisieren oder *Rückschreiben* von Dimensions- und Cubedaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="813a4-103">Besides using Multidimensional Expressions (MDX) to retrieve and handle data from dimensions and cubes, you can use MDX to update or *writeback* dimension and cube data.</span></span> <span data-ttu-id="813a4-104">Diese Updates können temporär (wie bei einer spekulativen oder "Was-wäre-wenn-Analyse") oder permanent sein (dies ist der Fall, wenn Änderungen aufgrund einer Datenanalyse vorgenommen werden müssen).</span><span class="sxs-lookup"><span data-stu-id="813a4-104">These updates can be temporary, as with speculative, or "what if", analysis, or permanent, as when changes must occur based upon data analysis.</span></span>  
  
 <span data-ttu-id="813a4-105">Updates von Daten sind auf Dimensions- oder Cubeebene möglich.</span><span class="sxs-lookup"><span data-stu-id="813a4-105">Updates to data can occur at the dimension or cube level:</span></span>  
  
 <span data-ttu-id="813a4-106">**Rückschreiben von Dimensionen**</span><span class="sxs-lookup"><span data-stu-id="813a4-106">**Dimension writebacks**</span></span>  
 <span data-ttu-id="813a4-107">Die [ALTER CUBE-Anweisung (MDX)](/sql/mdx/mdx-data-definition-alter-cube) wird verwendet, um die Daten einer Dimension mit aktiviertem Schreibzugriff zu ändern, und die [REFRESH CUBE-Anweisung (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) wird verwendet, um das Löschen, Erstellen oder Aktualisieren von Attributwerten zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="813a4-107">You use the [ALTER CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-alter-cube) statement to change a write-enabled dimension's data and the [REFRESH CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) to reflect the deletion, creation, and updating of attribute values.</span></span> <span data-ttu-id="813a4-108">Mit der ALTER CUBE-Anweisung können Sie auch komplexe Operationen ausführen, so z. B. das Löschen einer gesamten Unterstruktur in einer Hierarchie oder das Heraufstufen der untergeordneten Elemente eines gelöschten Elements.</span><span class="sxs-lookup"><span data-stu-id="813a4-108">You can also use the ALTER CUBE statement to perform complex operations, such as deleting a whole sub-tree in a hierarchy and promoting the children of a deleted member.</span></span>  
  
 <span data-ttu-id="813a4-109">**Cuberückschreiben**</span><span class="sxs-lookup"><span data-stu-id="813a4-109">**Cube writebacks**</span></span>  
 <span data-ttu-id="813a4-110">Sie verwenden die [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) -Anweisung dazu, Änderungen an einem Cube mit aktiviertem Schreibzugriff vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="813a4-110">You use the [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) statement to make updates to a write-enabled cube.</span></span> <span data-ttu-id="813a4-111">Mit der UPDATE CUBE-Anweisung können Sie ein Tupel mit einem bestimmten Wert aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="813a4-111">The UPDATE CUBE statement lets you update a tuple with a specific value.</span></span> <span data-ttu-id="813a4-112">Die [REFRESH CUBE-Anweisung (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) wird zum Aktualisieren von Daten in einer Clientsitzung mit aktualisierten Daten vom Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="813a4-112">You use the [REFRESH CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) to refresh data in a client session with updated data from the server.</span></span>  
  
 <span data-ttu-id="813a4-113">Weitere Informationen finden Sie unter [Verwenden von Cuberückschreiben &#40;MDX&#41;](mdx-data-modification-using-cube-writebacks.md).</span><span class="sxs-lookup"><span data-stu-id="813a4-113">For more information, see [Using Cube Writebacks &#40;MDX&#41;](mdx-data-modification-using-cube-writebacks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="813a4-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="813a4-114">See Also</span></span>  
 [<span data-ttu-id="813a4-115">Grundlegendes zu MDX-Abfragen &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="813a4-115">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
