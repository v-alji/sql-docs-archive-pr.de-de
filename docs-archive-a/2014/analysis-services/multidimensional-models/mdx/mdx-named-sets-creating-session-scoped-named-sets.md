---
title: Erstellen benannter Mengen im Bereich einer Sitzung (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- CREATE SET statement
- session-scoped named sets [MDX]
ms.assetid: b751e1e4-6d4c-4d36-a28d-ffdaaee0f1c7
author: minewiskan
ms.author: owend
ms.openlocfilehash: d35bd61dcc59eca8bcb920ed99f2e791631047c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718787"
---
# <a name="creating-session-scoped-named-sets-mdx"></a><span data-ttu-id="ccc88-102">Erstellen benannter Mengen im Bereich einer Sitzung (MDX)</span><span class="sxs-lookup"><span data-stu-id="ccc88-102">Creating Session-Scoped Named Sets (MDX)</span></span>
  <span data-ttu-id="ccc88-103">Zum Erstellen einer benannten Menge, die während einer gesamten MDX-Sitzung (Multidimensional Expressions) verfügbar ist, verwenden Sie die [CREATE SET](/sql/mdx/mdx-data-definition-create-set) -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ccc88-103">To create a named set that is available throughout a Multidimensional Expressions (MDX) session, you use the [CREATE SET](/sql/mdx/mdx-data-definition-create-set) statement.</span></span> <span data-ttu-id="ccc88-104">Eine benannte Menge, die mit der CREATE SET-Anweisung erstellt wurde, wird erst entfernt, nachdem die MDX-Sitzung geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="ccc88-104">A named set that is created by using the CREATE SET statement will not be removed until after the MDX session closes.</span></span>  
  
 <span data-ttu-id="ccc88-105">Wie in diesem Thema erläutert wird, ist die Syntax des WITH-Schlüsselworts unkompliziert und einfach zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ccc88-105">As discussed in this topic, the syntax of the WITH keyword is straightforward and easy to use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ccc88-106">Weitere Informationen zu benannten Mengen finden Sie unter [Erstellen von benannten Mengen in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="ccc88-106">For more information about named sets, see [Building Named Sets in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span></span>  
  
## <a name="create-set-syntax"></a><span data-ttu-id="ccc88-107">Syntax von CREATE SET</span><span class="sxs-lookup"><span data-stu-id="ccc88-107">CREATE SET Syntax</span></span>  
 <span data-ttu-id="ccc88-108">Die CREATE SET-Anweisung hat folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="ccc88-108">Use the following syntax for the CREATE SET statement:</span></span>  
  
```  
CREATE SESSION SET [CURRENTCUBE. | <cube name>.]<Set Identifier> AS <Set Expression>  
```  
  
 <span data-ttu-id="ccc88-109">In der Syntax von CREATE SET enthält der `cube name` -Parameter den Namen des Cubes, der die Elemente für die benannte Menge enthält.</span><span class="sxs-lookup"><span data-stu-id="ccc88-109">In the CREATE SET syntax, the `cube name` parameter contains the name of the cube that contains the members for the named set.</span></span> <span data-ttu-id="ccc88-110">Wenn der `cube name` -Parameter nicht angegeben ist, wird der aktuelle Cube als der Cube verwendet, der die Elemente für die benannte Menge enthält.</span><span class="sxs-lookup"><span data-stu-id="ccc88-110">If the `cube name` parameter is not specified, the current cube will be used as the cube that contains the member for the named set.</span></span> <span data-ttu-id="ccc88-111">Außerdem enthält der `Set_Identifier` -Parameter den Alias für die benannte Menge, und der `Set_Expression` -Parameter enthält den Mengenausdruck, auf den der Alias der benannten Menge verweist.</span><span class="sxs-lookup"><span data-stu-id="ccc88-111">Also, the `Set_Identifier` parameter contains the alias for the named set, and the `Set_Expression` parameter contains the set expression to which the named set alias will refer.</span></span>  
  
## <a name="create-set-example"></a><span data-ttu-id="ccc88-112">Beispiel zu CREATE SET</span><span class="sxs-lookup"><span data-stu-id="ccc88-112">CREATE SET Example</span></span>  
 <span data-ttu-id="ccc88-113">Im folgenden Beispiel wird die CREATE SET-Anweisung dazu verwendet, die benannte Menge `SetCities_2_3` aus dem Store-Cube zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ccc88-113">The following example uses the CREATE SET statement to create the `SetCities_2_3` named set based on the Store cube.</span></span> <span data-ttu-id="ccc88-114">Die Elemente der benannten Menge `SetCities_2_3` sind die Geschäfte in City 2 und City 3.</span><span class="sxs-lookup"><span data-stu-id="ccc88-114">The members of the `SetCities_2_3` named set are the stores within City 2 and City 3.</span></span>  
  
```  
create Session set [Store].[SetCities_2_3] as  
{[Data Stores].[ByLocation].[State].&[CA].&[City 02],  
[Data Stores].[ByLocation].[State].&[NH].&[City 03]}  
```  
  
 <span data-ttu-id="ccc88-115">Dadurch, dass die benannte Menge `SetCities_2_3` mit der CREATE SET-Anweisung erstellt wurde, bleibt die benannte Menge für die Dauer der aktuellen Sitzung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ccc88-115">By using the CREATE SET statement to define the `SetCities_2_3` named set, this named set remains available for the length of the current MDX session.</span></span> <span data-ttu-id="ccc88-116">Das folgende Beispiel ist eine gültige Abfrage, die die Elemente City 2 sowie City 3 zurückgibt und jederzeit ausgeführt werden kann, nachdem Sie die benannte Menge `SetCities_2_3` erstellt und bis Sie die Sitzung geschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="ccc88-116">The following example is a valid query that would return City 2 and City 3 members, and that could be run anytime after you create the `SetCities_2_3` named set and before the session closes.</span></span>  
  
```  
select SetCities_2_3 on 0 from [Store]  
```  
  
## <a name="see-also"></a><span data-ttu-id="ccc88-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ccc88-117">See Also</span></span>  
 [<span data-ttu-id="ccc88-118">Erstellen benannter Mengen im Bereich einer Abfrage &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="ccc88-118">Creating Query-Scoped Named Sets &#40;MDX&#41;</span></span>](mdx-named-sets-creating-query-scoped-named-sets.md)  
  
  