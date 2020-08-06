---
title: MSSQLSERVER_2515 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2515 (Database Engine error)
ms.assetid: af93aa29-70c9-4923-90af-aafadb20c1c6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 73b2d8b8ff01b97428ba6149f537d96044c6ae3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696878"
---
# <a name="mssqlserver_2515"></a><span data-ttu-id="3a0ab-102">MSSQLSERVER_2515</span><span class="sxs-lookup"><span data-stu-id="3a0ab-102">MSSQLSERVER_2515</span></span>
    
## <a name="details"></a><span data-ttu-id="3a0ab-103">Details</span><span class="sxs-lookup"><span data-stu-id="3a0ab-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3a0ab-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="3a0ab-104">Product Name</span></span>|<span data-ttu-id="3a0ab-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3a0ab-105">SQL Server</span></span>|  
|<span data-ttu-id="3a0ab-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="3a0ab-106">Event ID</span></span>|<span data-ttu-id="3a0ab-107">2515</span><span class="sxs-lookup"><span data-stu-id="3a0ab-107">2515</span></span>|  
|<span data-ttu-id="3a0ab-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="3a0ab-108">Event Source</span></span>|<span data-ttu-id="3a0ab-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3a0ab-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3a0ab-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="3a0ab-110">Component</span></span>|<span data-ttu-id="3a0ab-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3a0ab-111">SQLEngine</span></span>|  
|<span data-ttu-id="3a0ab-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="3a0ab-112">Symbolic Name</span></span>|<span data-ttu-id="3a0ab-113">DBCC_DIFF_MAP_OUT_OF_SYNC</span><span class="sxs-lookup"><span data-stu-id="3a0ab-113">DBCC_DIFF_MAP_OUT_OF_SYNC</span></span>|  
|<span data-ttu-id="3a0ab-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="3a0ab-114">Message Text</span></span>|<span data-ttu-id="3a0ab-115">Seite P_ID, Objekt-ID O_ID, Index-ID I_ID, Partitions-ID PN_ID, Zuordnungseinheits-ID A_ID (TYPE-Typ) wurde geändert, im differenziellen Sicherungsbitmuster jedoch nicht als geändert gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="3a0ab-115">Page P_ID, object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID type TYPE has been modified but is not marked modified in the differential backup bitmap.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3a0ab-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="3a0ab-116">Explanation</span></span>  
 <span data-ttu-id="3a0ab-117">Die angegebene Seite verfügt über eine Protokollfolgenummer, die höher ist als die differenzielle Referenzprotokollfolgenummer im Sicherungs-Manager der Datenbank oder die differenzielle Basisprotokollfolgenummer im Dateikontrollblock der Datei, je nachdem, welche neuer ist.</span><span class="sxs-lookup"><span data-stu-id="3a0ab-117">The page specified has a log sequence number (LSN) that is higher than the differential reference LSN in the BackupManager of the database, or the differential base LSN in the file control block of the file, whichever is more recent.</span></span> <span data-ttu-id="3a0ab-118">Die Seite ist jedoch im differenziellen Sicherungsbitmuster nicht als geändert markiert.</span><span class="sxs-lookup"><span data-stu-id="3a0ab-118">However, the page is not marked as changed in the differential backup bitmap.</span></span>  
  
 <span data-ttu-id="3a0ab-119">Es wird nur eine Seite pro Datenbank gemeldet, weil diese Prüfung nur vorgenommen wird, wenn das differenzielle Bitmuster als fehlerfrei bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="3a0ab-119">Only one page per database will be reported, because this check is only performed when the differential bitmap is known to be error free.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3a0ab-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="3a0ab-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="3a0ab-121">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="3a0ab-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="3a0ab-122">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="3a0ab-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="3a0ab-123">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="3a0ab-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="3a0ab-124">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="3a0ab-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="3a0ab-125">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="3a0ab-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="3a0ab-126">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="3a0ab-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="3a0ab-127">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="3a0ab-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="3a0ab-128">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="3a0ab-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="3a0ab-129">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="3a0ab-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="3a0ab-130">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="3a0ab-130">Restore from Backup</span></span>  
 <span data-ttu-id="3a0ab-131">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3a0ab-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="3a0ab-132">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="3a0ab-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="3a0ab-133">Führen Sie DBCC CHECKDB ohne eine REPAIR-Klausel aus, um das Ausmaß der Beschädigung festzustellen, falls keine fehlerfreie Sicherung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="3a0ab-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="3a0ab-134">DBCC CHECKDB empfiehlt die Verwendung einer REPAIR-Klausel.</span><span class="sxs-lookup"><span data-stu-id="3a0ab-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="3a0ab-135">Führen Sie dann DBCC CHECKDB mit der entsprechenden REPAIR-Klausel aus, um die Beschädigung zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="3a0ab-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="3a0ab-136">Wenden Sie sich an Ihren primären Unterstützungsanbieter, bevor Sie diese Anweisung ausführen, wenn Sie nicht sicher sind, inwiefern sich die Verwendung von DBCC CHECKDB mit einer REPAIR-Klausel auf Ihre Daten auswirkt.</span><span class="sxs-lookup"><span data-stu-id="3a0ab-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="3a0ab-137">Wenn DBCC CHECKDB mit einer der REPAIR-Klauseln ausgeführt wird und das Problem nicht behebt, wenden Sie sich an Ihren primären Unterstützungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="3a0ab-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="3a0ab-138">Ergebnis der Ausführung von REPAIR-Optionen</span><span class="sxs-lookup"><span data-stu-id="3a0ab-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="3a0ab-139">Durch Ausführen von REPAIR wird das differenzielle Bitmuster ungültig.</span><span class="sxs-lookup"><span data-stu-id="3a0ab-139">Running REPAIR will invalidate the differential bitmap.</span></span> <span data-ttu-id="3a0ab-140">Sie können eine differenzielle Sicherung erst nach einer vollständigen Datenbanksicherung ausführen.</span><span class="sxs-lookup"><span data-stu-id="3a0ab-140">You cannot perform a differential backup until a full database backup is taken.</span></span> <span data-ttu-id="3a0ab-141">Die vollständige Datenbanksicherung bietet eine Grundlage für die Neuerstellung des differenziellen Bitmusters.</span><span class="sxs-lookup"><span data-stu-id="3a0ab-141">The full database backup provides a baseline for the differential bitmap to be rebuilt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a0ab-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3a0ab-142">See Also</span></span>  
 <span data-ttu-id="3a0ab-143">[Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3a0ab-143">[Create a Full Database Backup &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md) </span></span>  
 [<span data-ttu-id="3a0ab-144">MSSQLSERVER_2516</span><span class="sxs-lookup"><span data-stu-id="3a0ab-144">MSSQLSERVER_2516</span></span>](mssqlserver-2516-database-engine-error.md)  
  
  
