---
title: MSSQLSERVER_8993 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8993 (Database Engine error)
ms.assetid: 06aac110-a41c-4853-bc8e-a83e8535b8be
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5ee9497e9c4484fd885803c0feff20362a159ff2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608718"
---
# <a name="mssqlserver_8993"></a><span data-ttu-id="257fb-102">MSSQLSERVER_8993</span><span class="sxs-lookup"><span data-stu-id="257fb-102">MSSQLSERVER_8993</span></span>
    
## <a name="details"></a><span data-ttu-id="257fb-103">Details</span><span class="sxs-lookup"><span data-stu-id="257fb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="257fb-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="257fb-104">Product Name</span></span>|<span data-ttu-id="257fb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="257fb-105">SQL Server</span></span>|  
|<span data-ttu-id="257fb-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="257fb-106">Event ID</span></span>|<span data-ttu-id="257fb-107">8993</span><span class="sxs-lookup"><span data-stu-id="257fb-107">8993</span></span>|  
|<span data-ttu-id="257fb-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="257fb-108">Event Source</span></span>|<span data-ttu-id="257fb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="257fb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="257fb-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="257fb-110">Component</span></span>|<span data-ttu-id="257fb-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="257fb-111">SQLEngine</span></span>|  
|<span data-ttu-id="257fb-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="257fb-112">Symbolic Name</span></span>|<span data-ttu-id="257fb-113">DBCC3_MISSING_FORWARDED_ROW</span><span class="sxs-lookup"><span data-stu-id="257fb-113">DBCC3_MISSING_FORWARDED_ROW</span></span>|  
|<span data-ttu-id="257fb-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="257fb-114">Message Text</span></span>|<span data-ttu-id="257fb-115">Objekt-ID O_ID, Seite P_ID1 der weitergeleiteten Zeile, Slot S_ID1 zeigt auf Seite P_ID2, Slot S_ID2.</span><span class="sxs-lookup"><span data-stu-id="257fb-115">Object ID O_ID, forwarding row page P_ID1, slot S_ID1 points to page P_ID2, slot S_ID2.</span></span> <span data-ttu-id="257fb-116">Die weitergeleitete Zeile wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="257fb-116">Did not encounter forwarded row.</span></span> <span data-ttu-id="257fb-117">Möglicherweise liegt ein Zuordnungsfehler vor.</span><span class="sxs-lookup"><span data-stu-id="257fb-117">Possible allocation error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="257fb-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="257fb-118">Explanation</span></span>  
 <span data-ttu-id="257fb-119">Eine weiterleitende Zeile in einem Heap zeigt auf eine nicht vorhandene weitergeleitete Zeile.</span><span class="sxs-lookup"><span data-stu-id="257fb-119">A forwarding row in a heap points to a nonexistent forwarded row.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="257fb-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="257fb-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="257fb-121">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="257fb-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="257fb-122">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="257fb-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="257fb-123">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="257fb-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="257fb-124">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="257fb-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="257fb-125">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="257fb-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="257fb-126">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="257fb-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="257fb-127">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="257fb-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="257fb-128">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="257fb-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="257fb-129">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="257fb-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="257fb-130">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="257fb-130">Restore from Backup</span></span>  
 <span data-ttu-id="257fb-131">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="257fb-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="257fb-132">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="257fb-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="257fb-133">Führen Sie DBCC CHECKDB ohne eine REPAIR-Klausel aus, um das Ausmaß der Beschädigung festzustellen, falls keine fehlerfreie Sicherung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="257fb-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="257fb-134">DBCC CHECKDB empfiehlt die Verwendung einer REPAIR-Klausel.</span><span class="sxs-lookup"><span data-stu-id="257fb-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="257fb-135">Führen Sie dann DBCC CHECKDB mit der entsprechenden REPAIR-Klausel aus, um die Beschädigung zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="257fb-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="257fb-136">Wenden Sie sich an Ihren primären Unterstützungsanbieter, bevor Sie diese Anweisung ausführen, wenn Sie nicht sicher sind, inwiefern sich die Verwendung von DBCC CHECKDB mit einer REPAIR-Klausel auf Ihre Daten auswirkt.</span><span class="sxs-lookup"><span data-stu-id="257fb-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="257fb-137">Wenn DBCC CHECKDB mit einer der REPAIR-Klauseln ausgeführt wird und das Problem nicht behebt, wenden Sie sich an Ihren primären Unterstützungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="257fb-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
#### <a name="results-of-running-repair-options"></a><span data-ttu-id="257fb-138">Ergebnis der Ausführung von REPAIR-Optionen</span><span class="sxs-lookup"><span data-stu-id="257fb-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="257fb-139">Die weiterleitende Zeile wird gelöscht, und alle nicht gruppierten Indizes werden neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="257fb-139">The forwarding row will be deleted and any nonclustered indexes will be rebuilt.</span></span>  
  
  
