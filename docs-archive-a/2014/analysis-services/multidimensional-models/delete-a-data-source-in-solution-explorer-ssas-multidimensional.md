---
title: Löschen einer Datenquelle in Projektmappen-Explorer (SSAS Multidimensional) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.deleteobjects.f1
helpviewer_keywords:
- data sources [Analysis Services], deleting
- deleting data sources
- removing data sources
ms.assetid: b45441ef-f909-4736-98b9-cc80d0acac99
author: minewiskan
ms.author: owend
ms.openlocfilehash: d6101c8704579894590994d88e0286197148b694
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622253"
---
# <a name="delete-a-data-source-in-solution-explorer-ssas-multidimensional"></a><span data-ttu-id="e05a4-102">Löschen einer Datenquelle in Projektmappen-Explorer (SSAS – mehrdimensional)</span><span class="sxs-lookup"><span data-stu-id="e05a4-102">Delete a Data Source in Solution Explorer (SSAS Multidimensional)</span></span>
  <span data-ttu-id="e05a4-103">Sie können ein Datenquellenobjekt löschen, um es dauerhaft aus einem mehrdimensionalen Analysis Services-Modellprojekt zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="e05a4-103">You can delete a data source object to permanently remove it from an Analysis Services multidimensional model project.</span></span>  
  
 <span data-ttu-id="e05a4-104">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]bilden Datenquellen die Grundlage, auf der Datenquellensichten erstellt werden. Datenquellensichten werden wiederum verwendet, um Dimensionen, Cubes und Miningstrukturen in einem Projekt oder einer Datenbank von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] zu definieren.</span><span class="sxs-lookup"><span data-stu-id="e05a4-104">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], data sources provide the basis on which data source views are constructed, and data source views are in turn used to define dimensions, cubes, and mining structures in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database.</span></span> <span data-ttu-id="e05a4-105">Aus diesem Grund führt das Löschen einer Datenquelle u. U. dazu, dass andere [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Objekte in einem [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekt ungültig werden.</span><span class="sxs-lookup"><span data-stu-id="e05a4-105">Therefore, deleting a data source may invalidate other [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="e05a4-106">Sie sollten immer die Liste der abhängigen Objekte überprüfen, die vor dem Löschen des Objekts bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e05a4-106">You should always review the list of dependent objects that is provided before deleting the object.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e05a4-107">Datenquellen, von denen andere Objekte abhängen, können nicht aus einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank gelöscht werden, die von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] im Onlinemodus geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="e05a4-107">Data sources on which other objects depend cannot be deleted from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database opened by [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in online mode.</span></span> <span data-ttu-id="e05a4-108">Sie müssen in der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank alle Objekte löschen, die von dieser Datenquelle abhängig sind, bevor Sie die Datenquelle löschen.</span><span class="sxs-lookup"><span data-stu-id="e05a4-108">You must delete all objects in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that depend on that data source before deleting the data source.</span></span> <span data-ttu-id="e05a4-109">Weitere Informationen zum Onlinemodus finden Sie unter [Connect in Online Mode to an Analysis Services Database](connect-in-online-mode-to-an-analysis-services-database.md).</span><span class="sxs-lookup"><span data-stu-id="e05a4-109">For more information about online mode, see [Connect in Online Mode to an Analysis Services Database](connect-in-online-mode-to-an-analysis-services-database.md).</span></span>  
  
### <a name="to-delete-a-data-source"></a><span data-ttu-id="e05a4-110">So löschen Sie eine Datenquelle</span><span class="sxs-lookup"><span data-stu-id="e05a4-110">To delete a data source</span></span>  
  
1.  <span data-ttu-id="e05a4-111">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das Projekt, oder stellen Sie eine Verbindung mit der Datenbank her, aus dem bzw. der Sie eine Datenquelle löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="e05a4-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database from which you want to delete a data source.</span></span>  
  
2.  <span data-ttu-id="e05a4-112">Erweitern Sie im **Projektmappen-Explorer**den Ordner **Datenquellen** .</span><span class="sxs-lookup"><span data-stu-id="e05a4-112">In **Solution Explorer**, expand the **Data Sources** folder.</span></span>  
  
3.  <span data-ttu-id="e05a4-113">Klicken Sie mit der rechten Maustaste auf die Datenquelle, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="e05a4-113">Right-click the data source, and then click **Delete**.</span></span> <span data-ttu-id="e05a4-114">Das Dialogfeld **Objekte löschen**  wird geöffnet und zeigt die Objekte an, die für ungültig erklärt werden, wenn Sie die Datenquelle löschen.</span><span class="sxs-lookup"><span data-stu-id="e05a4-114">The **Delete Objects**  dialog box appears, showing the objects that will be invalidated if you delete the data source.</span></span> <span data-ttu-id="e05a4-115">Überprüfen Sie diese Liste sorgfältig, bevor Sie auf **OK** klicken, um die Datenquelle zu löschen.</span><span class="sxs-lookup"><span data-stu-id="e05a4-115">Review this list carefully before clicking **OK** to delete the data source.</span></span>  
  
4.  <span data-ttu-id="e05a4-116">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="e05a4-116">Save the project.</span></span>  
  
     <span data-ttu-id="e05a4-117">Nachdem Sie eine Datenquelle aus einem [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekt gelöscht haben, müssen Sie das geänderte Projekt speichern. Andernfalls erhalten Sie einen Fehler, wenn Sie das Projekt das nächste Mal öffnen, da die zugrunde liegende XML-Datei der gelöschten Datenquelle fehlt, wenn das Projekt versucht, die gelöschte Datenquelle zu laden.</span><span class="sxs-lookup"><span data-stu-id="e05a4-117">After deleting a data source from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, you must save the modified project or you will receive an error the next time you open the project because the underlying XML file for the deleted data source will be missing when the project attempts to load the deleted data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e05a4-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e05a4-118">See Also</span></span>  
 <span data-ttu-id="e05a4-119">[Datenquellen in mehrdimensionalen Modellen](data-sources-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="e05a4-119">[Data Sources in Multidimensional Models](data-sources-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="e05a4-120">Unterstützte Datenquellen &#40;mehrdimensionalen SSAS-&#41;</span><span class="sxs-lookup"><span data-stu-id="e05a4-120">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](supported-data-sources-ssas-multidimensional.md)  
  
  
