---
title: Projekt Elemente kopieren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data sources [Integration Services], copying
- packages [Integration Services], copying
- copying data source views
- copying data sources
- copying packages
- data source views [Integration Services], copying
ms.assetid: 1606c54d-20f9-49f3-a4ef-caad83a772aa
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3456209c467c3b8474e130181d02304911098d2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618835"
---
# <a name="copy-project-items"></a><span data-ttu-id="d06ca-102">Kopieren von Projektelementen</span><span class="sxs-lookup"><span data-stu-id="d06ca-102">Copy Project Items</span></span>
  <span data-ttu-id="d06ca-103">In diesem Thema wird beschrieben, wie Sie Objekte in einem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt oder zwischen [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekten kopieren können.</span><span class="sxs-lookup"><span data-stu-id="d06ca-103">This topic describes how to copy objects within an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project or between [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects.</span></span> <span data-ttu-id="d06ca-104">Sie können Objekte auch zwischen anderen Typen von [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] -Projekten, [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] und [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]kopieren.</span><span class="sxs-lookup"><span data-stu-id="d06ca-104">You can also copy objects between the other types of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] projects, [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] and [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="d06ca-105">Für den Kopiervorgang zwischen den Projekten müssen die Projekte Teil derselben [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] -Projektmappe sein.</span><span class="sxs-lookup"><span data-stu-id="d06ca-105">To copy between projects, the project must be part of the same [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] solution.</span></span> <span data-ttu-id="d06ca-106">Weitere Informationen finden Sie unter [Integration Services-Projekte &#40;SSIS&#41;](integration-services-ssis-projects-and-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="d06ca-106">For more information, see [Integration Services &#40;SSIS&#41; Projects](integration-services-ssis-projects-and-solutions.md).</span></span>  
  
### <a name="to-copy-project-level-items"></a><span data-ttu-id="d06ca-107">So kopieren Sie Projektebenenelemente</span><span class="sxs-lookup"><span data-stu-id="d06ca-107">To copy project level items</span></span>  
  
1.  <span data-ttu-id="d06ca-108">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt bzw. die Projektmappe, mit dem bzw. mit der Sie arbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="d06ca-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project or solution that you want to work with.</span></span>  
  
2.  <span data-ttu-id="d06ca-109">Erweitern Sie das Projekt und den Elementordner, aus dem Sie kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d06ca-109">Expand the project and item folder to copy from.</span></span>  
  
3.  <span data-ttu-id="d06ca-110">Klicken Sie mit der rechten Maustaste auf das Element, und klicken Sie anschließend auf **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="d06ca-110">Right-click the item and click **Copy**.</span></span>  
  
4.  <span data-ttu-id="d06ca-111">Klicken Sie mit der rechten Maustaste auf das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt, in das kopiert werden soll, und klicken Sie auf **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="d06ca-111">Right-click the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to copy to and click **Paste**.</span></span>  
  
     <span data-ttu-id="d06ca-112">Die Elemente werden automatisch in den richtigen Ordner kopiert.</span><span class="sxs-lookup"><span data-stu-id="d06ca-112">The items are automatically copied to the correct folder.</span></span> <span data-ttu-id="d06ca-113">Wenn Sie in das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt Elemente kopieren, die keine Pakete darstellen, werden die Elemente in den Ordner **Sonstiges** kopiert.</span><span class="sxs-lookup"><span data-stu-id="d06ca-113">If you copy items to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that are not packages, the items are copied to the **Miscellaneous** folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d06ca-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d06ca-114">See Also</span></span>  
 <span data-ttu-id="d06ca-115">[Integration Services &#40;SSIS-&#41; Paketen](../../2014/integration-services/integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="d06ca-115">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="d06ca-116">Kopieren von Paketobjekten</span><span class="sxs-lookup"><span data-stu-id="d06ca-116">Copy Package Objects</span></span>](../../2014/integration-services/copy-package-objects.md)  
  
  
