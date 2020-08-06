---
title: MSSQLSERVER_8994 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8994 (Database Engine error)
ms.assetid: 8f4b0e2f-04c0-46e4-9208-20a7085d7a1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0bcc0b1db100b70390c09e9c825dbfd068d968af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608717"
---
# <a name="mssqlserver_8994"></a><span data-ttu-id="62551-102">MSSQLSERVER_8994</span><span class="sxs-lookup"><span data-stu-id="62551-102">MSSQLSERVER_8994</span></span>
    
## <a name="details"></a><span data-ttu-id="62551-103">Details</span><span class="sxs-lookup"><span data-stu-id="62551-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="62551-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="62551-104">Product Name</span></span>|<span data-ttu-id="62551-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="62551-105">SQL Server</span></span>|  
|<span data-ttu-id="62551-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="62551-106">Event ID</span></span>|<span data-ttu-id="62551-107">8994</span><span class="sxs-lookup"><span data-stu-id="62551-107">8994</span></span>|  
|<span data-ttu-id="62551-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="62551-108">Event Source</span></span>|<span data-ttu-id="62551-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="62551-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="62551-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="62551-110">Component</span></span>|<span data-ttu-id="62551-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="62551-111">SQLEngine</span></span>|  
|<span data-ttu-id="62551-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="62551-112">Symbolic Name</span></span>|<span data-ttu-id="62551-113">DBCC3_MISSING_FORWARDING_ROW</span><span class="sxs-lookup"><span data-stu-id="62551-113">DBCC3_MISSING_FORWARDING_ROW</span></span>|  
|<span data-ttu-id="62551-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="62551-114">Message Text</span></span>|<span data-ttu-id="62551-115">Objekt-ID O_ID: Auf die Seite P_ID1 der weitergeleiteten Zeile, Slot S_ID1 müsste die Seite P_ID2 der weitergeleiteten Zeile, Slot S_ID2 zeigen.</span><span class="sxs-lookup"><span data-stu-id="62551-115">Object ID O_ID, forwarded row page P_ID1, slot S_ID1 should be pointed to by forwarding row page P_ID2, slot S_ID2.</span></span> <span data-ttu-id="62551-116">Die weiterleitende Zeile wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="62551-116">Did not encounter forwarding row.</span></span> <span data-ttu-id="62551-117">Möglicherweise liegt ein Zuordnungsfehler vor.</span><span class="sxs-lookup"><span data-stu-id="62551-117">Possible allocation error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="62551-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="62551-118">Explanation</span></span>  
 <span data-ttu-id="62551-119">Für eine weitergeleitete Zeile in einem Heap fehlt die weiterleitende Zeile, die darauf zeigen soll.</span><span class="sxs-lookup"><span data-stu-id="62551-119">A forwarded row in a heap is missing the forwarding row that should point to it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="62551-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="62551-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="62551-121">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="62551-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="62551-122">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="62551-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="62551-123">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="62551-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="62551-124">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="62551-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="62551-125">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="62551-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="62551-126">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="62551-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="62551-127">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="62551-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="62551-128">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="62551-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="62551-129">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="62551-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="62551-130">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="62551-130">Restore from Backup</span></span>  
 <span data-ttu-id="62551-131">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="62551-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="62551-132">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="62551-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="62551-133">Führen Sie DBCC CHECKDB ohne eine REPAIR-Klausel aus, um das Ausmaß der Beschädigung festzustellen, falls keine fehlerfreie Sicherung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="62551-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="62551-134">DBCC CHECKDB empfiehlt die Verwendung einer REPAIR-Klausel.</span><span class="sxs-lookup"><span data-stu-id="62551-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="62551-135">Führen Sie dann DBCC CHECKDB mit der entsprechenden REPAIR-Klausel aus, um die Beschädigung zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="62551-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="62551-136">Wenden Sie sich an Ihren primären Unterstützungsanbieter, bevor Sie diese Anweisung ausführen, wenn Sie nicht sicher sind, inwiefern sich die Verwendung von DBCC CHECKDB mit einer REPAIR-Klausel auf Ihre Daten auswirkt.</span><span class="sxs-lookup"><span data-stu-id="62551-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="62551-137">Wenn DBCC CHECKDB mit einer der REPAIR-Klauseln ausgeführt wird und das Problem nicht behebt, wenden Sie sich an Ihren primären Unterstützungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="62551-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
#### <a name="results-of-running-repair-options"></a><span data-ttu-id="62551-138">Ergebnis der Ausführung von REPAIR-Optionen</span><span class="sxs-lookup"><span data-stu-id="62551-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="62551-139">Die weitergeleitete Zeile wird in eine reguläre Datenzeile konvertiert.</span><span class="sxs-lookup"><span data-stu-id="62551-139">The forwarded row will be converted to a regular data row.</span></span>  
  
  
