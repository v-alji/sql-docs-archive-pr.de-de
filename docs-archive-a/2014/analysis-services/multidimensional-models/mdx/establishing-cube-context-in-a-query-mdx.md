---
title: Einrichten des Cubekontexts in einer Abfrage (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cubes [Analysis Services], MDX
- MDX [Analysis Services], cube context
- SELECT statement [MDX]
- Multidimensional Expressions [Analysis Services], cube context
- queries [MDX], cube context
ms.assetid: 79d6a1e8-2825-4eb9-97df-5071aecae8f0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 72ae6e19f879651feb47841d70b444e9f845c74e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694754"
---
# <a name="establishing-cube-context-in-a-query-mdx"></a><span data-ttu-id="87719-102">Festlegen des Cubekontexts in einer Abfrage (MDX)</span><span class="sxs-lookup"><span data-stu-id="87719-102">Establishing Cube Context in a Query (MDX)</span></span>
  <span data-ttu-id="87719-103">Jede MDX-Abfrage wird in einem bestimmten Cubekontext ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="87719-103">Every MDX query runs within a specified cube context.</span></span> <span data-ttu-id="87719-104">Dieser Kontext definiert die Elemente, die durch die Ausdrücke in der Abfrage ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="87719-104">This context defines the members that are evaluated by the expressions within the query.</span></span>  
  
 <span data-ttu-id="87719-105">In der SELECT-Anweisung bestimmt die FROM-Klausel den Cubekontext.</span><span class="sxs-lookup"><span data-stu-id="87719-105">In the SELECT statement, the FROM clause determines the cube context.</span></span> <span data-ttu-id="87719-106">Bei diesem Kontext kann es sich um den gesamten Cube oder nur um einen Teilcube dieses Cubes handeln.</span><span class="sxs-lookup"><span data-stu-id="87719-106">This context can be the whole cube or just a subcube from that cube.</span></span> <span data-ttu-id="87719-107">Nachdem Sie den Cubekontext durch die FROM-Klausel angegeben haben, können Sie den Kontext mithilfe weiterer Funktionen erweitern oder einschränken.</span><span class="sxs-lookup"><span data-stu-id="87719-107">Having specified cube context through the FROM clause, you can use additional functions to expand or restrict that context.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="87719-108">Mit den SCOPE- und CALCULATE-Anweisungen können Sie den Cubekontext auch innerhalb eines MDX-Skripts verwalten.</span><span class="sxs-lookup"><span data-stu-id="87719-108">The SCOPE and CALCULATE statements also let you manage cube context from within an MDX script.</span></span> <span data-ttu-id="87719-109">Weitere Informationen finden Sie unter [Grundlegendes zu MDX-Skripts &#40;Analysis Services&#41;](mdx-scripting-fundamentals-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="87719-109">For more information, see [MDX Scripting Fundamentals &#40;Analysis Services&#41;](mdx-scripting-fundamentals-analysis-services.md).</span></span>  
  
## <a name="from-clause-syntax"></a><span data-ttu-id="87719-110">Syntax der FROM-Klausel</span><span class="sxs-lookup"><span data-stu-id="87719-110">FROM Clause Syntax</span></span>  
 <span data-ttu-id="87719-111">Die folgende Syntax beschreibt die FROM-Klausel:</span><span class="sxs-lookup"><span data-stu-id="87719-111">The following syntax describes the FROM clause:</span></span>  
  
```  
<SELECT subcube clause> ::=  
   Cube_Identifier |   
   (SELECT [  
      * |   
      ( <SELECT query axis clause> [ , <SELECT query axis clause> ... ] ) ]   
   FROM <SELECT subcube clause> <SELECT slicer axis clause> )  
```  
  
 <span data-ttu-id="87719-112">In dieser Syntax beschreibt die `<SELECT subcube clause>` -Klausel den Cube oder Teilcube, auf dem die SELECT-Anweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="87719-112">In this syntax, notice that it is the `<SELECT subcube clause>` clause that describes the cube or subcube on which the SELECT statement is executed.</span></span>  
  
 <span data-ttu-id="87719-113">Ein einfaches Beispiel wäre eine FROM-Klausel, die auf dem gesamten Adventure Works-Beispielcube ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="87719-113">A simple example of a FROM clause would be one that runs against the entire Adventure Works sample cube.</span></span> <span data-ttu-id="87719-114">Eine solche FROM-Klausel hätte das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="87719-114">Such a FROM clause would have the following format:</span></span>  
  
```  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="87719-115">Weitere Informationen zur FROM-Klausel in der SELECT-Anweisung von MDX finden Sie unter [SELECT-Anweisung &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="87719-115">For more information about the FROM clause in the MDX SELECT statement, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
## <a name="refining-the-context"></a><span data-ttu-id="87719-116">Genaueres Festlegen des Kontexts</span><span class="sxs-lookup"><span data-stu-id="87719-116">Refining the Context</span></span>  
 <span data-ttu-id="87719-117">Obwohl die FROM-Klausel den Cubekontext innerhalb eines einzelnen Cubes angibt, wird dadurch nicht ausgeschlossen, dass Sie Daten aus mehreren Cubes gleichzeitig verwenden.</span><span class="sxs-lookup"><span data-stu-id="87719-117">Although the FROM clause specifies the cube context as within a single cube, this does not have to limit you from working with data from more than one cube at a time.</span></span>  
  
 <span data-ttu-id="87719-118">Mit der MDX- [LookupCube](/sql/mdx/lookupcube-mdx) -Funktion können Sie Daten aus Cubes außerhalb des Cubekontexts abrufen.</span><span class="sxs-lookup"><span data-stu-id="87719-118">You can use the MDX [LookupCube](/sql/mdx/lookupcube-mdx) function to retrieve data from cubes outside the cube context.</span></span> <span data-ttu-id="87719-119">Darüber hinaus stehen Funktionen wie die [Filter](/sql/mdx/filter-mdx) -Funktion zur Verfügung, um den Kontext beim Auswerten der Abfrage vorübergehend einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="87719-119">Additionally, functions such as the [Filter](/sql/mdx/filter-mdx) function, are available that allow temporary restriction of the context while evaluating the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87719-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="87719-120">See Also</span></span>  
 [<span data-ttu-id="87719-121">Grundlegendes zu MDX-Abfragen &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="87719-121">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
