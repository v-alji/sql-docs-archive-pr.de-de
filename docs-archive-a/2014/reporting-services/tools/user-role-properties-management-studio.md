---
title: Benutzerrolleneigenschaften (Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.userroleproperties.f1
ms.assetid: c8b22236-a8b1-4e15-b1ff-4e1909b602d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6f79953abdf5e3d1cdb03de8c5feeb6b2de34ab7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700664"
---
# <a name="user-role-properties-management-studio"></a><span data-ttu-id="5b6a8-102">Benutzerrolleneigenschaften (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="5b6a8-102">User Role Properties (Management Studio)</span></span>
  <span data-ttu-id="5b6a8-103">Mithilfe dieser Seite sehen Sie, welche Aufgaben in einer Rollendefinition auf Elementebene eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="5b6a8-103">Use this page to view which tasks are included in an item-level role definition.</span></span> <span data-ttu-id="5b6a8-104">Mit dieser Seite können Sie außerdem die Aufgabenliste oder eine Rollenbeschreibung ändern.</span><span class="sxs-lookup"><span data-stu-id="5b6a8-104">You can also use this page to change the task list or modify a role description.</span></span>  
  
 <span data-ttu-id="5b6a8-105">Eine Rollendefinition auf Elementebene ist eine benannte Auflistung von Aufgaben, die Benutzer in Bezug auf ein bestimmtes Element ausführen können (d. h. für einen Ordner, Bericht, eine Ressource oder freigegebene Datenquelle).</span><span class="sxs-lookup"><span data-stu-id="5b6a8-105">An item-level role definition is a named collection of tasks that users perform relative to a specific item (that is, a folder, report, resource, or shared data source).</span></span> <span data-ttu-id="5b6a8-106">Rollendefinitionen werden im Berichts-Manager einem Benutzer oder einer Gruppe zum Erstellen einer Rollenzuweisung zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="5b6a8-106">Role definitions are assigned to a user or group to create a role assignment in Report Manager.</span></span> <span data-ttu-id="5b6a8-107">Die Aufgaben in der Rollendefinition beschreiben die Aktionen, die der Benutzer oder die Gruppe ausführen können.</span><span class="sxs-lookup"><span data-stu-id="5b6a8-107">The tasks in the role definition describe what the user or group can do.</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="5b6a8-108">enthält zahlreiche vordefinierte Rollendefinitionen auf Elementebene, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5b6a8-108">includes a number of predefined item-level role definitions that you can work with.</span></span> <span data-ttu-id="5b6a8-109">Sie können die Rollendefinitionen ändern, indem Sie die deren Aufgabenliste ändern.</span><span class="sxs-lookup"><span data-stu-id="5b6a8-109">You can modify the role definitions by changing the task list of each one.</span></span> <span data-ttu-id="5b6a8-110">Die Bearbeitung einer Rollendefinition wirkt sich auf alle Rollenzuweisungen aus, die diese Rollendefinition enthalten.</span><span class="sxs-lookup"><span data-stu-id="5b6a8-110">Editing a role definition affects all role assignments that include the role definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5b6a8-111">Benutzerrollenzuweisungen werden nur auf einem Berichtsserver verwendet, der im einheitlichen Modus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5b6a8-111">User role assignments are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="5b6a8-112">Ist der Berichtsserver für die SharePoint-Integration konfiguriert, werden auf dieser Seite schreibgeschützte Informationen zu den Berechtigungsstufen und -rollen angezeigt, die auf der SharePoint-Website definiert sind.</span><span class="sxs-lookup"><span data-stu-id="5b6a8-112">If the report server is configured for SharePoint integration, this page displays read-only information about the roles and permission levels that are defined on the SharePoint site.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5b6a8-113">Tastatur</span><span class="sxs-lookup"><span data-stu-id="5b6a8-113">Options</span></span>  
 <span data-ttu-id="5b6a8-114">**Name**</span><span class="sxs-lookup"><span data-stu-id="5b6a8-114">**Name**</span></span>  
 <span data-ttu-id="5b6a8-115">Gibt den Namen der Rollendefinition an.</span><span class="sxs-lookup"><span data-stu-id="5b6a8-115">Specifies the name of the role definition.</span></span>  
  
 <span data-ttu-id="5b6a8-116">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="5b6a8-116">**Description**</span></span>  
 <span data-ttu-id="5b6a8-117">Zeigt eine Beschreibung der Rollendefinition an.</span><span class="sxs-lookup"><span data-stu-id="5b6a8-117">Shows a description of the role definition.</span></span> <span data-ttu-id="5b6a8-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]wird diese Beschreibung nur auf dieser Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b6a8-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], this description is only visible in this page.</span></span> <span data-ttu-id="5b6a8-119">Im Berichts-Manager hilft diese Beschreibung Benutzern bei der Entscheidung, ob die Rolle in einer Rollenzuweisung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b6a8-119">In Report Manager, this description helps users decide whether to use the role in a role assignment.</span></span>  
  
 <span data-ttu-id="5b6a8-120">**Aufgabe**</span><span class="sxs-lookup"><span data-stu-id="5b6a8-120">**Task**</span></span>  
 <span data-ttu-id="5b6a8-121">Führt alle Tasks auf Elementebene auf, die für die Rollendefinition ausgewählt werden können.</span><span class="sxs-lookup"><span data-stu-id="5b6a8-121">Lists all item-level tasks that can be selected for this role definition.</span></span> <span data-ttu-id="5b6a8-122">Sie können in der vordefinierten Aufgabenliste Elemente hinzufügen oder löschen, um zu definieren, wie Benutzer über die Rolle auf ein bestimmtes Element zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="5b6a8-122">You can add or remove items from the predefined task list to define how users access a given item through this role.</span></span> <span data-ttu-id="5b6a8-123">Sie können keine neuen Tasks erstellen oder vorhandene Tasks ändern.</span><span class="sxs-lookup"><span data-stu-id="5b6a8-123">You cannot create new tasks, and you cannot modify existing tasks.</span></span> <span data-ttu-id="5b6a8-124">Die Aufgabenliste einer Rollendefinition wird nur in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b6a8-124">The task list of a role definition appears only in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="5b6a8-125">**Taskbeschreibung**</span><span class="sxs-lookup"><span data-stu-id="5b6a8-125">**Task Description**</span></span>  
 <span data-ttu-id="5b6a8-126">Bietet Informationen zu den einzelnen Tasks.</span><span class="sxs-lookup"><span data-stu-id="5b6a8-126">Provides information about each task.</span></span> <span data-ttu-id="5b6a8-127">Taskbeschreibungen können Sie nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="5b6a8-127">You cannot modify task descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b6a8-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b6a8-128">See Also</span></span>  
 <span data-ttu-id="5b6a8-129">[Aufgaben auf Elementebene](../security/tasks-and-permissions-item-level-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="5b6a8-129">[Item-Level Tasks](../security/tasks-and-permissions-item-level-tasks.md) </span></span>  
 <span data-ttu-id="5b6a8-130">[Rollendefinitionen](../security/role-definitions.md) </span><span class="sxs-lookup"><span data-stu-id="5b6a8-130">[Role Definitions](../security/role-definitions.md) </span></span>  
 <span data-ttu-id="5b6a8-131">[Berichtsserver im Management Studio (F1-Hilfe)](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="5b6a8-131">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="5b6a8-132">[Aufgaben und Berechtigungen](../security/tasks-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="5b6a8-132">[Tasks and Permissions](../security/tasks-and-permissions.md) </span></span>  
 [<span data-ttu-id="5b6a8-133">Vordefinierte Rollen</span><span class="sxs-lookup"><span data-stu-id="5b6a8-133">Predefined Roles</span></span>](../security/role-definitions-predefined-roles.md)  
  
  
