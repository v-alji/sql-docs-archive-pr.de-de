---
title: Verwenden von Abfrage-und Slicerachsen in einem einfachen Beispiel (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- slicer axis
- query axis [MDX]
ms.assetid: 85bcb26f-5971-4153-b334-61f8d8b475b5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 324f082fd6659592e56af65680bd4aa623c625d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620027"
---
# <a name="using-query-and-slicer-axes-in-a-simple-example-mdx"></a><span data-ttu-id="75dc0-102">Verwenden von Abfrage- und Slicerachsen in einem einfachen Beispiel (MDX)</span><span class="sxs-lookup"><span data-stu-id="75dc0-102">Using Query and Slicer Axes in a Simple Example (MDX)</span></span>
  <span data-ttu-id="75dc0-103">Anhand des einfachen Beispiels, das in diesem Thema vorgestellt wird, werden die Grundlagen zum Angeben und Verwenden von Abfrage- und Slicerachsen erläutert.</span><span class="sxs-lookup"><span data-stu-id="75dc0-103">The simple example presented in this topic illustrates the basics of specifying and using query and slicer axes.</span></span>  
  
## <a name="the-cube"></a><span data-ttu-id="75dc0-104">Der Cube</span><span class="sxs-lookup"><span data-stu-id="75dc0-104">The Cube</span></span>  
 <span data-ttu-id="75dc0-105">Ein Cube namens TestCube hat zwei einfache Dimensionen mit den Namen Route und Time.</span><span class="sxs-lookup"><span data-stu-id="75dc0-105">A cube, named TestCube, has two simple dimensions named Route and Time.</span></span> <span data-ttu-id="75dc0-106">Jede Dimension hat nur eine Benutzerhierarchie, die den Namen Route bzw. Time hat.</span><span class="sxs-lookup"><span data-stu-id="75dc0-106">Each dimension has only one user hierarchy, named Route and Time respectively.</span></span> <span data-ttu-id="75dc0-107">Da die Measures des Cubes Teil der Measures-Dimension sind, hat dieser Cube insgesamt drei Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="75dc0-107">Because the measures of the cube are part of the Measures dimension, this cube has three dimensions in all.</span></span>  
  
## <a name="the-query"></a><span data-ttu-id="75dc0-108">Die Abfrage</span><span class="sxs-lookup"><span data-stu-id="75dc0-108">The Query</span></span>  
 <span data-ttu-id="75dc0-109">Die Abfrage muss eine Matrix bereitstellen, in der das Packages-Measure über Routen und Zeiten hinweg verglichen werden kann.</span><span class="sxs-lookup"><span data-stu-id="75dc0-109">The query is to provide a matrix in which the Packages measure can be compared across routes and times.</span></span>  
  
 <span data-ttu-id="75dc0-110">Im folgenden MDX-Abfragebeispiel sind die Hierarchien Route und Time die Abfrageachsen, und die Measures-Dimension ist die Slicerachse.</span><span class="sxs-lookup"><span data-stu-id="75dc0-110">In the following MDX query example, the Route and Time hierarchies are the query axes, and the Measures dimension is the slicer axis.</span></span> <span data-ttu-id="75dc0-111">Die [Members](/sql/mdx/members-set-mdx) -Funktion zeigt an, dass MDX die Elemente der Hierarchie oder der Ebene zum Erstellen einer Menge verwendet.</span><span class="sxs-lookup"><span data-stu-id="75dc0-111">The [Members](/sql/mdx/members-set-mdx) function indicates that MDX will use the members of the hierarchy or level to construct a set.</span></span> <span data-ttu-id="75dc0-112">Wird die `Members`-Funktion verwendet, ist es nicht erforderlich, dass Sie in der jeweiligen MDX-Abfrage explizit jedes Element einer bestimmten Hierarchie oder Ebene angeben.</span><span class="sxs-lookup"><span data-stu-id="75dc0-112">The use of the `Members` function means that you do not have to explicitly state each member of a specific hierarchy or level in an MDX query.</span></span>  
  
```  
SELECT  
   { Route.nonground.Members } ON COLUMNS,  
   { Time.[1st half].Members } ON ROWS  
FROM TestCube  
WHERE ( [Measures].[Packages] )  
```  
  
## <a name="the-results"></a><span data-ttu-id="75dc0-113">Das Ergebnis</span><span class="sxs-lookup"><span data-stu-id="75dc0-113">The Results</span></span>  
 <span data-ttu-id="75dc0-114">Das Ergebnis ist ein Raster, das die Werte enthält, die das Packages-Measure in jedem Schnittpunkt der Achsendimensionen COLUMNS und ROWS hat.</span><span class="sxs-lookup"><span data-stu-id="75dc0-114">The result is a grid that identifies the value of the Packages measure at each intersection of the COLUMNS and ROWS axis dimensions.</span></span> <span data-ttu-id="75dc0-115">Die folgende Tabelle zeigt, wie dieses Raster aussehen würde:</span><span class="sxs-lookup"><span data-stu-id="75dc0-115">The following table shows how this grid would look.</span></span>  
  
||<span data-ttu-id="75dc0-116">air</span><span class="sxs-lookup"><span data-stu-id="75dc0-116">air</span></span>|<span data-ttu-id="75dc0-117">sea</span><span class="sxs-lookup"><span data-stu-id="75dc0-117">sea</span></span>|  
|-|---------|---------|  
|<span data-ttu-id="75dc0-118">Erstes Quartal</span><span class="sxs-lookup"><span data-stu-id="75dc0-118">1st quarter</span></span>|<span data-ttu-id="75dc0-119">60</span><span class="sxs-lookup"><span data-stu-id="75dc0-119">60</span></span>|<span data-ttu-id="75dc0-120">50</span><span class="sxs-lookup"><span data-stu-id="75dc0-120">50</span></span>|  
|<span data-ttu-id="75dc0-121">Zweites Quartal</span><span class="sxs-lookup"><span data-stu-id="75dc0-121">2nd quarter</span></span>|<span data-ttu-id="75dc0-122">45</span><span class="sxs-lookup"><span data-stu-id="75dc0-122">45</span></span>|<span data-ttu-id="75dc0-123">45</span><span class="sxs-lookup"><span data-stu-id="75dc0-123">45</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="75dc0-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="75dc0-124">See Also</span></span>  
 <span data-ttu-id="75dc0-125">[Angeben des Inhalts einer Abfrage Achse &#40;MDX-&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md) </span><span class="sxs-lookup"><span data-stu-id="75dc0-125">[Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md) </span></span>  
 [<span data-ttu-id="75dc0-126">Angeben des Inhalts einer Slicerachse &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="75dc0-126">Specifying the Contents of a Slicer Axis &#40;MDX&#41;</span></span>](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md)  
  
  
