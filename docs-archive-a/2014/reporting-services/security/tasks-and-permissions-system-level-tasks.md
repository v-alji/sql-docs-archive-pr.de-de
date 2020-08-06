---
title: Aufgaben auf Systemebene | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- system-level tasks [Reporting Services]
ms.assetid: 7023b388-40b2-4590-b227-115cf380a1e7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 98f9390664064cd293b80d094d65c903869bc709
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723334"
---
# <a name="system-level-tasks"></a><span data-ttu-id="5acdd-102">Aufgaben auf Systemebene</span><span class="sxs-lookup"><span data-stu-id="5acdd-102">System-Level Tasks</span></span>
  <span data-ttu-id="5acdd-103">Eine Aufgabe auf Systemebene ist eine Auflistung von Berechtigungen im Hinblick auf Vorgänge, die die Berichtsserversite insgesamt betreffen.</span><span class="sxs-lookup"><span data-stu-id="5acdd-103">A system-level task is a collection of permissions that relate to operations that apply to the report server site as a whole.</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="5acdd-104">enthält auch Aufgaben auf Elementebene, die sich auf bestimmte Elemente beziehen.</span><span class="sxs-lookup"><span data-stu-id="5acdd-104">also includes item-level tasks that apply to specific items.</span></span> <span data-ttu-id="5acdd-105">Weitere Informationen finden Sie unter [Aufgaben auf Elementebene](tasks-and-permissions-item-level-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="5acdd-105">For more information, see [Item-Level Tasks](tasks-and-permissions-item-level-tasks.md).</span></span> <span data-ttu-id="5acdd-106">Weitere Informationen zu Aufgaben und Berechtigungen im Allgemeinen finden Sie unter [Tasks and Permissions](tasks-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="5acdd-106">For more information about tasks and permissions in general, see [Tasks and Permissions](tasks-and-permissions.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5acdd-107">Wenn Sie mit diesen Aufgaben programmgesteuert arbeiten, müssen Sie Methoden verwenden, die Aufgaben auf Systemebene unterstützen.</span><span class="sxs-lookup"><span data-stu-id="5acdd-107">If you are working with these tasks programmatically, you must use methods that support system-level tasks.</span></span> <span data-ttu-id="5acdd-108">Weitere Informationen finden Sie unter <xref:ReportService2010.ReportingService2010.ListTasks%2A> und <xref:ReportService2010.ReportingService2010.ListRoles%2A>.</span><span class="sxs-lookup"><span data-stu-id="5acdd-108">For more information, see <xref:ReportService2010.ReportingService2010.ListTasks%2A> and <xref:ReportService2010.ReportingService2010.ListRoles%2A>.</span></span>  
  
## <a name="permissions-in-system-level-tasks"></a><span data-ttu-id="5acdd-109">Berechtigungen für Aufgaben auf Systemebene</span><span class="sxs-lookup"><span data-stu-id="5acdd-109">Permissions in System-Level Tasks</span></span>  
 <span data-ttu-id="5acdd-110">In der folgenden Tabelle sind die Berechtigungsarten für jede Systemaufgabe aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="5acdd-110">The following table identifies the collection of permissions for each system task.</span></span> <span data-ttu-id="5acdd-111">Die Berechtigungsarten sind nur zu Informationszwecken aufgeführt, um eine genauere Beschreibung der über die verschiedenen Aufgaben verfügbaren Funktionalität bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="5acdd-111">Permissions are listed for informational purposes only, to provide a more exact description of the functionality available through each task.</span></span>  
  
|<span data-ttu-id="5acdd-112">Aufgabe</span><span class="sxs-lookup"><span data-stu-id="5acdd-112">Task</span></span>|<span data-ttu-id="5acdd-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="5acdd-113">Permissions</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="5acdd-114">Berichtsdefinitionen ausführen</span><span class="sxs-lookup"><span data-stu-id="5acdd-114">Execute report definitions</span></span>|<span data-ttu-id="5acdd-115">Berichtsdefinitionen ausführen (Berechtigungs- und Aufgabenname sind identisch)</span><span class="sxs-lookup"><span data-stu-id="5acdd-115">Execute Report Definitions (the permission and task name are the same)</span></span>|  
|<span data-ttu-id="5acdd-116">Generieren von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="5acdd-116">Generate events</span></span>|<span data-ttu-id="5acdd-117">Ereignisse generieren</span><span class="sxs-lookup"><span data-stu-id="5acdd-117">Generate Events</span></span>|  
|<span data-ttu-id="5acdd-118">Aufträge verwalten</span><span class="sxs-lookup"><span data-stu-id="5acdd-118">Manage jobs</span></span>|<span data-ttu-id="5acdd-119">Lesen von Systemeigenschaften</span><span class="sxs-lookup"><span data-stu-id="5acdd-119">Read System Properties</span></span><br /><br /> <span data-ttu-id="5acdd-120">Aktualisieren von Systemeigenschaften</span><span class="sxs-lookup"><span data-stu-id="5acdd-120">Update System Properties</span></span>|  
|<span data-ttu-id="5acdd-121">Berichtsservereigenschaften verwalten</span><span class="sxs-lookup"><span data-stu-id="5acdd-121">Manage report server properties</span></span>|<span data-ttu-id="5acdd-122">Lesen von Systemeigenschaften</span><span class="sxs-lookup"><span data-stu-id="5acdd-122">Read System Properties</span></span><br /><br /> <span data-ttu-id="5acdd-123">Aktualisieren von Systemeigenschaften</span><span class="sxs-lookup"><span data-stu-id="5acdd-123">Update System Properties</span></span>|  
|<span data-ttu-id="5acdd-124">Verwalten von Rollen</span><span class="sxs-lookup"><span data-stu-id="5acdd-124">Manage roles</span></span>|<span data-ttu-id="5acdd-125">Erstellen von Rollen</span><span class="sxs-lookup"><span data-stu-id="5acdd-125">Create Roles</span></span><br /><br /> <span data-ttu-id="5acdd-126">Löschen von Rollen</span><span class="sxs-lookup"><span data-stu-id="5acdd-126">Delete Roles</span></span><br /><br /> <span data-ttu-id="5acdd-127">Lesen von Rolleneigenschaften</span><span class="sxs-lookup"><span data-stu-id="5acdd-127">Read Role Properties</span></span><br /><br /> <span data-ttu-id="5acdd-128">Aktualisieren von Rolleneigenschaften</span><span class="sxs-lookup"><span data-stu-id="5acdd-128">Update Role Properties</span></span>|  
|<span data-ttu-id="5acdd-129">Freigegebene Zeitpläne verwalten</span><span class="sxs-lookup"><span data-stu-id="5acdd-129">Manage shared schedules</span></span>|<span data-ttu-id="5acdd-130">Erstellen von Zeitplänen</span><span class="sxs-lookup"><span data-stu-id="5acdd-130">Create Schedules</span></span>|  
|<span data-ttu-id="5acdd-131">Berichtsserversicherheit verwalten</span><span class="sxs-lookup"><span data-stu-id="5acdd-131">Manage report server security</span></span>|<span data-ttu-id="5acdd-132">Lesen von Systemsicherheitsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="5acdd-132">Read System Security Policies</span></span><br /><br /> <span data-ttu-id="5acdd-133">Aktualisieren von Systemsicherheitsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="5acdd-133">Update System Security Policies</span></span>|  
|<span data-ttu-id="5acdd-134">Berichtsservereigenschaften anzeigen</span><span class="sxs-lookup"><span data-stu-id="5acdd-134">View report server properties</span></span>|<span data-ttu-id="5acdd-135">Lesen von Systemeigenschaften</span><span class="sxs-lookup"><span data-stu-id="5acdd-135">Read System Properties</span></span>|  
|<span data-ttu-id="5acdd-136">Freigegebene Zeitpläne anzeigen</span><span class="sxs-lookup"><span data-stu-id="5acdd-136">View shared schedules</span></span>|<span data-ttu-id="5acdd-137">Lesen von Zeitplänen</span><span class="sxs-lookup"><span data-stu-id="5acdd-137">Read Schedules</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5acdd-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5acdd-138">See Also</span></span>  
 [<span data-ttu-id="5acdd-139">Granting Permissions on a Native Mode Report Server (Erteilen von Berechtigungen für einen Berichtsserver im einheitlichen Modus)</span><span class="sxs-lookup"><span data-stu-id="5acdd-139">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
  
  
