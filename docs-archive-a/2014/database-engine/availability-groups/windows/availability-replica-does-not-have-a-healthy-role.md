---
title: Verfügbarkeitsreplikat hat keine fehlerfreie Rolle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp1rolehealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: ebb2c9f4-2097-4688-b4fb-8f0571047317
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f7be26945903a5e3b602ef4a99c269de6a58b04a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701930"
---
# <a name="availability-replica-does-not-have-a-healthy-role"></a><span data-ttu-id="aa52b-102">Verfügbarkeitsreplikat hat keine fehlerfreie Rolle</span><span class="sxs-lookup"><span data-stu-id="aa52b-102">Availability replica does not have a healthy role</span></span>
    
## <a name="introduction"></a><span data-ttu-id="aa52b-103">Einführung</span><span class="sxs-lookup"><span data-stu-id="aa52b-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aa52b-104">**Richtlinienname**</span><span class="sxs-lookup"><span data-stu-id="aa52b-104">**Policy Name**</span></span>|<span data-ttu-id="aa52b-105">Verfügbarkeitsreplikat-Rollenstatus</span><span class="sxs-lookup"><span data-stu-id="aa52b-105">Availability Replica Role State</span></span>|  
|<span data-ttu-id="aa52b-106">**Problem**</span><span class="sxs-lookup"><span data-stu-id="aa52b-106">**Issue**</span></span>|<span data-ttu-id="aa52b-107">Das Verfügbarkeitsreplikat hat keine fehlerfreie Rolle.</span><span class="sxs-lookup"><span data-stu-id="aa52b-107">Availability replica does not have a healthy role.</span></span>|  
|<span data-ttu-id="aa52b-108">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="aa52b-108">**Category**</span></span>|<span data-ttu-id="aa52b-109">**Critical** (Kritisch)</span><span class="sxs-lookup"><span data-stu-id="aa52b-109">**Critical**</span></span>|  
|<span data-ttu-id="aa52b-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="aa52b-110">**Facet**</span></span>|<span data-ttu-id="aa52b-111">Verfügbarkeitsreplikat</span><span class="sxs-lookup"><span data-stu-id="aa52b-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="aa52b-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="aa52b-112">Description</span></span>  
 <span data-ttu-id="aa52b-113">Diese Richtlinie überprüft den Status der Verfügbarkeitsreplikatrolle.</span><span class="sxs-lookup"><span data-stu-id="aa52b-113">This policy checks the state of the role of the availability replica.</span></span> <span data-ttu-id="aa52b-114">Die Richtlinie befindet sich in einem fehlerhaften Zustand, wenn die Rolle des Verfügbarkeitsreplikats weder primär noch sekundär ist.</span><span class="sxs-lookup"><span data-stu-id="aa52b-114">The policy is in an unhealthy state when the role of the availability replica is neither primary nor secondary.</span></span> <span data-ttu-id="aa52b-115">Die Richtlinie befindet sich andernfalls in einem ordnungsgemäßen Zustand.</span><span class="sxs-lookup"><span data-stu-id="aa52b-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa52b-116">Für diese Version von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]finden Sie Informationen zu möglichen Ursachen und Lösungen im TechNet Wiki unter [Verfügbarkeitsreplikat hat keine fehlerfreie Rolle](https://go.microsoft.com/fwlink/p/?LinkId=220856) .</span><span class="sxs-lookup"><span data-stu-id="aa52b-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability replica does not have a healthy role](https://go.microsoft.com/fwlink/p/?LinkId=220856) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="aa52b-117">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="aa52b-117">Possible Causes</span></span>  
 <span data-ttu-id="aa52b-118">Die Rolle dieses Verfügbarkeitsreplikats ist fehlerhaft.</span><span class="sxs-lookup"><span data-stu-id="aa52b-118">The role of this availability replica is unhealthy.</span></span> <span data-ttu-id="aa52b-119">Das Replikat hat nicht entweder die primäre oder sekundäre Rolle inne.</span><span class="sxs-lookup"><span data-stu-id="aa52b-119">The replica does not have either the primary or secondary role.</span></span>  
  
## <a name="possible-solution-information_still_to_come"></a><span data-ttu-id="aa52b-120">Mögliche Lösung: Informationen_werden_noch_bereitgestellt</span><span class="sxs-lookup"><span data-stu-id="aa52b-120">Possible Solution: Information_still_to_come</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa52b-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa52b-121">See Also</span></span>  
 <span data-ttu-id="aa52b-122">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="aa52b-122">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="aa52b-123">Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="aa52b-123">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
