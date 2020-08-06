---
title: Entfernen der Datenbankspiegelung (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], removing
- stopping database mirroring [SQL Server]
- removing database mirroring [SQL Server]
ms.assetid: 40c72091-8f03-4037-8b55-5e95309fe145
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8044fcef9d9f9bfc1fb41c1faa17b76c827da5a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701793"
---
# <a name="removing-database-mirroring-sql-server"></a><span data-ttu-id="2647e-102">Entfernen der Datenbankspiegelung (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2647e-102">Removing Database Mirroring (SQL Server)</span></span>
  <span data-ttu-id="2647e-103">Der Datenbankbesitzer kann eine Datenbankspiegelungssitzung jederzeit bei jedem Partner manuell beenden.</span><span class="sxs-lookup"><span data-stu-id="2647e-103">The database owner can manually stop a database mirroring session at any time, at either partner.</span></span>  
  
## <a name="impact-of-removing-mirroring"></a><span data-ttu-id="2647e-104">Auswirkungen aus dem Entfernen der Spiegelung</span><span class="sxs-lookup"><span data-stu-id="2647e-104">Impact of Removing Mirroring</span></span>  
 <span data-ttu-id="2647e-105">Durch das Entfernen der Spiegelung tritt folgende Situation ein:</span><span class="sxs-lookup"><span data-stu-id="2647e-105">When mirroring is removed, the following occurs:</span></span>  
  
-   <span data-ttu-id="2647e-106">Die Beziehung zwischen den Partnern sowie zwischen den einzelnen Partnern und dem Zeugen werden, sofern vorhanden, dauerhaft abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="2647e-106">The relationship between the partners and between each partner and the witness breaks permanently, if any relationship exists.</span></span>  
  
     <span data-ttu-id="2647e-107">Falls die Partner miteinander kommunizierten, als die Sitzung beendet wurde, wird die Beziehung unmittelbar auf beiden Computern abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="2647e-107">If the partners are communicating with each other when the session is stopped, their relationship is immediately broken on both computers.</span></span> <span data-ttu-id="2647e-108">Wenn die Partner nicht miteinander kommunizierten (die Datenbank besaß zum Beendigungszeitpunkt den Status DISCONNECTED), wird die Beziehung unmittelbar bei dem Partner abgebrochen, von dem aus die Spiegelung beendet wurde. Sobald der andere Partner versucht, die Verbindung wiederherzustellen, wird für diesen Partner ersichtlich, dass die Datenbankspiegelungssitzung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="2647e-108">If the partners are not communicating (the database is in a DISCONNECTED state at the time of stopping), the relationship is broken immediately on the partner from which mirroring is stopped; when the other partner tries to reconnect, it discovers that the database mirroring session has ended.</span></span>  
  
-   <span data-ttu-id="2647e-109">Die Informationen zur Spiegelungssitzung werden gelöscht, im Gegensatz zum Anhalten einer Sitzung.</span><span class="sxs-lookup"><span data-stu-id="2647e-109">Information about the mirroring session is dropped, unlike when pausing a session.</span></span> <span data-ttu-id="2647e-110">Die Spiegelung wird sowohl aus der Prinzipaldatenbank als auch aus der Spiegelungsdatenbank entfernt.</span><span class="sxs-lookup"><span data-stu-id="2647e-110">Mirroring is removed on both the principal database and the mirror database.</span></span> <span data-ttu-id="2647e-111">In **sys.databases** werden die**mirroring_state**-Spalte und alle anderen Spiegelungsspalten auf NULL festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2647e-111">In **sys.databases**, the **mirroring_state** column and all other mirroring columns are set to NULL.</span></span> <span data-ttu-id="2647e-112">Weitere Informationen finden Sie unter [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2647e-112">For more information, see [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span></span>  
  
-   <span data-ttu-id="2647e-113">Jede Partnerserverinstanz behält eine separate Kopie der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2647e-113">Each partner server instance is left with a separate copy of the database.</span></span>  
  
-   <span data-ttu-id="2647e-114">Die Spiegeldatenbank verbleibt im Status RESTORING (siehe Spalte für den **Status** in **sys.databases**), weil die Spiegeldatenbank mit RESTORE WITH NORECOVERY erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="2647e-114">The mirror database is left in the RESTORING state (see the **state** column of **sys.databases**), because the mirror database was created by using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="2647e-115">Zu diesem Zeitpunkt können Sie die bisherige Spiegelungsdatenbank löschen oder auch mit WITH RECOVERY wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="2647e-115">At this point, you can drop the former mirror database or restore it using WITH RECOVERY.</span></span> <span data-ttu-id="2647e-116">Wenn Sie die Datenbank wiederherstellen, weicht sie von der früheren Prinzipaldatenbank ab, weil mit der Wiederherstellung eine neue Wiederherstellungsverzweigung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="2647e-116">When you recover the database, it will have diverged from the former principal database because the recovery starts a new recovery fork.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2647e-117">Um die Spiegelung nach dem Anhalten einer Sitzung fortzusetzen, müssen Sie eine neue Datenbankspiegelungssitzung einrichten.</span><span class="sxs-lookup"><span data-stu-id="2647e-117">To continue mirroring after stopping a session, you must establish a new database mirroring session.</span></span> <span data-ttu-id="2647e-118">Wenn Sie nach dem Beenden der Spiegelung eine Protokollsicherung erstellt haben, müssen Sie diese Sicherung auf die Spiegelungsdatenbank anwenden, bevor Sie die Spiegelung erneut starten.</span><span class="sxs-lookup"><span data-stu-id="2647e-118">If you create a log backup after stopping mirroring, you must apply it to the mirror database before restarting mirroring.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="2647e-119">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="2647e-119">Related Tasks</span></span>  
 <span data-ttu-id="2647e-120">**So entfernen Sie die Datenbankspiegelung**</span><span class="sxs-lookup"><span data-stu-id="2647e-120">**To remove database mirroring**</span></span>  
  
-   [<span data-ttu-id="2647e-121">Entfernen der Datenbankspiegelung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2647e-121">Remove Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
 <span data-ttu-id="2647e-122">**So starten Sie die Datenbankspiegelung**</span><span class="sxs-lookup"><span data-stu-id="2647e-122">**To start database mirroring**</span></span>  
  
-   [<span data-ttu-id="2647e-123">Einrichten einer Datenbank-Spiegelungssitzung mithilfe der Windows-Authentifizierung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2647e-123">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="2647e-124">Einrichten einer Datenbank-Spiegelungssitzung mithilfe der Windows-Authentifizierung &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2647e-124">Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](database-mirroring-establish-session-windows-authentication.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="2647e-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2647e-125">See Also</span></span>  
 <span data-ttu-id="2647e-126">[ALTER DATABASE-Datenbankspiegelung &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="2647e-126">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="2647e-127">[Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2647e-127">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="2647e-128">[Anhalten und Fortsetzen der Datenbankspiegelung &#40;SQL Server&#41;](pausing-and-resuming-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2647e-128">[Pausing and Resuming Database Mirroring &#40;SQL Server&#41;](pausing-and-resuming-database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="2647e-129">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2647e-129">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
