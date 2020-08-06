---
title: MSSQLSERVER_2575 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2575 (Database Engine error)
ms.assetid: 92dfe449-a122-4730-942b-e1d319862d20
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 461d2b57b5ace98ca624f8dc3717c98f3e9e4d67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608726"
---
# <a name="mssqlserver_2575"></a><span data-ttu-id="71ea3-102">MSSQLSERVER_2575</span><span class="sxs-lookup"><span data-stu-id="71ea3-102">MSSQLSERVER_2575</span></span>
    
## <a name="details"></a><span data-ttu-id="71ea3-103">Details</span><span class="sxs-lookup"><span data-stu-id="71ea3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="71ea3-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="71ea3-104">Product Name</span></span>|<span data-ttu-id="71ea3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="71ea3-105">SQL Server</span></span>|  
|<span data-ttu-id="71ea3-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="71ea3-106">Event ID</span></span>|<span data-ttu-id="71ea3-107">2575</span><span class="sxs-lookup"><span data-stu-id="71ea3-107">2575</span></span>|  
|<span data-ttu-id="71ea3-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="71ea3-108">Event Source</span></span>|<span data-ttu-id="71ea3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="71ea3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="71ea3-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="71ea3-110">Component</span></span>|<span data-ttu-id="71ea3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="71ea3-111">SQLEngine</span></span>|  
|<span data-ttu-id="71ea3-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="71ea3-112">Symbolic Name</span></span>|<span data-ttu-id="71ea3-113">DBCC_IAM_PAGE_WAS_NOT_SEEN</span><span class="sxs-lookup"><span data-stu-id="71ea3-113">DBCC_IAM_PAGE_WAS_NOT_SEEN</span></span>|  
|<span data-ttu-id="71ea3-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="71ea3-114">Message Text</span></span>|<span data-ttu-id="71ea3-115">Auf die IAM-Seite P_ID1 zeigt der Zeiger für die nächste Seite der IAM-Seite P_ID2 in Objekt-ID O_ID, Index-ID I_ID, Partitions-ID PN_ID, Zuordnungseinheits-ID A_ID (TYPE-Typ), sie wurde jedoch im Scan nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="71ea3-115">IAM page P_ID1 is pointed to by the next pointer of IAM page P_ID2 in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) but was not detected in the scan.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="71ea3-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="71ea3-116">Explanation</span></span>  
 <span data-ttu-id="71ea3-117">Eine IAM-Seite (Index Allocation Map) wurde für den angegebenen Index gefunden. Die IAM-Seite für den Zeiger der nächsten Seite wurde jedoch nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="71ea3-117">An Index Allocation Map (IAM) page was found for the specified index; however, the IAM page for its next-page pointer was not found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="71ea3-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="71ea3-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="71ea3-119">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="71ea3-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="71ea3-120">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="71ea3-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="71ea3-121">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="71ea3-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="71ea3-122">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="71ea3-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="71ea3-123">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="71ea3-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="71ea3-124">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="71ea3-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="71ea3-125">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="71ea3-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="71ea3-126">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="71ea3-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="71ea3-127">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="71ea3-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="71ea3-128">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="71ea3-128">Restore from Backup</span></span>  
 <span data-ttu-id="71ea3-129">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="71ea3-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="71ea3-130">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="71ea3-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="71ea3-131">Führen Sie DBCC CHECKDB ohne eine REPAIR-Klausel aus, um das Ausmaß der Beschädigung festzustellen, falls keine fehlerfreie Sicherung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="71ea3-131">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="71ea3-132">DBCC CHECKDB empfiehlt die Verwendung einer REPAIR-Klausel.</span><span class="sxs-lookup"><span data-stu-id="71ea3-132">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="71ea3-133">Führen Sie dann DBCC CHECKDB mit der entsprechenden REPAIR-Klausel aus, um die Beschädigung zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="71ea3-133">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="71ea3-134">Wenden Sie sich an Ihren primären Unterstützungsanbieter, bevor Sie diese Anweisung ausführen, wenn Sie nicht sicher sind, inwiefern sich die Verwendung von DBCC CHECKDB mit einer REPAIR-Klausel auf Ihre Daten auswirkt.</span><span class="sxs-lookup"><span data-stu-id="71ea3-134">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="71ea3-135">Wenn DBCC CHECKDB mit einer der REPAIR-Klauseln ausgeführt wird und das Problem nicht behebt, wenden Sie sich an Ihren primären Unterstützungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="71ea3-135">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
#### <a name="results-of-running-repair-options"></a><span data-ttu-id="71ea3-136">Ergebnis der Ausführung von REPAIR-Optionen</span><span class="sxs-lookup"><span data-stu-id="71ea3-136">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="71ea3-137">DBCC wird den Index neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="71ea3-137">DBCC will rebuild the index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71ea3-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="71ea3-138">See Also</span></span>  
 [<span data-ttu-id="71ea3-139">DBCC CHECKDB &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="71ea3-139">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
