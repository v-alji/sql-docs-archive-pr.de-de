---
title: Grundlegendes zu MDX-Abfragen (Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- statements [MDX]
- Multidimensional Expressions [Analysis Services], statements
- Multidimensional Expressions [Analysis Services], queries
- MDX [Analysis Services], statements
- MDX queries [Analysis Services]
- MDX [Analysis Services], queries
- queries [MDX]
ms.assetid: a560383b-bb58-472e-95f5-65d03d8ea08b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1a2a9a4f564bc33cc7a1b41a1a4c766c7a76a2cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620614"
---
# <a name="mdx-query-fundamentals-analysis-services"></a><span data-ttu-id="683c3-102">Grundlegendes zu MDX-Abfragen (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="683c3-102">MDX Query Fundamentals (Analysis Services)</span></span>
  <span data-ttu-id="683c3-103">MDX (Multidimensional Expressions) ermöglicht Ihnen das Abfragen von mehrdimensionalen Objekten (z. B. Cubes) sowie das Zurückgeben von mehrdimensionalen Cellsets, die die Daten des jeweiligen Cubes enthalten.</span><span class="sxs-lookup"><span data-stu-id="683c3-103">Multidimensional Expressions (MDX) lets you query multidimensional objects, such as cubes, and return multidimensional cellsets that contain the cube's data.</span></span> <span data-ttu-id="683c3-104">Dieses Thema und die zugehörigen Unterthemen bieten eine Übersicht über MDX-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="683c3-104">This topic and its subtopics provide an overview of MDX queries.</span></span>  
  
 <span data-ttu-id="683c3-105">In den folgenden Themen werden MDX-Abfragen und die von ihnen erstellten Cellsets beschrieben und detailliertere Informationen zur grundlegenden MDX-Syntax bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="683c3-105">The following topics describe MDX queries and the cellsets they produce, and provide more detailed information about basic MDX syntax.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="683c3-106">Weitere Informationen zu Leistungsproblemen im Zusammenhang mit MDX-Abfragen und-Berechnungen finden Sie im Abschnitt "Writing Efficient MDX" im [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span><span class="sxs-lookup"><span data-stu-id="683c3-106">For more information about performance issues related to MDX queries and calculations, see the section "Writing Efficient MDX" in the [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="683c3-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="683c3-107">In This Section</span></span>  
  
|<span data-ttu-id="683c3-108">Thema</span><span class="sxs-lookup"><span data-stu-id="683c3-108">Topic</span></span>|<span data-ttu-id="683c3-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="683c3-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="683c3-110">Die grundlegende MDX-Abfrage &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="683c3-110">The Basic MDX Query &#40;MDX&#41;</span></span>](mdx-query-the-basic-query.md)|<span data-ttu-id="683c3-111">Stellt grundlegende Syntaxinformationen für die MDX-SELECT-Anweisung bereit.</span><span class="sxs-lookup"><span data-stu-id="683c3-111">Provides basic syntax information for the MDX SELECT statement.</span></span>|  
|[<span data-ttu-id="683c3-112">Einschränken der Abfrage mit Abfrage- und Slicerachsen &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="683c3-112">Restricting the Query with Query and Slicer Axes &#40;MDX&#41;</span></span>](mdx-query-and-slicer-axes-restricting-the-query.md)|<span data-ttu-id="683c3-113">Beschreibt, was Abfrage- und Slicerachsen sind und wie diese angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="683c3-113">Describes what query and slicer axes are and how to specify them.</span></span>|  
|[<span data-ttu-id="683c3-114">Festlegen des Cubekontexts in einer Abfrage &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="683c3-114">Establishing Cube Context in a Query &#40;MDX&#41;</span></span>](establishing-cube-context-in-a-query-mdx.md)|<span data-ttu-id="683c3-115">Beschreibt den Zweck, den die FROM-Klausel in einer MDX-SELECT-Anweisung hat.</span><span class="sxs-lookup"><span data-stu-id="683c3-115">Provides a description of the purpose of the FROM clause in an MDX SELECT statement.</span></span>|  
|[<span data-ttu-id="683c3-116">Erstellen von benannten Mengen in MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="683c3-116">Building Named Sets in MDX &#40;MDX&#41;</span></span>](mdx-named-sets-building-named-sets.md)|<span data-ttu-id="683c3-117">Beschreibt den Zweck benannter Mengen in MDX sowie die erforderlichen Techniken, um sie zu erstellen und in MDX-Abfragen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="683c3-117">Describes the purpose of named sets in MDX, and the techniques needed to create and use them in MDX queries.</span></span>|  
|[<span data-ttu-id="683c3-118">Erstellen von berechneten Elementen in MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="683c3-118">Building Calculated Members in MDX &#40;MDX&#41;</span></span>](mdx-calculated-members-building-calculated-members.md)|<span data-ttu-id="683c3-119">Stellt Informationen zu berechneten Elementen in MDX bereit, einschließlich der Techniken, um sie zu erstellen und in MDX-Ausdrücken zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="683c3-119">Provides information about calculated members in MDX, including the techniques needed to create and use them in MDX expressions.</span></span>|  
|[<span data-ttu-id="683c3-120">Erstellen von Zellenberechnungen in MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="683c3-120">Building Cell Calculations in MDX &#40;MDX&#41;</span></span>](../../multidimensional-models-olap-logical-cube-objects/calculations.md)|<span data-ttu-id="683c3-121">Erläutert den Prozess des Erstellens und Verwendens berechneter Zellen.</span><span class="sxs-lookup"><span data-stu-id="683c3-121">Details the process of creating and using calculated cells.</span></span>|  
|[<span data-ttu-id="683c3-122">Erstellen und Verwenden von Eigenschaftswerten &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="683c3-122">Creating and Using Property Values &#40;MDX&#41;</span></span>](../../creating-and-using-property-values-mdx.md)|<span data-ttu-id="683c3-123">Erläutert das Erstellen und Verwenden der Eigenschaften von Dimensionen, Ebenen, Elementen und Zellen.</span><span class="sxs-lookup"><span data-stu-id="683c3-123">Details the process of creating and using dimension, level, member, and cell properties.</span></span>|  
|[<span data-ttu-id="683c3-124">Bearbeiten von Daten &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="683c3-124">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)|<span data-ttu-id="683c3-125">Beschreibt die Grundlagen für das Bearbeiten von Daten mit Drillthrough sowie Rollup und beschreibt Durchlaufreihenfolge und Lösungsreihenfolge in MDX.</span><span class="sxs-lookup"><span data-stu-id="683c3-125">Describes the basics behind manipulating data using drillthrough and rollup, and also describes pass order and solve order in MDX.</span></span>|  
|[<span data-ttu-id="683c3-126">Ändern von Daten &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="683c3-126">Modifying Data &#40;MDX&#41;</span></span>](mdx-data-modification-modifying-data.md)|<span data-ttu-id="683c3-127">Beschreibt, wie Rückschreiben verwendet wird, um mehrdimensionale Daten temporär oder dauerhaft zu ändern.</span><span class="sxs-lookup"><span data-stu-id="683c3-127">Describes how to use writebacks to temporarily or permanently change multidimensional data.</span></span>|  
|[<span data-ttu-id="683c3-128">Verwenden von Variablen und Parametern &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="683c3-128">Using Variables and Parameters &#40;MDX&#41;</span></span>](using-variables-and-parameters-mdx.md)|<span data-ttu-id="683c3-129">Beschreibt, wie Variablen und Parameter in MDX-Abfragen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="683c3-129">Describes how to use variables and parameters within MDX queries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="683c3-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="683c3-130">See Also</span></span>  
 [<span data-ttu-id="683c3-131">Multidimensional Expressions &#40;MDX&#41; – Referenz</span><span class="sxs-lookup"><span data-stu-id="683c3-131">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
