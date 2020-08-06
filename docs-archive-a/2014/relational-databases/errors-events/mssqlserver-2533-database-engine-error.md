---
title: MSSQLSERVER_2533 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2533 (Database Engine error)
ms.assetid: 0418352c-0ab2-4dc7-b8b9-5c3bad94560c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1eb3e2780693a3a0ffed21ce7b9d7887615536c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699633"
---
# <a name="mssqlserver_2533"></a><span data-ttu-id="f46aa-102">MSSQLSERVER_2533</span><span class="sxs-lookup"><span data-stu-id="f46aa-102">MSSQLSERVER_2533</span></span>
    
## <a name="details"></a><span data-ttu-id="f46aa-103">Details</span><span class="sxs-lookup"><span data-stu-id="f46aa-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f46aa-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="f46aa-104">Product Name</span></span>|<span data-ttu-id="f46aa-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f46aa-105">SQL Server</span></span>|  
|<span data-ttu-id="f46aa-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="f46aa-106">Event ID</span></span>|<span data-ttu-id="f46aa-107">2533</span><span class="sxs-lookup"><span data-stu-id="f46aa-107">2533</span></span>|  
|<span data-ttu-id="f46aa-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="f46aa-108">Event Source</span></span>|<span data-ttu-id="f46aa-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f46aa-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f46aa-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="f46aa-110">Component</span></span>|<span data-ttu-id="f46aa-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f46aa-111">SQLEngine</span></span>|  
|<span data-ttu-id="f46aa-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="f46aa-112">Symbolic Name</span></span>|<span data-ttu-id="f46aa-113">DBCC_PAGE_WAS_NOT_SEEN</span><span class="sxs-lookup"><span data-stu-id="f46aa-113">DBCC_PAGE_WAS_NOT_SEEN</span></span>|  
|<span data-ttu-id="f46aa-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="f46aa-114">Message Text</span></span>|<span data-ttu-id="f46aa-115">Tabellenfehler: Der Objekt-ID „O_ID“ zugeordnete Seite „P_ID“, Index-ID „I_ID“, Partitions-ID „PN_ID“ und Zuordnungseinheits-ID „A_ID“ (TYPE-Typ) nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="f46aa-115">Table error: Page P_ID allocated to object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) was not seen.</span></span> <span data-ttu-id="f46aa-116">Die Seite ist möglicherweise ungültig oder enthält eine falsche Zuordnungseinheits-ID im Header.</span><span class="sxs-lookup"><span data-stu-id="f46aa-116">Page may be invalid or have incorrect alloc unit ID in its header.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f46aa-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="f46aa-117">Explanation</span></span>  
 <span data-ttu-id="f46aa-118">Eine Seite wird der Zuordnungseinheits-ID *A_ID* zugeordnet, aber diese Zuordnungseinheits-ID befindet sich nicht im Header der Seite.</span><span class="sxs-lookup"><span data-stu-id="f46aa-118">A page is allocated to the allocation unit ID, *A_ID*, but this allocation unit ID is not in the header of the page.</span></span> <span data-ttu-id="f46aa-119">Der Header hat eine andere Zuordnungseinheits-ID.</span><span class="sxs-lookup"><span data-stu-id="f46aa-119">The header has a different allocation unit ID.</span></span> <span data-ttu-id="f46aa-120">Wenn die Zuordnungseinheits-ID im Header der Seite einem gültigen Objekt zugewiesen ist, tritt für die Seite möglicherweise ein entsprechender MSSQLEngine_2534-Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="f46aa-120">If the allocation unit ID in the header of the page is for a valid object, the page may have a matching MSSQLEngine_2534 error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f46aa-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="f46aa-121">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="f46aa-122">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="f46aa-122">Look for Hardware Failure</span></span>  
 <span data-ttu-id="f46aa-123">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="f46aa-123">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="f46aa-124">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="f46aa-124">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="f46aa-125">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="f46aa-125">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="f46aa-126">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="f46aa-126">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="f46aa-127">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f46aa-127">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="f46aa-128">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="f46aa-128">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="f46aa-129">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="f46aa-129">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="f46aa-130">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="f46aa-130">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="f46aa-131">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="f46aa-131">Restore from Backup</span></span>  
 <span data-ttu-id="f46aa-132">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f46aa-132">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="f46aa-133">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="f46aa-133">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="f46aa-134">Führen Sie DBCC CHECKDB ohne eine REPAIR-Klausel aus, um das Ausmaß der Beschädigung festzustellen, falls keine fehlerfreie Sicherung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="f46aa-134">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="f46aa-135">DBCC CHECKDB empfiehlt die Verwendung einer REPAIR-Klausel.</span><span class="sxs-lookup"><span data-stu-id="f46aa-135">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="f46aa-136">Führen Sie dann DBCC CHECKDB mit der entsprechenden REPAIR-Klausel aus, um die Beschädigung zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="f46aa-136">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="f46aa-137">Wenden Sie sich an Ihren primären Unterstützungsanbieter, bevor Sie diese Anweisung ausführen, wenn Sie nicht sicher sind, inwiefern sich die Verwendung von DBCC CHECKDB mit einer REPAIR-Klausel auf Ihre Daten auswirkt.</span><span class="sxs-lookup"><span data-stu-id="f46aa-137">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="f46aa-138">Wenn DBCC CHECKDB mit einer der REPAIR-Klauseln ausgeführt wird und das Problem nicht behebt, wenden Sie sich an Ihren primären Unterstützungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="f46aa-138">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="f46aa-139">Ergebnis der Ausführung von REPAIR-Optionen</span><span class="sxs-lookup"><span data-stu-id="f46aa-139">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="f46aa-140">REPAIR hebt die Zuordnung der Seite auf.</span><span class="sxs-lookup"><span data-stu-id="f46aa-140">REPAIR will deallocate the page.</span></span> <span data-ttu-id="f46aa-141">Wenn die Seite aus einer Zuordnungseinheit für Daten in Zeilen stammte, wird der Index, falls vorhanden, neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="f46aa-141">If the page was from an in-row data allocation unit, the index, if one exists, will be rebuilt.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="f46aa-142">Diese Reparatur führt möglicherweise zum Datenverlust.</span><span class="sxs-lookup"><span data-stu-id="f46aa-142">This repair may cause data loss.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f46aa-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f46aa-143">See Also</span></span>  
 [<span data-ttu-id="f46aa-144">MSSQLSERVER_2534</span><span class="sxs-lookup"><span data-stu-id="f46aa-144">MSSQLSERVER_2534</span></span>](mssqlserver-2534-database-engine-error.md)  
  
  
