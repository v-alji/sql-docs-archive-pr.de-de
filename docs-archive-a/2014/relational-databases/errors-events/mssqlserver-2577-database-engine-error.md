---
title: MSSQLSERVER_2577 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2577 (Database Engine error)
ms.assetid: f53256a2-2fb0-47fd-9ed9-c45389104145
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9e4b7b85f59ba721eae6b4a0ac8db1b2d288422d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620908"
---
# <a name="mssqlserver_2577"></a><span data-ttu-id="4fe88-102">MSSQLSERVER_2577</span><span class="sxs-lookup"><span data-stu-id="4fe88-102">MSSQLSERVER_2577</span></span>
    
## <a name="details"></a><span data-ttu-id="4fe88-103">Details</span><span class="sxs-lookup"><span data-stu-id="4fe88-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4fe88-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="4fe88-104">Product Name</span></span>|<span data-ttu-id="4fe88-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4fe88-105">SQL Server</span></span>|  
|<span data-ttu-id="4fe88-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="4fe88-106">Event ID</span></span>|<span data-ttu-id="4fe88-107">2577</span><span class="sxs-lookup"><span data-stu-id="4fe88-107">2577</span></span>|  
|<span data-ttu-id="4fe88-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="4fe88-108">Event Source</span></span>|<span data-ttu-id="4fe88-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4fe88-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4fe88-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="4fe88-110">Component</span></span>|<span data-ttu-id="4fe88-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4fe88-111">SQLEngine</span></span>|  
|<span data-ttu-id="4fe88-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="4fe88-112">Symbolic Name</span></span>|<span data-ttu-id="4fe88-113">DBCC_IAM_CHAIN_SEQUENCE_OUT_OF_ORDER</span><span class="sxs-lookup"><span data-stu-id="4fe88-113">DBCC_IAM_CHAIN_SEQUENCE_OUT_OF_ORDER</span></span>|  
|<span data-ttu-id="4fe88-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="4fe88-114">Message Text</span></span>|<span data-ttu-id="4fe88-115">Die Kettensequenznummern in der IAM-Kette (Index Allocation Map) für Objekt-ID O_ID, Index-ID I_ID, Partitions-ID PN_ID, Zuordnungseinheits-ID A_ID (TYPE-Typ) weisen nicht die richtige Reihenfolge auf.</span><span class="sxs-lookup"><span data-stu-id="4fe88-115">Chain sequence numbers out of order in the Index Allocation Map (IAM) chain for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="4fe88-116">Die Seite P_ID1 mit der Sequenznummer SEQUENCE1 zeigt auf die Seite P_ID2 mit der Sequenznummer SEQUENCE2.</span><span class="sxs-lookup"><span data-stu-id="4fe88-116">Page P_ID1 with sequence number SEQUENCE1 points to page P_ID2 with sequence number SEQUENCE2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4fe88-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="4fe88-117">Explanation</span></span>  
 <span data-ttu-id="4fe88-118">Jede IAM-Seite (Index Allocation Map) hat eine Sequenznummer.</span><span class="sxs-lookup"><span data-stu-id="4fe88-118">Every Index Allocation Map (IAM) page has a sequence number.</span></span> <span data-ttu-id="4fe88-119">Die Sequenznummer gibt die Position der IAM-Seite in der IAM-Kette an.</span><span class="sxs-lookup"><span data-stu-id="4fe88-119">The sequence number is the position of the IAM page within the IAM chain.</span></span> <span data-ttu-id="4fe88-120">Die Regel besagt, dass Sequenznummern für jede IAM-Seite um eins erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="4fe88-120">The rule is that sequence numbers increase by one for each IAM page.</span></span> <span data-ttu-id="4fe88-121">IAM-Seite *P_ID2* hat eine Sequenznummer, die dieser Regel nicht entspricht.</span><span class="sxs-lookup"><span data-stu-id="4fe88-121">IAM page, *P_ID2*, has a sequence number that does not follow this rule.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4fe88-122">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="4fe88-122">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="4fe88-123">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="4fe88-123">Look for Hardware Failure</span></span>  
 <span data-ttu-id="4fe88-124">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="4fe88-124">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="4fe88-125">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4fe88-125">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="4fe88-126">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="4fe88-126">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="4fe88-127">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="4fe88-127">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="4fe88-128">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4fe88-128">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="4fe88-129">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="4fe88-129">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="4fe88-130">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="4fe88-130">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="4fe88-131">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="4fe88-131">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="4fe88-132">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="4fe88-132">Restore from Backup</span></span>  
 <span data-ttu-id="4fe88-133">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4fe88-133">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="4fe88-134">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="4fe88-134">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="4fe88-135">Führen Sie DBCC CHECKDB ohne eine REPAIR-Klausel aus, um das Ausmaß der Beschädigung festzustellen, falls keine fehlerfreie Sicherung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="4fe88-135">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="4fe88-136">DBCC CHECKDB empfiehlt die Verwendung einer REPAIR-Klausel.</span><span class="sxs-lookup"><span data-stu-id="4fe88-136">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="4fe88-137">Führen Sie dann DBCC CHECKDB mit der entsprechenden REPAIR-Klausel aus, um die Beschädigung zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="4fe88-137">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4fe88-138">Wenden Sie sich an Ihren primären Unterstützungsanbieter, bevor Sie diese Anweisung ausführen, wenn Sie nicht sicher sind, inwiefern sich die Verwendung von DBCC CHECKDB mit einer REPAIR-Klausel auf Ihre Daten auswirkt.</span><span class="sxs-lookup"><span data-stu-id="4fe88-138">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="4fe88-139">Wenn DBCC CHECKDB mit einer der REPAIR-Klauseln ausgeführt wird und das Problem nicht behebt, wenden Sie sich an Ihren primären Unterstützungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="4fe88-139">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="4fe88-140">Ergebnis der Ausführung von REPAIR-Optionen</span><span class="sxs-lookup"><span data-stu-id="4fe88-140">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="4fe88-141">Durch das Ausführen von REPAIR wird die IAM-Kette neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="4fe88-141">Running REPAIR will rebuild the IAM chain.</span></span> <span data-ttu-id="4fe88-142">REPAIR teilt die vorhandene IAM-Kette zunächst in zwei Hälften.</span><span class="sxs-lookup"><span data-stu-id="4fe88-142">REPAIR first splits the existing IAM chain in two halves.</span></span> <span data-ttu-id="4fe88-143">Die erste Hälfte der Kette endet mit IAM-Seite *P_ID1*.</span><span class="sxs-lookup"><span data-stu-id="4fe88-143">The first half of the chain will end with IAM page, *P_ID1*.</span></span> <span data-ttu-id="4fe88-144">Der Zeiger für die nächste Seite der Seite *P_ID1* wird auf (0:0) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4fe88-144">The next page pointer of the *P_ID1* page will be set to (0:0).</span></span> <span data-ttu-id="4fe88-145">Die zweite Hälfte der Kette beginnt mit IAM-Seite *P_ID2*.</span><span class="sxs-lookup"><span data-stu-id="4fe88-145">The second half of the chain will start with IAM page, *P_ID2*.</span></span> <span data-ttu-id="4fe88-146">Der Zeiger für die vorherige Seite der Seite *P_ID2* wird auf (0:0) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4fe88-146">The previous page pointer of the *P_ID2* page will be set to (0:0).</span></span>  
  
 <span data-ttu-id="4fe88-147">REPAIR verbindet dann die beiden Hälften der Kette und generiert die Sequenznummern für die IAM-Kette neu.</span><span class="sxs-lookup"><span data-stu-id="4fe88-147">REPAIR will then connect the two haves of the chain together and regenerate the sequence numbers for the IAM chain.</span></span> <span data-ttu-id="4fe88-148">Zuordnungen von IAM-Seiten, die nicht repariert werden können, werden aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="4fe88-148">Any IAM pages that cannot be repaired will be deallocated.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4fe88-149">Diese Reparatur führt möglicherweise zum Datenverlust.</span><span class="sxs-lookup"><span data-stu-id="4fe88-149">This repair may cause data loss.</span></span>  
  
  
