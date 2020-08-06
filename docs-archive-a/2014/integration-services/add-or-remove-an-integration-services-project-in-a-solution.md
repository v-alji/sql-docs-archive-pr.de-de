---
title: Hinzufügen oder Entfernen eines Integration Services Projekts in einer Projekt Mappe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- adding projects
- Integration Services projects, adding
- SQL Server Integration Services projects, adding
- SSIS projects, adding
- projects [Integration Services], adding
ms.assetid: f01f6475-b63c-41dc-82ac-b62162b3adf7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 49984c61047a6b716015bd72e518b73cb08b3226
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607959"
---
# <a name="add-or-remove-an-integration-services-project-in-a-solution"></a><span data-ttu-id="1d575-102">Hinzufügen oder Entfernen eines Integration Services-Projekts in einer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="1d575-102">Add or Remove an Integration Services Project in a Solution</span></span>
  <span data-ttu-id="1d575-103">In den folgenden Verfahren wird beschrieben, wie ein [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt zu einer Projektmappe hinzugefügt bzw. aus dieser entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="1d575-103">The following procedures descibe how to add or remove an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in a solution.</span></span>  
  
 <span data-ttu-id="1d575-104">Sie können nur ein Projekt zu einer vorhandenen Projektmappe hinzufügen oder aus einer Projektmappe entfernen, wenn die Projektmappe in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="1d575-104">You can only add a project to an existing solution, or remove a project from a solution, when the solution is visible in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="1d575-105">Wenn Sie die Option Projekt Mappe **immer anzeigen** in ausgewählt haben [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] zeigt eine Projekt Mappe auch dann an, wenn diese Projekt Mappe nur ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="1d575-105">If you have selected the **Always show solution** option in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] will display a solution even when that solution contains only one project.</span></span> <span data-ttu-id="1d575-106">Andernfalls zeigt [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] eine Projektmappe nur an, wenn diese mehr als ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="1d575-106">Otherwise, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] will display a solution only when that solution contains more than one project.</span></span> <span data-ttu-id="1d575-107">Die zusätzlichen Projekte können entweder [!INCLUDE[ssIS](../includes/ssis-md.md)] -Projekte oder Projekte anderer Typen sein.</span><span class="sxs-lookup"><span data-stu-id="1d575-107">The additional projects can be either [!INCLUDE[ssIS](../includes/ssis-md.md)] projects or projects of other types.</span></span>  
  
