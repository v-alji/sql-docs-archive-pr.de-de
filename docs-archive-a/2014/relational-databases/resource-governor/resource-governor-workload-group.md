---
title: Arbeitsauslastungsgruppe der Ressourcenkontrolle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, workload group
- workload groups [SQL Server]
- workload groups [SQL Server], overview
ms.assetid: a84c3c3f-55b6-4a30-9c42-13f082d9281e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6c6fa8f6fe960571f10d6a8505329fbe8f400e6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699375"
---
# <a name="resource-governor-workload-group"></a><span data-ttu-id="9c977-102">Arbeitsauslastungsgruppe der Ressourcenkontrolle</span><span class="sxs-lookup"><span data-stu-id="9c977-102">Resource Governor Workload Group</span></span>
  <span data-ttu-id="9c977-103">In der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Ressourcenkontrolle werden Arbeitsauslastungsgruppen als Container für Sitzungsanforderungen mit ähnlichen Klassifizierungskriterien verwendet.</span><span class="sxs-lookup"><span data-stu-id="9c977-103">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Resource Governor, a workload group serves as a container for session requests that have similar classification criteria.</span></span> <span data-ttu-id="9c977-104">Arbeitsauslastungen ermöglichen die gemeinsame Überwachung der Sitzungen und definieren Richtlinien für die Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="9c977-104">A workload allows for aggregate monitoring of the sessions, and defines policies for the sessions.</span></span> <span data-ttu-id="9c977-105">Jede Arbeitsauslastungsgruppe ist Teil eines Ressourcenpools, der wiederum eine Teilmenge der physischen Ressourcen einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)]darstellt.</span><span class="sxs-lookup"><span data-stu-id="9c977-105">Each workload group is in a resource pool, which represents a subset of the physical resources of an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="9c977-106">Wenn eine Sitzung gestartet wird, weist die Klassifizierungsfunktion der Ressourcenkontrolle die Sitzung einer bestimmten Arbeitsauslastungsgruppe zu, und die Sitzung muss mit den der Arbeitsauslastungsgruppe zugewiesenen Richtlinien und den für den Ressourcenpool definierten Ressourcen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9c977-106">When a session is started, the Resource Governor classifier assigns the session to a specific workload group, and the session must run using the policies assigned to the workload group and the resources defined for the resource pool.</span></span>  
  
## <a name="workload-group-concepts"></a><span data-ttu-id="9c977-107">Konzepte zu Arbeitsauslastungsgruppen</span><span class="sxs-lookup"><span data-stu-id="9c977-107">Workload Group Concepts</span></span>  
 <span data-ttu-id="9c977-108">Eine Arbeitsauslastungsgruppe fungiert als Container für Sitzungsanforderungen, die sich gemäß den auf die einzelnen Anforderungen angewendeten Klassifikationskriterien ähneln.</span><span class="sxs-lookup"><span data-stu-id="9c977-108">A workload group serves as a container for session requests that are similar according to the classification criteria that are applied to each request.</span></span> <span data-ttu-id="9c977-109">Sie ermöglicht die Überwachung der aggregierten Ressourcenbelegung und die Anwendung einer einheitlichen Richtlinie auf alle Anforderungen in der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="9c977-109">A workload group allows the aggregate monitoring of resource consumption and the application of a uniform policy to all the requests in the group.</span></span> <span data-ttu-id="9c977-110">Eine Gruppe definiert die Richtlinien für ihre Elemente.</span><span class="sxs-lookup"><span data-stu-id="9c977-110">A group defines the policies for its members.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9c977-111">Benutzerdefinierte Arbeitsauslastungsgruppen können zwischen Ressourcenpools verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="9c977-111">User-defined workload groups can be moved from one resource pool to another.</span></span>  
  
 <span data-ttu-id="9c977-112">Die Ressourcenkontrolle verfügt über zwei vordefinierte Arbeitsauslastungsgruppen: die interne Gruppe und die Standardgruppe.</span><span class="sxs-lookup"><span data-stu-id="9c977-112">Resource Governor predefines two workload groups: the internal group and the default group.</span></span> <span data-ttu-id="9c977-113">Interne Gruppen können von Benutzern nicht geändert werden. Sie können jedoch überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="9c977-113">A user cannot change anything classified as an internal group, but can monitor it.</span></span> <span data-ttu-id="9c977-114">Anforderungen werden der Standardgruppe zugeordnet, wenn die folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="9c977-114">Requests are classified into the default group when the following conditions exist:</span></span>  
  
