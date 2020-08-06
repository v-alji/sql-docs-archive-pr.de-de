---
title: MSSQLSERVER_2574 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2574 (Database Engine error)
ms.assetid: efba507a-b5ad-4f1d-b0c8-f73b663a0562
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 44fd103f8c651ca968ae997ae9c3d544b41cbf3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696870"
---
# <a name="mssqlserver_2574"></a><span data-ttu-id="a9db2-102">MSSQLSERVER_2574</span><span class="sxs-lookup"><span data-stu-id="a9db2-102">MSSQLSERVER_2574</span></span>
    
## <a name="details"></a><span data-ttu-id="a9db2-103">Details</span><span class="sxs-lookup"><span data-stu-id="a9db2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a9db2-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="a9db2-104">Product Name</span></span>|<span data-ttu-id="a9db2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a9db2-105">SQL Server</span></span>|  
|<span data-ttu-id="a9db2-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a9db2-106">Event ID</span></span>|<span data-ttu-id="a9db2-107">2574</span><span class="sxs-lookup"><span data-stu-id="a9db2-107">2574</span></span>|  
|<span data-ttu-id="a9db2-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="a9db2-108">Event Source</span></span>|<span data-ttu-id="a9db2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a9db2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a9db2-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="a9db2-110">Component</span></span>|<span data-ttu-id="a9db2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a9db2-111">SQLEngine</span></span>|  
|<span data-ttu-id="a9db2-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="a9db2-112">Symbolic Name</span></span>|<span data-ttu-id="a9db2-113">DBCC_EMPTY_INDEX_TREE_LEVEL_PAGE</span><span class="sxs-lookup"><span data-stu-id="a9db2-113">DBCC_EMPTY_INDEX_TREE_LEVEL_PAGE</span></span>|  
|<span data-ttu-id="a9db2-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="a9db2-114">Message Text</span></span>|<span data-ttu-id="a9db2-115">Tabellenfehler: Die Seite „P_ID“ ist in der Objekt-ID „O_ID“, Index-ID „I_ID“, Partitions-ID „PN_ID“ und Zuordnungseinheits-ID „A_ID“ (TYPE-Typ) leer.</span><span class="sxs-lookup"><span data-stu-id="a9db2-115">Table error: Page P_ID is empty in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="a9db2-116">Dies ist auf der LEVEL-Ebene der B-Struktur unzulässig.</span><span class="sxs-lookup"><span data-stu-id="a9db2-116">This is not permitted at level LEVEL of the B-tree.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a9db2-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="a9db2-117">Explanation</span></span>  
 <span data-ttu-id="a9db2-118">Eine Seite der B-Struktur über der Blattebene des angegebenen Indexes ist leer, hat also keine Zeilen.</span><span class="sxs-lookup"><span data-stu-id="a9db2-118">A B-tree page above the leaf level of the specified index is empty, that is it has no rows.</span></span> <span data-ttu-id="a9db2-119">Dieses Verhalten ist möglich für Seiten auf der Blattebene in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], war jedoch niemals möglich in Strukturebenen.</span><span class="sxs-lookup"><span data-stu-id="a9db2-119">This behavior is possible for leaf-level pages in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], but has never been possible in tree levels.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a9db2-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="a9db2-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="a9db2-121">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="a9db2-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="a9db2-122">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="a9db2-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="a9db2-123">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a9db2-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="a9db2-124">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a9db2-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="a9db2-125">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="a9db2-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="a9db2-126">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a9db2-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="a9db2-127">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="a9db2-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="a9db2-128">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="a9db2-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="a9db2-129">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="a9db2-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="a9db2-130">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="a9db2-130">Restore from Backup</span></span>  
 <span data-ttu-id="a9db2-131">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a9db2-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="a9db2-132">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="a9db2-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="a9db2-133">Führen Sie DBCC CHECKDB ohne eine REPAIR-Klausel aus, um das Ausmaß der Beschädigung festzustellen, falls keine fehlerfreie Sicherung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a9db2-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="a9db2-134">DBCC CHECKDB empfiehlt die Verwendung einer REPAIR-Klausel.</span><span class="sxs-lookup"><span data-stu-id="a9db2-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="a9db2-135">Führen Sie dann DBCC CHECKDB mit der entsprechenden REPAIR-Klausel aus, um die Beschädigung zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="a9db2-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="a9db2-136">Wenden Sie sich an Ihren primären Unterstützungsanbieter, bevor Sie diese Anweisung ausführen, wenn Sie nicht sicher sind, inwiefern sich die Verwendung von DBCC CHECKDB mit einer REPAIR-Klausel auf Ihre Daten auswirkt.</span><span class="sxs-lookup"><span data-stu-id="a9db2-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="a9db2-137">Wenn DBCC CHECKDB mit einer der REPAIR-Klauseln ausgeführt wird und das Problem nicht behebt, wenden Sie sich an Ihren primären Unterstützungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="a9db2-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="a9db2-138">Ergebnis der Ausführung von REPAIR-Optionen</span><span class="sxs-lookup"><span data-stu-id="a9db2-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="a9db2-139">DBCC wird den Index neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a9db2-139">DBCC will rebuild the index.</span></span>  
  
  
