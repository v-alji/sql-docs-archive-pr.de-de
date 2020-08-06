---
title: Hinzufügen oder Löschen einer benutzerdefinierten Hierarchie | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Analysis Services], adding
- removing hierarchies
- adding hierarchies
- deleting hierarchies
- hierarchies [Analysis Services], removing
ms.assetid: 953818b4-9543-4c01-bb20-1d45ec6dfb91
author: minewiskan
ms.author: owend
ms.openlocfilehash: d20404a1d93d57221eb830366392eb90600f26c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619392"
---
# <a name="add-or-delete-a-user-defined-hierarchy"></a><span data-ttu-id="51c2f-102">Hinzufügen oder Löschen einer benutzerdefinierten Hierarchie</span><span class="sxs-lookup"><span data-stu-id="51c2f-102">Add or Delete a User-Defined Hierarchy</span></span>
  <span data-ttu-id="51c2f-103">Zum Hinzufügen oder Entfernen einer benutzerdefinierten Hierarchie zu bzw. aus einer Dimension verwenden Sie die Registerkarte **Dimensionsstruktur** im Dimensions-Designer von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="51c2f-103">You add a user-defined hierarchy to or remove a user-defined hierarchy from a dimension on the **Dimension Structure** tab in Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="51c2f-104">Wenn Sie eine benutzerdefinierte Hierarchie hinzufügen, steht diese den Benutzern erst dann zur Verfügung, wenn sie in einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz instanziiert und die Dimension verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="51c2f-104">When you add a user-defined hierarchy, it is not available to users until it is instantiated in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and the dimension is processed.</span></span> <span data-ttu-id="51c2f-105">Weitere Informationen finden Sie unter mehr [dimensionale Modell Datenbanken &#40;SSAS&#41;](multidimensional-model-databases-ssas.md) und mehr [dimensionale Modell Objekt Verarbeitung](processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="51c2f-105">For more information, see [Multidimensional Model Databases &#40;SSAS&#41;](multidimensional-model-databases-ssas.md) and [Multidimensional Model Object Processing](processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
### <a name="to-add-a-user-defined-hierarchy-to-a-dimension"></a><span data-ttu-id="51c2f-106">So fügen Sie einer Dimension eine benutzerdefinierte Hierarchie hinzu</span><span class="sxs-lookup"><span data-stu-id="51c2f-106">To add a user-defined hierarchy to a dimension</span></span>  
  
1.  <span data-ttu-id="51c2f-107">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das entsprechende [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekt und danach die Dimension, mit der Sie arbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="51c2f-107">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the appropriate [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, and then open the dimension with which you want to work.</span></span>  
  
     <span data-ttu-id="51c2f-108">Die Dimension wird im Dimensions-Designer auf der Registerkarte **Dimensionsstruktur** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="51c2f-108">The dimension opens in Dimension Designer on the **Dimension Structure** tab.</span></span>  
  
2.  <span data-ttu-id="51c2f-109">Ziehen Sie das Attribut, das Sie in der benutzerdefinierten Hierarchie verwenden möchten, aus dem Bereich **Attribute** in den Bereich **Hierarchien** .</span><span class="sxs-lookup"><span data-stu-id="51c2f-109">From the **Attributes** pane, drag an attribute that you want to use in the user-defined hierarchy to the **Hierarchies** pane.</span></span>  
  
3.  <span data-ttu-id="51c2f-110">Ziehen Sie zusätzliche Attribute in den Bereich, um Ebenen in der benutzerdefinierten Hierarchie zu bilden.</span><span class="sxs-lookup"><span data-stu-id="51c2f-110">Drag additional attributes to form levels in the user-defined hierarchy.</span></span>  
  
     <span data-ttu-id="51c2f-111">Die Reihenfolge, in der Attribute in der Hierarchie aufgeführt sind, spielt eine wichtige Rolle.</span><span class="sxs-lookup"><span data-stu-id="51c2f-111">The order in which attributes are listed in the hierarchy is important.</span></span> <span data-ttu-id="51c2f-112">Beispielsweise sollten in einer Zeithierarchie Jahre in der Hierarchieliste höher angezeigt werden als Tage.</span><span class="sxs-lookup"><span data-stu-id="51c2f-112">For example, in a time hierarchy, years should appear higher in the hierarchy list than days.</span></span>  
  
4.  <span data-ttu-id="51c2f-113">Wahlweise können Sie die Ebenen in der benutzerdefinierten Hierarchie auch neu anordnen, indem Sie sie an die jeweils gewünschte Position ziehen.</span><span class="sxs-lookup"><span data-stu-id="51c2f-113">Optionally, rearrange the levels in the user-defined hierarchy by dragging them to the correct positions.</span></span>  
  
5.  <span data-ttu-id="51c2f-114">Sie haben auch die Möglichkeit, Eigenschaften der benutzerdefinierten Hierarchie oder deren Ebenen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="51c2f-114">Optionally, modify properties of the user-defined hierarchy or its levels.</span></span>  
  
     <span data-ttu-id="51c2f-115">So empfiehlt es sich beispielsweise, einen Namen für die benutzerdefinierte Hierarchie anzugeben, eine oder mehrere Ebenen umzubenennen und einen benutzerdefinierten Namen für die Alle-Ebene zu definieren.</span><span class="sxs-lookup"><span data-stu-id="51c2f-115">For example, you might want to specify a name for the user-defined hierarchy, rename one or more of its levels, and define a custom name for the All level.</span></span> <span data-ttu-id="51c2f-116">Weitere Informationen finden Sie unter [Eigenschaften der Benutzer Hierarchie und Eigenschaften](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md)von [Ebenen &#91;&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md).</span><span class="sxs-lookup"><span data-stu-id="51c2f-116">For more information, see [User Hierarchy Properties](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md), and [Level Properties &#91;Paved Over&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="51c2f-117">Standardmäßig ist eine benutzerdefinierte Hierarchie lediglich ein Pfad, in dem Benutzer nach Informationen suchen können.</span><span class="sxs-lookup"><span data-stu-id="51c2f-117">By default, a user-defined hierarchy is just a path that enables users to drill down for information.</span></span> <span data-ttu-id="51c2f-118">Wenn jedoch Beziehungen zwischen Ebenen vorhanden sind, können Sie die Abfrageleistung verbessern, indem Sie Attributbeziehungen zwischen Ebenen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="51c2f-118">However, if relationships exist between levels, you can increase query performance by configuring attribute relationships between levels.</span></span> <span data-ttu-id="51c2f-119">Weitere Informationen finden Sie unter [Attributbeziehungen](../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md) und [Definieren von Attributbeziehungen](attribute-relationships-define.md).</span><span class="sxs-lookup"><span data-stu-id="51c2f-119">For more information, see [Attribute Relationships](../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md) and [Define Attribute Relationships](attribute-relationships-define.md).</span></span>  
  
### <a name="to-remove-a-user-defined-hierarchy-from-a-dimension"></a><span data-ttu-id="51c2f-120">So entfernen Sie eine benutzerdefinierte Hierarchie aus einer Dimension</span><span class="sxs-lookup"><span data-stu-id="51c2f-120">To remove a user-defined hierarchy from a dimension</span></span>  
  
-   <span data-ttu-id="51c2f-121">Klicken Sie auf der Registerkarte **Dimensionsstruktur** im Bereich **Hierarchien** auf die benutzerdefinierte Hierarchie, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="51c2f-121">On the **Dimension Structure** tab, click the user-defined hierarchy that you want to remove in the **Hierarchies** pane.</span></span> <span data-ttu-id="51c2f-122">Klicken Sie auf der Symbolleiste auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="51c2f-122">On the toolbar, click **Delete**.</span></span>  
  
     - <span data-ttu-id="51c2f-123">ODER</span><span class="sxs-lookup"><span data-stu-id="51c2f-123">or -</span></span>  
  
-   <span data-ttu-id="51c2f-124">Klicken Sie im Bereich **Hierarchien** mit der rechten Maustaste auf die benutzerdefinierte Hierarchie, die Sie entfernen möchten, und klicken Sie anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="51c2f-124">Right-click the user-defined hierarchy that you want to remove in the **Hierarchies** pane and then click **Delete**.</span></span>  
  
     - <span data-ttu-id="51c2f-125">ODER</span><span class="sxs-lookup"><span data-stu-id="51c2f-125">or -</span></span>  
  
-   <span data-ttu-id="51c2f-126">Ziehen Sie die benutzerdefinierte Hierarchie von der Entwurfsoberfläche weg.</span><span class="sxs-lookup"><span data-stu-id="51c2f-126">Drag the user-defined hierarchy off of the design surface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51c2f-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51c2f-127">See Also</span></span>  
 <span data-ttu-id="51c2f-128">[Benutzer Hierarchien](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="51c2f-128">[User Hierarchies](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies.md) </span></span>  
 [<span data-ttu-id="51c2f-129">Erstellen von benutzerdefinierten Hierarchien</span><span class="sxs-lookup"><span data-stu-id="51c2f-129">Create User-Defined Hierarchies</span></span>](user-defined-hierarchies-create.md)  
  
  
