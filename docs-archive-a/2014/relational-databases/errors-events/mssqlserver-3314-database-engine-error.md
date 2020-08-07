---
title: MSSQLSERVER_3314 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3314 (Database Engine error)
ms.assetid: f3a5ca6a-b502-4cab-b3b1-4bc753763fa9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ff3b891b438f71d70f5dd62174eae2c5a07d29a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620906"
---
# <a name="mssqlserver_3314"></a><span data-ttu-id="a81d9-102">MSSQLSERVER_3314</span><span class="sxs-lookup"><span data-stu-id="a81d9-102">MSSQLSERVER_3314</span></span>
    
## <a name="details"></a><span data-ttu-id="a81d9-103">Details</span><span class="sxs-lookup"><span data-stu-id="a81d9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a81d9-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="a81d9-104">Product Name</span></span>|<span data-ttu-id="a81d9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a81d9-105">SQL Server</span></span>|  
|<span data-ttu-id="a81d9-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a81d9-106">Event ID</span></span>|<span data-ttu-id="a81d9-107">3314</span><span class="sxs-lookup"><span data-stu-id="a81d9-107">3314</span></span>|  
|<span data-ttu-id="a81d9-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="a81d9-108">Event Source</span></span>|<span data-ttu-id="a81d9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a81d9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a81d9-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="a81d9-110">Component</span></span>|<span data-ttu-id="a81d9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a81d9-111">SQLEngine</span></span>|  
|<span data-ttu-id="a81d9-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="a81d9-112">Symbolic Name</span></span>|<span data-ttu-id="a81d9-113">ERR_LOG_RID2</span><span class="sxs-lookup"><span data-stu-id="a81d9-113">ERR_LOG_RID2</span></span>|  
|<span data-ttu-id="a81d9-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="a81d9-114">Message Text</span></span>|<span data-ttu-id="a81d9-115">Fehler beim Rückgängigmachen des protokollierten Vorgangs in der „%.\*ls“-Datenbank bei Protokolldatensatz-ID „%S_LSN“.</span><span class="sxs-lookup"><span data-stu-id="a81d9-115">During undoing of a logged operation in database '%.\*ls', an error occurred at log record ID %S_LSN.</span></span> <span data-ttu-id="a81d9-116">Normalerweise wird der jeweilige Fehler zuvor als Fehler im Windows-Ereignisprotokoll protokolliert.</span><span class="sxs-lookup"><span data-stu-id="a81d9-116">Typically, the specific failure is logged previously as an error in the Windows Event Log service.</span></span> <span data-ttu-id="a81d9-117">Stellen Sie die Datenbank oder Datei von einer Sicherung wieder her, oder reparieren Sie die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="a81d9-117">Restore the database or file from a backup, or repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a81d9-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="a81d9-118">Explanation</span></span>  
 <span data-ttu-id="a81d9-119">Dies ist ein Rollupfehler für die Rollbackphasenwiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="a81d9-119">This is a rollup error for undo recovery.</span></span> <span data-ttu-id="a81d9-120">Durch diesen Fehler wurde die Datenbank in den SUSPECT-Status geschaltet.</span><span class="sxs-lookup"><span data-stu-id="a81d9-120">This error has placed the database into the SUSPECT state.</span></span> <span data-ttu-id="a81d9-121">Die primäre Dateigruppe und möglicherweise weitere Dateigruppen sind fehlerverdächtig und u. U. beschädigt.</span><span class="sxs-lookup"><span data-stu-id="a81d9-121">The primary filegroup, and possibly other filegroups, are suspect and may be damaged.</span></span> <span data-ttu-id="a81d9-122">Die Datenbank kann während Starts von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht wiederhergestellt werden und ist daher nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a81d9-122">The database cannot be recovered during startup of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is therefore unavailable.</span></span> <span data-ttu-id="a81d9-123">Eine Aktion seitens des Benutzers ist erforderlich, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="a81d9-123">User action is required to resolve the problem.</span></span>  
  
 <span data-ttu-id="a81d9-124">Falls dieser Fehler für **tempdb**auftritt, wird die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="a81d9-124">Note that if this error occurs for **tempdb**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a81d9-125">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="a81d9-125">User Action</span></span>  
 <span data-ttu-id="a81d9-126">Dieser Fehler kann auf vorübergehende Systemschwierigkeiten zurückzuführen sein, die beim Versuch, die Serverinstanz zu starten oder eine Datenbank wiederherzustellen, aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="a81d9-126">This error can be caused by a transient condition that existed on the system during a given attempt to start up the server instance or to recover a database.</span></span> <span data-ttu-id="a81d9-127">Es kann jedoch auch ein dauerhafter Fehler vorliegen, der bei jedem Versuch auftritt, die Datenbank zu starten.</span><span class="sxs-lookup"><span data-stu-id="a81d9-127">This error can also be caused by a permanent failure that occurs every time that you attempt to start the database.</span></span> <span data-ttu-id="a81d9-128">Um Informationen zur Ursache zu erhalten, überprüfen Sie das Windows-Ereignisprotokoll auf einen vorangehenden Fehler, der Aufschluss über den aktuellen Fehler geben könnte.</span><span class="sxs-lookup"><span data-stu-id="a81d9-128">For information about the cause, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span>  
  
 <span data-ttu-id="a81d9-129">Um Informationen zur Ursache dieses Auftretens von Fehler 3314 zu erhalten, überprüfen Sie das Windows-Ereignisprotokoll auf einen vorangehenden Fehler, der Aufschluss über den aktuellen Fehler geben könnte.</span><span class="sxs-lookup"><span data-stu-id="a81d9-129">For information about the cause of this occurrence of error 3314, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span> <span data-ttu-id="a81d9-130">Die entsprechende Benutzeraktion hängt davon ab, ob die Informationen im Windows-Ereignisprotokoll angeben, dass der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehler durch eine vorübergehende Bedingung oder einen dauerhaften Fehler verursacht wurde.</span><span class="sxs-lookup"><span data-stu-id="a81d9-130">The appropriate user action depends on whether the information in the Windows Event Log indicates that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error was caused by a transient condition or a permanent failure.</span></span> <span data-ttu-id="a81d9-131">Informationen zu den Benutzeraktionen zum Beheben von Fehler 3314 finden Sie in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="a81d9-131">For information about the user actions for troubleshooting error 3314, see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a81d9-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a81d9-132">See Also</span></span>  
 <span data-ttu-id="a81d9-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a81d9-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="a81d9-134">[DBCC CHECKDB &#40;Transact-SQL-&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a81d9-134">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="a81d9-135">[Vollständige Datenbankwiederherstellungen &#40;einfaches Wiederherstellungsmodell&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="a81d9-135">[Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="a81d9-136">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="a81d9-136">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span></span>  
 [<span data-ttu-id="a81d9-137">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a81d9-137">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
