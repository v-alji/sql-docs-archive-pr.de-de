---
title: Einige Verfügbarkeitsreplikate haben keine fehlerfreie Rolle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp6allroleshealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 7ec5b337-7201-4a66-a541-7560f8b18784
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 801fe20edf6f2dbe09bc800722cf4210988ebc69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618282"
---
# <a name="some-availability-replicas-do-not-have-a-healthy-role"></a><span data-ttu-id="d6ecf-102">Einige Verfügbarkeitsreplikate haben keine fehlerfreie Rolle</span><span class="sxs-lookup"><span data-stu-id="d6ecf-102">Some availability replicas do not have a healthy role</span></span>
    
## <a name="introduction"></a><span data-ttu-id="d6ecf-103">Einführung</span><span class="sxs-lookup"><span data-stu-id="d6ecf-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d6ecf-104">**Richtlinienname**</span><span class="sxs-lookup"><span data-stu-id="d6ecf-104">**Policy Name**</span></span>|<span data-ttu-id="d6ecf-105">Verfügbarkeitsreplikat-Rollenstatus</span><span class="sxs-lookup"><span data-stu-id="d6ecf-105">Availability Replicas Role State</span></span>|  
|<span data-ttu-id="d6ecf-106">**Problem**</span><span class="sxs-lookup"><span data-stu-id="d6ecf-106">**Issue**</span></span>|<span data-ttu-id="d6ecf-107">Einige Verfügbarkeitsreplikate haben keine fehlerfreie Rolle.</span><span class="sxs-lookup"><span data-stu-id="d6ecf-107">Some availability replicas do not have a healthy role.</span></span>|  
|<span data-ttu-id="d6ecf-108">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="d6ecf-108">**Category**</span></span>|<span data-ttu-id="d6ecf-109">**Warning**</span><span class="sxs-lookup"><span data-stu-id="d6ecf-109">**Warning**</span></span>|  
|<span data-ttu-id="d6ecf-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="d6ecf-110">**Facet**</span></span>|<span data-ttu-id="d6ecf-111">Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="d6ecf-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d6ecf-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d6ecf-112">Description</span></span>  
 <span data-ttu-id="d6ecf-113">Diese Richtlinie führt ein Rollup des Verbindungsstatus aller Verfügbarkeitsreplikate aus und überprüft, ob Verfügbarkeitsreplikate vorhanden sind, die keine fehlerfreie Rolle aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d6ecf-113">This policy rolls up the connection state of all availability replicas and checks if there are any availability replicas that are not in a healthy role.</span></span> <span data-ttu-id="d6ecf-114">Die Richtlinie befindet sich in einem fehlerhaften Zustand, wenn jedes Verfügbarkeitsreplikat weder primär noch sekundär ist.</span><span class="sxs-lookup"><span data-stu-id="d6ecf-114">The policy is in an unhealthy state when any availability replica is neither primary nor secondary.</span></span> <span data-ttu-id="d6ecf-115">Die Richtlinie befindet sich andernfalls in einem ordnungsgemäßen Zustand.</span><span class="sxs-lookup"><span data-stu-id="d6ecf-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d6ecf-116">Für diese Version von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]finden Sie Informationen zu möglichen Ursachen und Lösungen im TechNet Wiki unter [Einige Verfügbarkeitsreplikate haben keine fehlerfreie Rolle](https://go.microsoft.com/fwlink/p/?LinkId=220854) .</span><span class="sxs-lookup"><span data-stu-id="d6ecf-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some availability replicas do not have a healthy role](https://go.microsoft.com/fwlink/p/?LinkId=220854) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="d6ecf-117">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="d6ecf-117">Possible Causes</span></span>  
 <span data-ttu-id="d6ecf-118">In dieser Verfügbarkeitsgruppe verfügt mindestens ein Verfügbarkeitsreplikat derzeit nicht über die primäre oder sekundäre Rolle.</span><span class="sxs-lookup"><span data-stu-id="d6ecf-118">In this availability group, at least one availability replica does not currently have the primary or secondary role.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="d6ecf-119">Mögliche Lösung</span><span class="sxs-lookup"><span data-stu-id="d6ecf-119">Possible Solution</span></span>  
 <span data-ttu-id="d6ecf-120">Verwenden Sie den Verfügbarkeitsreplikat-Richtlinienstatus, um nach dem Verfügbarkeitsreplikat zu suchen, dessen Rolle nicht primär oder sekundär ist, und beheben Sie das Problem des Verfügbarkeitsreplikats.</span><span class="sxs-lookup"><span data-stu-id="d6ecf-120">Use the availability replica policy state to find the availability replica whose role is not primary or secondary, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6ecf-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6ecf-121">See Also</span></span>  
 <span data-ttu-id="d6ecf-122">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d6ecf-122">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="d6ecf-123">Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d6ecf-123">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
