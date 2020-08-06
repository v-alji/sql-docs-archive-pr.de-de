---
title: MSSQLSERVER_7986 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7986 (Database Engine error)
ms.assetid: ae64276c-4e1e-4ef3-9ee9-ebeb2f61e565
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4f7d312987a2692c95f2cf6dbe0c86a4b2acbe6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718151"
---
# <a name="mssqlserver_7986"></a><span data-ttu-id="c5fd4-102">MSSQLSERVER_7986</span><span class="sxs-lookup"><span data-stu-id="c5fd4-102">MSSQLSERVER_7986</span></span>
    
## <a name="details"></a><span data-ttu-id="c5fd4-103">Details</span><span class="sxs-lookup"><span data-stu-id="c5fd4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c5fd4-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="c5fd4-104">Product Name</span></span>|<span data-ttu-id="c5fd4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c5fd4-105">SQL Server</span></span>|  
|<span data-ttu-id="c5fd4-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c5fd4-106">Event ID</span></span>|<span data-ttu-id="c5fd4-107">7986</span><span class="sxs-lookup"><span data-stu-id="c5fd4-107">7986</span></span>|  
|<span data-ttu-id="c5fd4-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="c5fd4-108">Event Source</span></span>|<span data-ttu-id="c5fd4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c5fd4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c5fd4-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="c5fd4-110">Component</span></span>|<span data-ttu-id="c5fd4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c5fd4-111">SQLEngine</span></span>|  
|<span data-ttu-id="c5fd4-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="c5fd4-112">Symbolic Name</span></span>|<span data-ttu-id="c5fd4-113">DBCC2_PRE_CHECKS_CROSS_OBJECT_LINKAGE</span><span class="sxs-lookup"><span data-stu-id="c5fd4-113">DBCC2_PRE_CHECKS_CROSS_OBJECT_LINKAGE</span></span>|  
|<span data-ttu-id="c5fd4-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="c5fd4-114">Message Text</span></span>|<span data-ttu-id="c5fd4-115">Vorabüberprüfungen für Systemtabelle: Die Objekt-ID „O_ID“ besitzt eine objektübergreifende Kettenverknüpfung.</span><span class="sxs-lookup"><span data-stu-id="c5fd4-115">System table pre-checks: Object ID O_ID has cross-object chain linkage.</span></span> <span data-ttu-id="c5fd4-116">Die Seite P_ID1 zeigt auf P_ID2 in der Zuordnungseinheit mit der ID A_ID1 (sollte A_ID2 sein).</span><span class="sxs-lookup"><span data-stu-id="c5fd4-116">Page P_ID1 points to P_ID2 in alloc unit ID A_ID1 (should be A_ID2).</span></span> <span data-ttu-id="c5fd4-117">Die CHECK-Anweisung wurde aufgrund eines irreparablen Fehlers beendet.</span><span class="sxs-lookup"><span data-stu-id="c5fd4-117">Check statement terminated due to unrepairable error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c5fd4-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="c5fd4-118">Explanation</span></span>  
 <span data-ttu-id="c5fd4-119">Die erste Phase eines DBCC CHECKDB beinhaltet einfache Überprüfungen der Datenseiten kritischer Systemtabellen.</span><span class="sxs-lookup"><span data-stu-id="c5fd4-119">The first phase of a DBCC CHECKDB is to do primitive checks on the data pages of critical system tables.</span></span> <span data-ttu-id="c5fd4-120">Gefundene Fehler können nicht repariert werden. Daher wird DBCC CHECKDB sofort beendet.</span><span class="sxs-lookup"><span data-stu-id="c5fd4-120">If any errors are found, they cannot be repaired; therefore, the DBCC CHECKDB terminates immediately.</span></span> <span data-ttu-id="c5fd4-121">Der Zeiger für die nächste Seite *P_ID1* in der Datenebene des angegebenen Objekts verweist auf die Seite *P_ID2* in einem anderen Objekt.</span><span class="sxs-lookup"><span data-stu-id="c5fd4-121">The next page pointer of page *P_ID1* in the data level of the specified object points to a page, *P_ID2*, in a different object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c5fd4-122">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="c5fd4-122">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="c5fd4-123">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="c5fd4-123">Look for Hardware Failure</span></span>  
 <span data-ttu-id="c5fd4-124">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="c5fd4-124">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="c5fd4-125">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c5fd4-125">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="c5fd4-126">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="c5fd4-126">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="c5fd4-127">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="c5fd4-127">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="c5fd4-128">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c5fd4-128">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="c5fd4-129">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="c5fd4-129">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="c5fd4-130">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="c5fd4-130">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="c5fd4-131">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="c5fd4-131">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="c5fd4-132">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="c5fd4-132">Restore from Backup</span></span>  
 <span data-ttu-id="c5fd4-133">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c5fd4-133">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="c5fd4-134">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="c5fd4-134">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="c5fd4-135">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c5fd4-135">Not applicable.</span></span> <span data-ttu-id="c5fd4-136">Dieser Fehler kann nicht automatisch repariert werden.</span><span class="sxs-lookup"><span data-stu-id="c5fd4-136">This error cannot be repaired automatically.</span></span> <span data-ttu-id="c5fd4-137">Wenn Sie die Datenbank nicht mithilfe einer Sicherung wiederherstellen können, wenden Sie sich an den Kundenservice und -support von [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5fd4-137">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
