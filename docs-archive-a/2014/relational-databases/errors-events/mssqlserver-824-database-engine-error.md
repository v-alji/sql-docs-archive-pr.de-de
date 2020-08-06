---
title: MSSQLSERVER_824 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 824 (Database Engine error)
ms.assetid: 2aa22246-2712-4fdb-9744-36e7e6f3175e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d57b19bc8c837b92b65728fbb0046039b862d31a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617991"
---
# <a name="mssqlserver_824"></a><span data-ttu-id="27de4-102">MSSQLSERVER_824</span><span class="sxs-lookup"><span data-stu-id="27de4-102">MSSQLSERVER_824</span></span>
    
## <a name="details"></a><span data-ttu-id="27de4-103">Details</span><span class="sxs-lookup"><span data-stu-id="27de4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="27de4-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="27de4-104">Product Name</span></span>|<span data-ttu-id="27de4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="27de4-105">SQL Server</span></span>|  
|<span data-ttu-id="27de4-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="27de4-106">Event ID</span></span>|<span data-ttu-id="27de4-107">824</span><span class="sxs-lookup"><span data-stu-id="27de4-107">824</span></span>|  
|<span data-ttu-id="27de4-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="27de4-108">Event Source</span></span>|<span data-ttu-id="27de4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="27de4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="27de4-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="27de4-110">Component</span></span>|<span data-ttu-id="27de4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="27de4-111">SQLEngine</span></span>|  
|<span data-ttu-id="27de4-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="27de4-112">Symbolic Name</span></span>|<span data-ttu-id="27de4-113">B_HARDSSERR</span><span class="sxs-lookup"><span data-stu-id="27de4-113">B_HARDSSERR</span></span>|  
|<span data-ttu-id="27de4-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="27de4-114">Message Text</span></span>|<span data-ttu-id="27de4-115">SQL Server hat einen logischen, konsistenzbasierten E/A-Fehler gefunden: %ls</span><span class="sxs-lookup"><span data-stu-id="27de4-115">SQL Server detected a logical consistency-based I/O error: %ls.</span></span> <span data-ttu-id="27de4-116">Der Fehler ist beim %S_MSG von Seite %S_PGID in der Datenbank mit der ID %d bei Offset %#016I64x in der Datei '%ls' aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="27de4-116">It occurred during a %S_MSG of page %S_PGID in database ID %d at offset %#016I64x in file '%ls'.</span></span>  <span data-ttu-id="27de4-117">Weitere Informationen finden Sie möglicherweise in anderen Fehlermeldungen im SQL Server-Fehlerprotokoll oder im Systemereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="27de4-117">Additional messages in the SQL Server error log or system event log may provide more detail.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="27de4-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="27de4-118">Explanation</span></span>  
 <span data-ttu-id="27de4-119">Mit diesem Fehler wird angegeben, dass in Windows eine Meldung ausgegeben wurde, gemäß der die Seite erfolgreich vom Datenträger gelesen, aber in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ein Fehler auf der Seite festgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="27de4-119">This error indicates that Windows reports that the page is successfully read from disk, but [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has discovered something wrong with the page.</span></span> <span data-ttu-id="27de4-120">Dieser Fehler ist mit dem Fehler 823 vergleichbar, nur wurde er nicht von Windows erkannt.</span><span class="sxs-lookup"><span data-stu-id="27de4-120">This error is similar to error 823 except that Windows did not detect the error.</span></span> <span data-ttu-id="27de4-121">Dies führt in der Regel zu einem Problem im E/A-Subsystem. Dazu gehören beispielsweise der Ausfall von Festplattenlaufwerken, Firmwareprobleme auf Datenträgern, fehlerhafte Gerätetreiber usw.</span><span class="sxs-lookup"><span data-stu-id="27de4-121">This usually indicates a problem in the I/O subsystem, such as a failing disk drive, disk firmware problems, faulty device driver, and so on.</span></span> <span data-ttu-id="27de4-122">Weitere Informationen zu E/A-Fehlern finden Sie unter [Microsoft SQL Server I/O Basics, Chapter 2 (E/A-Grundlagen von Microsoft SQL Server, Kapitel 2)](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="27de4-122">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="27de4-123">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="27de4-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="27de4-124">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="27de4-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="27de4-125">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="27de4-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="27de4-126">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="27de4-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred because of hardware failure.</span></span> <span data-ttu-id="27de4-127">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="27de4-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="27de4-128">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="27de4-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="27de4-129">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="27de4-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="27de4-130">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="27de4-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="27de4-131">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="27de4-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="27de4-132">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="27de4-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="27de4-133">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="27de4-133">Restore from Backup</span></span>  
 <span data-ttu-id="27de4-134">Wenn das Problem nicht hardwarebedingt ist und eine bekanntermaßen fehlerfreie Sicherung zur Verfügung steht, stellen Sie die Datenbank mithilfe der Sicherung wieder her.</span><span class="sxs-lookup"><span data-stu-id="27de4-134">If the problem is not hardware-related and a known clean backup is available, restore the database from the backup.</span></span>  
  
 <span data-ttu-id="27de4-135">Ändern Sie die Datenbanken so, dass Sie die PAGE_VERIFY CHECKSUM-Option verwenden können.</span><span class="sxs-lookup"><span data-stu-id="27de4-135">Consider changing the databases to use the PAGE_VERIFY CHECKSUM option.</span></span> <span data-ttu-id="27de4-136">Weitere Informationen zu PAGE_VERIFY finden Sie unter [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="27de4-136">For information about PAGE_VERIFY, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27de4-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="27de4-137">See Also</span></span>  
 [<span data-ttu-id="27de4-138">Verwalten der suspect_pages-Tabelle &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="27de4-138">Manage the suspect_pages Table &#40;SQL Server&#41;</span></span>](../backup-restore/manage-the-suspect-pages-table-sql-server.md)  
  
  
