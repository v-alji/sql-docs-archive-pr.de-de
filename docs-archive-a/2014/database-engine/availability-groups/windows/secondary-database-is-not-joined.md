---
title: Sekundäre Datenbank ist nicht verknüpft | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.drp2joined.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 10817e5e-75fa-42dd-baa2-359bea3ad051
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 81275e85fd865924778f6d6f985e170a5bda9f9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724210"
---
# <a name="secondary-database-is-not-joined"></a><span data-ttu-id="26a82-102">Sekundäre Datenbank ist nicht verknüpft</span><span class="sxs-lookup"><span data-stu-id="26a82-102">Secondary database is not joined</span></span>
    
## <a name="introduction"></a><span data-ttu-id="26a82-103">Einführung</span><span class="sxs-lookup"><span data-stu-id="26a82-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="26a82-104">**Richtlinienname**</span><span class="sxs-lookup"><span data-stu-id="26a82-104">**Policy Name**</span></span>|<span data-ttu-id="26a82-105">Joinzustand der Verfügbarkeitsdatenbank</span><span class="sxs-lookup"><span data-stu-id="26a82-105">Availability Database Join State</span></span>|  
|<span data-ttu-id="26a82-106">**Problem**</span><span class="sxs-lookup"><span data-stu-id="26a82-106">**Issue**</span></span>|<span data-ttu-id="26a82-107">Die sekundäre Datenbank ist nicht verknüpft.</span><span class="sxs-lookup"><span data-stu-id="26a82-107">Secondary database is not joined.</span></span>|  
|<span data-ttu-id="26a82-108">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="26a82-108">**Category**</span></span>|<span data-ttu-id="26a82-109">**Warning**</span><span class="sxs-lookup"><span data-stu-id="26a82-109">**Warning**</span></span>|  
|<span data-ttu-id="26a82-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="26a82-110">**Facet**</span></span>|<span data-ttu-id="26a82-111">Verfügbarkeitsdatenbank</span><span class="sxs-lookup"><span data-stu-id="26a82-111">Availability database</span></span>|  
  
## <a name="description"></a><span data-ttu-id="26a82-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="26a82-112">Description</span></span>  
 <span data-ttu-id="26a82-113">Diese Richtlinie überprüft den Joinstatus der sekundären Datenbank (auch bekannt als "sekundäres Datenbankreplikat").</span><span class="sxs-lookup"><span data-stu-id="26a82-113">This policy checks the join state of the secondary database (also known as a "secondary database replica").</span></span> <span data-ttu-id="26a82-114">Die Richtlinie befindet sich in einem fehlerhaften Zustand, wenn das Datenbankreplikat nicht verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="26a82-114">The policy is in an unhealthy state when the dataset replica is not joined.</span></span> <span data-ttu-id="26a82-115">Die Richtlinie befindet sich andernfalls in einem ordnungsgemäßen Zustand.</span><span class="sxs-lookup"><span data-stu-id="26a82-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="26a82-116">Für diese Version von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]finden Sie Informationen zu möglichen Ursachen und Lösungen im TechNet Wiki unter [Sekundäre Datenbank ist nicht verknüpft](https://go.microsoft.com/fwlink/p/?LinkId=220862) .</span><span class="sxs-lookup"><span data-stu-id="26a82-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Secondary database is not joined](https://go.microsoft.com/fwlink/p/?LinkId=220862) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="26a82-117">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="26a82-117">Possible Causes</span></span>  
 <span data-ttu-id="26a82-118">Diese sekundäre Datenbank ist nicht mit der Verfügbarkeitsgruppe verknüpft.</span><span class="sxs-lookup"><span data-stu-id="26a82-118">This secondary database is not joined to the availability group.</span></span> <span data-ttu-id="26a82-119">Die Konfiguration dieser sekundären Datenbank ist unvollständig.</span><span class="sxs-lookup"><span data-stu-id="26a82-119">The configuration of this secondary database is incomplete.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="26a82-120">Mögliche Lösung</span><span class="sxs-lookup"><span data-stu-id="26a82-120">Possible Solution</span></span>  
 <span data-ttu-id="26a82-121">Verknüpfen Sie das sekundäre Replikat mit der Verfügbarkeitsgruppe mithilfe von Transact-SQL, PowerShell oder SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="26a82-121">Use Transact-SQL, PowerShell, or SQL Server Management Studio to join the secondary replica to the availability group.</span></span> <span data-ttu-id="26a82-122">Weitere Informationen zum Verknüpfen sekundärer Replikate mit Verfügbarkeitsgruppen finden Sie unter [Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span><span class="sxs-lookup"><span data-stu-id="26a82-122">For more information about joining secondary replicas to availability groups, see [Joining a Secondary Replica to an Availability Group (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26a82-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26a82-123">See Also</span></span>  
 <span data-ttu-id="26a82-124">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="26a82-124">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="26a82-125">Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="26a82-125">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