## <a name="adding-an-integration-services-project"></a><span data-ttu-id="1d575-108">Hinzufügen eines Integration Services-Projekts</span><span class="sxs-lookup"><span data-stu-id="1d575-108">Adding an Integration Services Project</span></span>  
 <span data-ttu-id="1d575-109">Beim Hinzufügen eines Projekts können Sie mit [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ein neues, leeres Projekt erstellen oder ein bereits für eine andere Projektmappe erstelltes Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1d575-109">When you add a project, you can have [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] create a new, blank project, or you can add a project that you have already created for a different solution.</span></span> <span data-ttu-id="1d575-110">Sie können ein Projekt nur einer vorhandenen Projektmappe hinzufügen, wenn die Projektmappe in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="1d575-110">You can only add a project to an existing solution when the solution is visible in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
#### <a name="to-add-a-new-integration-services-project-to-a-solution"></a><span data-ttu-id="1d575-111">So fügen Sie einer Projektmappe ein neues SQL Server Integration Services-Projekt hinzu</span><span class="sxs-lookup"><span data-stu-id="1d575-111">To add a new Integration Services project to a solution</span></span>  
  
1.  <span data-ttu-id="1d575-112">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]die Projektmappe, der Sie ein neues [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt hinzufügen möchten, und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="1d575-112">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution to which you want to add a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="1d575-113">Klicken Sie mit der rechten Maustaste auf die Projektmappe, klicken Sie auf **Hinzufügen**, und klicken Sie dann auf **Neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="1d575-113">Right-click the solution, click **Add**, and then click **New Project**.</span></span>  
  
    -   <span data-ttu-id="1d575-114">Zeigen Sie im Menü **Datei** auf **Hinzufügen**, und klicken Sie dann auf **Neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="1d575-114">On the **File** menu, point to **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="1d575-115">Klicken Sie im Dialogfeld **Neues Projekt hinzufügen** im Fensterbereich **Vorlagen** auf **Integration Services-Projekt** .</span><span class="sxs-lookup"><span data-stu-id="1d575-115">In the **Add New Project** dialog box, click **Integration Services Project** in the **Templates** pane.</span></span>  
  
3.  <span data-ttu-id="1d575-116">Bearbeiten Sie optional den Projektnamen und den Speicherort.</span><span class="sxs-lookup"><span data-stu-id="1d575-116">Optionally, edit the project name and location.</span></span>  
  
4.  <span data-ttu-id="1d575-117">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1d575-117">Click **OK**.</span></span>  
  
#### <a name="to-add-an-existing-integration-services-project-to-a-solution"></a><span data-ttu-id="1d575-118">So fügen Sie einer Projektmappe ein vorhandenes SQL Server Integration Services-Projekt hinzu</span><span class="sxs-lookup"><span data-stu-id="1d575-118">To add an existing Integration Services project to a solution</span></span>  
  
1.  <span data-ttu-id="1d575-119">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]die Projektmappe, der Sie ein vorhandenes [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt hinzufügen möchten, und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="1d575-119">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution to which you want to add an existing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="1d575-120">Klicken Sie mit der rechten Maustaste auf die Projektmappe, zeigen Sie auf **Hinzufügen**, und klicken Sie dann auf **Vorhandenes Projekt**.</span><span class="sxs-lookup"><span data-stu-id="1d575-120">Right-click the solution, point to **Add**, and then click **Existing Project**.</span></span>  
  
    -   <span data-ttu-id="1d575-121">Klicken Sie im Menü **Datei** auf **Hinzufügen**, und klicken Sie dann auf **Vorhandenes Projekt**.</span><span class="sxs-lookup"><span data-stu-id="1d575-121">On the **File** menu, click **Add**, and then click **Existing Project**.</span></span>  
  
2.  <span data-ttu-id="1d575-122">Suchen Sie im Dialogfeld **Vorhandenes Projekt hinzufügen** das Projekt, das Sie hinzufügen möchten, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="1d575-122">In the **Add Existing Project** dialog box, browse to locate the project you want to add, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="1d575-123">Das Projekt wird dem Projektmappenordner im **Projektmappen-Explorer**hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1d575-123">The project is added to the solution folder in **Solution Explorer**.</span></span>  
  
## <a name="removing-an-integration-services-project"></a><span data-ttu-id="1d575-124">Entfernen eines Integration Services-Projekts</span><span class="sxs-lookup"><span data-stu-id="1d575-124">Removing an Integration Services Project</span></span>  
 <span data-ttu-id="1d575-125">Sie können ein Projekt aus einer Projektmappe nur entfernen, wenn die Projektmappe in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="1d575-125">You can only remove a project from a solution when the solution is visible in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="1d575-126">Nachdem die Projektmappe sichtbar ist, können alle Projekte, außer einem Projekt, entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="1d575-126">After the solution is visible, you can remove all except one project.</span></span> <span data-ttu-id="1d575-127">Sobald nur ein Projekt verbleibt, wird der Projektmappenordner in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] nicht mehr angezeigt, und das Löschen des letzten Projekts ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="1d575-127">As soon as only one project remains, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] no longer displays the solution folder and you cannot remove the last project.</span></span>  
  
#### <a name="to-remove-an-integration-services-project-from-a-solution"></a><span data-ttu-id="1d575-128">So entfernen Sie ein Integration Services-Projekts aus einer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="1d575-128">To remove an Integration Services project from a solution</span></span>  
  
1.  <span data-ttu-id="1d575-129">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]die Projektmappe, aus der Sie ein [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="1d575-129">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution from which you want to remove an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="1d575-130">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Projekt entladen**.</span><span class="sxs-lookup"><span data-stu-id="1d575-130">In Solution Explorer, right-click the project, and then click **Unload Project**.</span></span>  
  
3.  <span data-ttu-id="1d575-131">Klicken Sie auf **OK**, um das Entfernen zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="1d575-131">Click **OK** to confirm the removal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d575-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1d575-132">See Also</span></span>  
 <span data-ttu-id="1d575-133">[Integration Services &#40;SSIS-&#41;-Projekte](integration-services-ssis-projects-and-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="1d575-133">[Integration Services &#40;SSIS&#41; Projects](integration-services-ssis-projects-and-solutions.md) </span></span>  
 [<span data-ttu-id="1d575-134">Erstellen eines neuen Integration Services Projekts</span><span class="sxs-lookup"><span data-stu-id="1d575-134">Create a New Integration Services Project</span></span>](../../2014/integration-services/create-a-new-integration-services-project.md)  
  
  
