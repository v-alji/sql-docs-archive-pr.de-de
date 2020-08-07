---
title: MSSQLSERVER_2579 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2579 (Database Engine error)
ms.assetid: 8f929d69-8eb4-4fe9-be52-b9680a7820db
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e68cd090ff9d20b14b3456dcda66496fc2bc02d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620904"
---
# <a name="mssqlserver_2579"></a><span data-ttu-id="6a0b8-102">MSSQLSERVER_2579</span><span class="sxs-lookup"><span data-stu-id="6a0b8-102">MSSQLSERVER_2579</span></span>
    
## <a name="details"></a><span data-ttu-id="6a0b8-103">Details</span><span class="sxs-lookup"><span data-stu-id="6a0b8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6a0b8-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="6a0b8-104">Product Name</span></span>|<span data-ttu-id="6a0b8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6a0b8-105">SQL Server</span></span>|  
|<span data-ttu-id="6a0b8-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="6a0b8-106">Event ID</span></span>|<span data-ttu-id="6a0b8-107">2579</span><span class="sxs-lookup"><span data-stu-id="6a0b8-107">2579</span></span>|  
|<span data-ttu-id="6a0b8-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="6a0b8-108">Event Source</span></span>|<span data-ttu-id="6a0b8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6a0b8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6a0b8-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="6a0b8-110">Component</span></span>|<span data-ttu-id="6a0b8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6a0b8-111">SQLEngine</span></span>|  
|<span data-ttu-id="6a0b8-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="6a0b8-112">Symbolic Name</span></span>|<span data-ttu-id="6a0b8-113">DBCC_EXTENT_OUT_OF_RANGE</span><span class="sxs-lookup"><span data-stu-id="6a0b8-113">DBCC_EXTENT_OUT_OF_RANGE</span></span>|  
|<span data-ttu-id="6a0b8-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="6a0b8-114">Message Text</span></span>|<span data-ttu-id="6a0b8-115">Tabellenfehler: Block P_ID in Objekt-ID O_ID, Index-ID I_ID, Partitions-ID PN_ID, Zuordnungseinheits-ID A_ID (TYPE-Typ) liegt außerhalb des gültigen Bereichs für diese Datenbank.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-115">Table error: Extent P_ID in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) is beyond the range of this database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6a0b8-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="6a0b8-116">Explanation</span></span>  
 <span data-ttu-id="6a0b8-117">*P_ID* ist eine Seiten-ID im Format *(filenum:pageinfile)* .</span><span class="sxs-lookup"><span data-stu-id="6a0b8-117">*P_ID* is a PageID of the form *(filenum:pageinfile)*.</span></span> <span data-ttu-id="6a0b8-118">Die *pageinfile* dieses Blocks ist größer als die physische Größe der Datei (*filenum)* der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-118">The *pageinfile* of this extent is greater than the physical size of the file (*filenum)* of the database.</span></span> <span data-ttu-id="6a0b8-119">Der Block wird als in einer IAM-Seite für die angegebene Zuordnungseinheits-ID zugeordnet markiert.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-119">The extent is marked as being allocated in an IAM page for the indicated allocation unit ID.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6a0b8-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="6a0b8-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="6a0b8-121">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="6a0b8-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="6a0b8-122">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="6a0b8-123">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="6a0b8-124">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="6a0b8-125">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="6a0b8-126">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="6a0b8-127">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="6a0b8-128">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="6a0b8-129">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="6a0b8-130">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="6a0b8-130">Restore from Backup</span></span>  
 <span data-ttu-id="6a0b8-131">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="6a0b8-132">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="6a0b8-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="6a0b8-133">Führen Sie DBCC CHECKDB ohne eine REPAIR-Klausel aus, um das Ausmaß der Beschädigung festzustellen, falls keine fehlerfreie Sicherung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="6a0b8-134">DBCC CHECKDB empfiehlt die Verwendung einer REPAIR-Klausel.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="6a0b8-135">Führen Sie dann DBCC CHECKDB mit der entsprechenden REPAIR-Klausel aus, um die Beschädigung zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="6a0b8-136">Wenden Sie sich an Ihren primären Unterstützungsanbieter, bevor Sie diese Anweisung ausführen, wenn Sie nicht sicher sind, inwiefern sich die Verwendung von DBCC CHECKDB mit einer REPAIR-Klausel auf Ihre Daten auswirkt.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="6a0b8-137">Wenn DBCC CHECKDB mit einer der REPAIR-Klauseln ausgeführt wird und das Problem nicht behebt, wenden Sie sich an Ihren primären Unterstützungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="6a0b8-138">Ergebnis der Ausführung von REPAIR-Optionen</span><span class="sxs-lookup"><span data-stu-id="6a0b8-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="6a0b8-139">Durch Ausführen von REPAIR wird die Zuordnung des Blocks zur IAM-Seite aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-139">Running REPAIR will cause the extent to be deallocated from the IAM page.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="6a0b8-140">Diese Reparatur führt möglicherweise zum Datenverlust.</span><span class="sxs-lookup"><span data-stu-id="6a0b8-140">This repair may cause data loss.</span></span>  
  
  
