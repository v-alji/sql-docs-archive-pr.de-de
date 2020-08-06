---
title: MSSQLSERVER_8974 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8974 (Database Engine error)
ms.assetid: 52098678-0858-4a14-ad07-37ebbafca5fc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ff3107f5b62caf04e232532c2d2b93d5da19fb53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630657"
---
# <a name="mssqlserver_8974"></a><span data-ttu-id="4362c-102">MSSQLSERVER_8974</span><span class="sxs-lookup"><span data-stu-id="4362c-102">MSSQLSERVER_8974</span></span>
    
## <a name="details"></a><span data-ttu-id="4362c-103">Details</span><span class="sxs-lookup"><span data-stu-id="4362c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4362c-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="4362c-104">Product Name</span></span>|<span data-ttu-id="4362c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4362c-105">SQL Server</span></span>|  
|<span data-ttu-id="4362c-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="4362c-106">Event ID</span></span>|<span data-ttu-id="4362c-107">8974</span><span class="sxs-lookup"><span data-stu-id="4362c-107">8974</span></span>|  
|<span data-ttu-id="4362c-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="4362c-108">Event Source</span></span>|<span data-ttu-id="4362c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4362c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4362c-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="4362c-110">Component</span></span>|<span data-ttu-id="4362c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4362c-111">SQLEngine</span></span>|  
|<span data-ttu-id="4362c-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="4362c-112">Symbolic Name</span></span>|<span data-ttu-id="4362c-113">DBCC3_OFF_ROW_DATA_NODE_HAS_TWO_PARENTS</span><span class="sxs-lookup"><span data-stu-id="4362c-113">DBCC3_OFF_ROW_DATA_NODE_HAS_TWO_PARENTS</span></span>|  
|<span data-ttu-id="4362c-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="4362c-114">Message Text</span></span>|<span data-ttu-id="4362c-115">Tabellenfehler: Objekt-ID O_ID, Index-ID I_ID, Partitions-ID PN_ID, Zuordnungseinheits-ID A_ID (TYPE-Typ).</span><span class="sxs-lookup"><span data-stu-id="4362c-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="4362c-116">Auf den Datenknoten außerhalb von Zeilen auf Seite P_ID1, Slot S_ID1, Text-ID TEXT_ID wird von Seite P_ID2, Slot S_ID2 und von Seite P_ID3, Slot S_ID3 verwiesen.</span><span class="sxs-lookup"><span data-stu-id="4362c-116">The off-row data node at page P_ID1, slot S_ID1, text ID TEXT_ID is pointed to by page P_ID2, slot S_ID2 and by page P_ID3, slot P_ID3.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4362c-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="4362c-117">Explanation</span></span>  
 <span data-ttu-id="4362c-118">Ein Datenknoten außerhalb von Zeilen besitzt zwei Daten- oder Indexdatensätze, in denen er als untergeordneter Knoten aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="4362c-118">An off-row data node has two data or index records that list it as a child node.</span></span> <span data-ttu-id="4362c-119">Ein Knoten kann nur einen übergeordneten Knoten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4362c-119">A node can have only one parent node.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4362c-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="4362c-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="4362c-121">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="4362c-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="4362c-122">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="4362c-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="4362c-123">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4362c-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="4362c-124">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="4362c-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="4362c-125">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="4362c-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="4362c-126">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4362c-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="4362c-127">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="4362c-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="4362c-128">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="4362c-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="4362c-129">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="4362c-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="4362c-130">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="4362c-130">Restore from Backup</span></span>  
 <span data-ttu-id="4362c-131">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4362c-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="4362c-132">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="4362c-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="4362c-133">Führen Sie DBCC CHECKDB ohne eine REPAIR-Klausel aus, um das Ausmaß der Beschädigung festzustellen, falls keine fehlerfreie Sicherung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="4362c-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="4362c-134">DBCC CHECKDB empfiehlt die Verwendung einer REPAIR-Klausel.</span><span class="sxs-lookup"><span data-stu-id="4362c-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="4362c-135">Führen Sie dann DBCC CHECKDB mit der entsprechenden REPAIR-Klausel aus, um die Beschädigung zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="4362c-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4362c-136">Wenden Sie sich an Ihren primären Unterstützungsanbieter, bevor Sie diese Anweisung ausführen, wenn Sie nicht sicher sind, inwiefern sich die Verwendung von DBCC CHECKDB mit einer REPAIR-Klausel auf Ihre Daten auswirkt.</span><span class="sxs-lookup"><span data-stu-id="4362c-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="4362c-137">Wenn DBCC CHECKDB mit einer der REPAIR-Klauseln ausgeführt wird und das Problem nicht behebt, wenden Sie sich an Ihren primären Unterstützungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="4362c-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
#### <a name="results-of-running-repair-options"></a><span data-ttu-id="4362c-138">Ergebnis der Ausführung von REPAIR-Optionen</span><span class="sxs-lookup"><span data-stu-id="4362c-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="4362c-139">Der Datenknoten außerhalb von Zeilen auf Seite *P_ID1* wird gelöscht, und beide Verweise auf den Seiten *P_ID2* und *P_ID3* werden ebenfalls gelöscht.</span><span class="sxs-lookup"><span data-stu-id="4362c-139">The off-row data node on page *P_ID1* will be deleted and both references on pages *P_ID2* and *P_ID3* will be deleted.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4362c-140">Diese Reparatur führt möglicherweise zu einem Datenverlust.</span><span class="sxs-lookup"><span data-stu-id="4362c-140">This repair might cause data loss.</span></span>  
  
  
