---
title: 'Lektion 5: Definieren von Beziehungen zwischen Dimensionen und Measure-Gruppen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 31aeb271-47a1-433b-a8a5-120bcb4584d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6dbdf20e64e3cd8adc751b69122a380d7b3b3648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616792"
---
# <a name="lesson-5-defining-relationships-between-dimensions-and-measure-groups"></a><span data-ttu-id="d5385-102">Lektion 5: Definieren von Beziehungen zwischen Dimensionen und Measuregruppen</span><span class="sxs-lookup"><span data-stu-id="d5385-102">Lesson 5: Defining Relationships Between Dimensions and Measure Groups</span></span>
  <span data-ttu-id="d5385-103">In den vorhergehenden Lektionen in diesem Lernprogramm haben Sie gelernt, dass zu einem Cube hinzugefügte Datenbankdimensionen als Basis für Cubedimensionen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d5385-103">In the previous lessons in this tutorial, you learned that database dimensions added to a cube can be used as the basis for one or more cube dimensions.</span></span> <span data-ttu-id="d5385-104">In dieser Lektion lernen Sie, verschiedene Typen von Beziehungen zwischen Cubedimensionen und Measuregruppen zu definieren und die Eigenschaften dieser Beziehungen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d5385-104">In this lesson, you learn to define different types of relationships between cube dimensions and measure groups, and to specify the properties of these relationships.</span></span>  
  
 <span data-ttu-id="d5385-105">Weitere Informationen finden Sie unter [Dimensionsbeziehungen](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="d5385-105">For more information, see [Dimension Relationships](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5385-106">Für alle Lektionen in diesem Lernprogramm sind abgeschlossene Projekte online verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d5385-106">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="d5385-107">Sie können jede Lektion aufrufen, indem Sie ein abgeschlossenes Projekt aus der vorherigen Lektion als Ausgangspunkt verwenden.</span><span class="sxs-lookup"><span data-stu-id="d5385-107">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="d5385-108">[Klicken Sie hier](https://go.microsoft.com/fwlink/?LinkID=221866) , um die Beispielprojekte für dieses Lernprogramm herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="d5385-108">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="d5385-109">Diese Lektion enthält die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="d5385-109">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="d5385-110">Definieren einer referenzierten Beziehung</span><span class="sxs-lookup"><span data-stu-id="d5385-110">Defining a Referenced Relationship</span></span>](lesson-5-1-defining-a-referenced-relationship.md)  
 <span data-ttu-id="d5385-111">In dieser Aufgabe erfahren Sie, wie Sie eine Dimension indirekt über eine Dimension mit einer Fakten Tabelle verknüpfen, die direkt über eine Primärschlüssel-Fremdschlüssel Beziehung verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="d5385-111">In this task, you learn to link a dimension to a fact table indirectly through a dimension that is linked directly through a primary key-foreign key relationship.</span></span>  
  
 [<span data-ttu-id="d5385-112">Definieren einer Faktenbeziehung</span><span class="sxs-lookup"><span data-stu-id="d5385-112">Defining a Fact Relationship</span></span>](lesson-5-2-defining-a-fact-relationship.md)  
 <span data-ttu-id="d5385-113">In dieser Aufgabe lernen Sie, eine auf Daten in der Faktentabelle basierende Dimension zu definieren und die Dimensionsbeziehung als Faktenbeziehung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="d5385-113">In this task, you learn to define a dimension based on data in the fact table, and to define the dimension relationship as a fact relationship.</span></span>  
  
 [<span data-ttu-id="d5385-114">Definieren einer m:n-Beziehung</span><span class="sxs-lookup"><span data-stu-id="d5385-114">Defining a Many-to-Many Relationship</span></span>](lesson-5-3-defining-a-many-to-many-relationship.md)  
 <span data-ttu-id="d5385-115">In dieser Aufgabe lernen Sie, einen Fakt mit mehreren Dimensionselementen durch die Definition einer n:n-Beziehung zwischen Dimensions- und Faktentabellen zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="d5385-115">In this task, you learn to relate a fact to multiple dimension members through the definition of a many-to-many relationship between dimension tables and fact tables.</span></span>  
  
 [<span data-ttu-id="d5385-116">Definieren von Dimensionsgranularität innerhalb einer Measuregruppe</span><span class="sxs-lookup"><span data-stu-id="d5385-116">Defining Dimension Granularity within a Measure Group</span></span>](lesson-5-4-defining-dimension-granularity-within-a-measure-group.md)  
 <span data-ttu-id="d5385-117">In dieser Aufgabe lernen Sie, die Granularität einer Dimension für eine bestimmte Measuregruppe zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d5385-117">In this task, you learn to modify the granularity of a dimension for a specific measure group.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="d5385-118">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="d5385-118">Next Lesson</span></span>  
 [<span data-ttu-id="d5385-119">Lektion 6: Definieren von Berechnungen</span><span class="sxs-lookup"><span data-stu-id="d5385-119">Lesson 6: Defining Calculations</span></span>](lesson-6-defining-calculations.md)  
  
## <a name="see-also"></a><span data-ttu-id="d5385-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d5385-120">See Also</span></span>  
 <span data-ttu-id="d5385-121">[Analysis Services Tutorial-Szenario](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d5385-121">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="d5385-122">[Mehrdimensionale Modellierung &#40;Adventure Works-Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="d5385-122">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 [<span data-ttu-id="d5385-123">Dimensionsbeziehungen</span><span class="sxs-lookup"><span data-stu-id="d5385-123">Dimension Relationships</span></span>](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md)  
  
  
