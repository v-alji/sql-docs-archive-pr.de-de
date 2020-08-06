---
title: Systemrolleneigenschaften (Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.systemroleproperties.f1
ms.assetid: 0210fc2a-74fb-41dd-8e39-4830047ec417
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b37ebb1cb95d6628884d81156c9c1bc29bff86fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615258"
---
# <a name="system-role-properties-management-studio"></a><span data-ttu-id="1e35c-102">Systemrolleneigenschaften (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="1e35c-102">System Role Properties (Management Studio)</span></span>
  <span data-ttu-id="1e35c-103">Mithilfe der Seite Systemrollen können Sie die Systemrollendefinitionen anzeigen, die aktuell für den Berichtsserver definiert sind.</span><span class="sxs-lookup"><span data-stu-id="1e35c-103">Use the System Roles page to view the system role definitions that are currently defined for the report server.</span></span> <span data-ttu-id="1e35c-104">Eine Systemrollendefinition enthält eine benannte Auflistung von Aufgaben, die in Bezug auf die gesamte Site statt nur für ein einzelnes Element ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1e35c-104">A system role definition contains a named collection of tasks that are performed relative to the entire site, instead of an individual item.</span></span> <span data-ttu-id="1e35c-105">Rollendefinitionen werden Benutzern oder Gruppen zugewiesen, um eine Rollenzuweisung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1e35c-105">Role definitions are assigned to a user or groups to create a resulting role assignment.</span></span> <span data-ttu-id="1e35c-106">Die Aufgaben in der Rollendefinition geben die Aktionen an, die der Benutzer oder die Gruppe ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="1e35c-106">The tasks in the role definition specify what the user or group can do.</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="1e35c-107">besitzt zwei vordefinierte Systemrollendefinitionen: **Systemadministrator** und **Systembenutzer**.</span><span class="sxs-lookup"><span data-stu-id="1e35c-107">has two predefined system role definitions: **System Administrator** and **System User**.</span></span> <span data-ttu-id="1e35c-108">Sie können die Rollendefinitionen ändern, indem Sie ihre Aufgabenlisten ändern. Oder Sie erstellen eine neue Systemrolle, die eine andere Kombination von Aufgaben unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1e35c-108">You can modify these role definitions by changing the task list, or you can create a new system role that supports a different combination of tasks.</span></span> <span data-ttu-id="1e35c-109">Die Bearbeitung einer Rollendefinition wirkt sich auf alle Rollenzuweisungen aus, die diese Rollendefinition enthalten.</span><span class="sxs-lookup"><span data-stu-id="1e35c-109">Editing a role definition affects all role assignments that include the role definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1e35c-110">Systemrollenzuweisungen werden nur auf einem Berichtsserver verwendet, der im einheitlichen Modus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1e35c-110">System role assignments are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="1e35c-111">Ist der Berichtsserver für den integrierten SharePoint-Modus konfiguriert, ist diese Seite nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1e35c-111">If the report server is configured for SharePoint integration, this page is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1e35c-112">Tastatur</span><span class="sxs-lookup"><span data-stu-id="1e35c-112">Options</span></span>  
 <span data-ttu-id="1e35c-113">**Name**</span><span class="sxs-lookup"><span data-stu-id="1e35c-113">**Name**</span></span>  
 <span data-ttu-id="1e35c-114">Gibt den Namen der Systemrollendefinition an.</span><span class="sxs-lookup"><span data-stu-id="1e35c-114">Specifies the name of the system role definition.</span></span>  
  
 <span data-ttu-id="1e35c-115">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1e35c-115">**Description**</span></span>  
 <span data-ttu-id="1e35c-116">Zeigt eine Beschreibung der Systemrollendefinition.</span><span class="sxs-lookup"><span data-stu-id="1e35c-116">Shows a description of the system role definition.</span></span> <span data-ttu-id="1e35c-117">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] wird diese Beschreibung nur auf dieser Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1e35c-117">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], this description is only visible in this page.</span></span> <span data-ttu-id="1e35c-118">Benutzer, die dieses Element über den Berichts-Manager anzeigen, sehen diese Beschreibung möglicherweise, wenn Sie die Ordnerhierarchie durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="1e35c-118">Users who view this item through Report Manager may see this description when browsing the folder hierarchy.</span></span>  
  
 <span data-ttu-id="1e35c-119">**Aufgabe**</span><span class="sxs-lookup"><span data-stu-id="1e35c-119">**Task**</span></span>  
 <span data-ttu-id="1e35c-120">Listet alle Tasks auf Systemebene auf, die für diese Rollendefinition ausgewählt werden können.</span><span class="sxs-lookup"><span data-stu-id="1e35c-120">Lists all system-level tasks that can be selected for this role definition.</span></span> <span data-ttu-id="1e35c-121">Sie können in der vordefinierten Aufgabenliste Elemente hinzufügen oder löschen, um zu definieren, wie Benutzer über die Rolle auf ein bestimmtes Element zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="1e35c-121">You can add or remove items from the predefined task list to define how users access a given item through this role.</span></span> <span data-ttu-id="1e35c-122">Sie können keine neuen Tasks erstellen oder vorhandene Tasks ändern.</span><span class="sxs-lookup"><span data-stu-id="1e35c-122">You cannot create new tasks, and you cannot modify existing tasks.</span></span>  
  
 <span data-ttu-id="1e35c-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1e35c-123">**Description**</span></span>  
 <span data-ttu-id="1e35c-124">Bietet Informationen zu den einzelnen Tasks.</span><span class="sxs-lookup"><span data-stu-id="1e35c-124">Provides information about each task.</span></span> <span data-ttu-id="1e35c-125">Taskbeschreibungen können Sie nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="1e35c-125">You cannot modify task descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e35c-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1e35c-126">See Also</span></span>  
 <span data-ttu-id="1e35c-127">[Berichtsserver im Management Studio (F1-Hilfe)](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="1e35c-127">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="1e35c-128">[Aufgaben auf Systemebene](../security/tasks-and-permissions-system-level-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="1e35c-128">[System-Level Tasks](../security/tasks-and-permissions-system-level-tasks.md) </span></span>  
 <span data-ttu-id="1e35c-129">[Aufgaben und Berechtigungen](../security/tasks-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="1e35c-129">[Tasks and Permissions](../security/tasks-and-permissions.md) </span></span>  
 [<span data-ttu-id="1e35c-130">Vordefinierte Rollen</span><span class="sxs-lookup"><span data-stu-id="1e35c-130">Predefined Roles</span></span>](../security/role-definitions-predefined-roles.md)  
  
  
