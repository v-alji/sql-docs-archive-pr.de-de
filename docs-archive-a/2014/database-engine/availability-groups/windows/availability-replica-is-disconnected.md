---
title: Verfügbarkeitsreplikat wird getrennt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp2connected.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 1a2162d3-54fb-4356-b349-effbdc15a5a4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1db92b8e73b6daaee7edf5042b1d73cfeb471d1d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701919"
---
# <a name="availability-replica-is-disconnected"></a><span data-ttu-id="38205-102">Verfügbarkeitsreplikat wird getrennt</span><span class="sxs-lookup"><span data-stu-id="38205-102">Availability replica is disconnected</span></span>
    
## <a name="introduction"></a><span data-ttu-id="38205-103">Einführung</span><span class="sxs-lookup"><span data-stu-id="38205-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="38205-104">**Richtlinienname**</span><span class="sxs-lookup"><span data-stu-id="38205-104">**Policy Name**</span></span>|<span data-ttu-id="38205-105">Verfügbarkeitsreplikat-Verbindungsstatus</span><span class="sxs-lookup"><span data-stu-id="38205-105">Availability Replica Connection State</span></span>|  
|<span data-ttu-id="38205-106">**Problem**</span><span class="sxs-lookup"><span data-stu-id="38205-106">**Issue**</span></span>|<span data-ttu-id="38205-107">Das Verfügbarkeitsreplikat wird getrennt.</span><span class="sxs-lookup"><span data-stu-id="38205-107">Availability replica is disconnected.</span></span>|  
|<span data-ttu-id="38205-108">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="38205-108">**Category**</span></span>|<span data-ttu-id="38205-109">**Critical** (Kritisch)</span><span class="sxs-lookup"><span data-stu-id="38205-109">**Critical**</span></span>|  
|<span data-ttu-id="38205-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="38205-110">**Facet**</span></span>|<span data-ttu-id="38205-111">Verfügbarkeitsreplikat</span><span class="sxs-lookup"><span data-stu-id="38205-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="38205-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="38205-112">Description</span></span>  
 <span data-ttu-id="38205-113">Diese Richtlinie überprüft den Verbindungsstatus zwischen Verfügbarkeitsreplikaten.</span><span class="sxs-lookup"><span data-stu-id="38205-113">This policy checks the connection state between availability replicas.</span></span> <span data-ttu-id="38205-114">Die Richtlinie befindet sich in einem fehlerhaften Zustand, wenn der Verbindungsstatus des Verfügbarkeitsreplikats DISCONNECTED lautet.</span><span class="sxs-lookup"><span data-stu-id="38205-114">The policy is in an unhealthy state when the connection state of the availability replica is DISCONNECTED.</span></span> <span data-ttu-id="38205-115">Die Richtlinie befindet sich andernfalls in einem ordnungsgemäßen Zustand.</span><span class="sxs-lookup"><span data-stu-id="38205-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38205-116"> Für diese Version von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]finden Sie Informationen zu möglichen Ursachen und Lösungen im TechNet Wiki unter [Verfügbarkeitsreplikat wird getrennt](https://go.microsoft.com/fwlink/p/?LinkId=220857) .</span><span class="sxs-lookup"><span data-stu-id="38205-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability replica is disconnected](https://go.microsoft.com/fwlink/p/?LinkId=220857) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="38205-117">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="38205-117">Possible Causes</span></span>  
 <span data-ttu-id="38205-118">Das sekundäre Replikat ist nicht mit dem primären Replikat verbunden.</span><span class="sxs-lookup"><span data-stu-id="38205-118">The secondary replica is not connected to the primary replica.</span></span> <span data-ttu-id="38205-119">Der Verbindungsstatus lautet DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="38205-119">The connected state is DISCONNECTED.</span></span> <span data-ttu-id="38205-120">Dieses Problem kann folgende Ursachen haben:</span><span class="sxs-lookup"><span data-stu-id="38205-120">This issue can be caused by the following:</span></span>  
  
-   <span data-ttu-id="38205-121">Für den Verbindungsport besteht ein Konflikt mit einer anderen Anwendung.</span><span class="sxs-lookup"><span data-stu-id="38205-121">The connection port might be in conflict with another application.</span></span>  
  
-   <span data-ttu-id="38205-122">Der Verschlüsselungstyp oder der Algorithmus stimmt nicht überein.</span><span class="sxs-lookup"><span data-stu-id="38205-122">The encryption type or algorithm is mismatched.</span></span>  
  
-   <span data-ttu-id="38205-123">Der Verbindungsendpunkt wurde gelöscht oder nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="38205-123">The connection endpoint has been deleted or has not been started.</span></span>  
  
-   <span data-ttu-id="38205-124">Die Verbindung des Transports wurde getrennt.</span><span class="sxs-lookup"><span data-stu-id="38205-124">The transport is disconnected.</span></span>  
  
## <a name="possible-solutions"></a><span data-ttu-id="38205-125">Mögliche Lösungen</span><span class="sxs-lookup"><span data-stu-id="38205-125">Possible Solutions</span></span>  
 <span data-ttu-id="38205-126">Für dieses Problem gibt es die folgenden möglichen Lösungen:</span><span class="sxs-lookup"><span data-stu-id="38205-126">Following are possible solutions for this issue:</span></span>  
  
-   <span data-ttu-id="38205-127">Überprüfen Sie die Datenbankspiegelungs-Endpunktkonfiguration für die Instanzen des primären und sekundären Replikats, und aktualisieren Sie die nicht übereinstimmende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="38205-127">Check the database mirroring endpoint configuration for the instances of the primary and secondary replica and update the mismatched configuration.</span></span>  
  
-   <span data-ttu-id="38205-128">Überprüfen Sie, ob für den Port ein Konflikt besteht, und ändern Sie ggf. die Portnummer.</span><span class="sxs-lookup"><span data-stu-id="38205-128">Check if the port is conflicting, and if so, change the port number.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38205-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="38205-129">See Also</span></span>  
 <span data-ttu-id="38205-130">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="38205-130">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="38205-131">Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="38205-131">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
