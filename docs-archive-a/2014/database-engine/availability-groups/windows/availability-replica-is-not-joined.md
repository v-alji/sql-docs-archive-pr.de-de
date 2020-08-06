---
title: Verfügbarkeitsreplikat ist nicht verknüpft | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp4joined.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 9c0d10b1-9e12-430c-83b9-ca2bd0a3afc4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7c4f76e98d373e50124f5ca2b135a9fad8f34226
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701918"
---
# <a name="availability-replica-is-not-joined"></a><span data-ttu-id="f51e9-102">Verfügbarkeitsreplikat ist nicht verknüpft</span><span class="sxs-lookup"><span data-stu-id="f51e9-102">Availability replica is not joined</span></span>
    
## <a name="introduction"></a><span data-ttu-id="f51e9-103">Einführung</span><span class="sxs-lookup"><span data-stu-id="f51e9-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f51e9-104">**Richtlinienname**</span><span class="sxs-lookup"><span data-stu-id="f51e9-104">**Policy Name**</span></span>|<span data-ttu-id="f51e9-105">Joinzustand des Verfügbarkeitsreplikats</span><span class="sxs-lookup"><span data-stu-id="f51e9-105">Availability Replica Join State</span></span>|  
|<span data-ttu-id="f51e9-106">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f51e9-106">**Issue**</span></span>|<span data-ttu-id="f51e9-107">Verfügbarkeitsreplikat ist nicht verknüpft.</span><span class="sxs-lookup"><span data-stu-id="f51e9-107">Availability Replica is not joined.</span></span>|  
|<span data-ttu-id="f51e9-108">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="f51e9-108">**Category**</span></span>|<span data-ttu-id="f51e9-109">**Warning**</span><span class="sxs-lookup"><span data-stu-id="f51e9-109">**Warning**</span></span>|  
|<span data-ttu-id="f51e9-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="f51e9-110">**Facet**</span></span>|<span data-ttu-id="f51e9-111">Verfügbarkeitsreplikat</span><span class="sxs-lookup"><span data-stu-id="f51e9-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f51e9-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f51e9-112">Description</span></span>  
 <span data-ttu-id="f51e9-113">Diese Richtlinie überprüft den Verknüpfungsstatus des Verfügbarkeitsreplikats.</span><span class="sxs-lookup"><span data-stu-id="f51e9-113">This policy checks the join state of the availability replica.</span></span> <span data-ttu-id="f51e9-114">Die Richtlinie befindet sich in einem fehlerhaften Zustand, wenn der Verfügbarkeitsgruppe das Verfügbarkeitsreplikat hinzugefügt, aber nicht ordnungsgemäß damit verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="f51e9-114">The policy is in an unhealthy state when the availability replica is added to the availability group, but is not joined properly.</span></span> <span data-ttu-id="f51e9-115">Die Richtlinie befindet sich andernfalls in einem ordnungsgemäßen Zustand.</span><span class="sxs-lookup"><span data-stu-id="f51e9-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f51e9-116">Für diese Version von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]finden Sie Informationen zu möglichen Ursachen und Lösungen im TechNet Wiki unter [Das Verfügbarkeitsreplikat ist nicht verknüpft](https://go.microsoft.com/fwlink/p/?LinkId=220859) .</span><span class="sxs-lookup"><span data-stu-id="f51e9-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability replica is not joined](https://go.microsoft.com/fwlink/p/?LinkId=220859) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="f51e9-117">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="f51e9-117">Possible Causes</span></span>  
 <span data-ttu-id="f51e9-118">Das sekundäre Replikat ist nicht mit der Verfügbarkeitsgruppe verknüpft.</span><span class="sxs-lookup"><span data-stu-id="f51e9-118">The secondary replica is not joined to the availability group.</span></span> <span data-ttu-id="f51e9-119">Damit ein Verfügbarkeitsreplikat erfolgreich mit der Verfügbarkeitsgruppe verknüpft wird, muss der Verknüpfungsstatus "Verknüpfte eigenständige Instanz" (1) oder "Verknüpfter Failovercluster" (2) lauten.</span><span class="sxs-lookup"><span data-stu-id="f51e9-119">For an availability replica to be successfully joined to the availability group, the join state must be Joined Standalone Instance (1) or Joined Failover Cluster (2).</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="f51e9-120">Mögliche Lösung</span><span class="sxs-lookup"><span data-stu-id="f51e9-120">Possible Solution</span></span>  
 <span data-ttu-id="f51e9-121">Verknüpfen Sie das sekundäre Replikat mit der Verfügbarkeitsgruppe mithilfe von Transact-SQL, PowerShell oder SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="f51e9-121">Use Transact-SQL, PowerShell, or SQL Server Management Studio to join the secondary replica to the availability group.</span></span> <span data-ttu-id="f51e9-122">Weitere Informationen zum Verknüpfen sekundärer Replikate mit Verfügbarkeitsgruppen finden Sie unter [Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span><span class="sxs-lookup"><span data-stu-id="f51e9-122">For more information about joining secondary replicas to availability groups, see [Joining a Secondary Replica to an Availability Group (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f51e9-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f51e9-123">See Also</span></span>  
 <span data-ttu-id="f51e9-124">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f51e9-124">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="f51e9-125">Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="f51e9-125">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
