---
title: MSSQLSERVER_7984 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7984 (Database Engine error)
ms.assetid: e3192f56-e4e2-41da-b132-65f1e7540b1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c7f92fe4f3751621e0cc636ffcd2d4de73b348d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620424"
---
# <a name="mssqlserver_7984"></a><span data-ttu-id="cb187-102">MSSQLSERVER_7984</span><span class="sxs-lookup"><span data-stu-id="cb187-102">MSSQLSERVER_7984</span></span>
    
## <a name="details"></a><span data-ttu-id="cb187-103">Details</span><span class="sxs-lookup"><span data-stu-id="cb187-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cb187-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="cb187-104">Product Name</span></span>|<span data-ttu-id="cb187-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cb187-105">SQL Server</span></span>|  
|<span data-ttu-id="cb187-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="cb187-106">Event ID</span></span>|<span data-ttu-id="cb187-107">7984</span><span class="sxs-lookup"><span data-stu-id="cb187-107">7984</span></span>|  
|<span data-ttu-id="cb187-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="cb187-108">Event Source</span></span>|<span data-ttu-id="cb187-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cb187-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cb187-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="cb187-110">Component</span></span>|<span data-ttu-id="cb187-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cb187-111">SQLEngine</span></span>|  
|<span data-ttu-id="cb187-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="cb187-112">Symbolic Name</span></span>|<span data-ttu-id="cb187-113">DBCC2_PRE_CHECKS_BAD_PAGE_TYPE</span><span class="sxs-lookup"><span data-stu-id="cb187-113">DBCC2_PRE_CHECKS_BAD_PAGE_TYPE</span></span>|  
|<span data-ttu-id="cb187-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="cb187-114">Message Text</span></span>|<span data-ttu-id="cb187-115">Vorabüberprüfungen für Systemtabelle: Objekt-ID O_ID.</span><span class="sxs-lookup"><span data-stu-id="cb187-115">System table pre-checks: Object ID O_ID.</span></span> <span data-ttu-id="cb187-116">Die Seite P_ID hat den unerwarteten Seitentyp PAGETYPE.</span><span class="sxs-lookup"><span data-stu-id="cb187-116">Page P_ID has unexpected page type PAGETYPE.</span></span> <span data-ttu-id="cb187-117">Die CHECK-Anweisung wurde aufgrund eines irreparablen Fehlers beendet.</span><span class="sxs-lookup"><span data-stu-id="cb187-117">Check statement terminated because of an irreparable error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cb187-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="cb187-118">Explanation</span></span>  
 <span data-ttu-id="cb187-119">Eine Seite eines anderen Typs als DATA_PAGE wurde auf der Datenebene des angegebenen Objekts gefunden.</span><span class="sxs-lookup"><span data-stu-id="cb187-119">A page with a type other than DATA_PAGE was found in the data level of the specified object.</span></span> <span data-ttu-id="cb187-120">Dieser Fehler wird während der ersten Phase der Überprüfungen durch den Befehl DBCC CHECKDB ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="cb187-120">This error is raised during the first phase of the DBCC CHECKDB command checks.</span></span> <span data-ttu-id="cb187-121">Während dieser Phase führt DBCC CHECKDB einfache Überprüfungen auf den Datenseiten kritischer Systembasistabellen aus.</span><span class="sxs-lookup"><span data-stu-id="cb187-121">During this phase, DBCC CHECKDB performs primitive checks on the data pages of critical system base tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cb187-122">Wenn Fehler in den Systemtabellen gefunden werden, können diese nicht behoben werden. Deshalb wird der Befehl DBCC CHECKDB sofort beendet.</span><span class="sxs-lookup"><span data-stu-id="cb187-122">If any errors are found in the system tables, the errors cannot be repaired; therefore, the DBCC CHECKDB command ends immediately.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cb187-123">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="cb187-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="cb187-124">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="cb187-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="cb187-125">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="cb187-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="cb187-126">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="cb187-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="cb187-127">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="cb187-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="cb187-128">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="cb187-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="cb187-129">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="cb187-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="cb187-130">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="cb187-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="cb187-131">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="cb187-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="cb187-132">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="cb187-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="cb187-133">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="cb187-133">Restore from Backup</span></span>  
 <span data-ttu-id="cb187-134">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="cb187-134">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="cb187-135">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="cb187-135">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="cb187-136">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="cb187-136">Not applicable.</span></span> <span data-ttu-id="cb187-137">Dieser Fehler kann nicht automatisch repariert werden.</span><span class="sxs-lookup"><span data-stu-id="cb187-137">This error cannot be repaired automatically.</span></span> <span data-ttu-id="cb187-138">Wenn Sie die Datenbank nicht von einer Sicherung wiederherstellen können, wenden Sie sich an den [!INCLUDE[msCoName](../../includes/msconame-md.md)] Support Services (CSS).</span><span class="sxs-lookup"><span data-stu-id="cb187-138">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service and Support (CSS).</span></span>  
  
  
