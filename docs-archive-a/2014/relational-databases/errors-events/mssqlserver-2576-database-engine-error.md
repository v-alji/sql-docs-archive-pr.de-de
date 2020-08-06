---
title: MSSQLSERVER_2576 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2576 (Database Engine error)
ms.assetid: b727cc2f-c76c-46f8-bbbe-5e7a05a6eabf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8f378051c7844bf08d617db56666d69b22ecf732
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616083"
---
# <a name="mssqlserver_2576"></a><span data-ttu-id="e6b0a-102">MSSQLSERVER_2576</span><span class="sxs-lookup"><span data-stu-id="e6b0a-102">MSSQLSERVER_2576</span></span>
    
## <a name="details"></a><span data-ttu-id="e6b0a-103">Details</span><span class="sxs-lookup"><span data-stu-id="e6b0a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e6b0a-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="e6b0a-104">Product Name</span></span>|<span data-ttu-id="e6b0a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e6b0a-105">SQL Server</span></span>|  
|<span data-ttu-id="e6b0a-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e6b0a-106">Event ID</span></span>|<span data-ttu-id="e6b0a-107">2576</span><span class="sxs-lookup"><span data-stu-id="e6b0a-107">2576</span></span>|  
|<span data-ttu-id="e6b0a-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="e6b0a-108">Event Source</span></span>|<span data-ttu-id="e6b0a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e6b0a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e6b0a-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="e6b0a-110">Component</span></span>|<span data-ttu-id="e6b0a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e6b0a-111">SQLEngine</span></span>|  
|<span data-ttu-id="e6b0a-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="e6b0a-112">Symbolic Name</span></span>|<span data-ttu-id="e6b0a-113">DBCC_IAM_PARENT_PAGE_WAS_NOT_SEEN</span><span class="sxs-lookup"><span data-stu-id="e6b0a-113">DBCC_IAM_PARENT_PAGE_WAS_NOT_SEEN</span></span>|  
|<span data-ttu-id="e6b0a-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="e6b0a-114">Message Text</span></span>|<span data-ttu-id="e6b0a-115">Auf die IAM-Seite (Index Allocation Map) P_ID1 zeigt der Zeiger für die nächste Seite der IAM-Seite P_ID2 in Objekt-ID O_ID, Index-ID I_ID, Partitions-ID PN_ID, Zuordnungseinheits-ID A_ID (TYPE-Typ), sie wurde jedoch nicht im Scan gefunden.</span><span class="sxs-lookup"><span data-stu-id="e6b0a-115">The Index Allocation Map (IAM) page P_ID1 is pointed to by the previous pointer of IAM page P_ID2 in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) but was not detected in the scan.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e6b0a-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="e6b0a-116">Explanation</span></span>  
 <span data-ttu-id="e6b0a-117">Eine IAM-Seite (Index Allocation Map) oder ein Metadateneintrag wurde nicht gefunden, obwohl ein Verweis auf die Seite als Link zu der vorherigen Seite auf einer anderen IAM-Seite in einer IAM-Kette vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e6b0a-117">An Index Allocation Map (IAM) page or metadata entry was not located, even though a reference to the page exists as the previous page link on another IAM page in an IAM chain.</span></span> <span data-ttu-id="e6b0a-118">Wenn die *P_ID1*-Seite (0:0) ist, ist die IAM-Seite *P_ID2* der Anfang einer IAM-Kette, und der Metadateneintrag für die IAM-Kette fehlt.</span><span class="sxs-lookup"><span data-stu-id="e6b0a-118">If the *P_ID1* page is (0:0), the IAM page, *P_ID2*, is the start of an IAM chain, and the metadata entry for the IAM chain is missing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e6b0a-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="e6b0a-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="e6b0a-120">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="e6b0a-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="e6b0a-121">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="e6b0a-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="e6b0a-122">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="e6b0a-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="e6b0a-123">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e6b0a-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="e6b0a-124">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="e6b0a-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="e6b0a-125">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e6b0a-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="e6b0a-126">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="e6b0a-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="e6b0a-127">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="e6b0a-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="e6b0a-128">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="e6b0a-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="e6b0a-129">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="e6b0a-129">Restore from Backup</span></span>  
 <span data-ttu-id="e6b0a-130">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e6b0a-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="e6b0a-131">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="e6b0a-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="e6b0a-132">Führen Sie DBCC CHECKDB ohne eine REPAIR-Klausel aus, um das Ausmaß der Beschädigung festzustellen, falls keine fehlerfreie Sicherung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e6b0a-132">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="e6b0a-133">DBCC CHECKDB empfiehlt die Verwendung einer REPAIR-Klausel.</span><span class="sxs-lookup"><span data-stu-id="e6b0a-133">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="e6b0a-134">Führen Sie dann DBCC CHECKDB mit der entsprechenden REPAIR-Klausel aus, um die Beschädigung zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="e6b0a-134">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="e6b0a-135">Wenden Sie sich an Ihren primären Unterstützungsanbieter, bevor Sie diese Anweisung ausführen, wenn Sie nicht sicher sind, inwiefern sich die Verwendung von DBCC CHECKDB mit einer REPAIR-Klausel auf Ihre Daten auswirkt.</span><span class="sxs-lookup"><span data-stu-id="e6b0a-135">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="e6b0a-136">Wenn DBCC CHECKDB mit einer der REPAIR-Klauseln ausgeführt wird und das Problem nicht behebt, wenden Sie sich an Ihren primären Unterstützungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="e6b0a-136">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="e6b0a-137">Ergebnis der Ausführung von REPAIR-Optionen</span><span class="sxs-lookup"><span data-stu-id="e6b0a-137">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="e6b0a-138">Von REPAIR wird versucht, die IAM-Kette mit der Seite *P_ID2* neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e6b0a-138">REPAIR will try to rebuild the IAM chain involving the *P_ID2* page.</span></span> <span data-ttu-id="e6b0a-139">Beim Neuerstellen der Kette müssen möglicherweise Seiten aus der Kette entfernt werden, oder es muss die gesamte Kette entfernt werden, wenn die Metadaten beschädigt sind.</span><span class="sxs-lookup"><span data-stu-id="e6b0a-139">Rebuilding the chain may involve removing pages from the chain, or removing the whole chain if the metadata is corrupted.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="e6b0a-140">Diese Reparatur führt möglicherweise zum Datenverlust.</span><span class="sxs-lookup"><span data-stu-id="e6b0a-140">This repair may cause data loss.</span></span>  
  
  
