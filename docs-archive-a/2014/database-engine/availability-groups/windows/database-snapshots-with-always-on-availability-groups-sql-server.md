---
title: Daten Bank Momentaufnahmen mit AlwaysOn-Verfügbarkeitsgruppen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 7432da1c-ce2f-4cd9-af41-54c97744166b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1e4307653b5b8150d71019a373ee073d15123f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721758"
---
# <a name="database-snapshots-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="85b99-102">Datenbankmomentaufnahmen bei AlwaysOn-Verfügbarkeitsgruppen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="85b99-102">Database Snapshots with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="85b99-103">Sie können auf einer primären oder sekundären Datenbank in einer Verfügbarkeitsgruppe eine Datenbankmomentaufnahme erstellen.</span><span class="sxs-lookup"><span data-stu-id="85b99-103">You can create a database snapshot on an primary or secondary database in an availability group.</span></span> <span data-ttu-id="85b99-104">Die Replikatrolle muss entweder PRIMARY oder SECONDARY sein und darf nicht den Status RESOLVING aufweisen.</span><span class="sxs-lookup"><span data-stu-id="85b99-104">The replica role must be either PRIMARY or SECONDARY, not in the RESOLVING state.</span></span>  
  
 <span data-ttu-id="85b99-105">Der Datenbanksynchronisierungsstatus sollte SYNCHRONIZING oder SYNCHRONIZED sein, wenn Sie eine Datenbankmomentaufnahme erstellen.</span><span class="sxs-lookup"><span data-stu-id="85b99-105">We recommend that the database synchronization state be SYNCHRONIZING or SYNCHRONIZED when you create a database snapshot.</span></span> <span data-ttu-id="85b99-106">Datenbankmomentaufnahmen können jedoch auch erstellt werden, wenn der Datenbanksynchronisierungsstatus NOT SYNCHRONIZING lautet.</span><span class="sxs-lookup"><span data-stu-id="85b99-106">However, database snapshots can be created when the database synchronization state is NOT SYNCHRONIZING.</span></span>  
  
 <span data-ttu-id="85b99-107">Eine Datenbankmomentaufnahme auf einem sekundären Replikat sollte weiterhin funktionieren, wenn das Replikat mit DISCONNECTED vom primären Replikat getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="85b99-107">A database snapshot on a secondary replica should continue to work if the replica is DISCONNECTED from the primary replica.</span></span>  
  
 <span data-ttu-id="85b99-108">Einige [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] -Bedingungen bewirken, dass sowohl die Quelldatenbank als auch deren Datenbankmomentaufnahmen neu gestartet werden, wobei die Verbindung für Benutzer vorübergehend getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="85b99-108">Some [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] conditions cause both the source database and its database snapshots to be restarted, temporarily disconnecting users.</span></span> <span data-ttu-id="85b99-109">Nachfolgend sind diese Bedingungen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="85b99-109">These conditions are as follows:</span></span>  
  
-   <span data-ttu-id="85b99-110">Das primäre Replikat ändert Rollen, entweder, weil das aktuelle primäre Replikat offline und dann auf der gleichen Serverinstanz wieder online geschaltet wird, oder weil die Verfügbarkeitsgruppe ein Failover ausführt.</span><span class="sxs-lookup"><span data-stu-id="85b99-110">The primary replica changes roles, whether because the current primary replica goes off line and comes back online on the same server instance or because the availability group fails over.</span></span>  
  
-   <span data-ttu-id="85b99-111">Die Datenbank wechselt zur sekundäre Rolle.</span><span class="sxs-lookup"><span data-stu-id="85b99-111">The database enters the secondary role.</span></span>  
  
 <span data-ttu-id="85b99-112">Wenn das Verfügbarkeitsreplikat, das Datenbankmomentaufnahmen hostet, ein Failover ausgeführt hat, bleiben die Datenbankmomentaufnahmen auf der Serverinstanz, auf der sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="85b99-112">If the availability replica that hosts database snapshots is failed over, the database snapshots remain on the server instance where they were created.</span></span> <span data-ttu-id="85b99-113">Benutzer können die Momentaufnahmen nach dem Failover weiter verwenden. Wenn die Leistung in Ihrer Umgebung wichtig ist, empfiehlt es sich, dass Sie Datenbankmomentaufnahmen nur auf sekundären Datenbanken erstellen, die von einem sekundären Replikat gehostet werden, das für manuellen Failovermodus konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="85b99-113">Users can continue to use the snapshots after the failover.If performance is a concern in your environment, we recommend that you create database snapshots only on secondary databases that are hosted by a secondary replica that is configured for manual failover mode.</span></span>  <span data-ttu-id="85b99-114">Sollte es je zu einem manuellen Failover der Verfügbarkeitsgruppe zu diesem sekundären Replikat kommen, können Sie auf einem anderen sekundären Replikat einen neuen Satz von Datenbankmomentaufnahmen erstellen, Clients an die neuen Datenbankmomentaufnahmen umleiten und alle Datenbankmomentaufnahmen aus den jetzt primären Datenbanken löschen.</span><span class="sxs-lookup"><span data-stu-id="85b99-114">If you ever manually fail over the availability group to this secondary replica, you can create a new set of database snapshots on another secondary replica, redirect clients to the new database snapshots, and drop all of the database snapshots from the now primary databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85b99-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85b99-115">See Also</span></span>  
 <span data-ttu-id="85b99-116">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="85b99-116">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="85b99-117">Datenbank-Momentaufnahmen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85b99-117">Database Snapshots &#40;SQL Server&#41;</span></span>](../../../relational-databases/databases/database-snapshots-sql-server.md)  
  
  
