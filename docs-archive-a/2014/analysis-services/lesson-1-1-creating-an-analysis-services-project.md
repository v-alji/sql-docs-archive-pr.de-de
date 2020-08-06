---
title: Erstellen eines Analysis Services Projekts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 065fdc60-1791-4e27-9ed5-51d751b3f8c4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 50640dd7821943dfc3914326f7e8cba32253d307
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608056"
---
# <a name="creating-an-analysis-services-project"></a><span data-ttu-id="ddb30-102">Erstellen eines Analysis Services-Projekts</span><span class="sxs-lookup"><span data-stu-id="ddb30-102">Creating an Analysis Services Project</span></span>
  <span data-ttu-id="ddb30-103">In der folgenden Aufgabe verwenden Sie, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] um auf [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] `Analysis Services Tutorial` der Grundlage der Projektvorlage ein neues Projekt mit dem Namen zu erstellen [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ddb30-103">In the following task, you use [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to create a new [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project named `Analysis Services Tutorial`, based on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Project template.</span></span> <span data-ttu-id="ddb30-104">Ein *Projekt* ist eine Sammlung verknüpfter Objekte.</span><span class="sxs-lookup"><span data-stu-id="ddb30-104">A *project* is a collection of related objects.</span></span> <span data-ttu-id="ddb30-105">Projekte befinden sich in einer Projektmappe, zu der mindestens ein Projekt gehört.</span><span class="sxs-lookup"><span data-stu-id="ddb30-105">Projects exist within a solution, which includes one or more projects.</span></span> <span data-ttu-id="ddb30-106">Weitere Informationen finden Sie unter [Erstellen eines Analysis Services-Projekts &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="ddb30-106">For more information, see [Create an Analysis Services Project &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md).</span></span>  
  
### <a name="to-create-a-new-analysis-services-project"></a><span data-ttu-id="ddb30-107">So erstellen Sie ein neues Analysis Services-Projekt</span><span class="sxs-lookup"><span data-stu-id="ddb30-107">To create a new Analysis Services project</span></span>  
  
1.  <span data-ttu-id="ddb30-108">Klicken Sie auf **Start**, zeigen sie auf **Alle Programme**und dann auf **Microsoft SQL Server 2012**, und klicken Sie auf **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="ddb30-108">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2012**, and then click **SQL Server Data Tools**.</span></span>  
  
     <span data-ttu-id="ddb30-109">Die [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Entwicklungsumgebung wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ddb30-109">The [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] development environment opens.</span></span>  
  
2.  <span data-ttu-id="ddb30-110">Klicken Sie auf der Startseite von [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]auf **Neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="ddb30-110">On the Start page of [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], click **New Project**.</span></span>  
  
3.  <span data-ttu-id="ddb30-111">Erweitern Sie im Dialogfeld **Neues Projekt** im Bereich **Installierte Vorlagen** die Option **Business Intelligence**, und wählen Sie dann **Analysis Services**aus.</span><span class="sxs-lookup"><span data-stu-id="ddb30-111">In the **New Project** dialog box, in the **Installed Templates** pane, expand **Business Intelligence**, and then select **Analysis Services**.</span></span> <span data-ttu-id="ddb30-112">Wählen Sie die Vorlage für multidimensionale Projekte bzw. Data Mining-Projekte von Analysis Services aus \*\*\*\* .</span><span class="sxs-lookup"><span data-stu-id="ddb30-112">Choose the **Analysis Services Multidimensional and Data Mining Project** template.</span></span>  
  
     <span data-ttu-id="ddb30-113">Beachten Sie, dass der Standardprojektname, Speicherort und Standardname der Projektmappe unten im Dialogfeld erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ddb30-113">Notice the default project name, location, and the default solution name are generated in the bottom of the dialog box.</span></span> <span data-ttu-id="ddb30-114">Für die Projektmappe wird standardmäßig ein neues Verzeichnis erstellt.</span><span class="sxs-lookup"><span data-stu-id="ddb30-114">By default, a new directory is created for the solution.</span></span>  
  
4.  <span data-ttu-id="ddb30-115">Ändern Sie den Projektnamen in `Analysis Services Tutorial` , wodurch auch das Feld Projektmappenname geändert wird, und klicken Sie dann auf **OK**. **Solution name**</span><span class="sxs-lookup"><span data-stu-id="ddb30-115">Change the project Name to `Analysis Services Tutorial`, which also changes the **Solution name** box, and then click **OK**.</span></span>  
  
 <span data-ttu-id="ddb30-116">Sie haben das `Analysis Services Tutorial` Projekt basierend auf der Analysis Services Vorlage für mehr **dimensionale und Data Mining-Projekte** in einer neuen Projekt Mappe erstellt, die ebenfalls den Namen hat `Analysis Services Tutorial` .</span><span class="sxs-lookup"><span data-stu-id="ddb30-116">You have successfully created the `Analysis Services Tutorial` project, based on the **Analysis Services Multidimensional and Data Mining Project** template, within a new solution that is also named `Analysis Services Tutorial`.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ddb30-117">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="ddb30-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ddb30-118">Definieren einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="ddb30-118">Defining a Data Source</span></span>](lesson-1-2-defining-a-data-source.md)  
  
## <a name="see-also"></a><span data-ttu-id="ddb30-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ddb30-119">See Also</span></span>  
 <span data-ttu-id="ddb30-120">[Erstellen mehrdimensionaler Modelle mithilfe von SQL Server Data Tools &#40;SSDT&#41;](multidimensional-models/creating-multidimensional-models-using-sql-server-data-tools-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="ddb30-120">[Creating Multidimensional Models Using SQL Server Data Tools &#40;SSDT&#41;](multidimensional-models/creating-multidimensional-models-using-sql-server-data-tools-ssdt.md) </span></span>  
 [<span data-ttu-id="ddb30-121">Erstellen eines Analysis Services-Projekts &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="ddb30-121">Create an Analysis Services Project &#40;SSDT&#41;</span></span>](multidimensional-models/create-an-analysis-services-project-ssdt.md)  
  
  
