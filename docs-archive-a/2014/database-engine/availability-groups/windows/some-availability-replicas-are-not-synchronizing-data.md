---
title: Einige Verfügbarkeitsreplikate synchronisieren keine Daten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp4synchronizing.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 3db6a569-e942-4321-a0dd-c4ab002087c8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 762b7da1f7b8a07257c2a900307eb1bb10408653
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618283"
---
# <a name="some-availability-replicas-are-not-synchronizing-data"></a><span data-ttu-id="e237c-102">Einige Verfügbarkeitsreplikate synchronisieren keine Daten</span><span class="sxs-lookup"><span data-stu-id="e237c-102">Some availability replicas are not synchronizing data</span></span>
    
## <a name="introduction"></a><span data-ttu-id="e237c-103">Einführung</span><span class="sxs-lookup"><span data-stu-id="e237c-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e237c-104">**Richtlinienname**</span><span class="sxs-lookup"><span data-stu-id="e237c-104">**Policy Name**</span></span>|<span data-ttu-id="e237c-105">Datensynchronisierungsstatus der Verfügbarkeitsreplikate</span><span class="sxs-lookup"><span data-stu-id="e237c-105">Availability Replicas Data Synchronization State</span></span>|  
|<span data-ttu-id="e237c-106">**Problem**</span><span class="sxs-lookup"><span data-stu-id="e237c-106">**Issue**</span></span>|<span data-ttu-id="e237c-107">Einige Verfügbarkeitsreplikate synchronisieren keine Daten.</span><span class="sxs-lookup"><span data-stu-id="e237c-107">Some availability replicas are not synchronizing data.</span></span>|  
|<span data-ttu-id="e237c-108">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="e237c-108">**Category**</span></span>|<span data-ttu-id="e237c-109">**Warning**</span><span class="sxs-lookup"><span data-stu-id="e237c-109">**Warning**</span></span>|  
|<span data-ttu-id="e237c-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="e237c-110">**Facet**</span></span>|<span data-ttu-id="e237c-111">Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="e237c-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e237c-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e237c-112">Description</span></span>  
 <span data-ttu-id="e237c-113">Diese Richtlinie führt ein Rollup des Datensynchronisierungsstatus aller Verfügbarkeitsreplikate in der Verfügbarkeitsgruppe aus und überprüft, ob die Synchronisierung der Verfügbarkeitsreplikate ggf. nicht betriebsbereit ist.</span><span class="sxs-lookup"><span data-stu-id="e237c-113">This policy rolls up the data synchronization state of all availability replicas in the availability group and checks if the synchronization of any availability replica is not operational.</span></span> <span data-ttu-id="e237c-114">Die Richtlinie befindet sich in einem fehlerhaften Zustand, wenn einer der Datensynchronisierungsstatus des Verfügbarkeitsreplikats NOT SYNCHRONIZING lautet.</span><span class="sxs-lookup"><span data-stu-id="e237c-114">The policy is in an unhealthy state if any of the data synchronization states of the availability replica is NOT SYNCRONIZING.</span></span>  
  
 <span data-ttu-id="e237c-115">Diese Richtlinie befindet sich in einem ordnungsgemäßen Zustand, wenn keiner der Datensynchronisierungsstatus des Verfügbarkeitsreplikats NOT SYNCHRONIZING lautet.</span><span class="sxs-lookup"><span data-stu-id="e237c-115">This policy is in a healthy state if none of the data synchronization states of the availability replica is NOT SYNCHRONIZING.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e237c-116">Für diese Version von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]finden Sie Informationen zu möglichen Ursachen und Lösungen im TechNet Wiki unter [Einige Verfügbarkeitsreplikate synchronisieren keine Daten](https://go.microsoft.com/fwlink/p/?LinkId=220852) .</span><span class="sxs-lookup"><span data-stu-id="e237c-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some availability replicas are not synchronizing data](https://go.microsoft.com/fwlink/p/?LinkId=220852) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="e237c-117">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="e237c-117">Possible Causes</span></span>  
 <span data-ttu-id="e237c-118">In dieser Verfügbarkeitsgruppe weist mindestens ein sekundäres Replikat den Synchronisierungsstatus NOT SYNCHRONIZING auf und empfängt keine Daten vom primären Replikat.</span><span class="sxs-lookup"><span data-stu-id="e237c-118">In this availability group, at least one secondary replica has a NOT SYNCHRONIZING synchronization state and is not receiving data from the primary replica.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="e237c-119">Mögliche Lösung</span><span class="sxs-lookup"><span data-stu-id="e237c-119">Possible Solution</span></span>  
 <span data-ttu-id="e237c-120">Verwenden Sie den Verfügbarkeitsreplikat-Richtlinienstatus, um das Verfügbarkeitsreplikat mit dem Status NOT SYNCHRONIZING zu ermitteln, und beheben Sie dann das Problem des Verfügbarkeitsreplikats.</span><span class="sxs-lookup"><span data-stu-id="e237c-120">Use the availability replica policy state to find the availability replica with a NOT SYNCHROINIZING state, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e237c-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e237c-121">See Also</span></span>  
 <span data-ttu-id="e237c-122">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e237c-122">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="e237c-123">Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e237c-123">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
