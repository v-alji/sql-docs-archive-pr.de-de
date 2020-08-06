---
title: Einige Verfügbarkeitsreplikate sind getrennt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp7allconnected.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: aea808be-6f0f-40c2-9aa2-a2a435ec6443
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1bb6535b513770b9b4718a0e8372c0a5bc3cba84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618286"
---
# <a name="some-availability-replicas-are-disconnected"></a><span data-ttu-id="aee85-102">Einige Verfügbarkeitsreplikate sind getrennt</span><span class="sxs-lookup"><span data-stu-id="aee85-102">Some availability replicas are disconnected</span></span>
    
## <a name="introduction"></a><span data-ttu-id="aee85-103">Einführung</span><span class="sxs-lookup"><span data-stu-id="aee85-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aee85-104">**Richtlinienname**</span><span class="sxs-lookup"><span data-stu-id="aee85-104">**Policy Name**</span></span>|<span data-ttu-id="aee85-105">Verbindungsstatus von Verfügbarkeitsreplikaten</span><span class="sxs-lookup"><span data-stu-id="aee85-105">Availability Replicas Connection State</span></span>|  
|<span data-ttu-id="aee85-106">**Problem**</span><span class="sxs-lookup"><span data-stu-id="aee85-106">**Issue**</span></span>|<span data-ttu-id="aee85-107">Einige Verfügbarkeitsreplikate sind getrennt.</span><span class="sxs-lookup"><span data-stu-id="aee85-107">Some availability replicas are disconnected.</span></span>|  
|<span data-ttu-id="aee85-108">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="aee85-108">**Category**</span></span>|<span data-ttu-id="aee85-109">**Warning**</span><span class="sxs-lookup"><span data-stu-id="aee85-109">**Warning**</span></span>|  
|<span data-ttu-id="aee85-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="aee85-110">**Facet**</span></span>|<span data-ttu-id="aee85-111">Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="aee85-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="aee85-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="aee85-112">Description</span></span>  
 <span data-ttu-id="aee85-113">Diese Richtlinie führt ein Rollup des Verbindungsstatus aller Verfügbarkeitsreplikate durch und überprüft, ob Verfügbarkeitsreplikate den Status DISCONNECTED aufweisen.</span><span class="sxs-lookup"><span data-stu-id="aee85-113">This policy rolls up the connection state of all availability replicas and checks for any availability replicas that are DISCONENCTED.</span></span> <span data-ttu-id="aee85-114">Die Richtlinie befindet sich in einem fehlerhaften Zustand, wenn der Verbindungsstatus von einem der Verfügbarkeitsreplikate DISCONNECTED lautet.</span><span class="sxs-lookup"><span data-stu-id="aee85-114">The policy is in an unhealthy state when any availability replica is DISCONNECTED.</span></span> <span data-ttu-id="aee85-115">Die Richtlinie befindet sich andernfalls in einem ordnungsgemäßen Zustand.</span><span class="sxs-lookup"><span data-stu-id="aee85-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aee85-116">Für diese Version von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]finden Sie Informationen zu möglichen Ursachen und Lösungen im TechNet Wiki unter [Einige Verfügbarkeitsreplikate sind getrennt](https://go.microsoft.com/fwlink/p/?LinkId=220855) .</span><span class="sxs-lookup"><span data-stu-id="aee85-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some availability replicas are disconnected](https://go.microsoft.com/fwlink/p/?LinkId=220855) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="aee85-117">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="aee85-117">Possible Causes</span></span>  
 <span data-ttu-id="aee85-118">In dieser Verfügbarkeitsgruppe ist mindestens ein sekundäres Replikat nicht mit dem primären Replikat verbunden.</span><span class="sxs-lookup"><span data-stu-id="aee85-118">In this availability group, at least one secondary replica is not connected to the primary replica.</span></span> <span data-ttu-id="aee85-119">Der Verbindungsstatus lautet DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="aee85-119">The connected state is DISCONNECTED.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="aee85-120">Mögliche Lösung</span><span class="sxs-lookup"><span data-stu-id="aee85-120">Possible Solution</span></span>  
 <span data-ttu-id="aee85-121">Verwenden Sie den Verfügbarkeitsreplikat-Richtlinienstatus, um nach dem Verfügbarkeitsreplikat mit dem Status DISCONNECTED zu suchen, und beheben Sie dann das Problem des Verfügbarkeitsreplikats.</span><span class="sxs-lookup"><span data-stu-id="aee85-121">Use the availability replica policy state to find the availability replica that is DISCONNECTED, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aee85-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aee85-122">See Also</span></span>  
 <span data-ttu-id="aee85-123">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="aee85-123">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="aee85-124">Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="aee85-124">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
