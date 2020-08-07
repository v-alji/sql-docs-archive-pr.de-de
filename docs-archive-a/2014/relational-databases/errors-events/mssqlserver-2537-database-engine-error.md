---
title: MSSQLSERVER_2537 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2537 (Database Engine error)
ms.assetid: 0af6ff69-d75a-4c39-8da2-9bd0695277c6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c227867bac5a0ea5789ba653414444d011e5910d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620916"
---
# <a name="mssqlserver_2537"></a><span data-ttu-id="6d8cd-102">MSSQLSERVER_2537</span><span class="sxs-lookup"><span data-stu-id="6d8cd-102">MSSQLSERVER_2537</span></span>
    
## <a name="details"></a><span data-ttu-id="6d8cd-103">Details</span><span class="sxs-lookup"><span data-stu-id="6d8cd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6d8cd-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="6d8cd-104">Product Name</span></span>|<span data-ttu-id="6d8cd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6d8cd-105">SQL Server</span></span>|  
|<span data-ttu-id="6d8cd-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="6d8cd-106">Event ID</span></span>|<span data-ttu-id="6d8cd-107">2537</span><span class="sxs-lookup"><span data-stu-id="6d8cd-107">2537</span></span>|  
|<span data-ttu-id="6d8cd-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="6d8cd-108">Event Source</span></span>|<span data-ttu-id="6d8cd-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6d8cd-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6d8cd-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="6d8cd-110">Component</span></span>|<span data-ttu-id="6d8cd-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6d8cd-111">SQLEngine</span></span>|  
|<span data-ttu-id="6d8cd-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="6d8cd-112">Symbolic Name</span></span>|<span data-ttu-id="6d8cd-113">DBCC_RECORD_CHECK_FAILED</span><span class="sxs-lookup"><span data-stu-id="6d8cd-113">DBCC_RECORD_CHECK_FAILED</span></span>|  
|<span data-ttu-id="6d8cd-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="6d8cd-114">Message Text</span></span>|<span data-ttu-id="6d8cd-115">Tabellenfehler: Objekt-ID „O_ID“, Index-ID „I_ID“, Partitions-ID „PN_ID“, Zuordnungseinheits-ID „A_ID“ (TYPE-Typ), Seite „P_ID“, Zeile „ROW_ID“.</span><span class="sxs-lookup"><span data-stu-id="6d8cd-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), page P_ID, row ROW_ID.</span></span> <span data-ttu-id="6d8cd-116">Fehler bei der Datensatzüberprüfung (CHECK_TEXT).</span><span class="sxs-lookup"><span data-stu-id="6d8cd-116">Record check (CHECK_TEXT) failed.</span></span> <span data-ttu-id="6d8cd-117">Die Werte sind VALUE1 und VALUE2.</span><span class="sxs-lookup"><span data-stu-id="6d8cd-117">Values are VALUE1 and VALUE2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6d8cd-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="6d8cd-118">Explanation</span></span>  
 <span data-ttu-id="6d8cd-119">Bei der Zeile ROW_ID (or a column in the row) ist bei dem durch CHECK_TEXT beschriebenen Test bzw. Bedingungsvorgang ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6d8cd-119">The row ROW_ID (or a column in the row) failed the test or condition described by CHECK_TEXT.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6d8cd-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="6d8cd-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="6d8cd-121">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="6d8cd-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="6d8cd-122">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="6d8cd-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="6d8cd-123">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="6d8cd-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="6d8cd-124">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="6d8cd-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="6d8cd-125">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="6d8cd-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="6d8cd-126">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6d8cd-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="6d8cd-127">Wenn Sie vermuten, dass der Schreibcache das Problem ist, wenden Sie sich an den Hardwarehersteller.</span><span class="sxs-lookup"><span data-stu-id="6d8cd-127">If you suspect that write-caching is the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="6d8cd-128">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="6d8cd-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="6d8cd-129">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="6d8cd-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="6d8cd-130">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="6d8cd-130">Restore from Backup</span></span>  
 <span data-ttu-id="6d8cd-131">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6d8cd-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="6d8cd-132">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="6d8cd-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="6d8cd-133">Führen Sie DBCC CHECKDB ohne eine REPAIR-Klausel aus, um das Ausmaß der Beschädigung festzustellen, falls keine fehlerfreie Sicherung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="6d8cd-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="6d8cd-134">DBCC CHECKDB empfiehlt die Verwendung einer REPAIR-Klausel.</span><span class="sxs-lookup"><span data-stu-id="6d8cd-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="6d8cd-135">Führen Sie dann DBCC CHECKDB mit der empfohlenen REPAIR-Klausel aus.</span><span class="sxs-lookup"><span data-stu-id="6d8cd-135">Then, run DBCC CHECKDB with the recommended REPAIR clause.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="6d8cd-136">Wenden Sie sich an Ihren primären Unterstützungsanbieter, bevor Sie diese Anweisung ausführen, wenn Sie nicht sicher sind, inwiefern sich die Verwendung von DBCC CHECKDB mit einer REPAIR-Klausel auf Ihre Daten auswirkt.</span><span class="sxs-lookup"><span data-stu-id="6d8cd-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="6d8cd-137">Wenn DBCC CHECKDB mit einer der REPAIR-Klauseln ausgeführt wird und das Problem nicht behebt, wenden Sie sich an Ihren primären Unterstützungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="6d8cd-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="6d8cd-138">Ergebnis der Ausführung von REPAIR-Optionen</span><span class="sxs-lookup"><span data-stu-id="6d8cd-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="6d8cd-139">REPAIR erstellt den Index neu, wenn ein Index vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6d8cd-139">REPAIR will rebuild the index if an index exists.</span></span>  
  
 <span data-ttu-id="6d8cd-140">**Vorsicht** Diese Reparatur führt möglicherweise zum Datenverlust.</span><span class="sxs-lookup"><span data-stu-id="6d8cd-140">**Caution** This repair may cause data loss.</span></span>  
  
  
