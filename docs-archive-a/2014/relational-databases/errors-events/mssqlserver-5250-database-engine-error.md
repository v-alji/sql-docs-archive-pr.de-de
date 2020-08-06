---
title: MSSQLSERVER_5250 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5250 (Database Engine error)
ms.assetid: f4a1d0e8-f27f-4cb8-a25d-040b40555dcc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ace26b88aca5b00c23aff3fe48f7c1d04ef35245
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718169"
---
# <a name="mssqlserver_5250"></a><span data-ttu-id="9817e-102">MSSQLSERVER_5250</span><span class="sxs-lookup"><span data-stu-id="9817e-102">MSSQLSERVER_5250</span></span>
    
## <a name="details"></a><span data-ttu-id="9817e-103">Details</span><span class="sxs-lookup"><span data-stu-id="9817e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9817e-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="9817e-104">Product Name</span></span>|<span data-ttu-id="9817e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9817e-105">SQL Server</span></span>|  
|<span data-ttu-id="9817e-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="9817e-106">Event ID</span></span>|<span data-ttu-id="9817e-107">5250</span><span class="sxs-lookup"><span data-stu-id="9817e-107">5250</span></span>|  
|<span data-ttu-id="9817e-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="9817e-108">Event Source</span></span>|<span data-ttu-id="9817e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9817e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9817e-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="9817e-110">Component</span></span>|<span data-ttu-id="9817e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9817e-111">SQLEngine</span></span>|  
|<span data-ttu-id="9817e-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="9817e-112">Symbolic Name</span></span>|<span data-ttu-id="9817e-113">DBCC4_CRITICAL_DATABASE_PAGE_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="9817e-113">DBCC4_CRITICAL_DATABASE_PAGE_CORRUPT</span></span>|  
|<span data-ttu-id="9817e-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="9817e-114">Message Text</span></span>|<span data-ttu-id="9817e-115">Datenbankfehler: Die PAGE_TYPE-Seite P_ID ist für die 'NAME'-Datenbank (Datenbank-ID DB_ID) ungültig.</span><span class="sxs-lookup"><span data-stu-id="9817e-115">Database error: PAGE_TYPE page P_ID for database 'NAME' (database ID DB_ID) is invalid.</span></span> <span data-ttu-id="9817e-116">Dieser Fehler kann nicht repariert werden.</span><span class="sxs-lookup"><span data-stu-id="9817e-116">This error cannot be repaired.</span></span> <span data-ttu-id="9817e-117">Sie müssen von einer Sicherungskopie wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="9817e-117">You must restore from backup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9817e-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="9817e-118">Explanation</span></span>  
 <span data-ttu-id="9817e-119">Eine Dateiheaderseite oder Startseite in der angegebenen Datenbank ist beschädigt.</span><span class="sxs-lookup"><span data-stu-id="9817e-119">A file header page or boot page in the specified database is corrupted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9817e-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="9817e-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="9817e-121">Hardwarefehlersuche</span><span class="sxs-lookup"><span data-stu-id="9817e-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="9817e-122">Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme.</span><span class="sxs-lookup"><span data-stu-id="9817e-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="9817e-123">Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="9817e-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="9817e-124">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="9817e-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="9817e-125">Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten.</span><span class="sxs-lookup"><span data-stu-id="9817e-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="9817e-126">Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9817e-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="9817e-127">Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.</span><span class="sxs-lookup"><span data-stu-id="9817e-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="9817e-128">Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln.</span><span class="sxs-lookup"><span data-stu-id="9817e-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="9817e-129">Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.</span><span class="sxs-lookup"><span data-stu-id="9817e-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="9817e-130">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="9817e-130">Restore from Backup</span></span>  
 <span data-ttu-id="9817e-131">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9817e-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="9817e-132">Ausführen von DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="9817e-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="9817e-133">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="9817e-133">Not applicable.</span></span> <span data-ttu-id="9817e-134">Dieser Fehler kann nicht repariert werden.</span><span class="sxs-lookup"><span data-stu-id="9817e-134">This error cannot be repaired.</span></span> <span data-ttu-id="9817e-135">Wenn Sie die Datenbank nicht mithilfe einer Sicherung wiederherstellen können, wenden Sie sich an den Kundenservice und -support von [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9817e-135">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
