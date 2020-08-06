---
title: Datensynchronisierungsstatus einer Verfügbarkeitsdatenbank ist nicht fehlerfrei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.drp3datasynchealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 89f95d15-33c6-4768-bccd-9dbf8c4f49a9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 221f25a1ee7e4a8719acc133372c742ca4a79303
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727117"
---
# <a name="data-synchronization-state-of-some-availability-database-is-not-healthy"></a><span data-ttu-id="1b22c-102">Datensynchronisierungsstatus einer Verfügbarkeitsdatenbank ist nicht fehlerfrei</span><span class="sxs-lookup"><span data-stu-id="1b22c-102">Data synchronization state of some availability database is not healthy</span></span>
    
## <a name="introduction"></a><span data-ttu-id="1b22c-103">Einführung</span><span class="sxs-lookup"><span data-stu-id="1b22c-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1b22c-104">**Richtlinienname**</span><span class="sxs-lookup"><span data-stu-id="1b22c-104">**Policy Name**</span></span>|<span data-ttu-id="1b22c-105">Datensynchronisierungsstatus des Verfügbarkeitsreplikats</span><span class="sxs-lookup"><span data-stu-id="1b22c-105">Availability Replica Data Synchronization State</span></span>|  
|<span data-ttu-id="1b22c-106">**Problem**</span><span class="sxs-lookup"><span data-stu-id="1b22c-106">**Issue**</span></span>|<span data-ttu-id="1b22c-107">Der Datensynchronisierungsstatus einer Verfügbarkeitsdatenbank ist nicht fehlerfrei.</span><span class="sxs-lookup"><span data-stu-id="1b22c-107">Data synchronization state of some availability database is not healthy.</span></span>|  
|<span data-ttu-id="1b22c-108">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="1b22c-108">**Category**</span></span>|<span data-ttu-id="1b22c-109">**Warning**</span><span class="sxs-lookup"><span data-stu-id="1b22c-109">**Warning**</span></span>|  
|<span data-ttu-id="1b22c-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="1b22c-110">**Facet**</span></span>|<span data-ttu-id="1b22c-111">Verfügbarkeitsreplikat</span><span class="sxs-lookup"><span data-stu-id="1b22c-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1b22c-112">Description</span><span class="sxs-lookup"><span data-stu-id="1b22c-112">Description</span></span>  
 <span data-ttu-id="1b22c-113">Diese Richtlinie überprüft den Datensynchronisierungsstatus der Verfügbarkeitsdatenbank (auch bekannt als "Datenbankreplikat").</span><span class="sxs-lookup"><span data-stu-id="1b22c-113">This policy checks the data synchronization state of the availability database (also known as a "database replica").</span></span> <span data-ttu-id="1b22c-114">Die Richtlinie befindet sich in einem fehlerhaften Zustand, wenn der Datensynchronisierungsstatus NOT SYNCHRONIZING lautet oder wenn der Status für das Datenbankreplikat mit synchronem Commit SYNCHRONIZED lautet.</span><span class="sxs-lookup"><span data-stu-id="1b22c-114">The policy is in an unhealthy state when the data synchronization state is NOT SYNCHRONIZING or the state is not SYNCHRONIZED for the synchronous-commit database replica.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1b22c-115">Für diese Version von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]finden Sie Informationen zu möglichen Ursachen und Lösungen im TechNet Wiki unter [Datensynchronisierungsstatus der Verfügbarkeitsdatenbank ist nicht fehlerfrei](https://go.microsoft.com/fwlink/p/?LinkId=220863) .</span><span class="sxs-lookup"><span data-stu-id="1b22c-115">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Data synchronization state of availability database is not healthy](https://go.microsoft.com/fwlink/p/?LinkId=220863) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="1b22c-116">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="1b22c-116">Possible Causes</span></span>  
 <span data-ttu-id="1b22c-117">Mindestens eine Verfügbarkeitsdatenbank des Replikats verfügt über einen fehlerhaften Datensynchronisierungsstatus.</span><span class="sxs-lookup"><span data-stu-id="1b22c-117">At least one availability database on the replica has an unhealthy data synchronization state.</span></span> <span data-ttu-id="1b22c-118">Wenn das Replikat ein Verfügbarkeitsreplikat für asynchrone Commits ist, sollten alle Verfügbarkeitsdatenbanken den Status SYNCHRONIZING aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1b22c-118">If this is an asynchronous-commit availability replica, all availability databases should be in the SYNCHRONIZING state.</span></span> <span data-ttu-id="1b22c-119">Falls es sich dabei um ein Verfügbarkeitsreplikat für synchrone Commits handelt, sollten sich alle Verfügbarkeitsdatenbanken im Status SYNCHRONIZED befinden.</span><span class="sxs-lookup"><span data-stu-id="1b22c-119">If this is a synchronous-commit availability replica, all availability databases should be in the SYNCHRONIZED state.</span></span> <span data-ttu-id="1b22c-120">Dieses Problem kann folgende Ursachen haben:</span><span class="sxs-lookup"><span data-stu-id="1b22c-120">This issue can be caused by the following:</span></span>  
  
-   <span data-ttu-id="1b22c-121">Die Verbindung des Verfügbarkeitsreplikats wurde getrennt.</span><span class="sxs-lookup"><span data-stu-id="1b22c-121">The availability replica might be disconnected.</span></span>  
  
-   <span data-ttu-id="1b22c-122">Die Datenverschiebung wurde angehalten.</span><span class="sxs-lookup"><span data-stu-id="1b22c-122">The data movement might be suspended.</span></span>  
  
-   <span data-ttu-id="1b22c-123">Auf die Datenbank kann nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="1b22c-123">The database might not be accessible.</span></span>  
  
-   <span data-ttu-id="1b22c-124">Es liegt ein vorübergehendes Verzögerungsproblem aufgrund der Netzwerklatenzzeit oder der Last auf dem primären oder sekundären Replikat vor.</span><span class="sxs-lookup"><span data-stu-id="1b22c-124">There might be a temporary delay issue due to network latency or the load on the primary or secondary replica.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="1b22c-125">Mögliche Lösung</span><span class="sxs-lookup"><span data-stu-id="1b22c-125">Possible Solution</span></span>  
 <span data-ttu-id="1b22c-126">Beheben Sie alle Probleme in Bezug auf die Verbindung oder auf die angehaltene Datenverschiebung.</span><span class="sxs-lookup"><span data-stu-id="1b22c-126">Resolve any connection or data movement suspend issues.</span></span> <span data-ttu-id="1b22c-127">Überprüfen Sie die Ereignisse für dieses Problem mit SQL Server Management Studio, und ermitteln Sie den Datenbankfehler.</span><span class="sxs-lookup"><span data-stu-id="1b22c-127">Check the events for this issue using SQL Server Management Studio, and find the database error.</span></span> <span data-ttu-id="1b22c-128">Führen Sie die entsprechenden Schritte der Problembehandlung für den Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="1b22c-128">Follow the troubleshooting steps for the specific error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b22c-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b22c-129">See Also</span></span>  
 <span data-ttu-id="1b22c-130">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1b22c-130">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="1b22c-131">Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1b22c-131">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
