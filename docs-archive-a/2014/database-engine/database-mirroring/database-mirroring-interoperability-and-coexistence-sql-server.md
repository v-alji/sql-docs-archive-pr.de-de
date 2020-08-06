---
title: 'Datenbankspiegelung: Interoperabilität und Koexistenz (SQL Server) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- high availability [SQL Server], interoperability and coexistence
- Database Engine [SQL Server], high availability
ms.assetid: 89fef397-e0cf-4e08-b598-25b8d4170523
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 057392842974c3342fc57d0ec113f8b1bb58b9dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616688"
---
# <a name="database-mirroring-interoperability-and-coexistence-sql-server"></a><span data-ttu-id="e6c5a-102">Datenbankspiegelung: Interoperabilität und Koexistenz (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e6c5a-102">Database Mirroring: Interoperability and Coexistence (SQL Server)</span></span>
  <span data-ttu-id="e6c5a-103">Die Datenbankspiegelung kann mit den folgenden Funktionen oder Komponenten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="e6c5a-103">Database mirroring can be used with the following features or components of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   [<span data-ttu-id="e6c5a-104">AlwaysOn-Failoverclusterinstanzen (SQL Server-Failoverclustering)</span><span class="sxs-lookup"><span data-stu-id="e6c5a-104">AlwaysOn Failover Cluster Instances (SQL Server Failover Clustering)</span></span>](database-mirroring-and-sql-server-failover-cluster-instances.md)  
  
-   [<span data-ttu-id="e6c5a-105">Change Data Capture (und Änderungsnachverfolgung)</span><span class="sxs-lookup"><span data-stu-id="e6c5a-105">Change data capture (and change tracking)</span></span>](../../relational-databases/track-changes/change-data-capture-and-other-sql-server-features.md)  
  
-   [<span data-ttu-id="e6c5a-106">Datenbankmomentaufnahmen</span><span class="sxs-lookup"><span data-stu-id="e6c5a-106">Database snapshots</span></span>](../../relational-databases/databases/database-snapshots-sql-server.md)  
  
-   [<span data-ttu-id="e6c5a-107">Volltextkataloge</span><span class="sxs-lookup"><span data-stu-id="e6c5a-107">Full-text catalogs</span></span>](database-mirroring-and-full-text-catalogs-sql-server.md)  
  
-   [<span data-ttu-id="e6c5a-108">Protokollversand</span><span class="sxs-lookup"><span data-stu-id="e6c5a-108">Log shipping</span></span>](database-mirroring-and-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="e6c5a-109">Replikation</span><span class="sxs-lookup"><span data-stu-id="e6c5a-109">Replication</span></span>](database-mirroring-and-replication-sql-server.md)  
  
 <span data-ttu-id="e6c5a-110">Die Datenbankspiegelung funktioniert nicht in Verbindung mit folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="e6c5a-110">Database mirroring does not interoperate with the following:</span></span>  
  
-   <span data-ttu-id="e6c5a-111">Datenbankübergreifende Transaktionen/verteilte Transaktionen</span><span class="sxs-lookup"><span data-stu-id="e6c5a-111">Cross-database transactions/distributed transactions</span></span>  
  
     <span data-ttu-id="e6c5a-112">Weitere Informationen dazu, warum solche Transaktionen nicht unterstützt werden, finden Sie unter [Datenbankübergreifende Transaktionen nicht unterstützt für Datenbankspiegelungs- oder AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](../availability-groups/windows/transactions-always-on-availability-and-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="e6c5a-112">For information about why such transactions are not supported, see [Cross-Database Transactions Not Supported For Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;](../availability-groups/windows/transactions-always-on-availability-and-database-mirroring.md).</span></span>  
  
-   [!INCLUDE[ssHADR](../../includes/sshadr-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e6c5a-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e6c5a-113">See Also</span></span>  
 [<span data-ttu-id="e6c5a-114">Datenbankspiegelung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e6c5a-114">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
