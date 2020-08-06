---
title: Entfernen oder Löschen eines Elements oder Projekts| Microsoft-Dokumente
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- deleting project items
- projects [SQL Server Management Studio], item removal
- removing project items
ms.assetid: 3fd92434-70f5-466e-bef0-7e0fd73ddb1c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 679911f15d6c47f4274180602a5376c4ec03c77b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616313"
---
# <a name="remove-or-delete-an-item-or-project"></a><span data-ttu-id="e9a33-102">Entfernen oder Löschen eines Elements oder Projekts</span><span class="sxs-lookup"><span data-stu-id="e9a33-102">Remove or Delete an Item or Project</span></span>
  <span data-ttu-id="e9a33-103">Projektelemente in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]-Projekten sind Abfragen, Verbindungen und sonstige Dateien.</span><span class="sxs-lookup"><span data-stu-id="e9a33-103">Project items in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] projects are Queries, Connections, and Miscellaneous files.</span></span> <span data-ttu-id="e9a33-104">Sie können Projektabfragen und sonstige Dateien aus der Projektmappe löschen, ohne die Dateien aus dem Speicher zu löschen.</span><span class="sxs-lookup"><span data-stu-id="e9a33-104">You can remove project queries and miscellaneous files from your solution without erasing the files from storage.</span></span> <span data-ttu-id="e9a33-105">Entfernen Sie ein Projekt oder Element, wenn es in der aktuellen Projektmappe nicht nützlich ist und in eine andere Projektmappe eingefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e9a33-105">Remove a project or item when it is not useful in the current solution but you want to include it in another solution.</span></span>  
  
### <a name="to-remove-a-project-item"></a><span data-ttu-id="e9a33-106">So entfernen Sie ein Projektelement</span><span class="sxs-lookup"><span data-stu-id="e9a33-106">To remove a project item</span></span>  
  
1.  <span data-ttu-id="e9a33-107">Wählen Sie im Projektmappen-Explorer das Projektelement aus, das Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="e9a33-107">In Solution Explorer, select the project item you want to remove.</span></span>  
  
2.  <span data-ttu-id="e9a33-108">Klicken Sie im Menü **Bearbeiten** auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="e9a33-108">On the **Edit** menu, click **Remove**.</span></span>  
  
3.  <span data-ttu-id="e9a33-109">Klicken Sie im Bestätigungsdialogfeld auf **Entfernen** , um das Element aus dem Projekt zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="e9a33-109">On the confirmation dialog, click **Remove** to remove the item from the project.</span></span>  
  
 <span data-ttu-id="e9a33-110">Ein entferntes Element ist weiterhin im Dateisystem vorhanden.</span><span class="sxs-lookup"><span data-stu-id="e9a33-110">A removed item still exists on the file system.</span></span> <span data-ttu-id="e9a33-111">Deshalb können Sie ein entferntes Element wieder zu seiner ursprünglichen oder zu einer anderen Projektmappe hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e9a33-111">Therefore, you can add a removed item to its original solution or to another solution.</span></span>  
  
#### <a name="to-remove-a-project"></a><span data-ttu-id="e9a33-112">So entfernen Sie ein Projekt</span><span class="sxs-lookup"><span data-stu-id="e9a33-112">To remove a project</span></span>  
  
1.  <span data-ttu-id="e9a33-113">Wählen Sie im Projektmappen-Explorer das Projekt aus, das Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="e9a33-113">In Solution Explorer, select the project you want to remove.</span></span>  
  
2.  <span data-ttu-id="e9a33-114">Klicken Sie im Menü **Bearbeiten** auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="e9a33-114">On the **Edit** menu, click **Remove**.</span></span>  
  
3.  <span data-ttu-id="e9a33-115">Klicken Sie im Bestätigungsdialogfeld auf **OK**, um das Projekt aus der Projektmappe zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="e9a33-115">On the confirmation dialog, click **OK**, to remove the project from the solution.</span></span>  
  
 <span data-ttu-id="e9a33-116">Sie können ein Projekt dauerhaft löschen, müssen jedoch zuerst alle Verweise auf das Projekt aus [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] -Projektmappen entfernen und dann die zugeordneten Dateien mithilfe von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Explorer dauerhaft aus dem Speicher löschen.</span><span class="sxs-lookup"><span data-stu-id="e9a33-116">You can delete a project permanently, but you first need to remove any references to the project from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] solutions, and then use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Explorer to permanently delete the associated files from storage.</span></span>  
  
#### <a name="to-delete-a-project"></a><span data-ttu-id="e9a33-117">So löschen Sie ein Projekt</span><span class="sxs-lookup"><span data-stu-id="e9a33-117">To delete a project</span></span>  
  
1.  <span data-ttu-id="e9a33-118">Entfernen Sie im Projektmappen-Explorer das Projekt, das Sie löschen möchten, aus der Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="e9a33-118">In Solution Explorer, remove the project you want to delete from the solution.</span></span>  
  
2.  <span data-ttu-id="e9a33-119">Suchen und markieren Sie in Windows Explorer die Dateien, die dem zu löschenden Projekt oder Element zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e9a33-119">In Windows Explorer, locate and select the files associated with the project or item you want to delete.</span></span>  
  
3.  <span data-ttu-id="e9a33-120">Klicken Sie im Menü **Datei** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="e9a33-120">On the **File** menu, click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9a33-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9a33-121">See Also</span></span>  
 <span data-ttu-id="e9a33-122">[Projektmappen-Explorer](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="e9a33-122">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="e9a33-123">[Hinzufügen neuer Elemente zu einem Projekt](add-new-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="e9a33-123">[Add New Items to a Project](add-new-items-to-a-project.md) </span></span>  
 [<span data-ttu-id="e9a33-124">Hinzufügen vorhandener Elemente zu einem Projekt</span><span class="sxs-lookup"><span data-stu-id="e9a33-124">Add Existing Items to a Project</span></span>](add-existing-items-to-a-project.md)  
  
  
