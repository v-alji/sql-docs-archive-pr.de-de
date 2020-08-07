---
title: 'Lektion 4: Definieren von erweiterten Attributen und Dimensions Eigenschaften | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0e86b9be-e47d-4bb4-87eb-136ff3a61aef
author: minewiskan
ms.author: owend
ms.openlocfilehash: deb2d9c40ad5024f6cc4ba6e9148df41a168c6e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718868"
---
# <a name="lesson-4-defining-advanced-attribute-and-dimension-properties"></a><span data-ttu-id="78520-102">Lektion 4: Definieren von erweiterten Attributen und Dimensionseigenschaften</span><span class="sxs-lookup"><span data-stu-id="78520-102">Lesson 4: Defining Advanced Attribute and Dimension Properties</span></span>
  <span data-ttu-id="78520-103">In dieser Lektion lernen Sie, wie einige erweiterte Attributeigenschaften, Attributhierarchien und Dimensionseigenschaften verwendet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="78520-103">In this lesson, you will learn how to use some of the advanced properties of attributes, attribute hierarchies, and dimension properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="78520-104">Diese Lektion baut auf einer erweiterten Version des [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Lernprogrammprojekts auf, das Sie in den ersten drei Lektionen dieses Lernprogramms abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="78520-104">This lesson is based on an enhanced version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project that you completed in the first three lessons of this tutorial.</span></span> <span data-ttu-id="78520-105">In der ersten Aufgabe dieser Lektion wird beschrieben, wo das entsprechende Beispielprojekt für diese Lektion zu finden ist, und welche Unterschiede zwischen diesem Projekt und dem Projekt bestehen, das Sie in den ersten drei Lektionen erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="78520-105">The first task in this lesson describes where to locate the appropriate sample project to use for the lesson, and the difference between this project and the project that you created in the first three lessons.</span></span>  
  
 <span data-ttu-id="78520-106">Diese Lektion enthält die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="78520-106">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="78520-107">Verwenden einer geänderten Version des Analysis Services Tutorial-Projekts</span><span class="sxs-lookup"><span data-stu-id="78520-107">Using a Modified Version of the Analysis Services Tutorial Project</span></span>](lesson-4-1-using-a-modified-version-of-the-analysis-services-tutorial-project.md)  
 <span data-ttu-id="78520-108">In dieser Aufgabe ist eine geänderte Version des [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Lernprogrammprojekts, das über mehrere Measuregruppen und zusätzliche Dimensionen verfügt, zu öffnen, zu überprüfen und bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="78520-108">In this task, you open, review, and deploy a modified version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, which has multiple measure groups and additional dimensions.</span></span>  
  
 [<span data-ttu-id="78520-109">Definieren der Eigenschaften des übergeordneten Attributs in einer Über-/Unterordnungshierarchie</span><span class="sxs-lookup"><span data-stu-id="78520-109">Defining Parent Attribute Properties in a Parent-Child Hierarchy</span></span>](lesson-4-2-defining-parent-attribute-properties-in-a-parent-child-hierarchy.md)  
 <span data-ttu-id="78520-110">In dieser Aufgabe definieren Sie Ebenennamen in einer über- und untergeordneten Dimension und geben an, ob mit übergeordneten Elementen verknüpfte Daten angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="78520-110">In this task, you define level names in a parent-child dimension and specify whether data related to parent members is displayed.</span></span> <span data-ttu-id="78520-111">Weitere Informationen finden Sie unter über [-](multidimensional-models/parent-child-dimension.md) /unterordnungshierarchie und [Attribute in über-und untergeordneten Hierarchien](multidimensional-models/parent-child-dimension-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="78520-111">For more information, see [Parent-Child Hierarchy](multidimensional-models/parent-child-dimension.md) and [Attributes in Parent-Child Hierarchies](multidimensional-models/parent-child-dimension-attributes.md).</span></span>  
  
 [<span data-ttu-id="78520-112">Automatisches Gruppieren von Attributelementen</span><span class="sxs-lookup"><span data-stu-id="78520-112">Automatically Grouping Attribute Members</span></span>](lesson-4-3-automatically-grouping-attribute-members.md)  
 <span data-ttu-id="78520-113">In dieser Aufgabe erstellen Sie automatisch Gruppierungen von Attributelementen basierend auf der Verteilung von Elementen innerhalb der Attributhierarchie.</span><span class="sxs-lookup"><span data-stu-id="78520-113">In this task, you automatically create groupings of attribute members based on the distribution of the members within the attribute hierarchy.</span></span> <span data-ttu-id="78520-114">Weitere Informationen finden Sie unter [Gruppieren von Attributelementen &#40;Diskretisierung&#41;](multidimensional-models/attribute-properties-group-attribute-members.md).</span><span class="sxs-lookup"><span data-stu-id="78520-114">For more information, see [Group Attribute Members &#40;Discretization&#41;](multidimensional-models/attribute-properties-group-attribute-members.md).</span></span>  
  
 [<span data-ttu-id="78520-115">Ausblenden und Deaktivieren von Attributhierarchien</span><span class="sxs-lookup"><span data-stu-id="78520-115">Hiding and Disabling Attribute Hierarchies</span></span>](lesson-4-4-hiding-and-disabling-attribute-hierarchies.md)  
 <span data-ttu-id="78520-116">In dieser Aufgabe lernen Sie, wie und wann Attributhierarchien zu deaktivieren oder auszublenden sind.</span><span class="sxs-lookup"><span data-stu-id="78520-116">In this task, you learn how and when to disable or hide attribute hierarchies.</span></span>  
  
 [<span data-ttu-id="78520-117">Sortieren von Attributelementen basierend auf einem sekundären Attribut</span><span class="sxs-lookup"><span data-stu-id="78520-117">Sorting Attribute Members Based on a Secondary Attribute</span></span>](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md)  
 <span data-ttu-id="78520-118">In dieser Aufgabe lernen Sie, wie Dimensionselemente basierend auf einem sekundären Attribut sortiert werden, um die gewünschte Sortierreihenfolge zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="78520-118">In this task, you learn how to sort dimension members based on a secondary attribute, to achieve the sort order that you want.</span></span>  
  
 [<span data-ttu-id="78520-119">Angeben von Attributbeziehungen zwischen Attributen in einer benutzerdefinierten Hierarchie</span><span class="sxs-lookup"><span data-stu-id="78520-119">Specifying Attribute Relationships Between Attributes in a User-Defined Hierarchy</span></span>](4-6-specifying-attribute-relationships-in-user-defined-hierarchy.md)  
 <span data-ttu-id="78520-120">In dieser Aufgabe lernen Sie, wie Elementeigenschaften für Attribute zu definieren und Aggregationsbeziehungen zwischen ihnen anzugeben sind.</span><span class="sxs-lookup"><span data-stu-id="78520-120">In this task, you learn how to define member properties for attributes and to specify aggregation relationships between them.</span></span> <span data-ttu-id="78520-121">Weitere Informationen finden Sie unter [Definieren von Attribut Beziehungen](multidimensional-models/attribute-relationships-define.md) und [Eigenschaften der Benutzer Hierarchie](multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md).</span><span class="sxs-lookup"><span data-stu-id="78520-121">For more information, see [Define Attribute Relationships](multidimensional-models/attribute-relationships-define.md) and [User Hierarchy Properties](multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md).</span></span>  
  
 [<span data-ttu-id="78520-122">Definieren von unbekannten Elementen und Eigenschaften für das Verarbeiten von NULL-Werten</span><span class="sxs-lookup"><span data-stu-id="78520-122">Defining the Unknown Member and Null Processing Properties</span></span>](lesson-4-7-defining-the-unknown-member-and-null-processing-properties.md)  
 <span data-ttu-id="78520-123">In dieser Aufgabe konfigurieren Sie die Eigenschaften UnknownMember und UnknownMemberName, um Fehlerbedingungen zu behandeln, die durch NULL-Dimensionselemente verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="78520-123">In this task, you configure the UnknownMember and UnknownMemberName properties to handle error conditions caused by null dimension members.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="78520-124">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="78520-124">Next Lesson</span></span>  
 [<span data-ttu-id="78520-125">Lektion 5: Definieren von Beziehungen zwischen Dimensionen und Measuregruppen</span><span class="sxs-lookup"><span data-stu-id="78520-125">Lesson 5: Defining Relationships Between Dimensions and Measure Groups</span></span>](lesson-5-defining-relationships-between-dimensions-and-measure-groups.md)  
  
## <a name="see-also"></a><span data-ttu-id="78520-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="78520-126">See Also</span></span>  
 <span data-ttu-id="78520-127">[Analysis Services Tutorial-Szenario](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="78520-127">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="78520-128">[Mehrdimensionale Modellierung &#40;Adventure Works-Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="78520-128">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 [<span data-ttu-id="78520-129">Dimensionen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="78520-129">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
