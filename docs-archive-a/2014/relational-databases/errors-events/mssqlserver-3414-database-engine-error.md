---
title: MSSQLSERVER_3414 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3414 (Database Engine error)
ms.assetid: f25852f9-b91c-4356-b817-78bec9ec8db4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: aecaf2a920552b8ea66804600fa8bd4168175e53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620899"
---
# <a name="mssqlserver_3414"></a><span data-ttu-id="240cd-102">MSSQLSERVER_3414</span><span class="sxs-lookup"><span data-stu-id="240cd-102">MSSQLSERVER_3414</span></span>
    
## <a name="details"></a><span data-ttu-id="240cd-103">Details</span><span class="sxs-lookup"><span data-stu-id="240cd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="240cd-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="240cd-104">Product Name</span></span>|<span data-ttu-id="240cd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="240cd-105">SQL Server</span></span>|  
|<span data-ttu-id="240cd-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="240cd-106">Event ID</span></span>|<span data-ttu-id="240cd-107">3414</span><span class="sxs-lookup"><span data-stu-id="240cd-107">3414</span></span>|  
|<span data-ttu-id="240cd-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="240cd-108">Event Source</span></span>|<span data-ttu-id="240cd-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="240cd-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="240cd-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="240cd-110">Component</span></span>|<span data-ttu-id="240cd-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="240cd-111">SQLEngine</span></span>|  
|<span data-ttu-id="240cd-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="240cd-112">Symbolic Name</span></span>|<span data-ttu-id="240cd-113">REC_GIVEUP</span><span class="sxs-lookup"><span data-stu-id="240cd-113">REC_GIVEUP</span></span>|  
|<span data-ttu-id="240cd-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="240cd-114">Message Text</span></span>|<span data-ttu-id="240cd-115">Fehler bei der Wiederherstellung. Die '%.\*ls'-Datenbank (Datenbank-ID %d) kann daher nicht neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="240cd-115">An error occurred during recovery, preventing the database '%.\*ls' (database ID %d) from restarting.</span></span> <span data-ttu-id="240cd-116">Diagnostizieren und beheben Sie die Wiederherstellungsfehler, oder führen Sie eine Wiederherstellung von einer als fehlerfrei bekannten Sicherung aus.</span><span class="sxs-lookup"><span data-stu-id="240cd-116">Diagnose the recovery errors and fix them, or restore from a known good backup.</span></span> <span data-ttu-id="240cd-117">Falls die Fehler nicht behoben werden oder unerwartete Fehler auftreten, wenden Sie sich an den technischen Support.</span><span class="sxs-lookup"><span data-stu-id="240cd-117">If errors are not corrected or expected, contact Technical Support.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="240cd-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="240cd-118">Explanation</span></span>  
 <span data-ttu-id="240cd-119">Die angegebene Datenbank wurde wiederhergestellt, konnte jedoch nicht gestartet werden, da Fehler bei der Wiederherstellung auftraten.</span><span class="sxs-lookup"><span data-stu-id="240cd-119">The specified database was recovered, but failed to start, because errors occurred during recovery.</span></span> <span data-ttu-id="240cd-120">Durch diesen Fehler wurde die Datenbank in den SUSPECT-Status geschaltet.</span><span class="sxs-lookup"><span data-stu-id="240cd-120">This error has placed the database into the SUSPECT state.</span></span> <span data-ttu-id="240cd-121">Die primäre Dateigruppe und möglicherweise weitere Dateigruppen sind fehlerverdächtig und u. U. beschädigt.</span><span class="sxs-lookup"><span data-stu-id="240cd-121">The primary filegroup, and possibly other filegroups, are suspect and may be damaged.</span></span> <span data-ttu-id="240cd-122">Die Datenbank kann während Starts von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht wiederhergestellt werden und ist daher nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="240cd-122">The database cannot be recovered during startup of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is therefore unavailable.</span></span> <span data-ttu-id="240cd-123">Eine Aktion seitens des Benutzers ist erforderlich, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="240cd-123">User action is required to resolve the problem.</span></span>  
  
 <span data-ttu-id="240cd-124">Falls dieser Fehler für **tempdb**auftritt, wird die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="240cd-124">Note that if this error occurs for **tempdb**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="240cd-125">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="240cd-125">User Action</span></span>  
 <span data-ttu-id="240cd-126">Dieser Fehler kann auf vorübergehende Systemschwierigkeiten zurückzuführen sein, die beim Versuch, die Serverinstanz zu starten oder eine Datenbank wiederherzustellen, aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="240cd-126">This error can be caused by a transient condition that existed on the system during a given attempt to start up the server instance or to recover a database.</span></span> <span data-ttu-id="240cd-127">Es kann jedoch auch ein dauerhafter Fehler vorliegen, der bei jedem Versuch auftritt, die Datenbank zu starten.</span><span class="sxs-lookup"><span data-stu-id="240cd-127">This error can also be caused by a permanent failure that occurs every time that you attempt to start the database.</span></span> <span data-ttu-id="240cd-128">Um Informationen zur Ursache zu erhalten, überprüfen Sie das Windows-Ereignisprotokoll auf einen vorangehenden Fehler, der Aufschluss über den aktuellen Fehler geben könnte.</span><span class="sxs-lookup"><span data-stu-id="240cd-128">For information about the cause, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span>  
  
 <span data-ttu-id="240cd-129">Um Informationen zur Ursache dieses Auftretens von Fehler 3414 zu erhalten, überprüfen Sie das Windows-Ereignisprotokoll auf einen vorangehenden Fehler, der Aufschluss über den aktuellen Fehler geben könnte.</span><span class="sxs-lookup"><span data-stu-id="240cd-129">For information about the cause of this occurrence of error 3414, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span> <span data-ttu-id="240cd-130">Die entsprechende Benutzeraktion hängt davon ab, ob die Informationen im Windows-Ereignisprotokoll angeben, dass der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehler durch eine vorübergehende Bedingung oder einen dauerhaften Fehler verursacht wurde.</span><span class="sxs-lookup"><span data-stu-id="240cd-130">The appropriate user action depends on whether the information in the Windows Event Log indicates that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error was caused by a transient condition or a permanent failure.</span></span> <span data-ttu-id="240cd-131">Informationen zu den Benutzeraktionen zum Beheben von Fehler 3414 finden Sie in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="240cd-131">For information about the user actions for troubleshooting error 3414, see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="240cd-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="240cd-132">See Also</span></span>  
 <span data-ttu-id="240cd-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="240cd-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="240cd-134">[DBCC CHECKDB &#40;Transact-SQL-&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="240cd-134">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="240cd-135">[Vollständige Datenbankwiederherstellungen &#40;einfaches Wiederherstellungsmodell&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="240cd-135">[Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="240cd-136">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="240cd-136">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span></span>  
 [<span data-ttu-id="240cd-137">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="240cd-137">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
