---
title: MSSQLSERVER_7987 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7987 (Database Engine error)
ms.assetid: 314aebf1-6cdf-488d-a274-ce967fadb57b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2fec3cf707e2e9923084f48096a88c60655513e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701217"
---
# <a name="mssqlserver_7987"></a><span data-ttu-id="7f7b5-102">MSSQLSERVER_7987</span><span class="sxs-lookup"><span data-stu-id="7f7b5-102">MSSQLSERVER_7987</span></span>
    
## <a name="details"></a><span data-ttu-id="7f7b5-103">Details</span><span class="sxs-lookup"><span data-stu-id="7f7b5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7f7b5-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="7f7b5-104">Product Name</span></span>|<span data-ttu-id="7f7b5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7f7b5-105">SQL Server</span></span>|  
|<span data-ttu-id="7f7b5-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="7f7b5-106">Event ID</span></span>|<span data-ttu-id="7f7b5-107">7987</span><span class="sxs-lookup"><span data-stu-id="7f7b5-107">7987</span></span>|  
|<span data-ttu-id="7f7b5-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="7f7b5-108">Event Source</span></span>|<span data-ttu-id="7f7b5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7f7b5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7f7b5-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="7f7b5-110">Component</span></span>|<span data-ttu-id="7f7b5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7f7b5-111">SQLEngine</span></span>|  
|<span data-ttu-id="7f7b5-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="7f7b5-112">Symbolic Name</span></span>|<span data-ttu-id="7f7b5-113">DBCC2_PRE_CHECKS_CHAIN_LINKAGE_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="7f7b5-113">DBCC2_PRE_CHECKS_CHAIN_LINKAGE_MISMATCH</span></span>|  
|<span data-ttu-id="7f7b5-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="7f7b5-114">Message Text</span></span>|<span data-ttu-id="7f7b5-115">Vorabüberprüfungen für Systemtabelle: Die Objekt-ID O_ID d besitzt eine nicht übereinstimmende Kettenverknüpfung.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-115">System table pre-checks: Object ID O_ID has chain linkage mismatch.</span></span> <span data-ttu-id="7f7b5-116">P_ID1->next = P_ID2, aber P_ID2->prev = P_ID3.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-116">P_ID1->next = P_ID2, but P_ID2->prev = P_ID3.</span></span> <span data-ttu-id="7f7b5-117">Die CHECK-Anweisung wurde aufgrund eines irreparablen Fehlers beendet.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-117">Check statement terminated because of an irreparable error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7f7b5-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="7f7b5-118">Explanation</span></span>  
 <span data-ttu-id="7f7b5-119">Die erste Phase eines DBCC CHECKDB beinhaltet einfache Überprüfungen der Datenseiten kritischer Systemtabellen.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-119">The first phase of a DBCC CHECKDB is to do primitive checks on the data pages of critical system tables.</span></span> <span data-ttu-id="7f7b5-120">Gefundene Fehler können nicht repariert werden. Daher wird DBCC CHECKDB sofort beendet.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-120">If any errors are found, they cannot be repaired; therefore, the DBCC CHECKDB terminates immediately.</span></span>  
  
 <span data-ttu-id="7f7b5-121">Der Zeiger für die nächste Seite der Seite *P_ID1* zeigt auf die Seite *P_ID2*. Der Zeiger für die vorherige Seite von Seite *P_ID2* zeigt jedoch auf die Seite *P_ID3*, aber nicht zurück auf die Seite *P_ID1*, wie er es sollte.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-121">The next page pointer of page *P_ID1* points to page *P_ID2*; however, the previous page pointer of page *P_ID2* points to page *P_ID3* but not back to page *P_ID1*, as it should.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7f7b5-122">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="7f7b5-122">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="7f7b5-123">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="7f7b5-123">Look for Hardware Failure</span></span>  
 <span data-ttu-id="7f7b5-124">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-124">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="7f7b5-125">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-125">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="7f7b5-126">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-126">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="7f7b5-127">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-127">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="7f7b5-128">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-128">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="7f7b5-129">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-129">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="7f7b5-130">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-130">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="7f7b5-131">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-131">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="7f7b5-132">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="7f7b5-132">Restore from Backup</span></span>  
 <span data-ttu-id="7f7b5-133">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-133">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="7f7b5-134">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="7f7b5-134">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="7f7b5-135">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="7f7b5-135">Not applicable.</span></span> <span data-ttu-id="7f7b5-136">Dieser Fehler kann nicht automatisch repariert werden.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-136">This error cannot be repaired automatically.</span></span> <span data-ttu-id="7f7b5-137">Wenn Sie die Datenbank nicht von einer Sicherung wiederherstellen können, wenden Sie sich an den [!INCLUDE[msCoName](../../includes/msconame-md.md)] Support Services (CSS).</span><span class="sxs-lookup"><span data-stu-id="7f7b5-137">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service and Support (CSS).</span></span>  
  
  
