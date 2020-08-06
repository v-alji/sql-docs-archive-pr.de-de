---
title: Verfügbarkeitsgruppe nicht bereit für automatisches Failover | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp3autofailover.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 28261014-342c-442a-bd89-6d04b8d4e8b7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2995ddec51cd70d8a3f209229d0ecb9b0132c79e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608875"
---
# <a name="availability-group-is-not-ready-for-automatic-failover"></a><span data-ttu-id="1287c-102">Verfügbarkeitsgruppe nicht bereit für automatischen Failover</span><span class="sxs-lookup"><span data-stu-id="1287c-102">Availability group is not ready for automatic failover</span></span>
    
## <a name="introduction"></a><span data-ttu-id="1287c-103">Einführung</span><span class="sxs-lookup"><span data-stu-id="1287c-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1287c-104">**Richtlinienname**</span><span class="sxs-lookup"><span data-stu-id="1287c-104">**Policy Name**</span></span>|<span data-ttu-id="1287c-105">Bereitschaft der Verfügbarkeitsgruppe für automatisches Failover</span><span class="sxs-lookup"><span data-stu-id="1287c-105">Availability Group Automatic Failover Readiness</span></span>|  
|<span data-ttu-id="1287c-106">**Problem**</span><span class="sxs-lookup"><span data-stu-id="1287c-106">**Issue**</span></span>|<span data-ttu-id="1287c-107">Die Verfügbarkeitsgruppe ist nicht für das automatische Failover bereit.</span><span class="sxs-lookup"><span data-stu-id="1287c-107">Availability group is not ready for automatic failover.</span></span>|  
|<span data-ttu-id="1287c-108">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="1287c-108">**Category**</span></span>|<span data-ttu-id="1287c-109">**Critical** (Kritisch)</span><span class="sxs-lookup"><span data-stu-id="1287c-109">**Critical**</span></span>|  
|<span data-ttu-id="1287c-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="1287c-110">**Facet**</span></span>|<span data-ttu-id="1287c-111">Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="1287c-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1287c-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1287c-112">Description</span></span>  
 <span data-ttu-id="1287c-113">Diese Richtlinie überprüft, ob die Verfügbarkeitsgruppe über mindestens ein sekundäres Replikat verfügt, das bereit für das Failover ist.</span><span class="sxs-lookup"><span data-stu-id="1287c-113">This policy checks to verify that the availability group has at least one secondary replica that is failover ready.</span></span> <span data-ttu-id="1287c-114">Die Richtlinie befindet sich in einem fehlerhaften Zustand, und es wird eine Warnung ausgelöst, wenn für das primäre Replikat der automatische Failovermodus aktiviert ist, aber keines der sekundären Replikate in der Verfügbarkeitsgruppe für das Failover bereit ist.</span><span class="sxs-lookup"><span data-stu-id="1287c-114">The policy is in an unhealthy state and an alert is raised when the failover mode of the primary replica is automatic, however none of the secondary replicas in the availability group are failover ready.</span></span>  
  
 <span data-ttu-id="1287c-115">Die Richtlinie befindet sich in einem ordnungsgemäßen Zustand, wenn mindestens ein sekundäres Replikat bereit für das automatische Failover ist.</span><span class="sxs-lookup"><span data-stu-id="1287c-115">The policy is in a healthy state when at least one secondary replica is automatic failover ready.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1287c-116">Für diese Version von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]finden Sie Informationen zu möglichen Ursachen und Lösungen im TechNet Wiki unter [Verfügbarkeitsgruppe nicht bereit für automatischen Failover](https://go.microsoft.com/fwlink/p/?LinkId=220851) .</span><span class="sxs-lookup"><span data-stu-id="1287c-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability group is not ready for automatic failover](https://go.microsoft.com/fwlink/p/?LinkId=220851) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="1287c-117">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="1287c-117">Possible Causes</span></span>  
 <span data-ttu-id="1287c-118">Die Verfügbarkeitsgruppe ist nicht für das automatische Failover bereit.</span><span class="sxs-lookup"><span data-stu-id="1287c-118">The availability group is not ready for automatic failover.</span></span> <span data-ttu-id="1287c-119">Das primäre Replikat wurde für das automatische Failover konfiguriert. Das sekundäre Replikat ist jedoch nicht für das automatische Failover bereit.</span><span class="sxs-lookup"><span data-stu-id="1287c-119">The primary replica is configured for automatic failover; however, the secondary replica is not ready for automatic failover.</span></span> <span data-ttu-id="1287c-120">Das sekundäre Replikat, das für automatisches Failover konfiguriert wurde, ist ggf. nicht verfügbar, oder dessen Datensynchronisierungsstatus lautet derzeit SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="1287c-120">The secondary replica that is configured for automatic failover might be unavailable or its data synchronization state is currently not SYNCHRONIZED.</span></span>  
  
## <a name="possible-solutions"></a><span data-ttu-id="1287c-121">Mögliche Lösungen</span><span class="sxs-lookup"><span data-stu-id="1287c-121">Possible Solutions</span></span>  
 <span data-ttu-id="1287c-122">Für dieses Problem gibt es die folgenden möglichen Lösungen:</span><span class="sxs-lookup"><span data-stu-id="1287c-122">Following are possible solutions for this issue:</span></span>  
  
-   <span data-ttu-id="1287c-123">Stellen Sie sicher, dass mindestens ein sekundäres Replikat für automatisches Failover konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="1287c-123">Verify that at least one secondary replica is configured as automatic failover.</span></span> <span data-ttu-id="1287c-124">Falls kein sekundäres Replikat für automatisches Failover konfiguriert ist, aktualisieren Sie die Konfiguration eines sekundären Replikats, sodass es als Ziel für das automatische Failover mit synchronem Commit dient.</span><span class="sxs-lookup"><span data-stu-id="1287c-124">If there is not a secondary replica configured as automatic failover, update the configuration of a secondary replica to be the automatic failover target with synchronous commit.</span></span>  
  
-   <span data-ttu-id="1287c-125">Überprüfen Sie anhand der Richtlinie, ob die Daten einen Synchronisierungsstatus aufweisen und ob das Ziel für das automatische Failover SYNCHRONIZED lautet. Beheben Sie dann das Problem des Verfügbarkeitsreplikats.</span><span class="sxs-lookup"><span data-stu-id="1287c-125">Use the policy to verify that the data is in a synchronization state and the automatic failover target is SYNCHRONIZED, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1287c-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1287c-126">See Also</span></span>  
 <span data-ttu-id="1287c-127">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1287c-127">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="1287c-128">Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1287c-128">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
