---
title: Datensynchronisierungsstatus der Verfügbarkeitsdatenbank ist nicht fehlerfrei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp3datasynchealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 4fd003e7-808e-4b0e-b28a-47d9f2616f06
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a179008c20b108a2f6aaefd5dd80b22708e94a8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727126"
---
# <a name="data-synchronization-state-of-availability-database-is-not-healthy"></a><span data-ttu-id="d450c-102">Datensynchronisierungsstatus der Verfügbarkeitsdatenbank ist nicht fehlerfrei</span><span class="sxs-lookup"><span data-stu-id="d450c-102">Data synchronization state of availability database is not healthy</span></span>
    
## <a name="introduction"></a><span data-ttu-id="d450c-103">Einführung</span><span class="sxs-lookup"><span data-stu-id="d450c-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d450c-104">**Richtlinienname**</span><span class="sxs-lookup"><span data-stu-id="d450c-104">**Policy Name**</span></span>|<span data-ttu-id="d450c-105">Datensynchronisierungsstatus der Verfügbarkeitsdatenbank</span><span class="sxs-lookup"><span data-stu-id="d450c-105">Availability Database Data Synchronization State</span></span>|  
|<span data-ttu-id="d450c-106">**Problem**</span><span class="sxs-lookup"><span data-stu-id="d450c-106">**Issue**</span></span>|<span data-ttu-id="d450c-107">Der Datensynchronisierungsstatus der Verfügbarkeitsdatenbank ist nicht fehlerfrei.</span><span class="sxs-lookup"><span data-stu-id="d450c-107">Data synchronization state of availability database is not healthy.</span></span>|  
|<span data-ttu-id="d450c-108">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="d450c-108">**Category**</span></span>|<span data-ttu-id="d450c-109">**Warning**</span><span class="sxs-lookup"><span data-stu-id="d450c-109">**Warning**</span></span>|  
|<span data-ttu-id="d450c-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="d450c-110">**Facet**</span></span>|<span data-ttu-id="d450c-111">Verfügbarkeitsdatenbank</span><span class="sxs-lookup"><span data-stu-id="d450c-111">Availability database</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d450c-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d450c-112">Description</span></span>  
 <span data-ttu-id="d450c-113">Diese Richtlinie führt ein Rollup des Datensynchronisierungsstatus aller Verfügbarkeitsdatenbanken (auch bekannt als "Datenbankreplikate") im Verfügbarkeitsreplikat aus.</span><span class="sxs-lookup"><span data-stu-id="d450c-113">This policy rolls up the data synchronization state of all availability databases (also known as "database replicas") in the availability replica.</span></span> <span data-ttu-id="d450c-114">Die Richtlinie befindet sich in einem fehlerhaften Zustand, wenn ein beliebiges Datenbankreplikat nicht den erwarteten Datensynchronisierungsstatus aufweist.</span><span class="sxs-lookup"><span data-stu-id="d450c-114">The policy is in an unhealthy sate when any database replica is not in the expected data synchronization state.</span></span> <span data-ttu-id="d450c-115">Die Richtlinie befindet sich andernfalls in einem ordnungsgemäßen Zustand.</span><span class="sxs-lookup"><span data-stu-id="d450c-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d450c-116">Für dieses Release von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]finden Sie Informationen zu möglichen Ursachen und Lösungen im TechNet Wiki unter [Datensynchronisierungsstatus einer Verfügbarkeitsdatenbank ist nicht fehlerfrei](https://go.microsoft.com/fwlink/p/?LinkId=220858) .</span><span class="sxs-lookup"><span data-stu-id="d450c-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Data synchronization state of some availability database is not healthy](https://go.microsoft.com/fwlink/p/?LinkId=220858) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="d450c-117">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="d450c-117">Possible Causes</span></span>  
 <span data-ttu-id="d450c-118">Der Datensynchronisierungsstatus dieser Verfügbarkeitsdatenbank ist fehlerhaft.</span><span class="sxs-lookup"><span data-stu-id="d450c-118">The data synchronization state of this availability database is unhealthy.</span></span> <span data-ttu-id="d450c-119">Auf einem Verfügbarkeitsreplikat für asynchrone Commits sollte sich jede Verfügbarkeitsdatenbank im Status SYNCHRONIZING befinden.</span><span class="sxs-lookup"><span data-stu-id="d450c-119">On an asynchronous-commit availability replica, every availability database should be in the SYNCHRONIZING state.</span></span> <span data-ttu-id="d450c-120">Auf einem Replikat für synchrone Commits muss sich jede Verfügbarkeitsdatenbank im Status SYNCHRONIZED befinden.</span><span class="sxs-lookup"><span data-stu-id="d450c-120">On a synchronous-commit replica, every availability database must be in the SYNCHRONIZED state.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="d450c-121">Mögliche Lösung</span><span class="sxs-lookup"><span data-stu-id="d450c-121">Possible Solution</span></span>  
 <span data-ttu-id="d450c-122">Verwenden Sie die Datenbankreplikatrichtlinie zum Suchen nach dem Datenbankreplikat mit einem fehlerhaften Datensynchronisierungsstatus, und beheben Sie das Problem für das Datenbankreplikat.</span><span class="sxs-lookup"><span data-stu-id="d450c-122">Use the database replica policy to find the database replica with an unhealthy data synchronization state, and then resolve the issue at the database replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d450c-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d450c-123">See Also</span></span>  
 <span data-ttu-id="d450c-124">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d450c-124">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="d450c-125">Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d450c-125">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
