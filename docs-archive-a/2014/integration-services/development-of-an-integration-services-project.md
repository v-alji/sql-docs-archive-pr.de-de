---
title: Entwicklung eines Integration Services Projekts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- projects [Integration Services], creating
- Integration Services projects, creating
- SQL Server Integration Services projects, creating
- SSIS projects, creating
ms.assetid: 6e90b016-36a5-415e-9440-a20199fffff0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: da648b3b09b25fa2a7b1cf886ad1bf770296f5ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621605"
---
# <a name="development-of-an-integration-services-project"></a><span data-ttu-id="11604-102">Entwicklung eines Integration Services-Projekts</span><span class="sxs-lookup"><span data-stu-id="11604-102">Development of an Integration Services Project</span></span>
  <span data-ttu-id="11604-103">Sie fügen [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Pakete zu Projekten hinzu.</span><span class="sxs-lookup"><span data-stu-id="11604-103">You add [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to projects.</span></span> <span data-ttu-id="11604-104">Sie müssen die [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Umgebung installieren, um [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] -Projekte zu erstellen und zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="11604-104">To create and work with [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects, you must install the [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] environment.</span></span> <span data-ttu-id="11604-105">Weitere Informationen finden Sie unter [Installieren von Integration Services](install-windows/install-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="11604-105">For more information, see [Install Integration Services](install-windows/install-integration-services.md).</span></span>  
  
 <span data-ttu-id="11604-106">Wenn Sie ein neues [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]erstellen, enthält das Dialogfeld **Neues Projekt** die Vorlage **Integration Services-Projekt** .</span><span class="sxs-lookup"><span data-stu-id="11604-106">When you create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], the **New Project** dialog box includes an **Integration Services Project** template.</span></span> <span data-ttu-id="11604-107">Diese Projektvorlage erstellt ein neues Projekt, das ein einzelnes Paket enthält.</span><span class="sxs-lookup"><span data-stu-id="11604-107">This project template creates a new project that contains a single package.</span></span>  
  
## <a name="projects-and-solutions"></a><span data-ttu-id="11604-108">Projekte und Projektmappen</span><span class="sxs-lookup"><span data-stu-id="11604-108">Projects and Solutions</span></span>  
 <span data-ttu-id="11604-109">Projekte werden in Projektmappen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="11604-109">Projects are stored in solutions.</span></span> <span data-ttu-id="11604-110">Sie können zuerst eine Projektmappe erstellen und dann ein [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="11604-110">You can create a solution first and then add an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to the solution.</span></span> <span data-ttu-id="11604-111">Falls keine Projektmappe vorhanden ist, erstellt [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] automatisch eine Projektmappe für Sie, wenn Sie das Projekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="11604-111">If no solution exists, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] automatically creates one for you when you first create the project.</span></span> <span data-ttu-id="11604-112">Eine Projektmappe kann mehrere Projekte unterschiedlichen Typs enthalten.</span><span class="sxs-lookup"><span data-stu-id="11604-112">A solution can contain multiple projects of different types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="11604-113">Wenn Sie in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ein neues [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]-Projekt erstellen, wird die Projektmappe standardmäßig nicht im Bereich **Projektmappen-Explorer** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="11604-113">By default, when you create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], the solution is not shown in the **Solution Explorer** pane.</span></span> <span data-ttu-id="11604-114">Um dieses Standardverhalten zu ändern, klicken Sie im Menü **Extras** auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="11604-114">To change this default behavior, on the **Tools** menus, click **Options**.</span></span> <span data-ttu-id="11604-115">Erweitern Sie im Dialogfeld **Optionen** den Eintrag **Projekte und Projektmappen**, und klicken Sie dann auf **Allgemein**.</span><span class="sxs-lookup"><span data-stu-id="11604-115">In the **Options** dialog box, expand **Projects and Solutions**, and then click **General**.</span></span> <span data-ttu-id="11604-116">Wählen Sie auf der Seite **Allgemein** die Option **Projektmappe immer anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="11604-116">On the **General** page, select **Always show solution**.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="11604-117">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="11604-117">Related Tasks</span></span>  
  
-   [<span data-ttu-id="11604-118">Erstellen eines neuen Integration Services Projekts</span><span class="sxs-lookup"><span data-stu-id="11604-118">Create a New Integration Services Project</span></span>](../../2014/integration-services/create-a-new-integration-services-project.md)  
  
-   [<span data-ttu-id="11604-119">Hinzufügen eines Elements zu einem Integration Services-Projekt</span><span class="sxs-lookup"><span data-stu-id="11604-119">Add an Item to an Integration Services Project</span></span>](../../2014/integration-services/add-an-item-to-an-integration-services-project.md)  
  
-   [<span data-ttu-id="11604-120">Hinzufügen oder Entfernen eines Integration Services-Projekts in einer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="11604-120">Add or Remove an Integration Services Project in a Solution</span></span>](../../2014/integration-services/add-or-remove-an-integration-services-project-in-a-solution.md)  
  
  
