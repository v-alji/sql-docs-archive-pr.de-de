---
title: Löschen einer Datenquellen Sicht (Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- deleting data source views
- data source views [Analysis Services], deleting
- removing data source views
ms.assetid: ae3f5ca0-ecbf-4b52-8386-eb457719d854
author: minewiskan
ms.author: owend
ms.openlocfilehash: 24b587e8d8961161ea803915c31d117c11f7cf2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622250"
---
# <a name="delete-a-data-source-view-analysis-services"></a><span data-ttu-id="33ceb-102">Löschen einer Datenquellensicht (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="33ceb-102">Delete a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="33ceb-103">Wenn Sie in einem OLAP-Projekt eine Datenquellensicht (Data Source View, DSV) nicht mehr verwenden, können Sie sie aus dem Projekt in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]löschen.</span><span class="sxs-lookup"><span data-stu-id="33ceb-103">If you are no longer using a data source view (DSV) in an OLAP project, you can delete it from the project in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="33ceb-104">Das Löschen einer DSV kann nicht rückgängig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="33ceb-104">Deleting a DSV is permanent.</span></span> <span data-ttu-id="33ceb-105">Eine gelöschte DSV kann in einem Projekt oder einer Datenbank von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="33ceb-105">You cannot restore a deleted DSV to a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database.</span></span>  
  
 <span data-ttu-id="33ceb-106">DSVs, von denen andere Objekte abhängen, können nicht aus einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank gelöscht werden, die von [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] im Onlinemodus geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="33ceb-106">DSVs that other objects depend on cannot be deleted from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database opened by [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] in online mode.</span></span> <span data-ttu-id="33ceb-107">Um eine DSV aus einem Projekt zu löschen, das mit einer auf einem Server ausgeführten Datenbank verbunden ist, müssen Sie zuerst alle von der DSV abhängigen Objekte in der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank löschen, bevor Sie die DSV selbst löschen können.</span><span class="sxs-lookup"><span data-stu-id="33ceb-107">To delete a DSV from a project that is connected o a database running on a server, you must first delete all objects in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that depend on that DSV before deleting the DSV itself.</span></span>  
  
 <span data-ttu-id="33ceb-108">Durch das Löschen einer DSV werden andere [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Objekte, die davon abhängig sind, ungültig. Aus diesem Grund wird vor dem Löschen der DSV die Liste der Objekte angezeigt, die durch das Entfernen der DSV ungültig werden.</span><span class="sxs-lookup"><span data-stu-id="33ceb-108">Deleting a DSV will invalidate other [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects that depend on it, so before you delete the DSV, you will see the list of objects that will become invalid once the DSV is removed.</span></span> <span data-ttu-id="33ceb-109">Überprüfen Sie die Liste sorgfältig, um sicherzustellen, dass keine Objekte enthalten sind, die Sie weiterhin verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="33ceb-109">Review this list carefully to be sure that it does not include objects you still expect to use.</span></span>  
  
 <span data-ttu-id="33ceb-110">![Objekte löschen (Dialogfeld)](../media/ssas-olapdsv-deleteobjects.gif "Objekte löschen (Dialogfeld)")</span><span class="sxs-lookup"><span data-stu-id="33ceb-110">![Delete Objects dialog box](../media/ssas-olapdsv-deleteobjects.gif "Delete Objects dialog box")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33ceb-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="33ceb-111">See Also</span></span>  
 <span data-ttu-id="33ceb-112">[Datenquellen Sichten in mehrdimensionalen Modellen](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="33ceb-112">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="33ceb-113">Ändern von Eigenschaften in einer Datenquellensicht &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="33ceb-113">Change Properties in a Data Source View &#40;Analysis Services&#41;</span></span>](change-properties-in-a-data-source-view-analysis-services.md)  
  
  
