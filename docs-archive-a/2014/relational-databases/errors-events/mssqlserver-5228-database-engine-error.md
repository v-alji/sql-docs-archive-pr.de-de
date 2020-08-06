---
title: MSSQLSERVER_5228 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5228 (Database Engine error)
ms.assetid: 5e83c617-4aa2-4755-bcc5-a798c46b97e4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: eef59e62f00a44aad7bfefb1719a6d8d2b3d0290
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608722"
---
# <a name="mssqlserver_5228"></a><span data-ttu-id="09ee9-102">MSSQLSERVER_5228</span><span class="sxs-lookup"><span data-stu-id="09ee9-102">MSSQLSERVER_5228</span></span>
    
## <a name="details"></a><span data-ttu-id="09ee9-103">Details</span><span class="sxs-lookup"><span data-stu-id="09ee9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="09ee9-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="09ee9-104">Product Name</span></span>|<span data-ttu-id="09ee9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="09ee9-105">SQL Server</span></span>|  
|<span data-ttu-id="09ee9-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="09ee9-106">Event ID</span></span>|<span data-ttu-id="09ee9-107">5228</span><span class="sxs-lookup"><span data-stu-id="09ee9-107">5228</span></span>|  
|<span data-ttu-id="09ee9-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="09ee9-108">Event Source</span></span>|<span data-ttu-id="09ee9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="09ee9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="09ee9-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="09ee9-110">Component</span></span>|<span data-ttu-id="09ee9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="09ee9-111">SQLEngine</span></span>|  
|<span data-ttu-id="09ee9-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="09ee9-112">Symbolic Name</span></span>|<span data-ttu-id="09ee9-113">DBCC4_ANTIMATTER_COLUMN_DETECTED</span><span class="sxs-lookup"><span data-stu-id="09ee9-113">DBCC4_ANTIMATTER_COLUMN_DETECTED</span></span>|  
|<span data-ttu-id="09ee9-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="09ee9-114">Message Text</span></span>|<span data-ttu-id="09ee9-115">Tabellenfehler: Objekt-ID „O_ID“, Index-ID „I_ID“, Partitions-ID „PN_ID“, Zuordnungseinheits-ID „A_ID“ (TYPE-Typ), Seite „P_ID“, Zeile „R_ID“.</span><span class="sxs-lookup"><span data-stu-id="09ee9-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), page PG_ID, row R_ID.</span></span> <span data-ttu-id="09ee9-116">DBCC hat einen unvollständigen Cleanup bei einem Vorgang zur Onlineindexerstellung erkannt.</span><span class="sxs-lookup"><span data-stu-id="09ee9-116">DBCC detected incomplete cleanup from an online index build operation.</span></span> <span data-ttu-id="09ee9-117">(Der Spaltenwert für die Cleanupmarkierung lautet VALUE.)</span><span class="sxs-lookup"><span data-stu-id="09ee9-117">(Antimatter column value is VALUE.)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="09ee9-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="09ee9-118">Explanation</span></span>  
 <span data-ttu-id="09ee9-119">Für Objekt *O_ID*, Index *I_ID* und Partition *PN_ID* wurde eine nicht abgeschlossene Onlineindexerstellung erkannt.</span><span class="sxs-lookup"><span data-stu-id="09ee9-119">An unfinished online index build was detected for object *O_ID*, index *I_ID*, and partition *PN_ID*.</span></span> <span data-ttu-id="09ee9-120">Dies äußert sich durch das Vorhandensein einer Spalte für die Cleanupmarkierung für die Zeile *R_ID*.</span><span class="sxs-lookup"><span data-stu-id="09ee9-120">This is manifested by the presence of an antimatter column on the row *R_ID*.</span></span> <span data-ttu-id="09ee9-121">Eine Spalte für die Cleanupmarkierung wird verwendet, wenn Datensätze aus mehreren Quellen während einer Onlineindexerstellung abgeglichen werden.</span><span class="sxs-lookup"><span data-stu-id="09ee9-121">An antimatter column is used when reconciling records from multiple sources during an online index build.</span></span> <span data-ttu-id="09ee9-122">In der Fehlermeldung wird zudem der Wert der Spalte für die Cleanupmarkierung angegeben.</span><span class="sxs-lookup"><span data-stu-id="09ee9-122">The error message also indicates the value of the antimatter column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="09ee9-123">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="09ee9-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="09ee9-124">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="09ee9-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="09ee9-125">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="09ee9-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="09ee9-126">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="09ee9-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="09ee9-127">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="09ee9-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="09ee9-128">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="09ee9-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="09ee9-129">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="09ee9-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="09ee9-130">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="09ee9-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="09ee9-131">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="09ee9-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="09ee9-132">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="09ee9-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="09ee9-133">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="09ee9-133">Restore from Backup</span></span>  
 <span data-ttu-id="09ee9-134">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="09ee9-134">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="09ee9-135">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="09ee9-135">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="09ee9-136">Führen Sie DBCC CHECKDB ohne eine REPAIR-Klausel aus, um das Ausmaß der Beschädigung festzustellen, falls keine fehlerfreie Sicherung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="09ee9-136">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="09ee9-137">DBCC CHECKDB empfiehlt die Verwendung einer REPAIR-Klausel.</span><span class="sxs-lookup"><span data-stu-id="09ee9-137">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="09ee9-138">Führen Sie dann DBCC CHECKDB mit der entsprechenden REPAIR-Klausel aus, um die Beschädigung zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="09ee9-138">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="09ee9-139">Wenden Sie sich an Ihren primären Unterstützungsanbieter, bevor Sie diese Anweisung ausführen, wenn Sie nicht sicher sind, inwiefern sich die Verwendung von DBCC CHECKDB mit einer REPAIR-Klausel auf Ihre Daten auswirkt.</span><span class="sxs-lookup"><span data-stu-id="09ee9-139">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="09ee9-140">Wenn DBCC CHECKDB mit einer der REPAIR-Klauseln ausgeführt wird und das Problem nicht behebt, wenden Sie sich an Ihren primären Unterstützungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="09ee9-140">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="09ee9-141">Ergebnis der Ausführung von REPAIR-Optionen</span><span class="sxs-lookup"><span data-stu-id="09ee9-141">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="09ee9-142">Durch Ausführen von REPAIR werden der angegebene Index sowie alle abhängigen Indizes neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="09ee9-142">Running REPAIR will cause the specified index and all its dependent indexes to be rebuilt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09ee9-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="09ee9-143">See Also</span></span>  
 [<span data-ttu-id="09ee9-144">DBCC CHECKDB &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="09ee9-144">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
