---
title: MSSQLSERVER_926 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 926 (Database Engine error)
ms.assetid: 57e01668-883b-4be4-84a8-a111caaf0486
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ae6796c9f4869d45223ab1283a68fc2bfe78aa11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617040"
---
# <a name="mssqlserver_926"></a><span data-ttu-id="8b00e-102">MSSQLSERVER_926</span><span class="sxs-lookup"><span data-stu-id="8b00e-102">MSSQLSERVER_926</span></span>
    
## <a name="details"></a><span data-ttu-id="8b00e-103">Details</span><span class="sxs-lookup"><span data-stu-id="8b00e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8b00e-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="8b00e-104">Product Name</span></span>|<span data-ttu-id="8b00e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8b00e-105">SQL Server</span></span>|  
|<span data-ttu-id="8b00e-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="8b00e-106">Event ID</span></span>|<span data-ttu-id="8b00e-107">926</span><span class="sxs-lookup"><span data-stu-id="8b00e-107">926</span></span>|  
|<span data-ttu-id="8b00e-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="8b00e-108">Event Source</span></span>|<span data-ttu-id="8b00e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8b00e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8b00e-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="8b00e-110">Component</span></span>|<span data-ttu-id="8b00e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8b00e-111">SQLEngine</span></span>|  
|<span data-ttu-id="8b00e-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="8b00e-112">Symbolic Name</span></span>|<span data-ttu-id="8b00e-113">DB_SUSPECT</span><span class="sxs-lookup"><span data-stu-id="8b00e-113">DB_SUSPECT</span></span>|  
|<span data-ttu-id="8b00e-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="8b00e-114">Message Text</span></span>|<span data-ttu-id="8b00e-115">Die „%.\*ls“-Datenbank kann nicht geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="8b00e-115">Database '%.\*ls' cannot be opened.</span></span> <span data-ttu-id="8b00e-116">Sie wurde bei der Wiederherstellung als SUSPECT gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="8b00e-116">It has been marked SUSPECT by recovery.</span></span> <span data-ttu-id="8b00e-117">Weitere Informationen finden Sie im SQL Server-Fehlerprotokoll.</span><span class="sxs-lookup"><span data-stu-id="8b00e-117">See the SQL Server errorlog for more information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8b00e-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="8b00e-118">Explanation</span></span>  
 <span data-ttu-id="8b00e-119">Diese Datenbank wurde aufgrund eines Fehlers beim Wiederherstellungsvorgang, bei dem eine Datenbank in einen konsistenten Transaktionszustand versetzt wird, als fehlerverdächtig gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="8b00e-119">The database is marked as suspect because it failed the recovery process that brings a database to a consistent transactional state.</span></span> <span data-ttu-id="8b00e-120">Dies kann während der folgenden Vorgänge auftreten:</span><span class="sxs-lookup"><span data-stu-id="8b00e-120">This can occur during the following operations:</span></span>  
  
-   <span data-ttu-id="8b00e-121">Beim Starten einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz.</span><span class="sxs-lookup"><span data-stu-id="8b00e-121">Starting up an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="8b00e-122">Beim Anfügen einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="8b00e-122">Attaching a database.</span></span>  
  
-   <span data-ttu-id="8b00e-123">Beim Verwenden der RESTORE-Datenbank oder der RESTORE LOG-Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="8b00e-123">Using the RESTORE database or RESTORE LOG procedures.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8b00e-124">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="8b00e-124">User Action</span></span>  
 <span data-ttu-id="8b00e-125">Überprüfen Sie das Fehlerprotokoll von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], und ermitteln Sie die Ursache für den Fehler.</span><span class="sxs-lookup"><span data-stu-id="8b00e-125">Inspect the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and determine the cause of the error.</span></span> <span data-ttu-id="8b00e-126">Wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] seit dem Fehler bei der Wiederherstellung erneut gestartet wurde, sehen Sie in vorherigen Fehlerprotokollen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nach, um den Grund für den Fehler bei der Wiederherstellung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="8b00e-126">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been restarted since the failed recovery, look at previous [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error logs to see the reason why recovery failed.</span></span>  
  
 <span data-ttu-id="8b00e-127">Wenn der Fehler bei der Wiederherstellung auf einen E/A-Fehler, eine zerrissene Seite oder ein Hardwareproblem zurückzuführen ist, beheben Sie das zugrunde liegende Hardwareproblem, und stellen Sie die Datenbank mithilfe einer Sicherung wieder her.</span><span class="sxs-lookup"><span data-stu-id="8b00e-127">If the recovery failed because of a persistent I/O error, a torn page, or other possible hardware problem, resolve the underlying hardware problem and restore the database by using a backup.</span></span> <span data-ttu-id="8b00e-128">Wenn keine Sicherungen vorhanden sind, können Sie die Reparaturoptionen von DBCC CHECKDB verwenden.</span><span class="sxs-lookup"><span data-stu-id="8b00e-128">If no backups are available, consider the repair options of DBCC CHECKDB.</span></span>  
  
 <span data-ttu-id="8b00e-129">Wenden Sie sich an Ihren primären Anbieter für technischen Support, wenn Sie das Problem nicht selbst beheben können.</span><span class="sxs-lookup"><span data-stu-id="8b00e-129">If you are unable to resolve this problem, contact your primary support provider.</span></span> <span data-ttu-id="8b00e-130">Halten Sie das Fehlerprotokoll für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zur Überprüfung bereit.</span><span class="sxs-lookup"><span data-stu-id="8b00e-130">Have the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log available for review.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b00e-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8b00e-131">See Also</span></span>  
 <span data-ttu-id="8b00e-132">[Sichern und Wiederherstellen von SQL Server-Datenbanken](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="8b00e-132">[Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="8b00e-133">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8b00e-133">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="8b00e-134">[sys.sysDatenbanken &#40;Transact-SQL-&#41;](/sql/relational-databases/system-compatibility-views/sys-sysdatabases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8b00e-134">[sys.sysdatabases &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysdatabases-transact-sql) </span></span>  
 [<span data-ttu-id="8b00e-135">Anfügen und Trennen von Datenbanken &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8b00e-135">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../../relational-databases/databases/database-detach-and-attach-sql-server.md)  
  
  
