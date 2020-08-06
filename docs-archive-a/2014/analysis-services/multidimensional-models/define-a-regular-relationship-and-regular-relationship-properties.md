---
title: Definieren regulärer Beziehungs-und regulärer Beziehungs Eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- granularity attribute
- relationships [Analysis Services], regular relationships
ms.assetid: 840280d8-20c3-46c0-99ea-62479469c36b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b4f49e219a85d5577fb1acddfe14e7afd3b105d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621698"
---
# <a name="define-a-regular-relationship-and-regular-relationship-properties"></a><span data-ttu-id="87912-102">Definieren einer regulären Beziehung und von Eigenschaften einer regulären Beziehung</span><span class="sxs-lookup"><span data-stu-id="87912-102">Define a Regular Relationship and Regular Relationship Properties</span></span>
  <span data-ttu-id="87912-103">Wenn Sie eine neue Cubedimension oder eine neue Measuregruppe definieren, versucht [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] zu erkennen, ob eine reguläre Beziehung vorhanden ist, und legt dann die Einstellung für die Dimensionsverwendung auf `Regular` fest.</span><span class="sxs-lookup"><span data-stu-id="87912-103">When you define a new cube dimension or a new measure group, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will try to detect if a regular relationship exists and then set the dimension usage setting to `Regular`.</span></span> <span data-ttu-id="87912-104">Sie können eine reguläre Dimensionsbeziehung im Cube-Designer auf der Registerkarte **Dimensionsverwendung** anzeigen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="87912-104">You can view or edit a regular dimension relationship on the **Dimension Usage** tab of Cube Designer.</span></span>  
  
 <span data-ttu-id="87912-105">Beim Definieren der Beziehung einer Cubedimension zu einer Measuregruppe geben Sie auch das Granularitätsattribut für die Beziehung an.</span><span class="sxs-lookup"><span data-stu-id="87912-105">When you define the relationship of a cube dimension to a measure group, you also specify the granularity attribute for that relationship.</span></span> <span data-ttu-id="87912-106">Das Granularitätsattribut definiert die niedrigste Detailstufe, die im Cube für die entsprechende Dimension verfügbar ist. Im Allgemeinen ist dies das Schlüsselattribut für die Dimension.</span><span class="sxs-lookup"><span data-stu-id="87912-106">The granularity attribute defines the lowest level of detail available in the cube for that dimension, which is generally the key attribute for the dimension.</span></span> <span data-ttu-id="87912-107">Mitunter kann es jedoch gewünscht sein, die Granularität einer bestimmten Cubedimension in einer bestimmten Measuregruppe auf eine andere Einheit festzulegen.</span><span class="sxs-lookup"><span data-stu-id="87912-107">However, sometimes you may want to set the granularity of a particular cube dimension in a particular measure group to a different grain.</span></span> <span data-ttu-id="87912-108">So könnte es beispielsweise gewünscht sein, das Granularitätsattribut für die Time-Dimension auf das Month-Attribut anstatt auf das Day-Attribut festzulegen, wenn Sie eine Sales Quotas- oder Budget-Measuregruppe verwenden.</span><span class="sxs-lookup"><span data-stu-id="87912-108">For example, you may want to set the granularity attribute for the Time dimension to the Month attribute instead of to the Day attribute, if you are using a Sales Quotas or a Budget measure group.</span></span> <span data-ttu-id="87912-109">Wenn Sie ein anderes als das Schlüsselattribut als Granularitätsattribut festlegen, müssen Sie sicherstellen, dass alle anderen Attribute in der Dimension über Attributbeziehungen direkt oder indirekt mit diesem anderen Attribut verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="87912-109">When you specify the granularity attribute to be an attribute other than the key attribute, you must guarantee that all other attributes in the dimension are directly or indirectly linked to this other attribute through attribute relationships.</span></span> <span data-ttu-id="87912-110">Andernfalls ist [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] nicht in der Lage, Daten ordnungsgemäß zu aggregieren.</span><span class="sxs-lookup"><span data-stu-id="87912-110">If not, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will be unable to aggregate data correctly.</span></span>  
  
  
