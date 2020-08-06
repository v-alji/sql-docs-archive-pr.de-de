---
title: Verfügbarkeitsdatenbank angehalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.drp1notsuspended.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 6baee70f-848c-4e86-b20d-78875c0f82cb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07a547f217367f13df739348325461c862d831f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608879"
---
# <a name="availability-database-is-suspended"></a><span data-ttu-id="079b3-102">Verfügbarkeitsdatenbank angehalten</span><span class="sxs-lookup"><span data-stu-id="079b3-102">Availability database is suspended</span></span>
    
## <a name="introduction"></a><span data-ttu-id="079b3-103">Einführung</span><span class="sxs-lookup"><span data-stu-id="079b3-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="079b3-104">**Richtlinienname**</span><span class="sxs-lookup"><span data-stu-id="079b3-104">**Policy Name**</span></span>|<span data-ttu-id="079b3-105">Verfügbarkeitsdatenbank im angehaltenen Zustand</span><span class="sxs-lookup"><span data-stu-id="079b3-105">Availability Database Suspension State</span></span>|  
|<span data-ttu-id="079b3-106">**Problem**</span><span class="sxs-lookup"><span data-stu-id="079b3-106">**Issue**</span></span>|<span data-ttu-id="079b3-107">Die Verfügbarkeitsdatenbank wurde angehalten.</span><span class="sxs-lookup"><span data-stu-id="079b3-107">Availability database is suspended.</span></span>|  
|<span data-ttu-id="079b3-108">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="079b3-108">**Category**</span></span>|<span data-ttu-id="079b3-109">**Warning**</span><span class="sxs-lookup"><span data-stu-id="079b3-109">**Warning**</span></span>|  
|<span data-ttu-id="079b3-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="079b3-110">**Facet**</span></span>|<span data-ttu-id="079b3-111">Verfügbarkeitsdatenbank</span><span class="sxs-lookup"><span data-stu-id="079b3-111">Availability database</span></span>|  
  
## <a name="description"></a><span data-ttu-id="079b3-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="079b3-112">Description</span></span>  
 <span data-ttu-id="079b3-113">Diese Richtlinie überprüft den Status der Datenverschiebung für die sekundäre Datenbank (auch bekannt als "sekundäres Datenbankreplikat").</span><span class="sxs-lookup"><span data-stu-id="079b3-113">This policy checks the state of data movement of the secondary database (also known as a "secondary database replica").</span></span> <span data-ttu-id="079b3-114">Die Richtlinie befindet sich in einem fehlerhaften Zustand, wenn die Datenverschiebung angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="079b3-114">The policy is in an unhealthy state when the data movement is suspended.</span></span> <span data-ttu-id="079b3-115">Die Richtlinie befindet sich andernfalls in einem ordnungsgemäßen Zustand.</span><span class="sxs-lookup"><span data-stu-id="079b3-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="079b3-116"> Für diese Version von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]finden Sie Informationen zu möglichen Ursachen und Lösungen im TechNet Wiki unter [Verfügbarkeitsdatenbank angehalten](https://go.microsoft.com/fwlink/p/?LinkId=220860) .</span><span class="sxs-lookup"><span data-stu-id="079b3-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability database is suspended](https://go.microsoft.com/fwlink/p/?LinkId=220860) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="079b3-117">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="079b3-117">Possible Causes</span></span>  
 <span data-ttu-id="079b3-118">Die Datensynchronisierung dieser Verfügbarkeitsdatenbank kann aus den folgenden Gründen angehalten worden sein:</span><span class="sxs-lookup"><span data-stu-id="079b3-118">Data synchronization on this availability database might have been suspended because of the following:</span></span>  
  
-   <span data-ttu-id="079b3-119">Aufgrund eines Fehlers kann es sein, dass das System die Datensynchronisierung angehalten hat.</span><span class="sxs-lookup"><span data-stu-id="079b3-119">Due to an error, the system might have suspended data synchronization.</span></span>  
  
-   <span data-ttu-id="079b3-120">Der Datenbankadministrator hat die Datensynchronisierung ggf. zu Wartungszwecken angehalten.</span><span class="sxs-lookup"><span data-stu-id="079b3-120">The database administrator might have suspended data synchronization for maintenance purposes.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="079b3-121">Mögliche Lösung</span><span class="sxs-lookup"><span data-stu-id="079b3-121">Possible Solution</span></span>  
 <span data-ttu-id="079b3-122">Setzen Sie die Datensynchronisierung fort.</span><span class="sxs-lookup"><span data-stu-id="079b3-122">Resume data synchronization.</span></span> <span data-ttu-id="079b3-123">Falls das Problem weiterhin auftritt, sollten Sie die Verfügbarkeitsgruppe im Ereignisprotokoll überprüfen und dann diagnostizieren, warum das System die Datenverschiebung angehalten hat.</span><span class="sxs-lookup"><span data-stu-id="079b3-123">If the issue persists, check the availability group in the Event log, and then diagnose why the system suspended data movement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="079b3-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="079b3-124">See Also</span></span>  
 <span data-ttu-id="079b3-125">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="079b3-125">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="079b3-126">Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="079b3-126">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
