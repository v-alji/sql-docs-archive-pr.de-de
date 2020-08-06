---
title: MSSQLSERVER_41030 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41030 (Database Engine error)
ms.assetid: c85341ae-0fbf-42ae-9275-4cfe678238f0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b137b739d4c1641b88983708df62d2e52fd0eab5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721477"
---
# <a name="mssqlserver_41030"></a><span data-ttu-id="66299-102">MSSQLSERVER_41030</span><span class="sxs-lookup"><span data-stu-id="66299-102">MSSQLSERVER_41030</span></span>
    
## <a name="details"></a><span data-ttu-id="66299-103">Details</span><span class="sxs-lookup"><span data-stu-id="66299-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="66299-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="66299-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="66299-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="66299-105">Event ID</span></span>|<span data-ttu-id="66299-106">41030</span><span class="sxs-lookup"><span data-stu-id="66299-106">41030</span></span>|  
|<span data-ttu-id="66299-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="66299-107">Event Source</span></span>|<span data-ttu-id="66299-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="66299-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="66299-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="66299-109">Component</span></span>|<span data-ttu-id="66299-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="66299-110">SQLEngine</span></span>|  
|<span data-ttu-id="66299-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="66299-111">Symbolic Name</span></span>|<span data-ttu-id="66299-112">OPEN_CLUSTER_SUB_KEY</span><span class="sxs-lookup"><span data-stu-id="66299-112">OPEN_CLUSTER_SUB_KEY</span></span>|  
|<span data-ttu-id="66299-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="66299-113">Message Text</span></span>|<span data-ttu-id="66299-114">Fehler beim Öffnen des WSFC (Windows Server Failover Clustering)-Registrierungsunterschlüssels '%.\*ls' (Fehlercode %d).</span><span class="sxs-lookup"><span data-stu-id="66299-114">Failed to open the Windows Server Failover Clustering registry subkey '%.\*ls' (Error code %d).</span></span>  <span data-ttu-id="66299-115">Der übergeordnete Schlüssel ist der Clusterstammschlüssel.</span><span class="sxs-lookup"><span data-stu-id="66299-115">The parent key is the cluster root key.</span></span>  <span data-ttu-id="66299-116">Der WSFC-Dienst wird möglicherweise nicht ausgeführt, der Zugriff auf den Dienst ist möglicherweise im aktuellen Zustand nicht möglich, oder die angegebenen Argumente sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="66299-116">The WSFC service may not be running or may not be accessible in its current state, or the specified arguments are invalid.</span></span> <span data-ttu-id="66299-117">Wurde die entsprechende Verfügbarkeitsgruppe gelöscht, wird dieser Fehler erwartet.</span><span class="sxs-lookup"><span data-stu-id="66299-117">If the corresponding availability group has been dropped, this error is expected.</span></span> <span data-ttu-id="66299-118">Informationen zu diesem Fehlercode finden Sie in der Dokumentation für die Windows-Entwicklung im Abschnitt zu Systemfehlercodes.</span><span class="sxs-lookup"><span data-stu-id="66299-118">For information about this error code, see "System Error Codes" in the Windows Development documentation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="66299-119">Erklärung</span><span class="sxs-lookup"><span data-stu-id="66299-119">Explanation</span></span>  
 <span data-ttu-id="66299-120">Wenn ein WSFC-Cluster zerstört wird, werden alle auf [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] bezogenen Registrierungsschlüssel entfernt.</span><span class="sxs-lookup"><span data-stu-id="66299-120">If a WSFC cluster is destroyed, it removes all registry keys related to [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="66299-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="66299-121">User Action</span></span>  
 <span data-ttu-id="66299-122">Nach dem Neuerstellen eines WSFC-Clusters deaktivieren und aktivieren Sie dann AlwaysOn auf jedem Clusterknoten erneut, auf dem eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz für AlwaysOn aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="66299-122">After re-creating a WSFC cluster, disable and then re-enable AlwaysOn on every cluster node on which an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is enabled for AlwaysOn.</span></span> <span data-ttu-id="66299-123">Sie können für diese Aufgabe den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Konfigurations-Manager verwenden.</span><span class="sxs-lookup"><span data-stu-id="66299-123">You can use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager for this task.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66299-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="66299-124">See Also</span></span>  
 <span data-ttu-id="66299-125">[Aktivieren und deaktivieren Sie AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/enable-and-disable-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="66299-125">[Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/enable-and-disable-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="66299-126">Windows Server-Failoverclustering &#40;WSFC&#41; mit SQL Server</span><span class="sxs-lookup"><span data-stu-id="66299-126">Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server</span></span>](../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md)  
  
  
