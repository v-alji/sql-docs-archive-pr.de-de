---
title: Verfügbarkeitsgruppe ist offline | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp2online.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 093c5208-bf7a-49f4-a546-72b48197cadf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b25e5b22a09783c8dfcad862500b5c0dfcb2c319
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608872"
---
# <a name="availability-group-is-offline"></a><span data-ttu-id="6fc7e-102">Verfügbarkeitsgruppe ist offline</span><span class="sxs-lookup"><span data-stu-id="6fc7e-102">Availability group is offline</span></span>
    
## <a name="introduction"></a><span data-ttu-id="6fc7e-103">Einführung</span><span class="sxs-lookup"><span data-stu-id="6fc7e-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6fc7e-104">**Richtlinienname**</span><span class="sxs-lookup"><span data-stu-id="6fc7e-104">**Policy Name**</span></span>|<span data-ttu-id="6fc7e-105">Onlinezustand der Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="6fc7e-105">Availability Group Online State</span></span>|  
|<span data-ttu-id="6fc7e-106">**Problem**</span><span class="sxs-lookup"><span data-stu-id="6fc7e-106">**Issue**</span></span>|<span data-ttu-id="6fc7e-107">Die Verfügbarkeitsgruppe ist offline.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-107">Availability group is offline.</span></span>|  
|<span data-ttu-id="6fc7e-108">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="6fc7e-108">**Category**</span></span>|<span data-ttu-id="6fc7e-109">**Critical** (Kritisch)</span><span class="sxs-lookup"><span data-stu-id="6fc7e-109">**Critical**</span></span>|  
|<span data-ttu-id="6fc7e-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="6fc7e-110">**Facet**</span></span>|<span data-ttu-id="6fc7e-111">Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="6fc7e-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6fc7e-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6fc7e-112">Description</span></span>  
 <span data-ttu-id="6fc7e-113">Diese Richtlinie überprüft den Online- oder Offlinestatus der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-113">This policy checks the online or offline state of the availability group.</span></span> <span data-ttu-id="6fc7e-114">Die Richtlinie befindet sich in einem fehlerhaften Zustand, und eine Warnung wird ausgelöst, wenn die Clusterressource der Verfügbarkeitsgruppe offline ist oder wenn die Verfügbarkeitsgruppe nicht über ein primäres Replikat verfügt.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-114">The policy is in an unhealthy state and an alert is raised when the cluster resource of the availability group is offline or the availability group does not have a primary replica.</span></span>  
  
 <span data-ttu-id="6fc7e-115">Der Zustand der Richtlinie ist fehlerfrei, wenn die Clusterressource der Verfügbarkeitsgruppe online ist und die Verfügbarkeitsgruppe über ein primäres Replikat verfügt.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-115">The policy state is healthy when the cluster resource of the availability group is online and the availability group has a primary replica.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6fc7e-116"> Für diese Version von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]finden Sie Informationen zu möglichen Ursachen und Lösungen im TechNet Wiki unter [Verfügbarkeitsgruppe ist offline](https://go.microsoft.com/fwlink/p/?LinkId=220850) .</span><span class="sxs-lookup"><span data-stu-id="6fc7e-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability group is offline](https://go.microsoft.com/fwlink/p/?LinkId=220850) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="6fc7e-117">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="6fc7e-117">Possible Causes</span></span>  
 <span data-ttu-id="6fc7e-118">Dieses Problem kann von einem Fehler in der Serverinstanz verursacht werden, die das primäre Replikat hostet, oder dadurch, dass die Windows Server-Failovercluster (WSFC)-Verfügbarkeitsgruppenressource offline geht.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-118">This issue can be caused by a failure in the server instance that hosts the primary replica or by the Windows Server Failover Cluster (WSFC) availability group resource going offline.</span></span> <span data-ttu-id="6fc7e-119">Im Folgenden sind mögliche Ursachen für den Offlinezustand der Verfügbarkeitsgruppe aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="6fc7e-119">Following are possible causes for the availability group to be offline:</span></span>  
  
-   <span data-ttu-id="6fc7e-120">Die Verfügbarkeitsgruppe ist nicht für den automatischen Failovermodus konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-120">The availability group is not configured with automatic failover mode.</span></span> <span data-ttu-id="6fc7e-121">Das primäre Replikat ist nicht mehr verfügbar, und alle Replikate in der Verfügbarkeitsgruppe nehmen den Status RESOLVING an.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-121">The primary replica becomes unavailable and the role of all replicas in the availability group become RESOLVING.</span></span>  
  
    -   <span data-ttu-id="6fc7e-122">Der Instanzdienst des primären Replikats ist ausgefallen oder reagiert nicht.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-122">The primary replica instance service is down or unresponsive.</span></span>  
  
    -   <span data-ttu-id="6fc7e-123">Für die Verfügbarkeitsgruppe besteht ein Problem bei der Verbindung zum Cluster.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-123">The availability group has a connectivity issue with the cluster.</span></span>  
  
-   <span data-ttu-id="6fc7e-124">Die Verfügbarkeitsgruppe wurde mit automatischem Failovermodus konfiguriert und nicht erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-124">The availability group is configured with automatic failover mode and does not complete successfully.</span></span>  
  
    -   <span data-ttu-id="6fc7e-125">Während des automatischen Failovers tritt für die primäre Bereitschaftsüberprüfung auf dem Zielreplikat ein Fehler auf, und es ist kein Replikat verfügbar, das zum neuen primären Replikat werden kann.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-125">During the automatic failover, the primary readiness check on the target replica fails, and there is no replica available to become the new primary.</span></span>  
  
-   <span data-ttu-id="6fc7e-126">Die Verfügbarkeitsgruppenressource im Cluster ist offline.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-126">The availability group resource in the cluster becomes offline.</span></span>  
  
    -   <span data-ttu-id="6fc7e-127">In einer abhängigen Clusterressource tritt ein schwerwiegendes Problem auf, und die Ressource wird in den Offlinezustand versetzt.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-127">Any dependent cluster resource encounters a critical issue and becomes offline.</span></span> <span data-ttu-id="6fc7e-128">Die Verfügbarkeitsgruppenressource ist ebenfalls offline, bis die abhängige Ressource online geschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-128">The availability group resource is also offline until the dependent resource becomes online.</span></span>  
  
    -   <span data-ttu-id="6fc7e-129">Durch ein schwerwiegendes Problem im Cluster wird die Verfügbarkeitsgruppenressource deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-129">A critical issue in the cluster turns off the availability group resource.</span></span>  
  
-   <span data-ttu-id="6fc7e-130">Für die Verfügbarkeitsgruppe wird ein automatisches, manuelles oder erzwungenes Failover durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-130">There is an automatic, manual, or forced failover in progress for the availability group.</span></span>  
  
## <a name="possible-solutions"></a><span data-ttu-id="6fc7e-131">Mögliche Lösungen</span><span class="sxs-lookup"><span data-stu-id="6fc7e-131">Possible Solutions</span></span>  
 <span data-ttu-id="6fc7e-132">Für dieses Problem gibt es die folgenden möglichen Lösungen:</span><span class="sxs-lookup"><span data-stu-id="6fc7e-132">Following are possible solutions for this issue:</span></span>  
  
-   <span data-ttu-id="6fc7e-133">Wenn die SQL Server-Instanz des primären Replikats ausgefallen ist, starten Sie den Server neu, und überprüfen Sie dann, ob die Verfügbarkeitsgruppe wieder einen ordnungsgemäßen Zustand erreicht.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-133">If the SQL Server instance of the primary replica is down, restart the server and then verify that the availability group recovers to a healthy state.</span></span>  
  
-   <span data-ttu-id="6fc7e-134">Falls anscheinend für das automatische Failover ein Fehler aufgetreten ist, überprüfen Sie, ob die Datenbanken auf dem Replikat mit dem zuvor bekannten primären Replikat synchronisiert werden, und führen Sie dann das Failover auf das primäre Replikat durch.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-134">If the automatic failover appears to have failed, verify that the databases on the replica are synchronized with the previously known primary replica, and then failover to the primary replica.</span></span> <span data-ttu-id="6fc7e-135">Falls die Datenbanken nicht synchronisiert werden, wählen Sie ein Replikat mit einem minimalen Datenverlust aus und stellen dann den Failovermodus wieder her.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-135">If the databases are not synchronized, select a replica with a minimum loss of data, and then recover to failover mode.</span></span>  
  
-   <span data-ttu-id="6fc7e-136">Falls die Ressource im Cluster offline ist, während die Instanzen von SQL Server anscheinend fehlerfrei sind, verwenden Sie den Failovercluster-Manager, um den Clusterzustand oder andere Clusterprobleme auf dem Server zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-136">If the resource in the cluster is offline while the instances of SQL Server appear to be healthy, use Failover Cluster Manager to check the cluster health or other cluster issues on the server.</span></span> <span data-ttu-id="6fc7e-137">Sie können mit dem Failovercluster-Manager auch versuchen, die Verfügbarkeitsgruppenressource wieder in den Onlinezustand zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-137">You can also use the Failover Cluster Manager to attempt to turn the availability group resource online.</span></span>  
  
-   <span data-ttu-id="6fc7e-138">Falls gerade ein Failover durchgeführt wird, warten Sie, bis das Failover abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="6fc7e-138">If there is a failover in progress, wait for the failover to complete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fc7e-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6fc7e-139">See Also</span></span>  
 <span data-ttu-id="6fc7e-140">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6fc7e-140">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="6fc7e-141">Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6fc7e-141">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
