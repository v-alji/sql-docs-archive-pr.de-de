---
title: Aufbauen von Teilcubes in MDX (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [MDX], subcubes
- subcubes [MDX]
- filtered views [MDX]
- MDX [Analysis Services], subcubes
- Multidimensional Expressions [Analysis Services], subcubes
- CREATE SUBCUBE statement
ms.assetid: 5403a62b-99ac-4d83-b02a-89bf78bf0f46
author: minewiskan
ms.author: owend
ms.openlocfilehash: 653b4d30aa86f52179c7b13619ac4347aa65c339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619415"
---
# <a name="building-subcubes-in-mdx-mdx"></a><span data-ttu-id="f0848-102">Erstellen von Teilcubes in MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="f0848-102">Building Subcubes in MDX (MDX)</span></span>
  <span data-ttu-id="f0848-103">Ein Teilcube ist eine Teilmenge eines Cubes, die einer gefilterten Sicht der zugrunde liegenden Daten entspricht.</span><span class="sxs-lookup"><span data-stu-id="f0848-103">A subcube is a subset of a cube on representing a filtered view of the underlying data.</span></span> <span data-ttu-id="f0848-104">Durch Begrenzen des Cubes auf einen Teilcube können Sie die Abfrageleistung verbessern.</span><span class="sxs-lookup"><span data-stu-id="f0848-104">By limiting the cube to a subcube, you can improve query performance.</span></span>  
  
 <span data-ttu-id="f0848-105">Zum Definieren eines Teilcubes verwenden Sie die in diesem Thema beschriebene [CREATE SUBCUBE](/sql/mdx/mdx-data-definition-create-subcube) -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f0848-105">To define a subcube, you use the [CREATE SUBCUBE](/sql/mdx/mdx-data-definition-create-subcube) statement, as described in this topic.</span></span>  
  
## <a name="create-subcube-syntax"></a><span data-ttu-id="f0848-106">Syntax von CREATE SUBCUBE</span><span class="sxs-lookup"><span data-stu-id="f0848-106">CREATE SUBCUBE Syntax</span></span>  
 <span data-ttu-id="f0848-107">Verwenden Sie die folgende Syntax, um einen Teilcube zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="f0848-107">Use the following syntax to create a subcube:</span></span>  
  
```  
CREATE SUBCUBE Subcube_Identifier AS Subcube_Expression  
```  
  
 <span data-ttu-id="f0848-108">Die Syntax von CREATE SUBCUBE ist recht einfach.</span><span class="sxs-lookup"><span data-stu-id="f0848-108">The CREATE SUBCUBE syntax is fairly simple.</span></span> <span data-ttu-id="f0848-109">Der *Subcube_Identifier* -Parameter gibt den Cube an, auf dem der Teilcube basieren soll.</span><span class="sxs-lookup"><span data-stu-id="f0848-109">The *Subcube_Identifier* parameter identifies the cube on which the subcube will be based.</span></span> <span data-ttu-id="f0848-110">Der *Subcube_Expression* -Parameter wählt den Teil des Cubes aus, der zum Teilcube werden soll.</span><span class="sxs-lookup"><span data-stu-id="f0848-110">The *Subcube_Expression* parameter selects the part of the cube that will become the subcube</span></span>  
  
 <span data-ttu-id="f0848-111">Nachdem Sie einen Teilcube erstellt haben, wird dieser Teilcube so lange der Kontext für alle MDX-Abfragen, bis Sie die Sitzung geschlossen oder die [DROP SUBCUBE](/sql/mdx/mdx-data-definition-drop-subcube) -Anweisung ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="f0848-111">After you create a subcube, that subcube becomes the context for all MDX queries until either the session closes or you run the [DROP SUBCUBE](/sql/mdx/mdx-data-definition-drop-subcube) statement.</span></span>  
  
### <a name="what-a-subcube-contains"></a><span data-ttu-id="f0848-112">Inhalt eines Teilcubes</span><span class="sxs-lookup"><span data-stu-id="f0848-112">What a Subcube Contains</span></span>  
 <span data-ttu-id="f0848-113">Obwohl die CREATE SUBCUBE-Anweisung recht einfach zu verwenden ist, zeigt die Anweisung selbst nicht explizit alle Elemente, die Bestandteil eines Teilcubes werden.</span><span class="sxs-lookup"><span data-stu-id="f0848-113">Although the CREATE SUBCUBE statement is fairly simple to use, the statement itself does not explicitly show all the members that become part of a subcube.</span></span> <span data-ttu-id="f0848-114">Für das Definieren eines Teilcubes gelten folgende Regeln:</span><span class="sxs-lookup"><span data-stu-id="f0848-114">In defining a subcube, the following rules apply:</span></span>  
  
-   <span data-ttu-id="f0848-115">Wenn Sie das `(All)`-Element einer Hierarchie einfügen, fügen Sie jedes Element dieser Hierarchie ein.</span><span class="sxs-lookup"><span data-stu-id="f0848-115">If you include the `(All)` member of a hierarchy, you include every member of that hierarchy.</span></span>  
  
-   <span data-ttu-id="f0848-116">Wenn Sie ein Element einfügen, fügen Sie auch die Vorgänger und Nachfolger dieses Elements ein.</span><span class="sxs-lookup"><span data-stu-id="f0848-116">If you include any member, you include that member's ascendants and descendants.</span></span>  
  
-   <span data-ttu-id="f0848-117">Wenn Sie jedes Element einer Ebene einfügen, fügen Sie alle Elemente aus der Hierarchie ein.</span><span class="sxs-lookup"><span data-stu-id="f0848-117">If you include every member from a level, you include all members from the hierarchy.</span></span> <span data-ttu-id="f0848-118">Elemente aus anderen Hierarchien werden ausgeschlossen, wenn diese Elemente keine Elemente auf der Ebene haben (beispielsweise eine unausgeglichene Hierarchie: etwa eine Stadt, für die es keine Kunden gibt).</span><span class="sxs-lookup"><span data-stu-id="f0848-118">Members from other hierarchies will be excluded if those members do not exist with members from the level (for example, an unbalanced hierarchy such as a city that does not contain customers).</span></span>  
  
-   <span data-ttu-id="f0848-119">Ein Teilcube enthält immer jedes `(All)`-Element aus dem Cube.</span><span class="sxs-lookup"><span data-stu-id="f0848-119">A subcube will always contain every `(All)` member from the cube.</span></span>  
  
 <span data-ttu-id="f0848-120">Aggregatwerte im Teilcube werden visuell summiert.</span><span class="sxs-lookup"><span data-stu-id="f0848-120">Additionally, aggregate values within the subcube are visually totaled.</span></span> <span data-ttu-id="f0848-121">Ein Teilcube enthält beispielsweise `USA`, `WA`und `OR`.</span><span class="sxs-lookup"><span data-stu-id="f0848-121">For example, a subcube contains `USA`, `WA`, and `OR`.</span></span> <span data-ttu-id="f0848-122">Der Aggregatwert für `USA` ist die Summe aus `{WA,OR}` , weil `WA` und `OR` die einzigen Staaten sind, die durch den Teilcube definiert sind.</span><span class="sxs-lookup"><span data-stu-id="f0848-122">The aggregate value for `USA` will be the sum of `{WA,OR}` because `WA` and `OR` are the only states defined by the subcube.</span></span> <span data-ttu-id="f0848-123">Alle anderen Staaten werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f0848-123">All other states will be ignored.</span></span>  
  
 <span data-ttu-id="f0848-124">Explizite Verweise auf Zellen, die sich außerhalb des Teilcubes befinden, geben Zellwerte zurück, die im Kontext des gesamten Cubes ausgewertet wurden.</span><span class="sxs-lookup"><span data-stu-id="f0848-124">Also, explicit references to cells outside the subcube return cell values that are evaluated in the context of the whole cube.</span></span> <span data-ttu-id="f0848-125">Beispielsweise erstellen Sie einen Teilcube, der auf das aktuelle Jahr beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="f0848-125">For example, you create a subcube that is limited to the current year.</span></span> <span data-ttu-id="f0848-126">Sie verwenden dann die [ParallelPeriod](/sql/mdx/parallelperiod-mdx) -Funktion, um das aktuelle Jahr mit dem vorherigen Jahr zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="f0848-126">You then use the [ParallelPeriod](/sql/mdx/parallelperiod-mdx) function to compare the current year to the previous year.</span></span> <span data-ttu-id="f0848-127">Der Unterschied in den Werten wird zurückgegeben, obwohl der Wert des vorherigen Jahres außerhalb des Teilcubes liegt.</span><span class="sxs-lookup"><span data-stu-id="f0848-127">The difference in values will be returned even though the previous year's value lies outside the subcube.</span></span>  
  
 <span data-ttu-id="f0848-128">Wenn der ursprüngliche Kontext nicht überschrieben wurde, werden SET-Funktionen, die in einer untergeordneten SELECT-Anweisung ausgewertet werden, im Kontext dieser Anweisung ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="f0848-128">Finally, if the original context is not overwritten, set functions evaluated in a subselect are evaluated in the context of the subselect.</span></span> <span data-ttu-id="f0848-129">Wurde der Kontext überschrieben, werden SET-Funktionen im Kontext des gesamten Cubes ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="f0848-129">If the context is overwritten, set functions are evaluated in the context of the whole cube.</span></span>  
  
## <a name="create-subcube-example"></a><span data-ttu-id="f0848-130">Beispiel zu CREATE SUBCUBE</span><span class="sxs-lookup"><span data-stu-id="f0848-130">CREATE SUBCUBE Example</span></span>  
 <span data-ttu-id="f0848-131">Im folgenden Beispiel wird ein Teilcube erstellt, der den Budget-Cube auf die Konten 4200 und 4300 beschränkt:</span><span class="sxs-lookup"><span data-stu-id="f0848-131">The following example creates a subcube that restricts the Budget cube to only accounts 4200 and 4300:</span></span>  
  
 `CREATE SUBCUBE Budget AS SELECT {[Account].[Account].&[4200], [Account].[Account].&[4300] } ON 0 FROM Budget`  
  
 <span data-ttu-id="f0848-132">Nachdem für die Sitzung ein Teilcube erstellt wurde, werden alle weiteren Abfragen nicht mehr für den gesamten Cube, sondern nur noch für den Teilcube ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f0848-132">Having created a subcube for the session, any subsequent queries will be against the subcube, not the whole cube.</span></span> <span data-ttu-id="f0848-133">Sie führen beispielsweise die folgende Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="f0848-133">For example, you run the following query.</span></span> <span data-ttu-id="f0848-134">Diese Abfrage gibt nur Elemente von den Konten 4200 und 4300 zurück.</span><span class="sxs-lookup"><span data-stu-id="f0848-134">This query will only return members from accounts 4200 and 4300.</span></span>  
  
 `SELECT [Account].[Account].Members ON 0, Measures.Members ON 1 FROM Budget`  
  
## <a name="see-also"></a><span data-ttu-id="f0848-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0848-135">See Also</span></span>  
 <span data-ttu-id="f0848-136">[Einrichten des Cubekontexts in einer Abfrage &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="f0848-136">[Establishing Cube Context in a Query &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span></span>  
 [<span data-ttu-id="f0848-137">Grundlegendes zu MDX-Abfragen &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f0848-137">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
