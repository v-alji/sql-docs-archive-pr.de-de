---
title: Dialog Feld ' Messungs Gruppen Bindungen ' (Analysis Services Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.dimensionusage.definerelationship.measuregroupbindings.f1
helpviewer_keywords:
- Measure Group Bindings dialog box
ms.assetid: ed642780-5350-438e-af73-b9ceab3f876d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 78693901a5898b140d6efeed16b6f0eaa7577e69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725145"
---
# <a name="measure-group-bindings-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="f3410-102">Dialogfeld 'Measuregruppenbindung' (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="f3410-102">Measure Group Bindings Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="f3410-103">Mithilfe des Dialogfelds **Measuregruppenbindungen** können Sie direkte Beziehungen zwischen Attributen ohne Granularität in einer Cubedimension und Spalten in einer Measuregruppe für eine Beziehung regulärer Dimensionen erstellen und ändern, sowie Optionen für die Verarbeitung von NULL-Werten für jedes Attribut in einer Cubedimension mithilfe des Dialogfelds **Beziehung definieren** angeben.</span><span class="sxs-lookup"><span data-stu-id="f3410-103">Use the **Measure Group Bindings** dialog box to create and modify direct relationships between non-granularity attributes in a cube dimension and columns in a measure group for a regular dimension relationship, as well as to specify null processing options for any attribute in a cube dimension, from the **Define Relationship** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f3410-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="f3410-104">Options</span></span>  
 <span data-ttu-id="f3410-105">**Measuregruppentabelle**</span><span class="sxs-lookup"><span data-stu-id="f3410-105">**Measure group table**</span></span>  
 <span data-ttu-id="f3410-106">Zeigt den Namen der Faktentabelle für die ausgewählte Measuregruppe an.</span><span class="sxs-lookup"><span data-stu-id="f3410-106">Displays the name of the fact table for the selected measure group.</span></span>  
  
 <span data-ttu-id="f3410-107">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="f3410-107">**Attributes**</span></span>  
 <span data-ttu-id="f3410-108">Zeigt ein Raster aus Attributen und Dimensionstabellen an.</span><span class="sxs-lookup"><span data-stu-id="f3410-108">Displays a grid of attributes and dimension tables.</span></span> <span data-ttu-id="f3410-109">Wählen Sie ein Attribut aus, um dessen Eigenschaften unter **Beziehung** zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f3410-109">Select an attribute to create or modify properties in **Relationship** for the selected attribute.</span></span> <span data-ttu-id="f3410-110">Das Raster enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="f3410-110">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="f3410-111">Option</span><span class="sxs-lookup"><span data-stu-id="f3410-111">Option</span></span>|<span data-ttu-id="f3410-112">Definition</span><span class="sxs-lookup"><span data-stu-id="f3410-112">Definition</span></span>|  
|------------|----------------|  
|<span data-ttu-id="f3410-113">**Attributname**</span><span class="sxs-lookup"><span data-stu-id="f3410-113">**Attribute Name**</span></span>|<span data-ttu-id="f3410-114">Zeigt den Namen des Attributs an.</span><span class="sxs-lookup"><span data-stu-id="f3410-114">Displays the name of the attribute.</span></span>|  
|<span data-ttu-id="f3410-115">**Dimensionstabelle**</span><span class="sxs-lookup"><span data-stu-id="f3410-115">**Dimension Table**</span></span>|<span data-ttu-id="f3410-116">Zeigt den Namen der Dimensionstabelle an, auf der das Attribut basiert.</span><span class="sxs-lookup"><span data-stu-id="f3410-116">Displays the name of the dimension table on which the attribute is based.</span></span>|  
  
 <span data-ttu-id="f3410-117">**Beziehung**</span><span class="sxs-lookup"><span data-stu-id="f3410-117">**Relationship**</span></span>  
 <span data-ttu-id="f3410-118">Zeigt ein Raster für die Beziehungen zwischen Dimensionstabellenspalten für das ausgewählte Attribut und Faktentabellenspalten für die ausgewählte Measuregruppe an. Außerdem wird die Option zur Verarbeitung von NULL-Werten für die Beziehung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f3410-118">Displays a grid of relationships between dimension table columns for the selected attribute and fact table columns for the selected measure group as well as the null processing option for the relationship.</span></span> <span data-ttu-id="f3410-119">Das Raster enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="f3410-119">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="f3410-120">Option</span><span class="sxs-lookup"><span data-stu-id="f3410-120">Option</span></span>|<span data-ttu-id="f3410-121">Definition</span><span class="sxs-lookup"><span data-stu-id="f3410-121">Definition</span></span>|  
|------------|----------------|  
|<span data-ttu-id="f3410-122">**Dimensionsspalten**</span><span class="sxs-lookup"><span data-stu-id="f3410-122">**Dimension Columns**</span></span>|<span data-ttu-id="f3410-123">Zeigt die Spalten der Dimensionstabelle an, auf denen das unter **Attribute** ausgewählte Attribut basiert.</span><span class="sxs-lookup"><span data-stu-id="f3410-123">Displays the columns from the dimension table on which the attribute selected in **Attributes** is based.</span></span>|  
|<span data-ttu-id="f3410-124">**Measuregruppenspalten**</span><span class="sxs-lookup"><span data-stu-id="f3410-124">**Measure Group Columns**</span></span>|<span data-ttu-id="f3410-125">Wählen Sie entweder **Von Dimension geerbt** aus, um die von der Dimension geerbte Measuregruppenbeziehung zu verwenden, oder wählen Sie eine Spalte aus der Faktentabelle aus, auf der die Measuregruppe basiert, um eine Beziehung explizit zu definieren.</span><span class="sxs-lookup"><span data-stu-id="f3410-125">Select either **Inherited from dimension** to use the measure group relationship inherited from the dimension, or select a column from the fact table on which the measure group is based to explicitly define a relationship.</span></span>|  
|<span data-ttu-id="f3410-126">**NULL-Verarbeitung**</span><span class="sxs-lookup"><span data-stu-id="f3410-126">**Null Processing**</span></span>|<span data-ttu-id="f3410-127">Wählen Sie eine Option zur NULL-Verarbeitung für das Attribut aus.</span><span class="sxs-lookup"><span data-stu-id="f3410-127">Select a null processing option for the attribute.</span></span> <span data-ttu-id="f3410-128">Weitere Informationen zu den Optionen für die NULL-Verarbeitung finden Sie unter [NullProcessing-Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/nullprocessing-element-assl).</span><span class="sxs-lookup"><span data-stu-id="f3410-128">For more information about null processing options, see [NullProcessing Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/nullprocessing-element-assl).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3410-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3410-129">See Also</span></span>  
 <span data-ttu-id="f3410-130">[Dialog Feld ' Beziehung definieren ' &#40;Analysis Services Mehrdimensionale Daten&#41;](define-relationship-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="f3410-130">[Define Relationship Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](define-relationship-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="f3410-131">Analysis Services Designer und Dialog Felder &#40;Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="f3410-131">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
