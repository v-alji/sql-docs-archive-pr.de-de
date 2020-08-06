---
title: Erzwingen des Diensts in einer Datenbank-Spiegelungssitzung (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- forced service [SQL Server]
- database mirroring [SQL Server], forcing service
ms.assetid: 8b6ffe77-35f3-4e2a-a658-8a38a8e1c794
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b909f3602a78f3244ab3cf4479b8745956a7bd62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726249"
---
# <a name="force-service-in-a-database-mirroring-session-transact-sql"></a><span data-ttu-id="367d3-102">Erzwingen des Diensts in einer Datenbank-Spiegelungssitzung (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="367d3-102">Force Service in a Database Mirroring Session (Transact-SQL)</span></span>
  <span data-ttu-id="367d3-103">Wenn der Prinzipalserver im Modus für hohe Leistung und im Modus für hohe Sicherheit ohne automatisches Failover ausfällt, der Spiegelserver jedoch zur Verfügung steht, kann der Datenbankbesitzer die Datenbank verfügbar machen, indem er ein Failover des Diensts auf die Spiegeldatenbank (bei möglichem Datenverlust) erzwingt.</span><span class="sxs-lookup"><span data-stu-id="367d3-103">In high-performance mode and high-safety mode without automatic failover, if the principal server fails while the mirror server is available, the database owner can make the database available by forcing service to fail over (with possible data loss) to the mirror database.</span></span> <span data-ttu-id="367d3-104">Diese Option steht nur zur Verfügung, wenn alle der folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="367d3-104">This option is available only under all the following conditions:</span></span>  
  
-   <span data-ttu-id="367d3-105">Der Prinzipalserver ist ausgefallen.</span><span class="sxs-lookup"><span data-stu-id="367d3-105">The principal server is down.</span></span>  
  
-   <span data-ttu-id="367d3-106">WITNESS ist auf OFF festgelegt oder ist mit dem Spiegelserver verbunden.</span><span class="sxs-lookup"><span data-stu-id="367d3-106">WITNESS is set to OFF or is connected to the mirror server.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="367d3-107">Das Erzwingen des Diensts ist eine Methode, die ausschließlich der Wiederherstellung in einem Notfall dient.</span><span class="sxs-lookup"><span data-stu-id="367d3-107">Forced service is strictly a disaster recovery method.</span></span> <span data-ttu-id="367d3-108">Das Erzwingen des Diensts kann Datenverluste zur Folge haben.</span><span class="sxs-lookup"><span data-stu-id="367d3-108">Forcing service may involve some data loss.</span></span> <span data-ttu-id="367d3-109">Sie sollten den Dienst daher nur erzwingen, wenn Sie bereit sind, Datenverluste in Kauf zu nehmen, um den Dienst für die Datenbank unverzüglich wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="367d3-109">Therefore, force service only if you are willing to risk losing some data in order to restore service to the database immediately.</span></span> <span data-ttu-id="367d3-110">Wenn es beim Erzwingen des Diensts zum Verlust wichtiger Daten kommen kann, wird empfohlen, die Spiegelung zu beenden und die Datenbanken manuell neu zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="367d3-110">If forcing service risks losing significant data, we recommend that you stop mirroring and manually resynchronize the databases.</span></span> <span data-ttu-id="367d3-111">Weitere Informationen zu den Risiken beim Erzwingen des Diensts finden Sie unter [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span><span class="sxs-lookup"><span data-stu-id="367d3-111">For more information about the risks of forcing service, see [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span></span>  
  
 <span data-ttu-id="367d3-112">Durch das Erzwingen des Diensts wird die Sitzung angehalten und ein neuer Wiederherstellungszweig gestartet.</span><span class="sxs-lookup"><span data-stu-id="367d3-112">Forcing service suspends the session and starts a new recovery fork.</span></span> <span data-ttu-id="367d3-113">Die Auswirkungen aus dem Erzwingen des Diensts sind vergleichbar mit dem Entfernen der Spiegelung und dem Wiederherstellen der vorherigen Prinzipaldatenbank.</span><span class="sxs-lookup"><span data-stu-id="367d3-113">The effect of forcing service is similar to removing mirroring and recovering the former principal database.</span></span> <span data-ttu-id="367d3-114">Durch das Erzwingen des Diensts wird jedoch das erneute Synchronisieren der Datenbanken (bei möglichem Datenverlust) vereinfacht, wenn die Spiegelung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="367d3-114">However, forcing service facilitates resynchronizing the databases (with possible data loss) when mirroring resumes.</span></span>  
  
### <a name="to-force-service-in-a-database-mirroring-session"></a><span data-ttu-id="367d3-115">So erzwingen Sie den Dienst in einer Datenbank-Spiegelungssitzung</span><span class="sxs-lookup"><span data-stu-id="367d3-115">To force service in a database mirroring session</span></span>  
  
1.  <span data-ttu-id="367d3-116">Stellen Sie eine Verbindung zum Spiegelserver her.</span><span class="sxs-lookup"><span data-stu-id="367d3-116">Connect to the mirror server.</span></span>  
  
2.  <span data-ttu-id="367d3-117">Führen Sie die folgende Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="367d3-117">Issue the following statement:</span></span>  
  
     <span data-ttu-id="367d3-118">ALTER DATABASE *<database_name>* SET PARTNER FORCE_SERVICE_ALLOW_DATA_LOSS</span><span class="sxs-lookup"><span data-stu-id="367d3-118">ALTER DATABASE *<database_name>* SET PARTNER FORCE_SERVICE_ALLOW_DATA_LOSS</span></span>  
  
     <span data-ttu-id="367d3-119">Dabei ist *<database_name>* die gespiegelte Datenbank.</span><span class="sxs-lookup"><span data-stu-id="367d3-119">where *<database_name>* is the mirrored database.</span></span>  
  
     <span data-ttu-id="367d3-120">Der Spiegelserver wird unverzüglich zum Prinzipalserver, und die Spiegelung wird unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="367d3-120">The mirror server immediately transitions to principal server, and mirroring is suspended.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="367d3-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="367d3-121">See Also</span></span>  
 <span data-ttu-id="367d3-122">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="367d3-122">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="367d3-123">Database Mirroring Operating Modes</span><span class="sxs-lookup"><span data-stu-id="367d3-123">Database Mirroring Operating Modes</span></span>](database-mirroring-operating-modes.md)  
  
  
