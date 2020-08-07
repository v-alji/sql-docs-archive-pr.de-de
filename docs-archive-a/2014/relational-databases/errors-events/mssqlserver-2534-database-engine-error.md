---
title: MSSQLSERVER_2534 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2534 (Database Engine error)
ms.assetid: 121cf99d-0722-494c-be24-3369c1a0badc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 409c429f961cd8357bfa2e40663c33f3c1f2e36d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620921"
---
# <a name="mssqlserver_2534"></a><span data-ttu-id="68040-102">MSSQLSERVER_2534</span><span class="sxs-lookup"><span data-stu-id="68040-102">MSSQLSERVER_2534</span></span>
    
## <a name="details"></a><span data-ttu-id="68040-103">Details</span><span class="sxs-lookup"><span data-stu-id="68040-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="68040-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="68040-104">Product Name</span></span>|<span data-ttu-id="68040-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="68040-105">SQL Server</span></span>|  
|<span data-ttu-id="68040-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="68040-106">Event ID</span></span>|<span data-ttu-id="68040-107">2534</span><span class="sxs-lookup"><span data-stu-id="68040-107">2534</span></span>|  
|<span data-ttu-id="68040-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="68040-108">Event Source</span></span>|<span data-ttu-id="68040-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="68040-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="68040-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="68040-110">Component</span></span>|<span data-ttu-id="68040-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="68040-111">SQLEngine</span></span>|  
|<span data-ttu-id="68040-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="68040-112">Symbolic Name</span></span>|<span data-ttu-id="68040-113">DBCC_PAGE_ALLOCATED_TO_OTHER_OBJECT</span><span class="sxs-lookup"><span data-stu-id="68040-113">DBCC_PAGE_ALLOCATED_TO_OTHER_OBJECT</span></span>|  
|<span data-ttu-id="68040-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="68040-114">Message Text</span></span>|<span data-ttu-id="68040-115">Tabellenfehler: Seite P_ID!, die laut Header der Objekt-ID O_ID!, Index ID I_ID, Partitions-ID PN_ID, Zuordnungseinheits-ID A_ID (TYPE-Typ) zugeordnet ist, ist von einem anderen Objekt zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="68040-115">Table error: Page P_ID, whose header indicates it as being allocated to object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), is allocated by another object.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="68040-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="68040-116">Explanation</span></span>  
 <span data-ttu-id="68040-117">Der Header der Seite enthält die Zuordnungseinheits-ID *A_ID*. Die Seite wird jedoch von keiner der IAM-Seiten (Index Allocation Map) dieser Zuordnungseinheit zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="68040-117">The header of the page contains the allocation unit ID, *A_ID*, but none of the Index Allocation Map (IAM) pages of that allocation unit allocates the page.</span></span> <span data-ttu-id="68040-118">Deshalb enthält der Header der Seite die falsche Zuordnungseinheits-ID, und die Seite verfügt über einen übereinstimmenden MSSQLServer_2533-Fehler, der der Zuordnungseinheits-ID entspricht, der die Seite tatsächlich zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="68040-118">Therefore, the header of the page contains the wrong allocation unit ID, and the page will have a matching MSSQLServer_2533 error that corresponds to the allocation unit ID to which the page is actually allocated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="68040-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="68040-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="68040-120">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="68040-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="68040-121">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="68040-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="68040-122">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="68040-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="68040-123">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="68040-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="68040-124">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="68040-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="68040-125">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="68040-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="68040-126">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="68040-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="68040-127">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="68040-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="68040-128">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="68040-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="68040-129">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="68040-129">Restore from Backup</span></span>  
 <span data-ttu-id="68040-130">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="68040-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="68040-131">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="68040-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="68040-132">Führen Sie DBCC CHECKDB ohne eine REPAIR-Klausel aus, um das Ausmaß der Beschädigung festzustellen, falls keine fehlerfreie Sicherung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="68040-132">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="68040-133">DBCC CHECKDB empfiehlt die Verwendung einer REPAIR-Klausel.</span><span class="sxs-lookup"><span data-stu-id="68040-133">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="68040-134">Führen Sie dann DBCC CHECKDB mit der entsprechenden REPAIR-Klausel aus, um die Beschädigung zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="68040-134">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="68040-135">Wenden Sie sich an Ihren primären Unterstützungsanbieter, bevor Sie diese Anweisung ausführen, wenn Sie nicht sicher sind, inwiefern sich die Verwendung von DBCC CHECKDB mit einer REPAIR-Klausel auf Ihre Daten auswirkt.</span><span class="sxs-lookup"><span data-stu-id="68040-135">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="68040-136">Wenn DBCC CHECKDB mit einer der REPAIR-Klauseln ausgeführt wird und das Problem nicht behebt, wenden Sie sich an Ihren primären Unterstützungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="68040-136">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="68040-137">Ergebnis der Ausführung von REPAIR-Optionen</span><span class="sxs-lookup"><span data-stu-id="68040-137">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="68040-138">REPAIR erstellt den Index neu, wenn ein Index vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="68040-138">REPAIR will rebuild the index if an index exists.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="68040-139">Durch das Ausführen von REPAIR für den übereinstimmenden [MSSQLSERVER_2533](mssqlserver-2533-database-engine-error.md)-Fehler wird die Zuordnung der Seite vor dem erneuten Build aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="68040-139">Running REPAIR for the matching [MSSQLSERVER_2533](mssqlserver-2533-database-engine-error.md) error deallocates the page before the rebuild.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="68040-140">Diese Reparatur führt möglicherweise zum Datenverlust.</span><span class="sxs-lookup"><span data-stu-id="68040-140">This repair may cause data loss.</span></span>  
  
  
