---
title: MSSQLSERVER_3456 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3456 (Database Engine error)
ms.assetid: d11b2b2c-3ae4-4023-b82f-05b561bfacce
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f13316bdd3147bb0ad63c8d4a2fb18f1fce74006
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701246"
---
# <a name="mssqlserver_3456"></a><span data-ttu-id="65ef9-102">MSSQLSERVER_3456</span><span class="sxs-lookup"><span data-stu-id="65ef9-102">MSSQLSERVER_3456</span></span>
    
## <a name="details"></a><span data-ttu-id="65ef9-103">Details</span><span class="sxs-lookup"><span data-stu-id="65ef9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="65ef9-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="65ef9-104">Product Name</span></span>|<span data-ttu-id="65ef9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="65ef9-105">SQL Server</span></span>|  
|<span data-ttu-id="65ef9-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="65ef9-106">Event ID</span></span>|<span data-ttu-id="65ef9-107">3456</span><span class="sxs-lookup"><span data-stu-id="65ef9-107">3456</span></span>|  
|<span data-ttu-id="65ef9-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="65ef9-108">Event Source</span></span>|<span data-ttu-id="65ef9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="65ef9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="65ef9-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="65ef9-110">Component</span></span>|<span data-ttu-id="65ef9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="65ef9-111">SQLEngine</span></span>|  
|<span data-ttu-id="65ef9-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="65ef9-112">Symbolic Name</span></span>|<span data-ttu-id="65ef9-113">REC_REDOLSNMISMATCH</span><span class="sxs-lookup"><span data-stu-id="65ef9-113">REC_REDOLSNMISMATCH</span></span>|  
|<span data-ttu-id="65ef9-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="65ef9-114">Message Text</span></span>|<span data-ttu-id="65ef9-115">Der Protokolleintrag %S_LSN für die Transaktions-ID %S_XID auf Seite %S_PGID, %.\*ls-Datenbank (Datenbank-ID %d) konnte nicht rückgängig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="65ef9-115">Could not redo log record %S_LSN, for transaction ID %S_XID, on page %S_PGID, database '%.\*ls' (database ID %d).</span></span> <span data-ttu-id="65ef9-116">Seite: LSN = %S_LSN, Typ = %ld.</span><span class="sxs-lookup"><span data-stu-id="65ef9-116">Page: LSN = %S_LSN, type = %ld.</span></span> <span data-ttu-id="65ef9-117">Protokoll: OpCode = %ld, Kontext %ld, PrevPageLSN: %S_LSN.</span><span class="sxs-lookup"><span data-stu-id="65ef9-117">Log: OpCode = %ld, context %ld, PrevPageLSN: %S_LSN.</span></span> <span data-ttu-id="65ef9-118">Stellen Sie die Datenbank von einer Sicherung wieder her, oder reparieren Sie die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="65ef9-118">Restore from a backup of the database, or repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="65ef9-119">Erklärung</span><span class="sxs-lookup"><span data-stu-id="65ef9-119">Explanation</span></span>  
 <span data-ttu-id="65ef9-120">Der Wiederherstellungsvorgang konnte das Transaktionsprotokoll nicht wiederholen.</span><span class="sxs-lookup"><span data-stu-id="65ef9-120">The restore operation was unable to redo the transaction log.</span></span> <span data-ttu-id="65ef9-121">Durch diesen Fehler wurde die Datenbank in den SUSPECT-Status geschaltet.</span><span class="sxs-lookup"><span data-stu-id="65ef9-121">This error has placed the database into the SUSPECT state.</span></span> <span data-ttu-id="65ef9-122">Die primäre Dateigruppe und möglicherweise weitere Dateigruppen sind fehlerverdächtig und u. U. beschädigt.</span><span class="sxs-lookup"><span data-stu-id="65ef9-122">The primary filegroup, and possibly other filegroups, are suspect and may be damaged.</span></span> <span data-ttu-id="65ef9-123">Die Datenbank kann während Starts von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht wiederhergestellt werden und ist daher nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="65ef9-123">The database cannot be recovered during startup of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is therefore unavailable.</span></span> <span data-ttu-id="65ef9-124">Eine Aktion seitens des Benutzers ist erforderlich, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="65ef9-124">User action is required to resolve the problem.</span></span>  
  
 <span data-ttu-id="65ef9-125">Falls dieser Fehler für **tempdb**auftritt, wird die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="65ef9-125">Note that if this error occurs for **tempdb**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="65ef9-126">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="65ef9-126">User Action</span></span>  
 <span data-ttu-id="65ef9-127">Dieser Fehler kann auf vorübergehende Systemschwierigkeiten zurückzuführen sein, die beim Versuch, die Serverinstanz zu starten oder eine Datenbank wiederherzustellen, aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="65ef9-127">This error can be caused by a transient condition that existed on the system during a given attempt to start up the server instance or to recover a database.</span></span> <span data-ttu-id="65ef9-128">Es kann jedoch auch ein dauerhafter Fehler vorliegen, der bei jedem Versuch auftritt, die Datenbank zu starten.</span><span class="sxs-lookup"><span data-stu-id="65ef9-128">This error can also be caused by a permanent failure that occurs every time that you attempt to start the database.</span></span> <span data-ttu-id="65ef9-129">Um Informationen zur Ursache zu erhalten, überprüfen Sie das Windows-Ereignisprotokoll auf einen vorangehenden Fehler, der Aufschluss über den aktuellen Fehler geben könnte.</span><span class="sxs-lookup"><span data-stu-id="65ef9-129">For information about the cause, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span>  
  
 <span data-ttu-id="65ef9-130">Um Informationen zur Ursache dieses Auftretens von Fehler 3456 zu erhalten, überprüfen Sie das Windows-Ereignisprotokoll auf einen vorangehenden Fehler, der Aufschluss über den aktuellen Fehler geben könnte.</span><span class="sxs-lookup"><span data-stu-id="65ef9-130">For information about the cause of this occurrence of error 3456, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span> <span data-ttu-id="65ef9-131">Die entsprechende Benutzeraktion hängt davon ab, ob die Informationen im Windows-Ereignisprotokoll angeben, dass der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehler durch eine vorübergehende Bedingung oder einen dauerhaften Fehler verursacht wurde.</span><span class="sxs-lookup"><span data-stu-id="65ef9-131">The appropriate user action depends on whether the information in the Windows Event Log indicates that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error was caused by a transient condition or a permanent failure.</span></span> <span data-ttu-id="65ef9-132">Informationen zu den Benutzeraktionen zum Beheben von Fehler 3456 finden Sie in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="65ef9-132">For information about the user actions for troubleshooting error 3456, see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65ef9-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="65ef9-133">See Also</span></span>  
 <span data-ttu-id="65ef9-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="65ef9-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="65ef9-135">[DBCC CHECKDB &#40;Transact-SQL-&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="65ef9-135">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="65ef9-136">[Vollständige Datenbankwiederherstellungen &#40;einfaches Wiederherstellungsmodell&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="65ef9-136">[Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="65ef9-137">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="65ef9-137">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span></span>  
 [<span data-ttu-id="65ef9-138">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="65ef9-138">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
