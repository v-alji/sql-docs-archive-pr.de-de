---
title: Einige synchrone Replikate wurden nicht synchronisiert | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp5synchronized.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: e58ed56e-4c30-42e6-a9fc-a8c401620e02
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ecef2d16e80e128834a71e1f1f112096f8ccc9cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618277"
---
# <a name="some-synchronous-replicas-are-not-synchronized"></a><span data-ttu-id="bb4c2-102">Einige synchrone Replikate wurden nicht synchronisiert</span><span class="sxs-lookup"><span data-stu-id="bb4c2-102">Some synchronous replicas are not synchronized</span></span>
    
## <a name="introduction"></a><span data-ttu-id="bb4c2-103">Einführung</span><span class="sxs-lookup"><span data-stu-id="bb4c2-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bb4c2-104">**Richtlinienname**</span><span class="sxs-lookup"><span data-stu-id="bb4c2-104">**Policy Name**</span></span>|<span data-ttu-id="bb4c2-105">Datensynchronisierungsstatus synchroner Replikate</span><span class="sxs-lookup"><span data-stu-id="bb4c2-105">Synchronous Replicas Data Synchronization State</span></span>|  
|<span data-ttu-id="bb4c2-106">**Problem**</span><span class="sxs-lookup"><span data-stu-id="bb4c2-106">**Issue**</span></span>|<span data-ttu-id="bb4c2-107">Einige synchrone Replikate wurden nicht synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="bb4c2-107">Some synchronous replicas are not synchronized.</span></span>|  
|<span data-ttu-id="bb4c2-108">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="bb4c2-108">**Category**</span></span>|<span data-ttu-id="bb4c2-109">**Warning**</span><span class="sxs-lookup"><span data-stu-id="bb4c2-109">**Warning**</span></span>|  
|<span data-ttu-id="bb4c2-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="bb4c2-110">**Facet**</span></span>|<span data-ttu-id="bb4c2-111">Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="bb4c2-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bb4c2-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bb4c2-112">Description</span></span>  
 <span data-ttu-id="bb4c2-113">Diese Richtlinie führt ein Rollup des Datensynchronisierungsstatus aller Verfügbarkeitsreplikate sowie eine Überprüfung auf Verfügbarkeitsreplikate durch, die sich nicht im erwarteten Synchronisierungsstatus befinden.</span><span class="sxs-lookup"><span data-stu-id="bb4c2-113">This policy rolls up the data synchronization state of all availability replicas and checks for any availability replicas that are not in the expected synchronization state.</span></span> <span data-ttu-id="bb4c2-114">Die Richtlinie befindet sich in einem fehlerhaften Zustand, wenn eines der asynchronen Replikate nicht den Status SYNCHRONIZING aufweist und eines der synchronen Replikate nicht den Status SYNCHRONIZED aufweist.</span><span class="sxs-lookup"><span data-stu-id="bb4c2-114">The policy is in an unhealthy state when any asynchronous replica is not in a SYNCHRONIZING state and any synchronous replica is not in a SYNCHRONIZED state.</span></span> <span data-ttu-id="bb4c2-115">Andernfalls befindet sich die Richtlinie in einem ordnungsgemäßen Zustand.</span><span class="sxs-lookup"><span data-stu-id="bb4c2-115">The policy state is otherwise healthy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb4c2-116">Für diese Version von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]finden Sie Informationen zu möglichen Ursachen und Lösungen im TechNet Wiki unter [Einige synchrone Replikate wurden nicht synchronisiert](https://go.microsoft.com/fwlink/p/?LinkId=220853) .</span><span class="sxs-lookup"><span data-stu-id="bb4c2-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some synchronous replicas are not synchronized](https://go.microsoft.com/fwlink/p/?LinkId=220853) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="bb4c2-117">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="bb4c2-117">Possible Causes</span></span>  
 <span data-ttu-id="bb4c2-118">In dieser Verfügbarkeitsgruppe wird derzeit mindestens ein synchrones Replikat nicht synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="bb4c2-118">In this availability group, at least one synchronous replica is not currently synchronized.</span></span> <span data-ttu-id="bb4c2-119">Der Synchronisierungsstatus des Replikats lautet entweder SYNCHRONIZING oder NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="bb4c2-119">The replica synchronization state could be either SYNCHONIZING or NOT SYNCHRONIZING.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="bb4c2-120">Mögliche Lösung</span><span class="sxs-lookup"><span data-stu-id="bb4c2-120">Possible Solution</span></span>  
 <span data-ttu-id="bb4c2-121">Verwenden Sie den Verfügbarkeitsreplikat-Richtlinienstatus, um nach dem Verfügbarkeitsreplikat mit dem fehlerhaften Synchronisierungsstatus zu suchen, und beheben Sie das Problem für das Verfügbarkeitsreplikat.</span><span class="sxs-lookup"><span data-stu-id="bb4c2-121">Use the availability replica policy state to find the availability replica with the incorrect synchronization state, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb4c2-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bb4c2-122">See Also</span></span>  
 <span data-ttu-id="bb4c2-123">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bb4c2-123">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="bb4c2-124">Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="bb4c2-124">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