-   <span data-ttu-id="9c977-115">Es sind keine Kriterien zum Klassifizieren einer Anforderung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="9c977-115">There are no criteria to classify a request.</span></span>  
  
-   <span data-ttu-id="9c977-116">Es wurde versucht, die Anforderung einer nicht vorhandenen Gruppe zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="9c977-116">There is an attempt to classify the request into a non-existent group.</span></span>  
  
-   <span data-ttu-id="9c977-117">Ein allgemeiner Klassifizierungsfehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9c977-117">There is a general classification failure.</span></span>  
  
 <span data-ttu-id="9c977-118">Die Ressourcenkontrolle stellt auch DDL-Anweisungen zum Erstellen, Ändern und Löschen von Arbeitsauslastungsgruppen bereit.</span><span class="sxs-lookup"><span data-stu-id="9c977-118">Resource Governor also provides DDL statements for creating, changing, and dropping workload groups.</span></span>  
  
## <a name="workload-group-tasks"></a><span data-ttu-id="9c977-119">Tasks zu Arbeitsauslastungsgruppen</span><span class="sxs-lookup"><span data-stu-id="9c977-119">Workload Group Tasks</span></span>  
  
|<span data-ttu-id="9c977-120">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="9c977-120">Task Description</span></span>|<span data-ttu-id="9c977-121">Thema</span><span class="sxs-lookup"><span data-stu-id="9c977-121">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="9c977-122">Beschreibt, wie eine Arbeitsauslastungsgruppe erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="9c977-122">Describes how to create a workload group.</span></span>|[<span data-ttu-id="9c977-123">Erstellen einer Arbeitsauslastungsgruppe</span><span class="sxs-lookup"><span data-stu-id="9c977-123">Create a Workload Group</span></span>](create-a-workload-group.md)|  
|<span data-ttu-id="9c977-124">Beschreibt, wie Einstellungen für Arbeitsauslastungsgruppen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="9c977-124">Describes how to change workload group settings.</span></span>|[<span data-ttu-id="9c977-125">Ändern der Einstellungen von Arbeitsauslastungsgruppen</span><span class="sxs-lookup"><span data-stu-id="9c977-125">Change Workload Group Settings</span></span>](change-workload-group-settings.md)|  
|<span data-ttu-id="9c977-126">Beschreibt, wie eine Arbeitsauslastungsgruppe gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="9c977-126">Describes how to delete a workload group.</span></span>|[<span data-ttu-id="9c977-127">Löschen von Arbeitsauslastungsgruppen</span><span class="sxs-lookup"><span data-stu-id="9c977-127">Delete a Workload Group</span></span>](delete-a-workload-group.md)|  
  
## <a name="see-also"></a><span data-ttu-id="9c977-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9c977-128">See Also</span></span>  
 <span data-ttu-id="9c977-129">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="9c977-129">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="9c977-130">[Aktivieren der Ressourcenkontrolle](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="9c977-130">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="9c977-131">[Ressourcenpool für die Ressourcenkontrolle](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="9c977-131">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="9c977-132">[Klassifizierungsfunktion der Ressourcenkontrolle](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="9c977-132">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="9c977-133">[Konfigurieren der Ressourcenkontrolle mit einer Vorlage](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="9c977-133">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 [<span data-ttu-id="9c977-134">Anzeigen der Eigenschaften der Ressourcenkontrolle</span><span class="sxs-lookup"><span data-stu-id="9c977-134">View Resource Governor Properties</span></span>](view-resource-governor-properties.md)  
  
  
