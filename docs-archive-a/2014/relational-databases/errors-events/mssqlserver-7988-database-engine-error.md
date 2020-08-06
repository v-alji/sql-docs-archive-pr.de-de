---
title: MSSQLSERVER_7988 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7988 (Database Engine error)
ms.assetid: 29b967b8-de30-4618-99a8-8b1155e69026
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 984cb03aeb5feaa230762e200304f16cd8c5df08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699615"
---
# <a name="mssqlserver_7988"></a><span data-ttu-id="275d0-102">MSSQLSERVER_7988</span><span class="sxs-lookup"><span data-stu-id="275d0-102">MSSQLSERVER_7988</span></span>
    
## <a name="details"></a><span data-ttu-id="275d0-103">Details</span><span class="sxs-lookup"><span data-stu-id="275d0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="275d0-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="275d0-104">Product Name</span></span>|<span data-ttu-id="275d0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="275d0-105">SQL Server</span></span>|  
|<span data-ttu-id="275d0-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="275d0-106">Event ID</span></span>|<span data-ttu-id="275d0-107">7988</span><span class="sxs-lookup"><span data-stu-id="275d0-107">7988</span></span>|  
|<span data-ttu-id="275d0-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="275d0-108">Event Source</span></span>|<span data-ttu-id="275d0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="275d0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="275d0-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="275d0-110">Component</span></span>|<span data-ttu-id="275d0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="275d0-111">SQLEngine</span></span>|  
|<span data-ttu-id="275d0-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="275d0-112">Symbolic Name</span></span>|<span data-ttu-id="275d0-113">DBCC2_PRE_CHECKS_CHAIN_LOOP_DETECTED</span><span class="sxs-lookup"><span data-stu-id="275d0-113">DBCC2_PRE_CHECKS_CHAIN_LOOP_DETECTED</span></span>|  
|<span data-ttu-id="275d0-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="275d0-114">Message Text</span></span>|<span data-ttu-id="275d0-115">Vorabüberprüfungen für Systemtabelle: Objekt-ID O_ID.</span><span class="sxs-lookup"><span data-stu-id="275d0-115">System table pre-checks: Object ID O_ID.</span></span> <span data-ttu-id="275d0-116">Bei P_ID wurde eine Schleife in der Datenkette erkannt.</span><span class="sxs-lookup"><span data-stu-id="275d0-116">Loop in data chain detected at P_ID.</span></span> <span data-ttu-id="275d0-117">Die CHECK-Anweisung wurde aufgrund eines irreparablen Fehlers beendet.</span><span class="sxs-lookup"><span data-stu-id="275d0-117">Check statement terminated because of an irreparable error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="275d0-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="275d0-118">Explanation</span></span>  
 <span data-ttu-id="275d0-119">Die erste Phase eines DBCC CHECKDB beinhaltet einfache Überprüfungen der Datenseiten kritischer Systemtabellen.</span><span class="sxs-lookup"><span data-stu-id="275d0-119">The first phase of a DBCC CHECKDB is to do primitive checks on the data pages of critical system tables.</span></span> <span data-ttu-id="275d0-120">Wenn Fehler gefunden werden, können sie nicht repariert werden. Daher wird DBCC CHECKDB sofort beendet.</span><span class="sxs-lookup"><span data-stu-id="275d0-120">If any errors are found, they cannot be repaired; therefore, DBCC CHECKDB terminates immediately.</span></span> <span data-ttu-id="275d0-121">Eine Seitenverknüpfungsschleife wurde auf der Seite *P_ID* erkannt.</span><span class="sxs-lookup"><span data-stu-id="275d0-121">A page linkage loop has been detected on page *P_ID*.</span></span> <span data-ttu-id="275d0-122">Eine Seitenverknüpfungsschleife tritt auf, wenn der Zeiger für die nächste Seite einer Seite wieder zu der Seite zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="275d0-122">A page linkage loop occurs when the next page pointers from a page eventually return to the page.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="275d0-123">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="275d0-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="275d0-124">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="275d0-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="275d0-125">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="275d0-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="275d0-126">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="275d0-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="275d0-127">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="275d0-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="275d0-128">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="275d0-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="275d0-129">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="275d0-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="275d0-130">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="275d0-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="275d0-131">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="275d0-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="275d0-132">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="275d0-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="275d0-133">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="275d0-133">Restore from Backup</span></span>  
 <span data-ttu-id="275d0-134">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="275d0-134">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="275d0-135">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="275d0-135">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="275d0-136">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="275d0-136">Not applicable.</span></span> <span data-ttu-id="275d0-137">Dieser Fehler kann nicht automatisch repariert werden.</span><span class="sxs-lookup"><span data-stu-id="275d0-137">This error cannot be repaired automatically.</span></span> <span data-ttu-id="275d0-138">Wenn Sie die Datenbank nicht von einer Sicherung wiederherstellen können, wenden Sie sich an den [!INCLUDE[msCoName](../../includes/msconame-md.md)] Support Services (CSS).</span><span class="sxs-lookup"><span data-stu-id="275d0-138">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service and Support (CSS).</span></span>  
  
  
