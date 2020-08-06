---
title: Ausführen des manuellen Failovers einer Datenbank-Spiegelungssitzung (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover [SQL Server], database mirroring
- manual failover [SQL Server]
- database mirroring [SQL Server], failover
ms.assetid: 36218d61-b5f5-4194-905a-608e0e903db4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2c04ea4908ccbc4cfe4f6bb3606347dd444ef416
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609396"
---
# <a name="manually-fail-over-a-database-mirroring-session-transact-sql"></a><span data-ttu-id="4b51e-102">Ausführen des manuellen Failovers einer Datenbank-Spiegelungssitzung (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4b51e-102">Manually Fail Over a Database Mirroring Session (Transact-SQL)</span></span>
  <span data-ttu-id="4b51e-103">Wenn die gespiegelte Datenbank synchronisiert wird, also den Status SYNCHRONIZED aufweist, kann der Datenbankbesitzer ein manuelles Failover zu dem gespiegelten Server initiieren.</span><span class="sxs-lookup"><span data-stu-id="4b51e-103">When the mirrored database is synchronized (that is, when the database is in the SYNCHRONIZED state), the database owner can initiate manual failover to the mirror server.</span></span> <span data-ttu-id="4b51e-104">Das manuelle Failover kann nur vom Prinzipalserver aus initiiert werden.</span><span class="sxs-lookup"><span data-stu-id="4b51e-104">Manual failover can be initiated only from the principal server.</span></span>  
  
### <a name="to-manually-fail-over-a-database-mirroring-session"></a><span data-ttu-id="4b51e-105">So führen Sie das manuelle Failover einer Datenbank-Spiegelungssitzung durch</span><span class="sxs-lookup"><span data-stu-id="4b51e-105">To manually fail over a database mirroring session</span></span>  
  
1.  <span data-ttu-id="4b51e-106">Stellen Sie eine Verbindung mit dem Prinzipalserver her.</span><span class="sxs-lookup"><span data-stu-id="4b51e-106">Connect to the principal server.</span></span>  
  
2.  <span data-ttu-id="4b51e-107">Ändern Sie den Datenbankkontext auf die **master** -Datenbank um:</span><span class="sxs-lookup"><span data-stu-id="4b51e-107">Set the database context to the **master** database:</span></span>  
  
     `USE master;`  
  
3.  <span data-ttu-id="4b51e-108">Führen Sie auf dem Prinzipalserver die folgende Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="4b51e-108">Issue the following statement on the principal server:</span></span>  
  
     <span data-ttu-id="4b51e-109">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *database_name* SET PARTNER FAILOVER, wobei *database_name* die gespiegelte Datenbank darstellt.</span><span class="sxs-lookup"><span data-stu-id="4b51e-109">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *database_name* SET PARTNER FAILOVER, where *database_name* is the mirrored database.</span></span>  
  
     <span data-ttu-id="4b51e-110">Hierdurch wird die sofortige Übertragung des Spiegelservers in die Prinzipalrolle initiiert.</span><span class="sxs-lookup"><span data-stu-id="4b51e-110">This initiates an immediate transition of the mirror server to the principal role.</span></span>  
  
 <span data-ttu-id="4b51e-111">Auf dem ehemaligen Prinzipal wird die Verbindung der Clients mit der Datenbank getrennt, und das Rollback der umgehend ausgeführten Transaktionen wird vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="4b51e-111">On the former principal, clients are disconnected from the database and in-flight transactions are rolled back.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4b51e-112">Transaktionen, die mit dem [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator vorbereitet wurden, für die beim Auftreten eines Failovers jedoch noch kein Commit ausgeführt wurde, werden nach dem Failover der Datenbank als abgebrochen betrachtet.</span><span class="sxs-lookup"><span data-stu-id="4b51e-112">Transactions that have been prepared by using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator but are still not committed when a failover occurs are considered aborted after the database has failed over.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b51e-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4b51e-113">See Also</span></span>  
 <span data-ttu-id="4b51e-114">[ALTER DATABASE-Datenbankspiegelung &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="4b51e-114">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="4b51e-115">[Manuelles Failover für eine Datenbank-Spiegelungs Sitzung &#40;SQL Server Management Studio&#41;](manually-fail-over-a-database-mirroring-session-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="4b51e-115">[Manually Fail Over a Database Mirroring Session &#40;SQL Server Management Studio&#41;](manually-fail-over-a-database-mirroring-session-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="4b51e-116">Rollenwechsel während einer Datenbank-Spiegelungssitzung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4b51e-116">Role Switching During a Database Mirroring Session &#40;SQL Server&#41;</span></span>](role-switching-during-a-database-mirroring-session-sql-server.md)  
  
  
